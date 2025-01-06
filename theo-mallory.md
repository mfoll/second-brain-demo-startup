---
type: Person
related_to:
  - "[[theo-mallory-migration-review]]"
  - "[[theo-mallory-review-session-2026-05-12]]"
  - "[[tenant-isolation-migration]]"
_organized: true
---

# Theo Mallory

Independent PostgreSQL consultant. Reviewed the tenant migration in 2026-05.

## Engagement

- Hired by me on a fixed scope of five days in 2026-05 after the outage, for $9,500, to review the database-per-tenant rollout, our connection handling and the RLS alternative.
- Working session with [[teodora-vasilescu]], [[kwabena-asare]] and me on 2026-05-12 ([[theo-mallory-review-session-2026-05-12]]); written report on 2026-05-19 ([[theo-mallory-migration-review]]).

## What He Told Us

- Database-per-tenant on a single team of our size is an operational multiplier: every pool, migration and monitoring check multiplies by the tenant count.
- Our shared schema was in decent shape; the gap was enforcement in the database, which RLS with `FORCE ROW LEVEL SECURITY` and a transaction-scoped tenant setting would close.
- Keep dedicated databases for customers who pay for them.

## How We Work Together

Precise, quick, and blunt about trade-offs, never about people. He reviewed our first RLS policies by email in 2026-07 at no extra charge. We would hire him again for the PostgreSQL 17 upgrade.
