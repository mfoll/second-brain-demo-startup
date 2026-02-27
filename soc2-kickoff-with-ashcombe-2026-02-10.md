---
type: Event
date: 2026-02-10
belongs_to: "[[soc2-type-1-audit]]"
related_to:
  - "[[patrice-ndour]]"
  - "[[trust-services-criteria]]"
  - "[[ashcombe-assurance-engagement-letter]]"
_organized: true
---

# SOC 2 Kickoff With Ashcombe 2026-02-10

Kickoff meeting for the SOC 2 Type I with [[patrice-ndour]] and one associate from Ashcombe Assurance. From Quaylane: me, [[colette-fairbanks]] and [[renata-castellano]] for the first half.

## Agreed

- **Report type:** Type I first, Type II observation to start right after ([[soc2-type-1-vs-type-2]]).
- **Criteria:** Security (required), Availability and Confidentiality. Patrice advised against Privacy and Processing Integrity for a first report: Privacy would pull in the full data lifecycle of patient contact data and roughly double the work.
- **As-of date:** 2026-07-31, chosen to leave time for a readiness review in April and fixes in May to July, while still issuing before Meridale's 2026-09-30 deadline.
- **System boundary:** the four production repositories, the AWS production account, the job queue, and subprocessors carved out (AWS, Pingrove, email provider).
- **Fee and timeline:** $24,500 for the Type I, per the [[ashcombe-assurance-engagement-letter]]. Readiness review in the week of 2026-04-20, fieldwork from 2026-08-03.

## What I Took Away

Patrice explained that a control is something you can show happened, not something you believe happens. He used code review as his example, two months before it became a team argument ([[engineering-meeting-2026-04-08]]). I started the [[soc2-control-matrix]] the next week, replacing the loose checklist I had made in January ([[soc2-readiness-checklist-2026-02]]).
