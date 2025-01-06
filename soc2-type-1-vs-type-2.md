---
type: Concept
maturity: Evergreen
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[system-and-organization-controls]]"
  - "[[soc2-type-1-audit]]"
  - "[[soc2-type-2-observation]]"
_organized: true
---

# SOC 2 Type I Vs Type II

The two kinds of SOC 2 report, as I explain them to the team and to investors.

## Definition

- **Type I** answers: on one date, were the controls described accurately, designed sensibly and in place? The auditor looks at design and implementation as of that date. Ours was as of 2026-07-31 ([[soc2-type-1-report]]).
- **Type II** answers: over a period, usually 3 to 12 months, did the controls actually operate every time? The auditor samples real occurrences: merged pull requests, leavers, access reviews. Ours covers 2026-09-01 to 2027-02-28 ([[soc2-type-2-observation]]).

## Why It Matters Here

A Type I was the only report we could get before Meridale's 2026-09-30 deadline, because a Type II needs an observation window first. Customers and investors know the difference: [[samir-haddad]] accepted the Type I as a first step and asked when the Type II would come.

## Practical Difference for Engineers

Type I: write the control, set it up, show one example. Type II: never miss. A single unreviewed merge or a late access review becomes an exception. That is why the team felt the [[code-review-policy]] more after 2026-09-01 than before it.

## See Also

[[trust-services-criteria]], [[control-exception]], [[aicpa-soc-suite-of-services]].
