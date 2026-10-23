---
type: Source
source_type: Spreadsheet
date_accessed: 2026-10-20
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[run-an-incident]]"
  - "[[reliability-and-incidents]]"
_organized: true
---

# Incident Log

One row per incident and planned high-risk change since 2025-01: date, severity, duration, commander, tenants affected (count), postmortem link.

## Key Details

- 2025: 11 incidents, 1 SEV1 (a certificate expiry, 2025-05-22, 40 minutes).
- 2026 to date: 9 incidents. SEV1: 2026-03-17 reminders. SEV2: 2026-06-30 SSO login loop for 3 Meridale clinics (1 h 10 min); 2026-09-16 calendar slowness after the 3.0 release (2 h 05 min).
- Planned changes logged: Meridale database cutover, fold-back waves, PgBouncer cutover.
- It is the population the auditor samples for incident response in the [[soc2-control-matrix]].

## Source Location

Engineering shared drive, `Incidents/incident-log`. Entries created by the incident commander.
