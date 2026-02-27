---
type: Note
belongs_to: "[[soc2-type-1-audit]]"
related_to:
  - "[[compliance-should-be-a-byproduct-of-engineering-practice]]"
  - "[[soc2-readiness-review-2026-04-20]]"
  - "[[grow-as-a-leader]]"
_organized: true
---

# Lessons From The SOC 2 Type I Audit

My reflection after the report was issued on 2026-08-28. Written for myself and for whoever runs the next audit.

## What Went Well

- Starting from a real questionnaire ([[meridale-security-questionnaire]]) meant every control answered a customer question.
- The spreadsheet matrix was enough ([[a-spreadsheet-is-enough-for-a-first-soc-2]]).
- Choosing an as-of date three months after readiness gave room to fix 9 of 11 gaps.
- Being honest in fieldwork. When Patrice asked for an access review that did not exist, we said so.

## What I Got Wrong

- I owned too many controls myself: 19 of the 31 engineering rows at the start. The two that failed were both rows I had not delegated or scheduled. This is the same delegation problem I work on with [[miriam-oduya]], showing up in a spreadsheet.
- I prioritized visible work (the pen test, the policy, branch protection) over boring recurring work. The readiness review told me which two were at risk.
- I underestimated the team cost of the code review rule. The argument at [[engineering-meeting-2026-04-08]] was about more than evidence; I should have discussed pairing with [[hamish-pettigrew]] before the meeting, not in it.

## Changes for the Type II

- Engineering rows redistributed: Kwabena owns infrastructure and backups, Teodora owns database access, I keep change management and the access review.
- Every recurring control has a calendar entry and a named backup.
- Monthly evidence check with Colette.
