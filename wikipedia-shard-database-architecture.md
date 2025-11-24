---
type: Source
source_type: Encyclopedia article
url: https://en.wikipedia.org/wiki/Shard_(database_architecture)
date_accessed: 2025-11-12
licence: CC BY-SA 4.0
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[multi-tenancy]]"
  - "[[rds-capacity-plan-2027]]"
_organized: true
---

# Shard (database architecture)

## Summary

Wikipedia article on database sharding: a shard is a horizontal partition of data, and each shard may sit on a separate database server to spread load.

## Why It Matters

At [[architecture-review-2025-11-18]] [[hamish-pettigrew]] asked whether database-per-tenant was "just sharding by tenant". Partly: it partitions by tenant, but we were not doing it for load. Keeping the two motives apart helped in June, when we kept tenant-level separation only where contracts required it. If load ever forces partitioning, sharding by tenant group is the option recorded in [[rds-capacity-plan-2027]].

## Caveats

Generic; nothing on operational cost for a small team. Last edited 2026-09-17 at re-check.

## Source Links

- [Shard (database architecture)](https://en.wikipedia.org/wiki/Shard_(database_architecture)), Wikipedia, CC BY-SA 4.0.
