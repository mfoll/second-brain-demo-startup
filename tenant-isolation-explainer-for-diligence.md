---
type: Note
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[technical-diligence-call-2026-08-19]]"
  - "[[seed-extension-diligence]]"
  - "[[arun-velayudhan]]"
_organized: true
---

# Tenant Isolation Explainer For Diligence

The written one-pager I sent [[arun-velayudhan]] ahead of the [[technical-diligence-call-2026-08-19]], kept because the next investor or enterprise customer will ask the same thing.

## The Explainer

- **Today:** enterprise tenants on a dedicated database with their own key; everyone else in a shared database with application filters and PostgreSQL row-level security on every tenant-scoped table (coverage then 38 of 47, now 41).
- **History:** we decided on a database per tenant in 2025-11, moved 48 tenants, then reversed in 2026-06 because migrations took 2 h 40 min, cost rose $3,100 a month, and a migration batch caused our March outage. The reversal kept what customers pay for.
- **Evidence:** independent pen test in 2026-05 found no cross-tenant access; SOC 2 Type I fieldwork finished on 2026-08-14, report expected by the end of August.
- **What we learned:** the March outage changed how we migrate, pool connections and run incidents; all 9 postmortem actions closed.

## How It Landed

On the call Arun asked two questions on isolation and accepted the answers; how I prepared the spoken version is in [[explaining-the-tenant-reversal-to-investors]]. His follow-ups were about cost per clinic and the bus factor on the scheduling engine. See [[cloud-cost-per-clinic]].
