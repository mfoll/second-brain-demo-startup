---
type: Project
status: Completed
start: 2026-03-30
end: 2026-05-15
belongs_to: "[[lead-engineering-team]]"
related_to:
  - "[[reminder-outage-postmortem]]"
  - "[[reliability-and-incidents]]"
  - "[[team-health]]"
has:
  - "[[on-call-handbook]]"
  - "[[on-call-schedule]]"
  - "[[on-call-stipend-decision-memo]]"
  - "[[on-call-review-2026-05-15]]"
_organized: true
---

# On-Call Rotation Redesign

Replace the informal "whoever notices" on-call of 2025 with a real rotation. One of the nine actions from [[postmortem-review-2026-03-24]] after the [[reminder-outage-2026-03-17]].

## Outcome

Weekly primary and secondary rotation across six engineers, a $300 weekly stipend, a handbook, and paging only on customer-facing alerts. Reached on 2026-05-15.

## Current State

- Six engineers in rotation: Kwabena, Teodora, Lucia, Min-jae, Hamish and Ayesha. Bram shadows and joins on 2026-11-02. I am the escalation after the secondary, not a rotation member.
- Primary is paid $300 for the week; handoff is Monday at 10:00 with a written note.
- Paging is limited to four customer-facing alerts; everything else goes to a Slack channel. Pages averaged 9 a week in 2026-Q3 ([[paging-report-2026-q3]]).
- Survey score for on-call sustainability rose from 2.6 (2025-11) to 3.5 (2026-06).
- The next decision is not this project's: whether to hire a platform engineer ([[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]]).

## Scope and Boundaries

In scope: rotation shape, pay, paging rules, handbook. Out of scope: incident roles during an incident ([[run-an-incident]]), alert thresholds themselves (owned by [[kwabena-asare]] under [[run-the-platform]]).

## Working Context

Before: the 2025 arrangement was in [[on-call-rotation-2025]], now archived. Kwabena and I took most pages; nobody was formally primary or secondary when the outage started on 2026-03-17, and no alert watched the reminder queue.

Choices made:

- Weekly, not daily: fewer handoffs, and a week is long enough to fix the noisy alert you were paged by.
- Primary plus secondary: the secondary is there for the cases where the primary is mid-incident or unreachable for 15 minutes.
- Stipend of $300 for the primary week, agreed with [[renata-castellano]] and [[colette-fairbanks]] ([[on-call-stipend-decision-memo]]). Rejected: time off in lieu only (hard to take in a team this size) and hourly pay for pages (rewards noise).
- Only customer-facing alerts page. Rejected: paging on all errors, which in a February test produced 31 pages in a week.

## Active Workflows

- [[on-call-handbook]] for the week itself.
- [[run-an-incident]] when a page turns into an incident.
- Quarterly paging review using the PagerDuty export.

## Next Actions

- [ ] Bram's first primary week starting 2026-11-02, with Kwabena as secondary.
- [ ] Q4 paging review on 2026-11-30, feeding the platform hire decision.

## Open Questions

- [[how-many-pages-a-week-is-too-many]]
- [[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]]

## Important Notes

- [[on-call-handbook]]
- [[on-call-review-2026-05-15]]
- [[alert-fatigue]]

## Maintenance Log

- 2026-05-15: Review after the first four weeks; rotation kept unchanged; project closed.
- 2026-04-20: First rotation week, Kwabena primary.
- 2026-03-30: Started as one of the nine postmortem actions.
