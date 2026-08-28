---
type: Event
date: 2026-08-28
belongs_to: "[[row-level-security-rollout]]"
related_to:
  - "[[full-tenant-database-rollout]]"
  - "[[bram-verhoef]]"
  - "[[rds-cost-dashboard]]"
_organized: true
---

# Fold-Back Complete 2026-08-28

The last of the 48 tenants that had moved to their own databases returned to the shared database on 2026-08-28. Same day as the SOC 2 Type I report, which made for a good Friday.

## How It Went

- Six waves between 2026-07-13 and 2026-08-28, run by [[bram-verhoef]] and [[teodora-vasilescu]] with `tenantctl move` in reverse.
- Each tenant: read-only for 8 to 25 minutes, outside clinic hours. No failed move.
- A pre-check confirmed that RLS policies covered every table holding data for the wave before it moved. That ordering mattered: by the first wave 29 tables were covered and they were the ones with most rows.

## Results

- Instances `tenants-a`, `tenants-b` and `tenants-c` deleted on 2026-09-11 after final snapshots.
- RDS cost back to $2,650 a month from $5,000 ([[rds-cost-dashboard]]).
- Schema migrations: 2 h 40 min down to 6 to 12 minutes.

## Follow-up

[[full-tenant-database-rollout]] closed as Superseded. Snapshots kept 90 days, then deleted on 2026-12-10.
