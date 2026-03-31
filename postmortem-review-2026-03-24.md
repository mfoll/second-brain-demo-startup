---
type: Event
date: 2026-03-24
belongs_to: "[[reminder-outage-postmortem]]"
related_to:
  - "[[reminder-outage-2026-03-17]]"
  - "[[run-an-incident]]"
  - "[[on-call-rotation-redesign]]"
  - "[[wikipedia-postmortem-documentation]]"
_organized: true
---

# Postmortem Review 2026-03-24

The blameless review of the [[reminder-outage-2026-03-17]]. 90 minutes, recorded, with the draft document circulated the day before.

## At a Glance

> [!success]
> Nine action items agreed with owners and dates, including PgBouncer in transaction mode, a throttle on migration jobs, an alert on reminder queue age over 10 minutes and a redesign of on-call. All nine closed by 2026-05-29.

## Attendees

[[kwabena-asare]] (facilitator, as incident commander), [[teodora-vasilescu]], [[hamish-pettigrew]], [[lucia-ferreyra]], [[min-jae-oh]], [[ayesha-qureshi]] (in her second week, as an observer), [[pablo-arriaga]], [[imani-brooks]], me. [[renata-castellano]] read the document but did not attend, on purpose: we wanted engineers to speak freely.

## How We Ran It

- Ground rule read aloud at the start: we discuss decisions and systems, not people; anyone who made a decision that day made it with the information they had.
- Walked the timeline first, then asked at each step "what made this the reasonable thing to do at the time".
- Teodora described starting the migration batch at 09:31. The discussion moved quickly to why our tooling allowed 24 parallel workers on one instance with no limit, which is the right question.
- I said that I had been the scribe while also answering Renata and Meridale, and that the scribe notes had gaps between 10:40 and 11:30 as a result. That is on me and is why I stepped out of incident roles.

## Contributing Factors Agreed

1. Migration tooling had no concurrency or connection limit.
2. Tenant databases lived on the primary instance, sharing one connection limit with everything else.
3. Reminder workers had no reserved connections and no backoff.
4. No queue-age alert; the first signal was a clinic.
5. On-call was informal: whoever noticed, plus me. Nobody was formally second.

## Actions

| # | Action | Owner | Closed |
|---|---|---|---|
| 1 | PgBouncer in transaction mode in front of the primary | Kwabena | 2026-04-14 |
| 2 | Migration throttle: 4 databases in parallel, 8 connections each | Teodora | 2026-04-03 |
| 3 | Alert on reminder queue age over 10 minutes | Kwabena | 2026-03-27 |
| 4 | On-call redesign | Me, then [[on-call-rotation-redesign]] | 2026-05-15 |
| 5 | Honor `Retry-After`, 45 per second token bucket | Hamish | 2026-04-10 |
| 6 | Reserved connection budget for the reminder role | Kwabena | 2026-04-08 |
| 7 | Clinic communication templates and status page | Pablo, Imani | 2026-04-20 |
| 8 | Unsent reminders report for clinics | Lucia | 2026-05-06 |
| 9 | Load test of migration fan-out at 100 databases | Teodora | 2026-05-29 |

## Decisions Beyond the Actions

- Kwabena becomes the default incident commander; I stop taking incident roles unless he asks. See [[incident-commander-should-not-be-the-founder]].
- [[run-an-incident]] to be written from what we did right and wrong that day.
- Tenant rollout paused until actions 2 and 6 are done (resumed 2026-04-09).

## Reading Shared Afterwards

[[wikipedia-postmortem-documentation]], [[wikipedia-site-reliability-engineering]], [[wikipedia-exponential-backoff]].
