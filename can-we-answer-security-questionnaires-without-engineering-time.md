---
type: Question
status: Open
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[security-questionnaire-answer-library]]"
  - "[[dana-prescott]]"
  - "[[answer-a-security-questionnaire]]"
_organized: true
---

# Can We Answer Security Questionnaires Without Engineering Time?

[[dana-prescott]] wants sales to answer most security questionnaires alone, using the answer library and the SOC 2 report, so prospects do not wait on engineering.

## Data

- 9 questionnaires in 2026 to date, 40 to 310 questions each.
- Engineering time per questionnaire fell from about 30 hours (Meridale, 2025) to about 4 hours (2026-Q3) as the [[security-questionnaire-answer-library]] grew to 412 answers.
- About 85% of questions in recent questionnaires matched an existing answer.

## Tension

Answers drift. The library said "isolation enforced in application code" until 2026-06; then it said "per-tenant databases"; now it says "row-level security, dedicated databases for enterprise contracts". A salesperson cannot tell which answer is still true.

## Leaning

Yes for matched answers reviewed in the last six months; engineering signs off only new or stale answers, within five business days. Needs a `last_reviewed` column in the library and a security one-pager. Trial with Dana in 2026-11.
