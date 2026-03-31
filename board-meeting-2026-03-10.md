---
type: Event
date: 2026-03-10
belongs_to: "[[support-the-company]]"
related_to:
  - "[[margot-ellison]]"
  - "[[renata-castellano]]"
  - "[[tenant-isolation-migration]]"
_organized: true
---

# Board Meeting 2026-03-10

Quarterly board meeting: Renata, Margot Ellison and me. Two hours.

## Engineering Page

- Meridale signed on 2026-01-12: 42 clinics, three years, $186,000 a year, three conditions with dates.
- [[database-per-tenant-pilot]] done on 2026-02-27, 12 tenants moved. [[full-tenant-database-rollout]] started 2026-03-02, target all of about 280 tenants by 2026-09.
- SOC 2 Type I kicked off with Ashcombe; as-of date 2026-07-31.
- Version 3 on track for 2026-06-23.
- Headcount: Ayesha Qureshi starting 2026-03-16.

## Discussion

Margot asked what the per-tenant rollout would cost at 280 databases. I gave the pilot number and an estimate, and said migrations would be the harder cost. Seven days later a migration batch exhausted the RDS connection limit and caused the [[reminder-outage-2026-03-17]]. Rereading this page I see the risk was named and nobody, including me, put a throttle on the rollout because of it.

## Decisions

- Board approved the SOC 2 budget ($24,500 audit, up to $15,000 pen test).
- Next meeting set for 2026-06-16.
