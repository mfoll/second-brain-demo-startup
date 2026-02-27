---
type: Event
date: 2026-02-27
belongs_to: "[[database-per-tenant-pilot]]"
related_to:
  - "[[migration-fan-out]]"
  - "[[teodora-vasilescu]]"
_organized: true
---

# Pilot Retrospective 2026-02-27

Retrospective after the twelfth and last pilot tenant moved to its own database. Teodora, Kwabena, Hamish and me, 45 minutes.

## What Went Well

- 12 moves, median 14 minutes of read-only time, no clinic complaint.
- `tenantctl verify` caught the sequence bug on tenant 1102 before any data was written wrongly.
- Customer success said the maintenance notices were clear.

## What Worried Us

- [[kwabena-asare]] showed that connections on the primary had grown from about 1,100 to 1,450 at peak with only 12 tenant databases, because the API keeps a pool per database. Extrapolated to 280 tenants it was far beyond the instance limit.
- Schema migrations had already gone from 6 minutes to 19 across 13 databases.

## What We Decided

- Go ahead with [[full-tenant-database-rollout]] from 2026-03-02, smallest tenants first.
- PgBouncer "before we pass 50 tenant databases". Not before the rollout.
- No change to migration tooling yet.

## Looking Back

Both worries were the right ones and we deferred both. Three weeks later a migration batch caused the [[reminder-outage-2026-03-17]]. The decision to proceed was mine; I wrote about it in [[lessons-from-the-database-per-tenant-decision]].
