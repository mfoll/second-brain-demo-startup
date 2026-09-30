---
type: Event
date: 2026-09-08
belongs_to: "[[meridale-enterprise-rollout]]"
related_to:
  - "[[onboard-an-enterprise-clinic]]"
  - "[[meridale-rollout-tracker]]"
_organized: true
---

# Meridale Rollout Wave 1 2026-09-08

Eight Meridale clinics went live, bringing the total to 11 of 42. First wave on the dedicated database and on SSO from day one.

## What went well

- All eight clinics on the multi-location calendars beta build, a week before 3.0 GA. No calendar issues.
- Data imports done on the Friday before; Lucia's import script from the [[onboard-an-enterprise-clinic]] runbook validated 41,000 future appointments with zero rejects after two dry runs.
- Training by Joanne Pruett and Pablo Arriaga, two sessions per clinic.

## What did not

- Two clinics had staff rosters that listed the same person under two names. Fixed by hand during hypercare; we added a duplicate check to the import.
- Reminders for the first day were scheduled in the old system and in Quaylane for one clinic. Some appointments got two reminders. Added a cutover step to switch reminders off in the old system the day before.

## Hypercare

Two weeks, 23 issues logged, none above medium. Review held on 2026-09-23.

Next: [[meridale-rollout-wave-2-2026-10-06]].
