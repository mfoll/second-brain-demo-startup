---
type: Person
belongs_to: "[[lead-engineering-team]]"
related_to:
  - "[[run-the-platform]]"
  - "[[reminder-outage-2026-03-17]]"
  - "[[platform-engineer-hire]]"
_organized: true
---

# Kwabena Asare

Senior engineer, infrastructure and reliability. Incident commander on 2026-03-17 and the default incident commander since.

## Role

Kwabena owns `quaylane-infra`: Terraform, the AWS accounts, RDS, PgBouncer, the Redis queue and CI runners. He joined in 2024-02 from a hosting company's operations team. In practice he is our platform team of one, which is why the [[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]] question is partly about him.

## How We Work Together

- One-to-one on Mondays, usually walking through the weekend's pages first.
- He is precise about risk and quantifies it. At [[architecture-review-2025-11-18]] he warned that one database per tenant would multiply connections and turn every schema migration into a fan-out. He was right on both counts, and I should have weighted the warning more (see [[lessons-from-the-database-per-tenant-decision]]).
- He prefers to be handed an outcome, not a task list. My coaching work on delegation with [[miriam-oduya]] started with him as the first real test.

## Current Threads

- Default incident commander since the March outage; trains others on [[run-an-incident]].
- Argues that the first 2027 hire should be a platform engineer: he wants infrastructure and paging off the product engineers' plates. [[felix-ostrowski]] argues for a product engineer. Decision planned for 2026-12-08.
- Mentors [[bram-verhoef]] on infrastructure.
- [[rds-capacity-plan-2027]] for the budget.

## History With Key Decisions

- Incident commander for the [[reminder-outage-2026-03-17]]; closed postmortem actions 1, 3 and 6, including PgBouncer ([[pgbouncer-cutover-2026-04-14]]).
- Wrote the [[enterprise-database-terraform-module]] for Meridale.
- His tracing work in [[observability-overhaul]] was paused on 2026-04-06 so he could produce SOC 2 evidence for infrastructure controls.

## Links

[[reliability-and-incidents]], [[primary-postgres-cluster]], [[infrastructure-map]].
