---
type: Source
source_type: Consultant report
date_accessed: 2026-05-19
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[theo-mallory]]"
  - "[[architecture-review-2026-06-11]]"
  - "[[row-level-security]]"
_organized: true
---

# Theo Mallory Migration Review

Written report by [[theo-mallory]], "Review of tenant isolation approach", 11 pages, delivered 2026-05-19 after the [[theo-mallory-review-session-2026-05-12]].

## Summary

- Finding 1: the database-per-tenant model multiplies every operational task by tenant count; at 48 databases Quaylane was already carrying most of that cost.
- Finding 2: the shared schema had consistent `tenant_id` columns and indexes on 44 of 47 tenant-scoped tables, a good base for RLS.
- Finding 3: transaction-scoped tenant settings fit PgBouncer transaction pooling.
- Recommendation: RLS with `FORCE` and per-policy tests for all tenants; dedicated databases on separate instances only for contracts that pay for them; fold back the 48.

## Caveats

Theo reviewed design and configuration, not application code paths. RLS coverage of join-only tables was left to us, and those are the slow ones.

## Source Location

Engineering shared drive, `Tenant isolation/external-review-2026-05.pdf`.
