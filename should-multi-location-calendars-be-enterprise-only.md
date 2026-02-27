---
type: Question
status: Answered
belongs_to: "[[multi-location-calendars]]"
related_to:
  - "[[clinic-segments-overview]]"
  - "[[felix-ostrowski]]"
_organized: true
---

# Should Multi-Location Calendars Be Enterprise-Only?

## Question

Should the cross-site calendar be an enterprise plan feature, or available to every account with more than one site?

## Current Answer

Available on every plan for accounts with more than one site. Decided by Renata and Felix on 2026-03-11, with my input on cost.

## Reasoning

- 34 accounts have more than one site; most are small groups of two or three. They had been paying for separate accounts per site and complaining about it ([[customer-feedback-log]], tag `multi-site`).
- Engineering cost does not depend on the plan: the data model change applies to everyone.
- Enterprise differentiation comes from SSO, a dedicated database and contractual commitments, not from the calendar.

## Rejected

Dana's proposal to gate it to enterprise to give sales a lever. Renata judged the churn risk among small groups larger than the upsell.

Related: [[should-we-charge-separately-for-sso]].
