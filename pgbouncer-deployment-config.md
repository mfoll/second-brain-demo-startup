---
type: Source
source_type: Code repository
date_accessed: 2026-08-20
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[transaction-pooling]]"
  - "[[pgbouncer-cutover-2026-04-14]]"
_organized: true
---

# PgBouncer Deployment Config

PgBouncer configuration and container definition in `quaylane-infra`.

## Key Details

- Two tasks behind an internal load balancer; image pinned to a PgBouncer release, upgraded deliberately.
- `pool_mode = transaction`, `default_pool_size = 40`, `max_client_conn = 4000`, `reserve_pool_size = 10`.
- Separate pool entries: shared database, `ql_reminders` role (30 connections reserved), `ent-meridale` database.
- Config changes go through the normal pull request and are applied with a reload, not a restart.

## Source Location

`quaylane-infra` repository, `services/pgbouncer`.
