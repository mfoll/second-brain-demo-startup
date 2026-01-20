---
type: Project
status: Active
start: 2026-01-12
belongs_to: "[[partner-with-customers]]"
related_to:
  - "[[meridale-clinic-group]]"
  - "[[victoria-ashdown]]"
  - "[[imani-brooks]]"
has:
  - "[[meridale-rollout-tracker]]"
  - "[[meridale-commitments-tracker]]"
  - "[[onboard-an-enterprise-clinic]]"
  - "[[can-meridale-finish-rollout-by-december]]"
_organized: true
---

# Meridale Enterprise Rollout

Bringing all 42 clinics of [[meridale-clinic-group|Meridale Clinic Group]] onto Quaylane under the three-year contract signed on 2026-01-12. Our largest account by far: $186,000 a year, about 17% of ARR.

## Outcome

All 42 Meridale clinics live on Quaylane by 2026-12-11.

## Current State

- 19 of 42 clinics live as of 2026-10-23: the 3 pilot clinics (since 2025-06), 8 in wave 1 on 2026-09-08 and 8 in wave 2 on 2026-10-06.
- Wave 3 (12 clinics) is planned for 2026-11-03 and wave 4 (11 clinics) for 2026-12-01, leaving ten days of slack before 2026-12-11.
- All three contract conditions met: SSO on 2026-06-30, dedicated database on 2026-08-21, SOC 2 Type I report on 2026-08-28. See [[meridale-commitments-tracker]].
- Main risk: data imports from the old system at the wave 3 clinics, which kept appointment books in three different formats.

## Scope and Boundaries

This Project covers go-live of each clinic: configuration, data import, staff training with customer success, and hypercare for two weeks after each wave. The contract, pricing and renewal belong to Renata and Dana. Security questionnaires and audits belong to [[secure-and-comply]]. The dedicated database itself was built under [[enterprise-dedicated-databases]].

## Working Context

[[imani-brooks|Imani Brooks]] leads the customer side with [[pablo-arriaga|Pablo Arriaga]]; [[lucia-ferreyra|Lucia]] is the engineering contact for each wave. On Meridale's side, [[victoria-ashdown|Victoria Ashdown]] is the executive sponsor, [[samir-haddad|Samir Haddad]] owns IT and identity, and [[joanne-pruett|Joanne Pruett]] trains front-desk leads.

We did not start waves until all three conditions were met. Victoria agreed to this in February after we explained that a clinic moved before the dedicated database cutover would need a second migration. That is why nothing went live between the pilot and 2026-09-08 even though the contract started in January.

Each wave follows [[onboard-an-enterprise-clinic]]. Wave tracking lives in [[meridale-rollout-tracker]].

## Next Actions

- [ ] Run test imports for the wave 3 clinics by 2026-10-27.
- [ ] Confirm wave 3 trainers with Joanne by 2026-10-28.
- [ ] Hold the wave 2 hypercare review on 2026-10-21 and log the issues (done; 7 issues, none blocking).
- [ ] Decide on 2026-11-10 whether wave 4 needs to split.

## Open Questions

- [[can-meridale-finish-rollout-by-december]]

## Important Notes

- [[meridale-commitments-tracker]]
- [[meridale-rollout-wave-1-2026-09-08]]
- [[meridale-rollout-wave-2-2026-10-06]]
- [[meridale-contract-signed-2026-01-12]]

## Maintenance Log

- 2026-10-06: Wave 2 live; 19 of 42.
- 2026-09-08: Wave 1 live; 11 of 42.
- 2026-08-28: Last contract condition met (SOC 2 Type I report).
- 2026-01-12: Contract signed; project started.
