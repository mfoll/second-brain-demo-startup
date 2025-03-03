---
type: Project
status: Active
start: 2025-03-03
belongs_to: "[[partner-with-customers]]"
related_to:
  - "[[imani-brooks]]"
  - "[[felix-ostrowski]]"
  - "[[product-discovery]]"
has:
  - "[[customer-feedback-log]]"
  - "[[triage-customer-feedback]]"
  - "[[product-review-2026-09-29]]"
_organized: true
---

# Customer Feedback Loop

Making sure every piece of customer feedback lands in one place, gets a tag within a week, and is looked at in the monthly product review. Started in 2025-03 after Imani and I found the same request in four different Slack channels with four different answers.

## Outcome

Every feedback item tagged in the feedback log within a week and reviewed in the monthly product review.

## Current State

- The [[customer-feedback-log]] holds 2,960 items since 2025-03; about 140 a month in 2026.
- Tagging lag: 91% of items tagged within seven days in 2026-Q3, up from 64% in 2025-Q3. Target is 95%.
- Monthly product review on the last Tuesday of each month with Felix, Mai, Imani and me. The September review fed the [[roadmap-2027]]; see [[product-review-2026-09-29]].

## Scope and Boundaries

Feedback from calls, support tickets, the in-app widget, NPS comments and sales. Bugs go to the issue tracker, not the log, though a bug that recurs gets a feedback tag too. I do not want the log to become a voting system; see [[feedback-volume-is-not-priority]].

## Working Context

Customer success tags most items. Engineering's part is to link items to tickets (`QL-` references in a column) and to close the loop when something ships: Imani's team writes back to everyone tagged on a shipped item, which they did for 430 accounts after 3.0.

The weekly triage follows [[triage-customer-feedback]]. Before the loop existed, roadmap arguments were about who had spoken to the loudest customer; now they are about the log.

## Next Actions

- [ ] Get tagging within seven days to 95% by year end (Imani).
- [ ] Add a column for segment so the [[clinic-segments-overview]] can be read against requests.
- [ ] Export the 2026 top themes for the roadmap by 2026-11-03.

## Important Notes

- [[customer-feedback-log]]
- [[nps-survey-2026-q2]]
- [[support-ticket-dashboard]]
- [[feedback-volume-is-not-priority]]

## Maintenance Log

- 2026-09-29: September review used as the roadmap input session.
- 2026-01-27: Added the "segment" and "churn risk" tags.
- 2025-03-03: Started with Imani.
