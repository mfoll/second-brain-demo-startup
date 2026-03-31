---
type: Procedure
belongs_to: "[[on-call-rotation-redesign]]"
related_to:
  - "[[run-an-incident]]"
  - "[[on-call-schedule]]"
  - "[[reliability-and-incidents]]"
_organized: true
---

# On-Call Handbook

How the weekly on-call works at Quaylane since 2026-04-20. Written as part of the [[on-call-rotation-redesign]]; replaces the archived [[on-call-rotation-2025]].

## Rotation

- Six engineers: [[kwabena-asare]], [[teodora-vasilescu]], [[lucia-ferreyra]], [[min-jae-oh]], [[hamish-pettigrew]], [[ayesha-qureshi]]. [[bram-verhoef]] joins on 2026-11-02 after shadowing.
- Weekly shifts, Monday 10:00 to Monday 10:00. Each person is primary about one week in six and secondary the week after.
- The schedule lives in PagerDuty and is mirrored in [[on-call-schedule]]. Swaps are fine; arrange them yourself and update PagerDuty.
- The primary week pays a $300 stipend ([[on-call-stipend-decision-memo]]). If you are paged after 22:00, start late the next day without asking.

## What pages

Only customer-facing alerts page. Since 2026-05:

1. Reminder queue age over 10 minutes (added after [[reminder-outage-2026-03-17]]).
2. API 5xx rate above 2% for 5 minutes.
3. Login failure rate above 10% for 5 minutes, including SSO.
4. Database connections above 85% of the limit on the [[primary-postgres-cluster]].

Everything else goes to `#alerts` and is looked at during working hours. If an alert pages and did not need to, fix or demote it during your week. That is part of the job.

## Escalation

1. Primary acknowledges within 15 minutes.
2. No acknowledgement after 15 minutes: PagerDuty pages the secondary.
3. Secondary unreachable after another 15 minutes, or anything severity 1: Nikolas.
4. If it is an incident, follow [[run-an-incident]]. Kwabena is the default incident commander during working hours since 2026-03-24; outside them, the primary is commander until someone takes over.
5. A fix that cannot wait for review goes through [[ship-an-emergency-change]].

## Customer contact

The primary never contacts clinics directly. Customer success ([[imani-brooks]] or [[pablo-arriaga]]) owns communication; page them through the incident channel.

## Handoff

On Monday at 10:00 the outgoing primary posts a handoff note in `#oncall`: pages received, anything still open, any alert changed, anything the next person should watch. Five lines is enough. The note feeds the quarterly paging review ([[paging-report-2026-q3]]).

## Not your job on call

Feature work deadlines slip by the time you lose to pages; tell Lucia at the Tuesday sync. You are not expected to fix root causes during the week, only to make the system safe and file a ticket.
