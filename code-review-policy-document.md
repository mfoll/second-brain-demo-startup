---
type: Source
source_type: Internal document
date_accessed: 2026-04-14
belongs_to: "[[code-review-policy]]"
related_to:
  - "[[engineering-meeting-2026-04-08]]"
  - "[[soc2-control-matrix]]"
_organized: true
---

# Code Review Policy Document

The one-page written policy approved on 2026-04-14, following [[engineering-meeting-2026-04-08]]. Version 1.1 since 2026-08 (added the watcher).

## Summary

Every pull request to `main` in the four production repositories needs one approving review from someone other than the author, recorded in GitHub; stale approvals are dismissed on new commits; code owner review applies in `quaylane-infra`; emergencies follow [[ship-an-emergency-change]].

## Key Details

- Owner: Nikolas. Reviewed yearly or when the SOC 2 scope changes.
- Explicitly states that co-authored commits are not a substitute for an approval, and why (auditor evidence).
- Mapped to the change management row of the [[soc2-control-matrix]].
- Kept to one page on purpose ([[review-rules-should-be-boring]]); advice on how to review well lives in the [[engineering-handbook]].

## Why It Matters

The document the auditor reads. Also the first thing new engineers read about review ([[onboarding-plan-for-new-engineers]]).

## Source Location

Engineering handbook, `Policies / Code review`, with a PDF copy in the SOC 2 evidence folder.
