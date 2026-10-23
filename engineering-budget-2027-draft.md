---
type: Note
belongs_to: "[[engineering-budget-2027]]"
related_to:
  - "[[cloud-cost-per-clinic-model]]"
  - "[[how-much-should-we-spend-on-security-in-2027]]"
  - "[[engineering-budget-2026]]"
_organized: true
---

# Engineering Budget 2027 Draft

Working draft as of 2026-10-23. Figures are rounded and for planning only; salaries are entered by level band in Renata's model and do not appear here.

## Headcount

- 2026 year end: 8 engineers including me.
- 2027: 10, with the two hires the extension funds. Hire 1 in 2027-Q1, hire 2 in 2027-Q3.
- Scenario A: hire 1 is a platform engineer. Scenario B: hire 1 is a product engineer. Cost difference under 5% at the same level band ([[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]]).
- On-call stipend: $300 a week, one primary at a time, about $15,600 a year.

## Non-Headcount

| Line | 2026 actual (forecast) | 2027 draft |
| --- | --- | --- |
| AWS (shared platform) | $44,000 | $48,000 |
| Enterprise dedicated databases | $3,750 (from 2026-08) | $9,000 (Meridale) + $6,400 contingency for a second |
| Pingrove platform fees | $3,600 | $4,200 |
| Tooling (GitHub, error tracker, CI, design) | $24,000 | $29,000 |
| Audit and security | $38,500 | $71,000 |
| Training and conferences | $6,000 | $9,000 |

## Assumptions

- Active clinics: 280 now, 340 by 2027-12, per Renata's plan.
- [[cloud-cost-per-clinic]] stays between $12 and $14.
- No second observability vendor; the [[observability-overhaul]] resumes in 2027-Q1 within the current tooling line.

## Open

Security line ([[how-much-should-we-spend-on-security-in-2027]]); compliance tool ([[should-we-buy-a-compliance-automation-platform]]).
