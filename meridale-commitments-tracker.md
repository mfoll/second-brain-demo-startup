---
type: Note
belongs_to: "[[meridale-enterprise-rollout]]"
related_to:
  - "[[meridale-clinic-group]]"
  - "[[soc2-type-1-report]]"
  - "[[enterprise-dedicated-databases]]"
_organized: true
---

# Meridale Commitments Tracker

What we promised Meridale Clinic Group and whether we delivered. The short answer for anyone asking: three engineering conditions in the 2026-01-12 contract, all three met on time.

## Contract conditions

| Promise | Due | Delivered | Notes |
| --- | --- | --- | --- |
| SAML SSO with deprovisioning | 2026-07-01 | 2026-06-30 | Shipped alone after 3.0 slipped. [[sso-go-live-2026-06-30]] |
| Dedicated database | Before the first wave | 2026-08-21 | Kept after the partial reversal of the tenant decision. [[enterprise-dedicated-databases]] |
| SOC 2 Type I report | 2026-09-30 | 2026-08-28 | Two exceptions: quarterly access review not yet evidenced; one leaver's laptop returned without a wipe record. [[soc2-type-1-report]] |

## Other commitments

- 99.5% monthly availability of the web app: met every month since signing.
- Named engineering contact per wave: Lucia Ferreyra.
- 30 days' notice of breaking changes to exports: no breaking change so far.
- All 42 clinics live by 2026-12-11: 19 of 42 on 2026-10-23, on plan. See [[meridale-enterprise-rollout]].

## Commitments we did not make

Recorded because people ask:

- No date for the cross-site room report or email waitlist offers. Both are 2027 candidates; see [[enterprise-customers-should-not-own-the-roadmap]].
- No commitment on reminder delivery times. The contract treats reminders as best effort. After March I would not want to rely on that.

## Follow-ups owed

- Evidence that both Type I exceptions are closed during the [[soc2-type-2-observation]]. Samir Haddad asked for it when he accepted the report.
- SAML certificate rotation with Samir in 2027-06.
