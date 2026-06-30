---
type: Source
source_type: Decision record
date_accessed: 2026-06-12
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[architecture-review-2026-06-11]]"
  - "[[row-level-security]]"
  - "[[adr-014-database-per-tenant]]"
_organized: true
---

# ADR 019 Isolation By Contract Tier

The decision record written the day after [[architecture-review-2026-06-11]]. Supersedes [[adr-014-database-per-tenant]].

## Summary

Status: Accepted. Tenants on an enterprise contract that requires it get a dedicated database on its own RDS instance with its own KMS key and a separate migration lane. All other tenants live in the shared database, with `ENABLE` and `FORCE ROW LEVEL SECURITY` and a `tenant_isolation` policy on every tenant-scoped table, plus application filters. Tenants already moved are folded back by 2026-08-31.

## Key Details

- Options rejected and why: continue the rollout (cost, migration time), pause (two architectures).
- Consequences: cross-tenant reporting needs the `BYPASSRLS` reporting role, reviewed quarterly; policy coverage must be measured ([[rls-policy-coverage-tracker]]); `tenantctl move` stays maintained.
- Review trigger: a third enterprise tenant, or a security review that rejects RLS.

## Source Location

`quaylane-api` repository, `docs/adr/019-isolation-by-contract-tier.md`.
