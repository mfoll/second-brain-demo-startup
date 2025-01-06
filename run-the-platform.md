---
type: Responsibility
status: Active
related_to:
  - "[[reliability-and-incidents]]"
  - "[[multi-tenancy]]"
  - "[[kwabena-asare]]"
has:
  - "[[tenant-isolation-migration]]"
  - "[[observability-overhaul]]"
  - "[[primary-postgres-cluster]]"
  - "[[run-an-incident]]"
_organized: true
---

# Run The Platform

Architecture decisions, infrastructure, reliability, incidents and postmortems for Quaylane. It has no end date: as long as clinics book appointments through us, somebody has to own how the system is built and what happens when it breaks.

## Scope

- Architecture decisions that change how data is stored, isolated or moved: the tenancy model, the database layout, the job queue, the reminder pipeline.
- Infrastructure in `quaylane-infra` (Terraform, AWS accounts, Amazon RDS, the Redis queue, GitHub Actions runners).
- Reliability: alerts, incident response, postmortems and their action items.
- Observability: logs, metrics and tracing.
- Not here: on-call rotation design and the stipend (see [[lead-engineering-team]] and [[on-call-handbook]]), SOC 2 control ownership (see [[secure-and-comply]]), feature delivery (see [[deliver-the-product]]).

## Current State

- Tenancy: everyone except Meridale lives in the shared database on the [[primary-postgres-cluster]], protected by [[row-level-security]]. Policy coverage is 41 of 47 tenant-scoped tables. Meridale has had its own database since 2026-08-21.
- The 48 tenants moved during the [[full-tenant-database-rollout]] were folded back by 2026-08-28. The reasoning is in [[architecture-review-2026-06-11]].
- PgBouncer in transaction mode has fronted the primary since 2026-04-14. No connection-exhaustion event since.
- Incident command defaults to [[kwabena-asare]] since the March outage, not me. The playbook is [[run-an-incident]].
- [[observability-overhaul]] is paused until 2027-Q1. Tracing covers most API routes, not the workers.
- Paging averaged 9 pages a week in 2026-Q3. Whether that justifies a dedicated platform engineer is the open question in [[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]].

## Active Projects and Workflows

- [[tenant-isolation-migration]], with [[row-level-security-rollout]] as the live child and [[enterprise-dedicated-databases]] done.
- [[observability-overhaul]] (paused).
- [[reminder-outage-postmortem]] (completed; kept as the reference for how we run a postmortem).
- Workflows: [[run-an-incident]], [[run-a-schema-migration]], [[move-a-tenant-to-a-dedicated-database]].
- Reference: [[infrastructure-map]], [[reminder-pipeline-overview]], [[cloud-cost-per-clinic]].

## Next Actions

- [ ] Close the last 6 tables of row-level security coverage and get the coverage check into CI.
- [ ] Bring [[rds-capacity-plan-2027]] to the [[engineering-budget-2027]] discussion with real numbers.
- [ ] Give Kwabena and Felix the 2026-Q4 paging data for the platform hire decision on 2026-12-08.
- [ ] Write the restart plan for tracing in the workers before 2027-Q1.

## Maintenance Log

- 2026-10-23: Updated current state after RLS coverage reached 41 of 47 tables.
- 2026-08-28: Fold-back of the 48 moved tenants finished; shared database is the default again.
- 2026-06-11: Partial reversal of the tenant isolation decision.
- 2026-03-24: Postmortem of the reminder outage; incident command handed to Kwabena.
- 2025-11-18: Architecture review chose a database per tenant.
