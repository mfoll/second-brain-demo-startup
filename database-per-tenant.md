---
type: Concept
maturity: Evergreen
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[multi-tenancy]]"
  - "[[row-level-security]]"
  - "[[wikipedia-multitenancy]]"
_organized: true
---

# Database Per Tenant

A tenancy model in which each customer's data lives in its own database, rather than sharing tables with other customers. In the vocabulary of [[wikipedia-multitenancy]] it sits close to the multi-instance end of the spectrum.

## What It Buys

- A simple isolation story for security reviewers.
- Per-tenant restore, export and deletion.
- A separate encryption key per tenant if each database is on its own instance or storage.
- Tenant-specific maintenance windows and migration timing.

## What It Costs

- Connections multiply with tenant count, since pools are per database ([[connection-exhaustion]]).
- Every schema migration runs once per tenant ([[migration-fan-out]]).
- Monitoring, backups and upgrades multiply too.
- Cross-tenant reporting needs a separate pipeline.

## Our Experience

We chose it for everyone on 2025-11-18 and moved 48 tenants before reversing on 2026-06-11. The numbers are in [[full-tenant-database-rollout]]. We now use it only for enterprise contracts, on a separate instance per tenant ([[enterprise-dedicated-databases]]). For a team of eight engineers, the multiplication of operations outweighed the benefits for small tenants. See [[isolation-should-follow-the-contract]].
