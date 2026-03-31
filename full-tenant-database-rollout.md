---
type: Project
status: Superseded
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[architecture-review-2026-06-11]]"
  - "[[migration-fan-out]]"
has:
  - "[[tenant-migration-wave-plan]]"
  - "[[reminder-outage-2026-03-17]]"
  - "[[schema-migration-timing-log]]"
_organized: true
---

# Full Tenant Database Rollout

The plan to move all of about 280 tenants to their own databases after the pilot. Superseded on 2026-06-11 after 48 had moved, by the contract-tier model in [[adr-019-isolation-by-contract-tier]].

## Outcome

Original outcome: move all of about 280 tenants to their own databases. Not reached by design; superseded by [[row-level-security-rollout]] and [[enterprise-dedicated-databases]].

## Current State

- Superseded on 2026-06-11. 48 tenants had moved (12 from the pilot, 36 in this rollout).
- All 48 were folded back into the shared database by 2026-08-28.
- The wave plan is archived as [[tenant-migration-wave-plan]].

## Scope and Boundaries

Waves of 10 to 20 tenants a week, smallest first, Meridale last. The three additional RDS instances (`tenants-a`, `tenants-b`, `tenants-c`) were added in 2026-04 and 2026-05 after the outage, to take tenant databases off the primary.

## Working Context

What the numbers looked like by early June, from [[schema-migration-timing-log]] and [[rds-cost-dashboard]]:

- A routine schema migration took 2 h 40 min end to end across 49 databases (the shared one plus 48 tenants), against 6 minutes before.
- RDS cost rose from $1,900 to $5,000 a month (+$3,100), mostly the three extra Multi-AZ instances.
- Connection pressure: even behind PgBouncer, each tenant database needs its own pool, see [[pgbouncer-docs-configuration]].
- The rollout's worst day was the [[reminder-outage-2026-03-17]], caused by a migration batch fanning out across tenant databases on the primary.
- Two engineers spent about 11 weeks on tenant moves and outage clean-up, which is a large part of why version 3 slipped ([[release-planning-2026-06-02]]).

The reversal reasoning is in [[architecture-review-2026-06-11]]. I kept this project note rather than deleting it because the numbers are the evidence for the reversal and someone will propose database-per-tenant again.

## Important Notes

- [[architecture-review-2026-06-11]]
- [[tenant-migration-wave-plan]]
- [[lessons-from-the-database-per-tenant-decision]]

## Maintenance Log

- 2026-08-28: Fold-back finished; project closed as Superseded.
- 2026-06-11: Superseded at the architecture review after 48 tenants.
- 2026-03-17: Rollout paused after the outage; resumed 2026-04-09 with migration throttling and reserved connections.
- 2026-03-02: Rollout started.
