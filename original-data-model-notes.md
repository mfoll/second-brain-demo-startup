---
type: Source
source_type: Internal document
date_accessed: 2025-10-24
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[nadia-carvalho]]"
  - "[[multi-tenancy]]"
_organized: true
---

# Original Data Model Notes

[[nadia-carvalho]]'s design notes for the first Quaylane data model, written 2023-05 to 2023-08 and annotated during her handover on 2025-10-24.

## Key Details

- Shared schema, `tenant_id bigint not null` on every tenant-scoped table, composite indexes leading with `tenant_id`.
- Explicit decision: keep a shared schema "until a customer pays for something else". The 2026 contract-tier model is that sentence.
- Patient contact fields kept in one table (`patients_contact`) to make data-subject requests and retention easier; the vault refers to them as a data category only.
- Known weak spots added in 2025-10: no database-level tenant enforcement, unpartitioned `reminder_deliveries`, single queue consumer assumption.

## Source Location

Engineering shared drive, `Design docs/2023/data-model`.
