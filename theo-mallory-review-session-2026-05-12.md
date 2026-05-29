---
type: Event
date: 2026-05-12
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[theo-mallory]]"
  - "[[theo-mallory-migration-review]]"
  - "[[row-level-security]]"
_organized: true
---

# Theo Mallory Review Session 2026-05-12

Four-hour working session with [[theo-mallory]], the PostgreSQL consultant, with [[teodora-vasilescu]], [[kwabena-asare]] and me.

## Agenda

1. Walk through the database-per-tenant layout, `tenantctl` and the connection setup after PgBouncer.
2. The outage timeline.
3. Alternatives.

## What He Said

- At 48 tenant databases and three extra instances we were already paying most of the operational cost of the model, with less than a fifth of the tenants moved.
- PgBouncer pools are per database and user, so pooling helps but does not remove the multiplication.
- RLS with `FORCE`, a transaction-scoped tenant setting and tests for every policy is a standard pattern; he has seen it pass enterprise security reviews.
- If a customer pays for a dedicated database, give them a separate instance, not a separate database on a shared instance: that is what buys the restore and key separation.

## Effect

His written report ([[theo-mallory-migration-review]], 2026-05-19) went into the pre-read for [[architecture-review-2026-06-11]]. Teodora said afterwards that the session changed her mind more than the cost numbers did.
