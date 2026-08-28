---
type: Source
source_type: Internal document
date_accessed: 2026-08-25
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[subprocessor]]"
  - "[[data-processing-agreement-template]]"
  - "[[rania-saleh]]"
_organized: true
---

# Subprocessor List

The customer-facing list of [[subprocessor|subprocessors]] that may process clinics' personal data, with a change log. Referenced from every customer DPA.

## Current Entries (2026-08-25)

| Subprocessor | Purpose | Data categories |
| --- | --- | --- |
| AWS | Hosting, databases, backups | All customer data |
| Pingrove | SMS reminders | Patient phone number, message text, send time |
| Transactional email provider | Email reminders and staff notifications | Patient or staff email, message text |
| Error tracker | Application error reports | Staff user IDs; request metadata with phone numbers scrubbed |

## Change Log

- 2025-05-20: List first published with the DPA template.
- 2026-03-30: Error tracker scrubbing rules tightened after the outage investigation showed request bodies in two events.
- 2026-08-25: Clarified that Meridale's dedicated database runs in the same AWS account and region as the shared database.

## Why It Matters

Meridale's contract, drafted by [[rania-saleh]], requires 30 days' notice before a new subprocessor. Any engineering proposal for a new tool that could see tenant data must check this list first.

## Source Location

Shared drive, `Legal/Customers/subprocessor-list.md`, published to customers as a PDF on request. Owner: Colette, engineering review by Nikolas.
