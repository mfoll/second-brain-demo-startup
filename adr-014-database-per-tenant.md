---
type: Source
source_type: Decision record
date_accessed: 2025-11-19
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[adr-019-isolation-by-contract-tier]]"
  - "[[architecture-review-2025-11-18]]"
_archived: true
_organized: true
---

# ADR 014 Database Per Tenant

Superseded on 2026-06-11 by [[adr-019-isolation-by-contract-tier]]. Kept as the record of what we decided and why.

## Summary

Status: Superseded. Decision of 2025-11-18: every tenant moves to its own PostgreSQL database. Context: enterprise isolation questions from the [[meridale-security-questionnaire]]. Consequences listed at the time: more connections (to be solved by pooling "before 50 tenants"), longer migrations (to be solved by parallel runs), per-tenant restore gained.

## Caveats

Both listed mitigations turned out to be where the trouble came from. See [[architecture-review-2026-06-11]].

## Source Location

`quaylane-api` repository, `docs/adr/014-database-per-tenant.md`, marked superseded in its header.
