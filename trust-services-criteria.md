---
type: Concept
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[soc2-control-matrix]]"
  - "[[system-and-organization-controls]]"
_organized: true
---

# Trust Services Criteria

The criteria a SOC 2 report is measured against, grouped into five categories: Security, Availability, Processing Integrity, Confidentiality and Privacy. Security is always included; the others are chosen by the company being audited.

## Our Choice

For the Type I and Type II we chose Security, Availability and Confidentiality, on [[patrice-ndour]]'s advice at [[soc2-kickoff-with-ashcombe-2026-02-10]]:

- **Availability** because reminders are time-critical and the [[reminder-outage-2026-03-17]] made customers ask about it.
- **Confidentiality** because tenant isolation is the question every clinic group asks.
- **Privacy** left out for now: it would bring the whole lifecycle of patient contact data into scope (notice, consent, retention, deletion), and we act as a processor for clinics who own that relationship. We will revisit after the retention question is settled ([[how-long-should-we-retain-reminder-message-logs]]).
- **Processing Integrity** left out: no customer has asked for it.

## How It Shows Up

Every row of the [[soc2-control-matrix]] maps to one or more criteria IDs (for example CC6.1 for logical access, CC8.1 for change management, A1.2 for backup and recovery). When a questionnaire asks "is X covered by your SOC 2?", the criteria column answers it.
