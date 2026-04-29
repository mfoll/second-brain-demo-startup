---
type: Event
date: 2026-04-14
belongs_to: "[[reminder-outage-postmortem]]"
related_to:
  - "[[transaction-pooling]]"
  - "[[primary-postgres-cluster]]"
  - "[[pgbouncer-docs-features]]"
_organized: true
---

# PgBouncer Cutover 2026-04-14

PgBouncer went live in front of the primary database at 21:00 on 2026-04-14. Postmortem action 1, owned by [[kwabena-asare]].

## What Changed

- Two PgBouncer tasks behind an internal load balancer, transaction pooling, `default_pool_size` 40 per database and user, `max_client_conn` 4,000.
- API and workers switched by changing one connection setting, deployed in that order with 30 minutes between.
- Server connections on the primary dropped from about 1,500 at peak to about 160.

## What Broke

- Two code paths used session-level `SET` statements (a statement timeout and a search path in a report job). In transaction mode they leaked between clients. Found in staging the week before; both changed to `SET LOCAL`. The [[pgbouncer-docs-features]] table of features incompatible with transaction pooling was the checklist.
- Prepared statements in the `pg` driver needed protocol-level handling; tested in staging, no production issue.

## Why It Matters Later

Transaction pooling is what made the RLS design work: the tenant setting has to be transaction-scoped. See [[transaction-pooling]] and [[row-level-security]].
