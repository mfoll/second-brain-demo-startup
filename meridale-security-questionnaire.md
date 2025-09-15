---
type: Source
source_type: Internal document
date_accessed: 2025-09-15
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[meridale-clinic-group]]"
  - "[[samir-haddad]]"
  - "[[architecture-review-2025-11-18]]"
  - "[[soc2-type-1-audit]]"
_organized: true
---

# Meridale Security Questionnaire

The vendor security questionnaire Meridale Clinic Group sent us on 2025-09-15, during the pilot, before they would sign for 42 clinics. 186 questions in 14 sections, sent by [[samir-haddad]], their IT and security manager. Our answers went back on 2025-10-10. This is the document that started Quaylane's security program.

## Summary

Most of the 186 questions we could answer honestly with "yes" and a sentence. Two clusters we could not, and both changed the company:

- **Tenant isolation (section 6, questions 61 to 74).** How is one customer's data separated from another's; is isolation enforced in the database or only in application code; can a customer have dedicated storage with its own encryption key. In 2025 our honest answer was: one shared PostgreSQL schema, a `tenant_id` column on every tenant-scoped table, and filtering in the API's data access layer. Nothing in the database itself stopped a query without the filter. This cluster led to the [[architecture-review-2025-11-18]] and the [[tenant-isolation-migration]].
- **Audit and assurance (section 11, questions 140 to 158).** Do you hold a SOC 2 or ISO 27001 report; is every production change reviewed and logged; how often are user access rights reviewed; what happens to company devices when someone leaves. We had none of the paperwork and only part of the practice. This cluster led to the [[soc2-type-1-audit]], the [[code-review-policy]] and the access review.

## Why It Matters

Meridale became our largest customer on 2026-01-12, and their contract turned three of these answers into conditions: SSO by 2026-07-01, a dedicated database, and a SOC 2 Type I report by 2026-09-30 ([[meridale-clinic-group]]). Every enterprise questionnaire since has asked a subset of the same questions, which is why the answers became the seed of our answer library ([[security-questionnaire-answer-library]], [[answer-a-security-questionnaire]]).

## Key Details

- Format: spreadsheet, one row per question, columns for answer (Yes / No / Partial / N/A), explanation and evidence reference.
- Our first-pass result: 141 Yes, 23 Partial, 17 No, 5 N/A. I wrote 120 answers; [[teodora-vasilescu]] and [[kwabena-asare]] wrote the database and infrastructure sections; [[dana-prescott]] handled commercial ones after I checked them.
- The 17 No answers included: no third-party assurance report, no recorded review on every change, no documented access review, no SSO, no customer-specific encryption keys, no formal vendor risk process.
- Follow-up call with Samir on 2025-10-02 ([[meridale-security-review-call-2025-10-02]]), 40 minutes of which went to tenant isolation.
- Questions on encryption at rest were answered Yes: RDS storage encryption was on from the start ([[amazon-rds-encryption-at-rest]]).

## Caveats

The answers were honest but optimistic on timelines: we wrote "planned for 2026-Q2" for SOC 2, and the Type I report arrived on 2026-08-28. The first draft of answers ([[meridale-questionnaire-draft-answers-2025-10]]) is archived; it overstated isolation in two answers before Teodora corrected them.

## Source Location

Shared drive, `Security/Questionnaires/Meridale/2025-09`, the received spreadsheet and our returned version. Access limited to engineering leads, Dana and Renata.
