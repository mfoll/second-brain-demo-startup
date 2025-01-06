---
type: Procedure
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[security-questionnaire-answer-library]]"
  - "[[dana-prescott]]"
  - "[[meridale-security-questionnaire]]"
_organized: true
---

# Answer A Security Questionnaire

How we answer a customer's or prospect's security questionnaire. Agreed with [[dana-prescott]] on 2026-03-09 and revised 2026-09-14 after the Type I report.

## Inputs

- The questionnaire in whatever format the customer sent.
- The [[security-questionnaire-answer-library]] (412 answers, each with a `last_reviewed` date).
- The [[soc2-type-1-report]] (shared only under NDA, watermarked by Colette).
- The [[subprocessor-list]] and [[information-security-policy]].

## Steps

1. Dana logs the questionnaire with its due date and checks whether the prospect will accept the SOC 2 report in place of the audit sections. Many will.
2. Dana fills every question that matches a library answer reviewed in the last six months.
3. Everything else, and any question on tenant isolation, encryption keys, incident history or data retention, goes to engineering. I answer or assign within five business days.
4. New answers go back into the library with today's `last_reviewed` date and the author.
5. Engineering reviews the complete set once before it is sent. Any "Yes" must be true today, not planned.
6. File the returned questionnaire under `Security/Questionnaires/<customer>/<date>`.

## Rules

- Never answer "Yes" for something planned. Write "Planned for <quarter>" and keep the date honest. We learned this from the Meridale answers ([[meridale-questionnaire-draft-answers-2025-10]]).
- Describe tenant isolation as it is now: row-level security in the shared database; a dedicated database for enterprise contracts. Do not reuse 2026-H1 answers about per-tenant databases.
- Never include internal hostnames, account IDs, or security findings beyond severity and fix.
- Pen test results: share the summary letter, not the report.

## Verification

The returned questionnaire and the library change are both filed, and the questionnaire count for the quarter is updated for [[can-we-answer-security-questionnaires-without-engineering-time]].
