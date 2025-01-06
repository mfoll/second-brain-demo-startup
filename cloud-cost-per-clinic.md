---
type: Note
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[rds-cost-dashboard]]"
  - "[[engineering-budget-2027]]"
  - "[[technical-diligence-call-2026-08-19]]"
_organized: true
---

# Cloud Cost Per Clinic

How I compute the "$14 a month per clinic" figure quoted on the [[technical-diligence-call-2026-08-19]].

## Method

Total AWS spend for production and staging, excluding the billing account, averaged over 2026-07 to 2026-09 at the post-fold-back run rate, divided by active clinic accounts.

- AWS run rate after fold-back: about $3,900 a month (RDS $2,650, containers $720, Redis $210, the rest storage, transfer and monitoring).
- Active clinics: about 280.
- $3,900 / 280 = about $14 a month per clinic.

## Caveats

- Excludes Pingrove SMS (a per-message cost passed through in pricing) and the tracing backend (free tier).
- Meridale's dedicated database is about $750 of the total; Meridale's 42 clinics carry it in their contract.
- At the June peak the same figure was about $25.

Used in [[engineering-budget-2027]] and [[rds-capacity-plan-2027]].
