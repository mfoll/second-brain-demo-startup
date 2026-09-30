---
type: Source
source_type: Internal spreadsheet
date_accessed: 2026-09-14
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[answer-a-security-questionnaire]]"
  - "[[can-we-answer-security-questionnaires-without-engineering-time]]"
  - "[[dana-prescott]]"
_organized: true
---

# Security Questionnaire Answer Library

The reusable bank of answers to security questions, grown from the [[meridale-security-questionnaire]] answers in 2025-10 to 412 answers on 2026-09-14.

## Structure

`question_pattern`, `category` (14 categories mirroring the Meridale sections), `answer`, `evidence` (e.g. "SOC 2 control CM-01"), `author`, `last_reviewed`, `superseded_by`.

## Maintenance

- `last_reviewed` added on 2026-09-14. Answers older than six months go back to engineering before reuse.
- After the tenant isolation reversal, 17 answers about tenancy were rewritten on 2026-06-19 and the per-tenant versions marked superseded.
- After the Type I report, 23 audit answers were replaced by "see SOC 2 Type I report, available under NDA".

## Why It Matters

It cut engineering time per questionnaire from about 30 hours to about 4. It is also the clearest record of how our security story changed over 2026.

## Source Location

Shared drive, `Security/Questionnaires/answer-library.xlsx`. Edit: Nikolas and Dana; engineering leads comment.
