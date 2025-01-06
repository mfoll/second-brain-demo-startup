---
type: Note
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[primary-postgres-cluster]]"
  - "[[engineering-budget-2027]]"
  - "[[kwabena-asare]]"
_organized: true
---

# RDS Capacity Plan 2027

Draft by [[kwabena-asare]] and me for the [[engineering-budget-2027]], as of 2026-10-20.

## Assumptions

- Clinics grow from about 280 to about 400; Meridale's remaining 23 clinics live by 2026-12-11.
- One more enterprise tenant possible in 2027-H2.

## Plan

- Primary stays on db.r6g.xlarge through 2027-H1; CPU peak 45% today, projected 65% at 400 clinics.
- Upgrade to PostgreSQL 17 in 2027-Q2, with [[theo-mallory]] reviewing.
- Possible read replica for reporting, decided by [[do-we-need-a-read-replica-for-reporting]].
- Budget line: $2,650 a month today, $3,700 to $4,600 by 2027-12 depending on the replica and a second enterprise database.

## Not Planned

Sharding. If load ever forces it, group tenants by shard rather than one per database ([[wikipedia-shard-database-architecture]]).
