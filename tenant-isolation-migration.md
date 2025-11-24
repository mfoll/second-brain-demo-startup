---
type: Project
status: Active
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[multi-tenancy]]"
  - "[[meridale-clinic-group]]"
  - "[[teodora-vasilescu]]"
has:
  - "[[row-level-security-rollout]]"
  - "[[enterprise-dedicated-databases]]"
  - "[[architecture-review-2026-06-11]]"
  - "[[primary-postgres-cluster]]"
  - "[[adr-019-isolation-by-contract-tier]]"
_organized: true
---

# Tenant Isolation Migration

Umbrella for the work that changed how clinic data is separated in Quaylane, from the shared schema we started with in 2023 to isolation that follows each customer's contract.

## Outcome

Every tenant has the isolation its contract requires: a dedicated database for enterprise accounts, PostgreSQL [[row-level-security]] for all others.

## Current State

- Enterprise: Meridale has run on its own database, with its own encryption key and migration lane, since 2026-08-21 ([[enterprise-dedicated-databases]], completed).
- Everyone else: back in the shared database. The 48 tenants moved during the rollout were folded back by 2026-08-28.
- [[row-level-security-rollout]] is the only active child. Policy coverage is 41 of 47 tenant-scoped tables as of 2026-10-23.
- Cost: RDS spend is $2,650 a month, down from the $5,000 peak in June. See [[rds-cost-dashboard]].
- Nothing blocks the remaining work; it competes with roadmap tickets for [[bram-verhoef]]'s and [[teodora-vasilescu]]'s time.

## Scope and Boundaries

In scope: the tenancy model, the migration tooling (`tenantctl` in `quaylane-infra`), the database layout, RLS policies and their tests. Out of scope: SSO and SCIM ([[enterprise-sso]]), the SOC 2 evidence itself ([[soc2-type-1-audit]]), and Meridale's clinic rollout ([[meridale-enterprise-rollout]]).

## Working Context

The short version for anyone asking why not every clinic has its own database:

1. [[meridale-security-questionnaire]] (186 questions, received 2025-09-15) asked how tenant data is isolated. Our honest answer was "a `tenant_id` column and application code".
2. [[architecture-review-2025-11-18]] chose a [[database-per-tenant]] (Teodora's proposal). Kwabena warned about connection counts and [[migration-fan-out]]; we accepted the risk.
3. [[database-per-tenant-pilot]] moved 12 small tenants by 2026-02-27 and looked fine.
4. [[full-tenant-database-rollout]] reached 48 tenants by June. Schema migrations took 2 h 40 min across databases, RDS cost rose by $3,100 a month, and a migration batch caused the [[reminder-outage-2026-03-17]].
5. [[theo-mallory-migration-review]] and [[bracken-hollow-pen-test-report-2026]] both pointed the same way: the shared schema was not the weak point, and RLS would close the gap we actually had.
6. [[architecture-review-2026-06-11]] reversed the decision for everyone except enterprise contracts. The written record is [[adr-019-isolation-by-contract-tier]], which supersedes [[adr-014-database-per-tenant]].

My own read of what went wrong in November is in [[lessons-from-the-database-per-tenant-decision]].

## Active Workflows

- [[run-a-schema-migration]]: migrations now run against the shared database and then the Meridale lane, throttled.
- [[move-a-tenant-to-a-dedicated-database]]: kept for the next enterprise contract.
- Weekly RLS coverage check, tracked in [[rls-policy-coverage-tracker]].

## Next Actions

- [ ] Reach RLS policy coverage on all 47 tenant-scoped tables (6 left, mostly reporting and join tables).
- [ ] Add the policy coverage check to CI in `quaylane-api` so a new table without a policy fails the build.
- [ ] Rewrite the isolation answers in [[tenant-isolation-faq-for-customer-success]] for the next enterprise questionnaire.
- [ ] Decide the criteria for a second dedicated database before Sales promises one ([[when-should-a-tenant-get-a-dedicated-database]]).

## Open Questions

- [[can-we-reach-full-rls-coverage-this-year]]
- [[when-should-a-tenant-get-a-dedicated-database]]
- [[how-do-we-show-tenant-isolation-to-auditors]]

## Important Notes

- [[architecture-review-2026-06-11]]
- [[adr-019-isolation-by-contract-tier]]
- [[primary-postgres-cluster]]
- [[row-level-security]]
- [[tenant-isolation-explainer-for-diligence]]

## Do Not Do Yet

> [!danger]
> Do not promise a dedicated database to any customer below an enterprise contract, and do not delete `tenantctl move` from `quaylane-infra`: it is the only tested path for the next enterprise tenant.

## Maintenance Log

- 2026-10-23: RLS coverage at 41 of 47 tables.
- 2026-08-28: Fold-back of the 48 moved tenants complete; [[full-tenant-database-rollout]] closed as superseded.
- 2026-08-21: Meridale live on its dedicated database.
- 2026-06-11: Partial reversal at [[architecture-review-2026-06-11]].
- 2025-11-18: Project opened after [[architecture-review-2025-11-18]].
