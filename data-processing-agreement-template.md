---
type: Source
source_type: Contract summary
date_accessed: 2025-05-20
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[abigail-ferris]]"
  - "[[subprocessor-list]]"
  - "[[subprocessor]]"
_organized: true
---

# Data Processing Agreement Template

Our standard data processing agreement for clinic customers, drafted by [[abigail-ferris]] and adopted 2025-05-20.

## Engineering-Relevant Terms

- Quaylane processes clinic data only on the clinic's instructions: scheduling, reminders, waitlist.
- Data categories: patient name, phone number, email, appointment times and locations; clinic staff accounts.
- Subprocessors listed in the [[subprocessor-list]], 30 days' notice of changes.
- Security measures annex: encryption at rest and in transit, access control, logging, backups. Updated 2026-09 to reference the SOC 2 report.
- Breach notification "without undue delay"; enterprise contracts may set a fixed time.
- Return and deletion of data within 30 days of contract end. The deletion job for churned tenants was built in 2025-09 to meet this.

## Source Location

Shared drive, `Legal/Templates/dpa-template-v2.docx`. Signed DPAs per customer in `Legal/Customers/`.
