---
type: Source
source_type: Dashboard
date_accessed: 2026-10-12
belongs_to: "[[engineering-budget-2027]]"
related_to:
  - "[[cloud-cost-per-clinic-model]]"
  - "[[kwabena-asare]]"
_organized: true
---

# AWS Cost Explorer Dashboard

The saved Cost Explorer views for the production account, set up by [[kwabena-asare]] in 2025-08 and extended in 2026-06 with a cost allocation tag per enterprise tenant.

## Views

- Monthly cost by service, 18 months.
- RDS cost split: shared cluster vs dedicated enterprise databases (tag `tenant_class`).
- Daily cost anomaly view, emailed to Kwabena and me.

## Readings That Mattered

- 2026-03 to 2026-08: RDS line up to $3,100 a month above the 2025-12 baseline during the per-tenant rollout.
- 2026-09: back to baseline plus Meridale's dedicated database, about $750 a month.

## Source Location

AWS console, production account, Cost Explorer saved reports "Monthly by service", "RDS by tenant class". Read access for engineering leads and Gwen via a read-only role.
