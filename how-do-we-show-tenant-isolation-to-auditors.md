---
type: Question
status: Answered
belongs_to: "[[row-level-security-rollout]]"
related_to:
  - "[[soc2-type-2-observation]]"
  - "[[soc2-control-matrix]]"
  - "[[row-level-security]]"
_organized: true
---

# How Do We Show Tenant Isolation To Auditors?

## Current Answer

For the SOC 2 Type II window, the evidence package is: the [[rls-policy-coverage-tracker]] output each month, the pgTAP test run from CI on every merge to main, the quarterly review of roles with `BYPASSRLS`, and the 2026 pen test summary. Agreed with [[colette-fairbanks]] on 2026-09-03 for the [[soc2-type-2-observation]].

## Why It Was a Question

The Type I report covered design, not operation over time. A policy that exists in September proves nothing about a table added in January. The CI coverage check (planned) closes that gap.

## Remaining Risk

Six tables are not covered yet; the auditor will see that in the tracker. See [[can-we-reach-full-rls-coverage-this-year]].
