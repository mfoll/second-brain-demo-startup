---
type: Question
status: Open
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[primary-postgres-cluster]]"
  - "[[rds-capacity-plan-2027]]"
_organized: true
---

# Do We Need A Read Replica For Reporting?

Reporting jobs (practice reports, exports) run on the primary through the `BYPASSRLS` reporting role. They cause most of the 08:30 CPU spikes.

## For

Takes reporting load off the primary; isolates the privileged role from the main database.

## Against

About $950 a month Multi-AZ, replica lag for "today" reports, one more instance in the SOC 2 asset list.

## Next

[[kwabena-asare]] measures reporting CPU share in 2026-11 for [[rds-capacity-plan-2027]].
