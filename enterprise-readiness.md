---
type: Concept
maturity: Seed
belongs_to: "[[partner-with-customers]]"
related_to:
  - "[[meridale-clinic-group]]"
  - "[[should-we-charge-separately-for-sso]]"
_organized: true
---

# Enterprise Readiness

What a clinic group of Meridale's size needs from us before it will sign, as I understand it after one enterprise deal. A checklist more than a theory.

## The list

1. SSO with deprovisioning ([[enterprise-sso]]).
2. A security answer they can audit: SOC 2 report, questionnaire answers, a penetration test summary.
3. Data isolation they can explain to their own board: a dedicated database for enterprise contracts since [[architecture-review-2026-06-11]].
4. Multi-site operations in the product ([[multi-location-calendars]]).
5. Contractual availability and a named engineering contact during rollout.
6. Predictable change: notice of breaking changes to exports, a release cadence they can plan around.

## What it costs

Each item has a recurring cost. SSO setups, a dedicated database per enterprise tenant (part of the +$3,100 a month the full rollout had added before the reversal), the Type II audit. The enterprise plan has to carry those costs, which is the logic behind [[should-we-charge-separately-for-sso]].

## Caution

One customer is not a market. The second enterprise prospect may want different things. Revisit after the next enterprise deal.
