---
type: Project
status: Active
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[row-level-security]]"
  - "[[bram-verhoef]]"
  - "[[soc2-type-2-observation]]"
has:
  - "[[rls-policy-coverage-tracker]]"
  - "[[fold-back-complete-2026-08-28]]"
  - "[[can-we-reach-full-rls-coverage-this-year]]"
  - "[[postgresql-docs-row-security-policies]]"
_organized: true
---

# Row-Level Security Rollout

Put PostgreSQL [[row-level-security]] policies on every tenant-scoped table of the shared database, and fold the 48 tenants that had moved to their own databases back into it.

## Outcome

Row-level security policies on every tenant-scoped table of the shared database, and the 48 moved tenants folded back (done 2026-08-28). Policy coverage 41 of 47 tables as of 2026-10-23.

## Current State

- Fold-back: done on 2026-08-28, see [[fold-back-complete-2026-08-28]].
- Coverage: 41 of 47 tenant-scoped tables have `ENABLE` and `FORCE ROW LEVEL SECURITY` and a `tenant_isolation` policy. Tracked in [[rls-policy-coverage-tracker]].
- The 6 remaining tables: `report_daily_counts`, `report_room_utilization`, `waitlist_offers_archive`, `staff_room_links`, `audit_events` (partitioned, 24 partitions) and `import_batches`.
- The API sets `app.tenant_id` with `set_config(..., true)` at the start of every transaction, which works under PgBouncer transaction pooling.
- Owner: [[bram-verhoef]] since 2026-07, with [[teodora-vasilescu]] reviewing every policy.

## Scope and Boundaries

The shared database only. Meridale's dedicated database also has the policies (belt and braces) but is tracked under [[enterprise-dedicated-databases]]. Application-level `tenant_id` filters stay in place; RLS is a second layer, not a replacement. The reporting jobs that legitimately read across tenants use a separate role with `BYPASSRLS`, which is listed in the [[soc2-control-matrix]] as a privileged role reviewed quarterly.

## Working Context

- Order of work: highest-risk tables first (`appointments`, `patients_contact`, `reminder_deliveries`, `waitlist_entries`), then everything with a direct `tenant_id`, then tables that only reach a tenant through a join.
- Join-only tables are the slow part: a policy that does a subquery on every row costs real time. `staff_room_links` added 30% to the room roster query in staging, so we are adding a `tenant_id` column there instead.
- `audit_events` is partitioned by month; policies must exist on each partition and on the parent. Bram is scripting this in `quaylane-infra` so new partitions get the policy automatically.
- Tests: every policy has a pgTAP test that connects as tenant A and asserts zero rows from tenant B, run in CI against a seeded database with three tenants.
- The table owner bypasses RLS unless forced, which is why `FORCE ROW LEVEL SECURITY` is in every migration. See [[postgresql-docs-row-security-policies]].

## Active Workflows

- Weekly coverage check (a query over `pg_class.relrowsecurity` and `relforcerowsecurity`), posted to the platform channel on Mondays.
- New tables follow [[run-a-schema-migration]], which now requires a policy in the same migration.

## Next Actions

- [ ] Add `tenant_id` to `staff_room_links` and `import_batches` and cover them.
- [ ] Automate policies on new `audit_events` partitions.
- [ ] Decide whether the two report tables become views over covered tables instead.
- [ ] Make the coverage check fail CI in `quaylane-api`.

## Open Questions

- [[can-we-reach-full-rls-coverage-this-year]]
- [[how-do-we-show-tenant-isolation-to-auditors]]

## Important Notes

- [[row-level-security]]
- [[rls-policy-coverage-tracker]]
- [[postgresql-docs-create-policy]]
- [[architecture-review-2026-06-11]]

## Maintenance Log

- 2026-10-23: Coverage 41 of 47.
- 2026-08-28: All 48 moved tenants folded back.
- 2026-07-06: Bram joined and took over day-to-day ownership.
- 2026-06-15: Project started, first four policies in production by 2026-06-26.
