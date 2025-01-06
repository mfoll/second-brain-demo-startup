---
type: Question
status: Open
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[abigail-ferris]]"
  - "[[privacy-counsel-memo-reminder-logs]]"
  - "[[security-and-privacy]]"
_organized: true
---

# How Long Should We Retain Reminder Message Logs?

Every SMS and email reminder produces a delivery log row: tenant, recipient phone number or email, send time, status from Pingrove. We keep them indefinitely today. That is a data category (patient contact details plus the fact of an appointment) we should not keep longer than needed.

## Why It Is Open

- Clinics use delivery logs to answer "did the patient get a reminder?" disputes, usually within a few weeks.
- The March outage investigation used 30 days of logs ([[reminder-outage-2026-03-17]]).
- The data protection law requires us to keep personal data no longer than necessary; our DPA lets the clinic set retention, but no clinic has.
- [[abigail-ferris]] gave a first view in [[privacy-counsel-memo-reminder-logs]]: pick a default, document the reason, let enterprise customers change it.

## Options

1. 90 days, then delete recipient fields and keep counts. Engineering preference.
2. 13 months, to cover a yearly audit cycle. Customer success preference.
3. Customer-configurable with 90 days as default. Most work.

Next step: decide with Imani Brooks and Abigail by 2026-11-30, then a retention job in `quaylane-workers`.
