---
type: Source
source_type: Internal document
date_accessed: 2025-11-14
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[teodora-vasilescu]]"
  - "[[architecture-review-2025-11-18]]"
  - "[[database-per-tenant]]"
_organized: true
---

# Tenant Isolation Design Doc

Teodora Vasilescu's design document, "Tenant isolation for enterprise readiness", version 3, dated 2025-11-14 and circulated as the pre-read for [[architecture-review-2025-11-18]].

## Summary

Compares four models (application filters, row-level security, schema per tenant, database per tenant) against the isolation questions in the [[meridale-security-questionnaire]], per-tenant restore and deletion, cost and operational effort. Recommends a database per tenant, migrated in waves through a new `tenantctl` tool.

## Key Details

- Estimated cost at 280 tenants: +$1,400 a month in RDS. Actual by June at 48 tenants: +$3,100, because the estimate assumed all tenant databases on the existing instance.
- Migration time was estimated "linear in tenants, parallelizable". It was linear; parallelizing it caused the outage.
- The RLS section is two paragraphs and flags "unfamiliar to the team" as the main risk.
- A good section on per-tenant restore that still holds for enterprise tenants.

## Caveats

Superseded in its recommendation by [[adr-019-isolation-by-contract-tier]]. Still the clearest description of the options; read it with [[lessons-from-the-database-per-tenant-decision]].

## Source Location

Engineering shared drive, `Design docs/2025/tenant-isolation-v3`. Comment history kept.
