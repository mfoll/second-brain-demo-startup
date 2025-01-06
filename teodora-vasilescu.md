---
type: Person
belongs_to: "[[lead-engineering-team]]"
related_to:
  - "[[tenant-isolation-migration]]"
  - "[[architecture-review-2025-11-18]]"
  - "[[technical-diligence-call-2026-08-19]]"
_organized: true
---

# Teodora Vasilescu

Staff engineer, backend and data. Author of the tenant isolation design and, with me, one of the two people who know the scheduling engine well.

## Role

Teodora owns the data layer: the PostgreSQL schema, the migration tooling and the scheduling engine's slot-finding queries. She joined in 2023-09 as the third engineer and became staff engineer in 2025. Since [[nadia-carvalho]] left in 2025-10 she is the reference for why the data model looks the way it does.

## How We Work Together

- Weekly one-to-one on Wednesdays. She prefers a written agenda the day before and pushes back in writing, which I have learned to read as engagement, not resistance.
- She writes design documents before code. The [[tenant-isolation-design-doc]] is the example I point new engineers to, even though we reversed most of its conclusion.
- When she disagrees with a decision she says so once, clearly, and then executes it well.

## Current Threads

- Reviews every policy in the [[row-level-security-rollout]]; [[bram-verhoef]] writes most of them.
- The scheduling engine walkthrough and pairing rotation that came out of the [[technical-diligence-call-2026-08-19]]: Arun flagged that only Teodora and I understand it. She recorded the walkthrough on 2026-09-09 ([[scheduling-engine-walkthrough-recording]]), and the pairing rotation has run since 2026-09-14.
- Owns `tenantctl` in `quaylane-infra` ([[tenant-migration-tooling]]).

## History With Key Decisions

- Proposed the [[database-per-tenant]] model at [[architecture-review-2025-11-18]]. Her argument was strong on per-tenant restore and on giving Meridale a simple isolation answer.
- At [[architecture-review-2026-06-11]] she agreed the cost and migration time no longer justified it for small tenants, and argued, successfully, to keep the move tooling for enterprise contracts.
- Owned postmortem actions 2 and 9 after the [[reminder-outage-2026-03-17]] (migration throttle, fan-out load test).

## Links

[[tenant-isolation-migration]], [[migration-fan-out]], [[run-a-schema-migration]].
