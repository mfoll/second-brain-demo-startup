---
type: Concept
maturity: Growing
belongs_to: "[[row-level-security-rollout]]"
related_to:
  - "[[multi-tenancy]]"
  - "[[postgresql-docs-row-security-policies]]"
  - "[[database-per-tenant]]"
_organized: true
---

# Row-Level Security

PostgreSQL row-level security (RLS) as Quaylane uses it: the database itself filters every query on a tenant-scoped table to the current tenant's rows, so a missing `WHERE tenant_id = ...` in application code no longer leaks data.

## Definition

> [!info]
> Row-level security is a PostgreSQL feature that attaches policies to a table; once enabled, every SELECT, INSERT, UPDATE and DELETE only sees or touches rows the policy allows. If RLS is enabled and no policy exists, nothing is visible (default deny).

The authoritative description is the PostgreSQL manual, summarized in [[postgresql-docs-row-security-policies]] and [[postgresql-docs-create-policy]].

## How We Use It

Every tenant-scoped table gets the same pattern in its migration:

```sql
ALTER TABLE appointments ENABLE ROW LEVEL SECURITY;
ALTER TABLE appointments FORCE ROW LEVEL SECURITY;
CREATE POLICY tenant_isolation ON appointments
  USING (tenant_id = current_setting('app.tenant_id')::bigint)
  WITH CHECK (tenant_id = current_setting('app.tenant_id')::bigint);
```

- The API sets the tenant at the start of every transaction with `SELECT set_config('app.tenant_id', $1, true)`. The `true` makes it local to the transaction, which is what makes it safe behind PgBouncer in [[transaction-pooling]] mode: the next transaction on the same server connection starts without a tenant and sees nothing.
- If `app.tenant_id` is not set in the transaction, the policy expression errors (the setting is either unknown or an empty string that cannot be cast to `bigint`), so a forgotten setting fails loudly instead of returning everything.
- `FORCE` matters because our application role owns the tables, and table owners bypass RLS unless forced.
- Reporting jobs use a separate role with `BYPASSRLS`, reviewed as a privileged role.

## What It Protects

- Application bugs that forget a tenant filter: the most likely way one clinic sees another's data.
- Ad hoc queries by engineers through the application role.

## What It Does Not Protect

- Anyone with a superuser or `BYPASSRLS` role, including the reporting role.
- Bugs in the policy itself or in how `app.tenant_id` is set. Every policy has a pgTAP test for exactly this.
- Operations on the whole table such as `TRUNCATE`, which RLS does not cover.
- Per-tenant restore, deletion of a whole tenant in one statement, or a separate encryption key. Those are what a [[database-per-tenant]] gives, and why enterprise contracts still get one.
- Noisy neighbors: one tenant's heavy query still competes with everyone. See [[noisy-neighbor]].

## Costs We Have Seen

- A policy that needs a join costs time on every row; `staff_room_links` added 30% to a roster query, so we add a `tenant_id` column instead.
- Partitioned tables need the policy on each partition.
- Debugging is harder: "zero rows" can mean "wrong tenant setting". We log the tenant ID with every slow query.

## Related

[[row-level-security-rollout]], [[rls-policy-coverage-tracker]], [[architecture-review-2026-06-11]], [[how-do-we-show-tenant-isolation-to-auditors]].
