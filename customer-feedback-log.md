---
type: Source
source_type: Internal spreadsheet
date_accessed: 2026-10-19
belongs_to: "[[customer-feedback-loop]]"
related_to:
  - "[[product-discovery]]"
  - "[[imani-brooks]]"
  - "[[triage-customer-feedback]]"
_organized: true
---

# Customer Feedback Log

The shared spreadsheet where every piece of customer feedback lands, maintained by customer success since 2025-03-03. It is the single input to the monthly product review and the main evidence behind the [[roadmap-2027]].

## Summary

- 2,960 rows from 2025-03-03 to 2026-10-19.
- About 95 items a month in 2025, about 140 a month in 2026 as the customer base and the in-app feedback button grew.
- Tagged by customer success within seven days (91% in 2026-Q3). Reviewed monthly by Felix, Mai, Imani and me.
- Top request in 2026 by mentions and by accounts: online booking for patients.

## Why It Matters

It replaced arguments about who had talked to the loudest customer. The [[waitlist-autofill]] case was built from it (186 mentions in 2025), and so is the case for the [[online-booking-widget]]. It also feeds the churn view in [[churn-analysis-2025]] through the "churn risk" tag. My caution about reading it as a vote count is in [[feedback-volume-is-not-priority]].

## Key Details

### Columns

`id`, `date`, `account_id`, `segment` (added 2026-01-27), `channel` (call, ticket, in-app, NPS, sales), `summary` (one line, in our words, never a quote about a patient), `tags`, `ticket` (a `QL-` reference if one exists), `status` (new, tagged, planned, shipped, won't do), `closed_loop` (date customer success told the customer).

### Tags

About 40 tags in use. The ones that matter most: `online-booking`, `waitlist`, `multi-site`, `recall-reminders`, `group-booking`, `reporting`, `reminder-delivery`, `sso`, `pricing`, `churn-risk`, `Meridale pilot`.

### Top requests in 2026 (2026-01-01 to 2026-10-19)

| Theme | Items | Accounts |
| --- | --- | --- |
| Online booking for patients | 164 | 71 |
| Reporting and exports | 118 | 52 |
| Recall reminders (dental, physio) | 97 | 38 |
| Reminder delivery and timing | 88 | 41 (mostly 2026-03 and 2026-04) |
| Group or class bookings | 61 | 19 |
| Multi-site calendars | 57 | 22 (fell to near zero after 3.0) |

Online booking totals 212 items since the log started.

## Caveats

- Mentions count noise: a single vocal account can log ten items in a month. Read the accounts column, not just items.
- Sales-sourced items are under-tagged before 2026-01.
- Rows hold account IDs and clinic types only. Customer success removes any patient detail at entry, and the triage checks for it.

## Source Location

- Google Sheets, `Customer Success/Feedback/Customer feedback log`, owned by Imani Brooks. Engineering has comment access.
- Weekly triage follows [[triage-customer-feedback]].
