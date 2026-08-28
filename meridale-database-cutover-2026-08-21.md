---
type: Event
date: 2026-08-21
belongs_to: "[[enterprise-dedicated-databases]]"
related_to:
  - "[[meridale-clinic-group]]"
  - "[[move-a-tenant-to-a-dedicated-database]]"
  - "[[meridale-enterprise-rollout]]"
_organized: true
---

# Meridale Database Cutover 2026-08-21

Meridale Clinic Group moved to its dedicated database, `ent-meridale`, on Friday 2026-08-21 from 19:00 to 19:48. This met the dedicated database condition of the contract signed on 2026-01-12.

## Who

[[kwabena-asare]] ran the steps, [[teodora-vasilescu]] verified, [[bram-verhoef]] scribed, I was on call for decisions. [[imani-brooks]] had agreed the window with Meridale; [[samir-haddad]] was informed the day before.

## What Happened

- 19:00 tenant frozen (read-only), 7 Meridale clinics live at the time.
- 19:04 to 19:31 `tenantctl move`, 6.2 million rows.
- 19:31 to 19:39 `tenantctl verify`: counts, sequences, policies, schema version all matched.
- 19:39 routing switched; 19:48 smoke tests passed and tenant unfrozen.

No issues on Monday morning. Rows in the shared database were purged on 2026-09-04 after 14 days.

## After

- Procedure confirmed as [[move-a-tenant-to-a-dedicated-database]].
- Dana and Imani reported the condition as met to Meridale on 2026-08-24.
