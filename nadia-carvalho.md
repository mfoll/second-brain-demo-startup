---
type: Person
belongs_to: "[[lead-engineering-team]]"
related_to:
  - "[[original-data-model-notes]]"
  - "[[nadia-carvalho-handover-2025-10-24]]"
_organized: true
---

# Nadia Carvalho

Former senior engineer. Left on 2025-10-31 to join a larger company. Designed Quaylane's original data model in 2023.

## Role While Here

Nadia was the first engineer after me (2023-05). She designed the shared-schema model with a `tenant_id` column on every tenant-scoped table, the appointment and slot tables, and the first version of the reminder scheduler. Most of the naming conventions in `quaylane-api` are hers.

## What She Left Behind

- [[original-data-model-notes]]: her 2023 design notes, including the explicit choice of a shared schema "until a customer pays for something else". That sentence turned out to describe the 2026 reversal almost exactly.
- The handover on 2025-10-24 ([[nadia-carvalho-handover-2025-10-24]]) transferred the data model to [[teodora-vasilescu]] and the reminder scheduler to [[hamish-pettigrew]].

## Contact

We are on good terms. She answered two questions about old migrations by message in 2026-02. I do not ask her for unpaid work.

## Links

[[multi-tenancy]], [[tenant-isolation-migration]].
