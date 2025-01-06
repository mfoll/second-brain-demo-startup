---
type: Topic
related_to:
  - "[[run-the-platform]]"
  - "[[tenant-isolation-migration]]"
  - "[[security-and-privacy]]"
_organized: true
---

# Multi-Tenancy

How Quaylane keeps about 280 clinic accounts in one product without one clinic ever seeing another's data, and what each isolation model costs us. This is the retrieval surface; decisions live in the Events and the project notes.

## Where We Are

Since [[architecture-review-2026-06-11]], isolation follows the contract: a dedicated database for enterprise accounts (Meridale only, so far) and [[row-level-security]] in the shared database for everyone else. Before that we spent seven months moving toward a [[database-per-tenant]] model decided at [[architecture-review-2025-11-18]].

## Key Notes

- Decisions: [[architecture-review-2025-11-18]], [[architecture-review-2026-06-11]], [[adr-019-isolation-by-contract-tier]], and the superseded [[adr-014-database-per-tenant]].
- Concepts: [[row-level-security]], [[database-per-tenant]], [[migration-fan-out]], [[noisy-neighbor]], [[connection-exhaustion]].
- Projects: [[tenant-isolation-migration]] and its children.
- Questions: [[when-should-a-tenant-get-a-dedicated-database]], [[how-do-we-show-tenant-isolation-to-auditors]], [[can-we-reach-full-rls-coverage-this-year]].
- My stance: [[isolation-should-follow-the-contract]].

## Reading

- [[wikipedia-multitenancy]] and [[wikipedia-shard-database-architecture]] for vocabulary.
- [[postgresql-docs-row-security-policies]] and [[postgresql-docs-create-policy]] for what the database actually enforces.
- [[pgbouncer-docs-configuration]] for why pools multiply per database.

## Related Topics

[[security-and-privacy]] for the questionnaire and audit angle, [[reliability-and-incidents]] for the outage that the database-per-tenant rollout caused.
