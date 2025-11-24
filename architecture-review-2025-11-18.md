---
type: Event
date: 2025-11-18
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[meridale-security-questionnaire]]"
  - "[[database-per-tenant]]"
  - "[[teodora-vasilescu]]"
  - "[[kwabena-asare]]"
_organized: true
---

# Architecture Review 2025-11-18

The architecture review that decided to move every tenant from the shared PostgreSQL schema to its own database. Partly reversed on 2026-06-11.

## Summary

> [!note]
> Decision: every tenant moves to its own PostgreSQL database, starting with a pilot of 12 small tenants in 2026-01. Proposed by Teodora Vasilescu; Kwabena Asare warned about connection counts and migration fan-out; we accepted the risk and planned to mitigate it later. Recorded as ADR 014.

## Context

[[meridale-security-questionnaire]] arrived on 2025-09-15 with 186 questions. The isolation block (questions 41 to 47) asked how one customer's data is separated from another's, whether a customer's data can be restored or deleted on its own, and whether it can be encrypted with a separate key. Our honest answer was a `tenant_id` column on every table and filters in the application code. [[dana-prescott]] reported that Meridale's IT manager, [[samir-haddad]], had marked these answers for follow-up. The contract was worth $186,000 a year and on the table for January.

## Attendees

Me, [[teodora-vasilescu]], [[kwabena-asare]], [[hamish-pettigrew]], [[lucia-ferreyra]]. [[renata-castellano]] joined for the last 20 minutes.

## Options Considered

1. **Keep the shared schema with application filters.** Rejected: no answer to the questionnaire beyond "we are careful".
2. **Shared schema with PostgreSQL row-level security.** Rejected at the time. Our reasons: we had never run RLS in production, we feared a policy bug would be silent, and we doubted an enterprise security reviewer would accept "a database feature" as isolation. In hindsight the last point was an assumption nobody tested.
3. **A schema per tenant.** Rejected: most of the operational cost of option 4 without the restore or key benefits.
4. **A database per tenant.** Chosen. Teodora's [[tenant-isolation-design-doc]] showed per-tenant restore, per-tenant deletion for offboarding, and a clean story for the questionnaire.

## Concerns Raised

Kwabena put two concerns on record:

- Connections: the API keeps a pool per database, so connections would grow with tenant count. He estimated 280 tenants would need PgBouncer at minimum.
- [[migration-fan-out]]: every schema migration would run once per tenant, so a 6-minute migration would become hours and partial failures would leave tenants on different schema versions.

We agreed to address both "during the rollout". Neither was in the pilot's success criteria, which is the mistake I wrote up in [[lessons-from-the-database-per-tenant-decision]].

## Decisions and Follow-up

- Pilot with 12 small tenants from 2026-01-05 ([[database-per-tenant-pilot]]), databases on the existing instance.
- Rollout to all tenants from 2026-03 ([[full-tenant-database-rollout]]).
- Recorded as [[adr-014-database-per-tenant]], now superseded by [[adr-019-isolation-by-contract-tier]].
- Opened [[tenant-isolation-migration]].
- Dana told Meridale that dedicated databases were on the roadmap; that became a contract condition on 2026-01-12.

## What Happened Next

The pilot went fine; the rollout did not scale. See [[reminder-outage-2026-03-17]] and [[architecture-review-2026-06-11]].
