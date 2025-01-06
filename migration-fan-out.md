---
type: Concept
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[database-per-tenant]]"
  - "[[run-a-schema-migration]]"
  - "[[reminder-outage-2026-03-17]]"
_organized: true
---

# Migration Fan-Out

Our name for what happens to schema migrations when the same schema exists in many databases: one change becomes N runs, with N times the connections, N times the failure points and, unless throttled, N times the load at once.

## How It Shows Up

- Duration: 6 minutes for one database became 2 h 40 min across 49 ([[schema-migration-timing-log]]).
- Partial state: when run 17 of 49 fails, tenants sit on different schema versions and the application must cope with both.
- Load: parallel runs open connections to every database at once. On 2026-03-17 that exhausted the primary's connection limit ([[reminder-outage-2026-03-17]]).

## Mitigations We Tried

- Throttling (4 databases in parallel, 8 connections each), which fixed load but made duration worse.
- Expand and contract migrations, so the application works with old and new schema during the fan-out.
- In the end, reducing N: the shared database plus one enterprise lane. See [[run-a-schema-migration]].

[[kwabena-asare]] named this risk at [[architecture-review-2025-11-18]], before we had a word for it.
