---
type: Event
date: 2026-01-12
belongs_to: "[[meridale-enterprise-rollout]]"
related_to:
  - "[[meridale-clinic-group]]"
  - "[[dana-prescott]]"
  - "[[meridale-master-services-agreement]]"
_organized: true
---

# Meridale Contract Signed 2026-01-12

Meridale Clinic Group signed a three-year contract for all 42 clinics at $186,000 a year. Signed by Victoria Ashdown and Renata Castellano; closed by Dana Prescott after a four-month negotiation.

## The engineering conditions

1. SAML SSO with deprovisioning by 2026-07-01.
2. A dedicated database for Meridale data before the first rollout wave.
3. A SOC 2 Type I report by 2026-09-30.

I had agreed to all three in writing on 2025-12-19 after checking them against the plan from the [[architecture-review-2025-11-18]], which at that point moved every tenant to its own database anyway. The second condition was therefore free in December. It stopped being free when we partly reversed the decision at [[architecture-review-2026-06-11]], and it is the reason enterprise tenants kept dedicated databases.

## Same day

- Started [[waitlist-autofill]] and [[meridale-enterprise-rollout]].
- Hiring plan for two engineers approved by Renata ([[engineering-hiring-2026]]).
- Sent a short note to the team: what the conditions are, who owns each, and that none of them is optional.

## Follow-up

All three met; tracked in [[meridale-commitments-tracker]].
