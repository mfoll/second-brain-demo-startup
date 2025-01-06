---
type: Note
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[primary-postgres-cluster]]"
  - "[[wikipedia-infrastructure-as-code]]"
  - "[[bram-verhoef]]"
_organized: true
---

# Infrastructure Map

One-page orientation to production for new engineers. Updated 2026-10-12 after [[bram-verhoef]]'s onboarding questions.

## Repositories

- `quaylane-api`: TypeScript API, migrations, ADRs.
- `quaylane-web`: React front end.
- `quaylane-workers`: scheduler, reminder workers, imports and exports.
- `quaylane-infra`: Terraform, `tenantctl`, PgBouncer, monitoring rules.

## Production

- Containers for API (6 tasks), workers (8 tasks) and PgBouncer (2 tasks).
- [[primary-postgres-cluster]]: shared database, PostgreSQL 16 on RDS.
- `ent-meridale`: Meridale's dedicated database ([[enterprise-dedicated-databases]]).
- Redis for the job queue and short-lived caches.
- Separate AWS accounts for production, staging and billing.
- CI and deploys in GitHub Actions; production deploys need a merged pull request with one recorded approval.

## Where To Look

Alerts in [[alerting-rules-inventory]], costs in [[rds-cost-dashboard]], incidents in [[incident-log]], reminders in [[reminder-pipeline-overview]].
