---
type: Source
source_type: Encyclopedia article
url: https://en.wikipedia.org/wiki/Multitenancy
date_accessed: 2025-11-10
licence: CC BY-SA 4.0
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[multi-tenancy]]"
  - "[[database-per-tenant]]"
_organized: true
---

# Multitenancy

## Summary

English Wikipedia article on software multitenancy: one instance of software serving several tenants, each with a dedicated share of data, configuration and user management. It contrasts multitenancy with multi-instance architectures, where each tenant gets a separate software instance.

## Why It Matters

[[teodora-vasilescu]] put this in the pre-read for [[architecture-review-2025-11-18]] to give everyone the same vocabulary. The multitenant versus multi-instance distinction is the axis we moved along twice: toward multi-instance for data in November 2025, back toward shared in June 2026.

## Caveats

General overview. It says nothing about PostgreSQL mechanisms or costs; for those see [[postgresql-docs-row-security-policies]] and [[database-per-tenant]]. Revision checked: last edited 2026-10-09 when re-read for this note.

## Source Links

- [Multitenancy](https://en.wikipedia.org/wiki/Multitenancy), Wikipedia, CC BY-SA 4.0.
