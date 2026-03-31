---
type: Source
source_type: Encyclopedia article
url: https://en.wikipedia.org/wiki/Connection_pool
date_accessed: 2026-03-26
licence: CC BY-SA 4.0
belongs_to: "[[reminder-outage-postmortem]]"
related_to:
  - "[[connection-exhaustion]]"
  - "[[transaction-pooling]]"
_organized: true
---

# Connection pool

## Summary

Wikipedia article defining a connection pool as a cache of reusable database connections, kept by the client or by middleware, to avoid the overhead of opening and closing connections.

## Why It Matters

[[ayesha-qureshi]], in her second week, asked during [[postmortem-review-2026-03-24]] why we had "pools everywhere and still ran out". The answer is the client-versus-middleware distinction in this article: our pools were in every API and worker process, per database, so they multiplied. PgBouncer moved pooling into middleware ([[pgbouncer-cutover-2026-04-14]]).

## Caveats

Introductory. Last edited 2026-10-22 at re-check.

## Source Links

- [Connection pool](https://en.wikipedia.org/wiki/Connection_pool), Wikipedia, CC BY-SA 4.0.
