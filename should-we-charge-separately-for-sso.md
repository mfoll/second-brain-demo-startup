---
type: Question
status: Answered
belongs_to: "[[enterprise-sso]]"
related_to:
  - "[[enterprise-readiness]]"
  - "[[should-multi-location-calendars-be-enterprise-only]]"
_organized: true
---

# Should We Charge Separately For SSO?

## Question

After SSO shipped for Meridale, two other accounts asked for it. Do we sell SSO as an add-on, or include it in the enterprise plan?

## Current Answer

Included in the enterprise plan, not available on smaller plans and not sold separately. Decided by Renata on 2026-09-22 after a discussion with Dana, Felix and me.

## Reasoning

- Each SSO customer costs engineering time: about two days of Min-jae's time for setup and testing with their identity provider, plus certificate rotations. That cost fits an enterprise plan with an onboarding fee.
- An add-on price for SSO alone invites small accounts with no IT team, where most setup problems come from.
- Including it keeps the enterprise plan's promise simple: SSO, a dedicated database on request, and contractual commitments. See [[enterprise-readiness]].

## Open edge

One of the two accounts asking is a 9-site physio group, too small for the enterprise plan. Dana will offer the plan at a discount rather than break the rule.
