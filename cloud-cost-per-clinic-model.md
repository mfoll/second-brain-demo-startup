---
type: Source
source_type: Internal spreadsheet
date_accessed: 2026-10-12
belongs_to: "[[engineering-budget-2027]]"
related_to:
  - "[[cloud-cost-per-clinic]]"
  - "[[gwen-talbot]]"
  - "[[aws-cost-explorer-dashboard]]"
_organized: true
---

# Cloud Cost Per Clinic Model

The spreadsheet that computes [[cloud-cost-per-clinic]] monthly and forecasts it for the budget. Built 2025-11 for Renata, rebuilt 2026-06 for [[gwen-talbot]] after the tenant isolation reversal.

## Structure

- `actuals`: monthly AWS bill by service (from the [[aws-cost-explorer-dashboard]]), Pingrove platform fees, active clinic count.
- `enterprise`: one row per dedicated database, cost separated from the shared platform.
- `forecast`: clinic count scenarios (Renata's plan), fixed and variable shares, enterprise tenants added.

## Key Figures

- 2025-12: $11 per clinic per month.
- 2026-05: $19, at the peak of the per-tenant rollout.
- 2026-07: $14, the figure used in diligence.
- 2027 forecast: $12 to $14 at 340 clinics, excluding enterprise databases.

## Caveats

Excludes SMS charges (passed through), engineering tools and people. The fixed share is an estimate based on which services would not change with clinic count.

## Source Location

Shared drive, `Finance/Engineering/cloud-cost-per-clinic.xlsx`. Owner Nikolas; Gwen has read access.
