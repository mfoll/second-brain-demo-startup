---
type: Event
date: 2026-06-11
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[architecture-review-2025-11-18]]"
  - "[[row-level-security]]"
  - "[[adr-019-isolation-by-contract-tier]]"
  - "[[theo-mallory-migration-review]]"
_organized: true
---

# Architecture Review 2026-06-11

The review that partly reversed the database-per-tenant decision of 2025-11-18. This is the note to open when someone asks why not every clinic is on its own database.

## Summary

> [!note]
> Decision: dedicated databases only for enterprise contracts (Meridale first); every other tenant stays in, or returns to, the shared database protected by PostgreSQL row-level security. The 48 tenants already moved are folded back by the end of August. Recorded as ADR 019.

## Attendees

Me, [[teodora-vasilescu]], [[kwabena-asare]], [[hamish-pettigrew]], [[min-jae-oh]], [[felix-ostrowski]] for the roadmap impact. [[renata-castellano]] read the pre-read and joined the decision.

## Evidence Presented

I sent a two-page pre-read on 2026-06-08. The numbers:

- 48 tenants moved (12 pilot, 36 rollout), out of about 280.
- Schema migrations: 2 h 40 min end to end across 49 databases, against 6 minutes before ([[schema-migration-timing-log]]). Two migrations had left tenants on different versions for over an hour.
- RDS cost: +$3,100 a month, from $1,900 to $5,000, after adding three instances for tenant databases ([[rds-cost-dashboard]]).
- The [[reminder-outage-2026-03-17]] was caused by a migration batch fanning out across tenant databases.
- [[theo-mallory-migration-review]]: shared schema in good shape; recommends RLS plus dedicated databases only where paid for.
- [[bracken-hollow-pen-test-report-2026]]: no cross-tenant access found in the shared schema.
- Two engineers had spent about 11 weeks on tenant moves and outage clean-up; version 3 was already at risk ([[release-planning-2026-06-02]]).
- [[samir-haddad]] had confirmed on 2026-06-04 that Meridale's requirement is a dedicated database for Meridale, not for everyone.

## Options Considered

1. **Continue the rollout.** Another 230 tenants at 15 a week is four more months, plus about $6,000 a month in RDS at full scale. Rejected.
2. **Pause where we are.** Leaves 48 tenants on a different architecture forever. Rejected: two architectures is the worst outcome.
3. **Contract tier: dedicated for enterprise, RLS for the rest.** Chosen.

## Positions

- Teodora agreed the economics had changed and asked that `tenantctl move` be kept and maintained for enterprise tenants. Agreed.
- Kwabena supported the reversal and asked for RLS coverage to be measured, not assumed. That became the [[rls-policy-coverage-tracker]].
- Hamish asked whether we were reversing because of the outage alone. My answer: no, the migration time and cost would have forced it within months anyway.

## Decisions and Follow-up

- [[adr-019-isolation-by-contract-tier]] supersedes [[adr-014-database-per-tenant]].
- [[full-tenant-database-rollout]] closed as Superseded.
- New children: [[row-level-security-rollout]] and [[enterprise-dedicated-databases]], both started 2026-06-15.
- Fold-back of the 48 tenants by 2026-08-28 ([[fold-back-complete-2026-08-28]]). Meridale live on its own database 2026-08-21.
- Customer success briefed with [[tenant-isolation-faq-for-customer-success]]. No clinic was told about the fold-back beyond a maintenance window.

## Reflection

The meeting took 70 minutes and the decision was easy because the pre-read did the work. What I want to remember is in [[reversals-should-be-cheap-and-public]].
