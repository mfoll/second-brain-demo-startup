---
type: Project
status: Completed
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[database-per-tenant]]"
  - "[[teodora-vasilescu]]"
has:
  - "[[pilot-retrospective-2026-02-27]]"
  - "[[tenant-migration-tooling]]"
  - "[[move-a-tenant-to-a-dedicated-database]]"
_organized: true
---

# Database-Per-Tenant Pilot

The first slice of the [[database-per-tenant]] plan: move a handful of small tenants to their own PostgreSQL databases and find out what breaks before touching anyone large.

## Outcome

12 small tenants moved to their own databases; migration tooling and runbook tested. Reached on 2026-02-27.

## Current State

- Completed. All 12 pilot tenants were later folded back into the shared database in 2026-08 after [[architecture-review-2026-06-11]].
- The tooling it produced (`tenantctl move`, `tenantctl verify`) survives and is how Meridale got its own database. See [[tenant-migration-tooling]].
- The runbook became [[move-a-tenant-to-a-dedicated-database]].

## Scope and Boundaries

Twelve tenants chosen by [[teodora-vasilescu]] and [[kwabena-asare]]: all under 20 admin users, no integrations, two physiotherapy, five dental, three family practice and two imaging accounts (tenant IDs 1012 to 1187 range, listed in the pilot sheet). Databases were created on the existing [[primary-postgres-cluster]] instance, not on new instances, to keep cost flat during the pilot. Customer success told each clinic about a 20-minute maintenance window; none were told about the architecture.

## Working Context

- First move: tenant 1044 on 2026-01-14, 23 minutes of read-only mode.
- Median move time across the 12: 14 minutes. Longest: 31 minutes (tenant 1187, because of a large `reminder_deliveries` history).
- One failed move (tenant 1102, 2026-02-04): a sequence was not reset after copy and the first new appointment insert failed. Rolled back in 9 minutes; `tenantctl verify` now checks sequences.
- What the pilot did not test, and should have: a schema migration across many databases at once, and connection use when the API holds a pool per database. Both came back as the [[reminder-outage-2026-03-17]]. See [[pilot-retrospective-2026-02-27]].

## Next Actions

None. Closed.

## Important Notes

- [[pilot-retrospective-2026-02-27]]
- [[tenant-migration-tooling]]
- [[migration-fan-out]]

## Maintenance Log

- 2026-08-28: Pilot tenants folded back as part of the reversal.
- 2026-02-27: Pilot closed after the twelfth move; retrospective held.
- 2026-01-14: First tenant moved.
- 2026-01-05: Pilot started.
