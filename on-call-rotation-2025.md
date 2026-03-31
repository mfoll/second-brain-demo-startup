---
type: Note
belongs_to: "[[on-call-rotation-redesign]]"
related_to:
  - "[[on-call-handbook]]"
_archived: true
_organized: true
---

# On-Call Rotation 2025

How on-call worked before the redesign. Superseded by the [[on-call-handbook]] on 2026-04-20.

## The arrangement

- No formal rotation. Alerts went to PagerDuty with an escalation policy of Kwabena, then me, at all hours.
- Other engineers were added "for coverage" during holidays, without a stipend or a handoff.
- About 20 alerts paged, many on internal errors with no customer impact.

## Why it was replaced

Two people carried almost all the load, nobody was formally secondary, and no alert watched the reminder queue. The [[reminder-outage-2026-03-17]] made all three problems visible at once, and the redesign became one of the postmortem actions ([[on-call-rotation-redesign]]).
