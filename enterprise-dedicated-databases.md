---
type: Project
status: Completed
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[meridale-clinic-group]]"
  - "[[meridale-enterprise-rollout]]"
  - "[[kwabena-asare]]"
has:
  - "[[meridale-database-cutover-2026-08-21]]"
  - "[[enterprise-database-terraform-module]]"
  - "[[move-a-tenant-to-a-dedicated-database]]"
_organized: true
---

# Enterprise Dedicated Databases

Give enterprise tenants, starting with Meridale, a database of their own as their contract requires, using what the pilot taught us and nothing more.

## Outcome

Meridale, and any future enterprise tenant, on a dedicated database with its own encryption key and migration lane. Reached on 2026-08-21.

## Current State

- Completed. Meridale (tenant 2044) runs on its own RDS instance, `ent-meridale`, a db.r6g.large Multi-AZ instance with its own AWS KMS key.
- Cost is about $750 a month, which the Meridale contract covers comfortably.
- Schema migrations run in a separate lane after the shared database succeeds, so Meridale gets changes about 10 minutes later and never in the middle of a clinic day.
- The contract condition (dedicated database) is met. See [[meridale-clinic-group]] for the full list of conditions.

## Scope and Boundaries

One instance per enterprise tenant, created from the [[enterprise-database-terraform-module]]. Shared infrastructure stays shared: the API, the workers, the Redis queue and PgBouncer (with a separate pool for each enterprise database). RLS policies are applied in the dedicated database too.

## Working Context

- Cutover on 2026-08-21, Friday 19:00 to 19:48, when only 7 of the 42 Meridale clinics were live, so the blast radius was small. See [[meridale-database-cutover-2026-08-21]].
- [[kwabena-asare]] wrote the Terraform module; [[teodora-vasilescu]] adapted `tenantctl move` for a separate instance instead of a separate database on the primary.
- [[samir-haddad]] at Meridale reviewed the design document and asked for the KMS key policy, which we shared as a redacted excerpt.
- Restore test on 2026-09-09: point-in-time restore of `ent-meridale` into a scratch instance took 34 minutes.

## Next Actions

None. Closed. The next enterprise tenant starts from [[move-a-tenant-to-a-dedicated-database]].

## Important Notes

- [[meridale-database-cutover-2026-08-21]]
- [[when-should-a-tenant-get-a-dedicated-database]]
- [[adr-019-isolation-by-contract-tier]]

## Maintenance Log

- 2026-09-09: Restore test passed; project closed.
- 2026-08-21: Meridale cut over to its dedicated database.
- 2026-07-20: Terraform module merged (QL-1688).
- 2026-06-15: Project started after [[architecture-review-2026-06-11]].
