---
type: Procedure
belongs_to: "[[meridale-enterprise-rollout]]"
related_to:
  - "[[meridale-rollout-tracker]]"
  - "[[imani-brooks]]"
  - "[[lucia-ferreyra]]"
_organized: true
---

# Onboard An Enterprise Clinic

The go-live runbook for bringing a clinic of an enterprise customer onto Quaylane, written for the Meridale waves and revised after each one. Customer success owns training; engineering owns configuration, import and cutover.

## Two weeks before

1. Confirm the clinic list for the wave with the customer's operations lead and record it in [[meridale-rollout-tracker]].
2. Create the sites, rooms and roster templates in the customer's organization from their site survey.
3. Confirm SSO users exist for all front-desk staff at the clinic (SCIM sync).
4. Request the appointment book export from the old system in an agreed format.

## One week before

5. Run a test import into staging. Fix mapping problems; the import must finish with zero rejects.
6. Check for duplicate staff names and merge them. Added after wave 1.
7. Training sessions, two per clinic, run by customer success with the customer's trainer.

## Friday before go-live

8. Final import into production for future appointments only. Record counts in the tracker.
9. Turn off reminders in the old system for appointments from Monday onward. Added after wave 1, where some appointments got two reminders.

## Go-live day

10. Engineering contact on a call with the clinics from 07:30 to 10:00.
11. Watch the reminder queue and the error rate for the customer's organization.
12. Log every issue in the wave's hypercare list.

## Hypercare

13. Two weeks. Daily check-in for the first three days, then twice a week.
14. Review at the end, with the issue list and what to change in this runbook.

## Guardrails

- No go-live on a Friday or a day before a public holiday.
- No go-live while an incident is open, or on a release train day.
- Data imports carry only the fields we store: names, contact details and appointment times. Anything else in the export is dropped, never imported.
