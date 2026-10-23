---
type: Source
source_type: Dashboard
date_accessed: 2026-10-05
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[cloud-cost-per-clinic]]"
  - "[[full-tenant-database-rollout]]"
  - "[[engineering-budget-2027]]"
_organized: true
---

# RDS Cost Dashboard

The AWS Cost Explorer view saved as "RDS by instance, monthly", which [[kwabena-asare]] and I check on the fifth of each month.

## Key Details

| Month | RDS cost | Note |
|---|---|---|
| 2025-11 | $1,900 | Primary only |
| 2026-03 | $2,050 | Tenant databases on the primary |
| 2026-06 | $5,000 | Plus `tenants-a`, `tenants-b`, `tenants-c` |
| 2026-09 | $2,900 | Partial month of tenant instances, plus `ent-meridale` |
| 2026-10 (forecast) | $2,650 | Primary plus `ent-meridale` |

The +$3,100 a month quoted in [[architecture-review-2026-06-11]] is June against November.

## Caveats

Includes storage and backups; excludes data transfer. Multi-AZ doubles instance cost, which the original design estimate missed.

## Source Location

AWS Cost Explorer, saved report in the production billing account. Monthly exports in the finance drive, owned by [[colette-fairbanks]].
