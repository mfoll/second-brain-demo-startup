---
type: Source
source_type: Documentation
url: https://www.pgbouncer.org/config.html
publisher: PgBouncer project
date_accessed: 2026-04-02
belongs_to: "[[full-tenant-database-rollout]]"
related_to:
  - "[[database-per-tenant]]"
  - "[[connection-exhaustion]]"
_organized: true
---

# PgBouncer config

## Summary

PgBouncer's configuration reference. Two settings mattered to us: `default_pool_size` is the maximum number of server connections per user and database pair, and `max_client_conn` caps client connections. The page notes that the theoretical maximum of connections used grows with pool size times the number of databases (and users).

## Why It Matters

This is the line that made the [[database-per-tenant]] model look bad even with pooling: pools are per database, so 280 tenant databases at a pool of 10 would still allow 2,800 server connections. [[kwabena-asare]] quoted it in the pre-read for [[architecture-review-2026-06-11]].

## Caveats

The theoretical maximum is a ceiling, not typical use; most tenant pools would be idle most of the day.

## Source Links

- [PgBouncer config](https://www.pgbouncer.org/config.html)
