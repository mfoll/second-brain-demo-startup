---
type: Source
source_type: Documentation
url: https://www.pgbouncer.org/features.html
publisher: PgBouncer project
date_accessed: 2026-03-30
belongs_to: "[[reminder-outage-postmortem]]"
related_to:
  - "[[transaction-pooling]]"
  - "[[pgbouncer-cutover-2026-04-14]]"
_organized: true
---

# PgBouncer features

## Summary

PgBouncer's features page. It describes three pooling modes: session (a server connection for the whole client session; supports all PostgreSQL features), transaction (a server connection only for the duration of a transaction; breaks some session features and needs a cooperating application), and statement (transaction pooling that disallows multi-statement transactions). It includes a table of PostgreSQL features and their compatibility with each mode; in transaction mode, session `SET`/`RESET`, `LISTEN`, `WITH HOLD` cursors and SQL `PREPARE` do not work.

## Why It Matters

[[kwabena-asare]] used the compatibility table as the checklist for the [[pgbouncer-cutover-2026-04-14]]. It found the two session `SET` statements we had to change, and it is why the RLS tenant setting is transaction-scoped.

## Caveats

Feature support changes between PgBouncer versions; check the page for the version deployed.

## Source Links

- [PgBouncer features](https://www.pgbouncer.org/features.html)
