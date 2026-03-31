---
type: Concept
belongs_to: "[[on-call-rotation-redesign]]"
related_to:
  - "[[how-many-pages-a-week-is-too-many]]"
  - "[[reliability-and-incidents]]"
_organized: true
---

# Alert Fatigue

What happens when people are paged so often, or so often for nothing, that they start treating pages as noise: slower acknowledgement, muted channels, and real problems lost among false ones.

## How we saw it

In a February 2026 test we paged on every error-level alert: 31 pages in one week, of which 4 needed action. By Thursday the person carrying the pager was acknowledging without looking. That test shaped the rule in the [[on-call-handbook]] that only four customer-facing alerts page.

## Our countermeasures

- Page only on customer-facing symptoms; send causes to `#alerts`.
- The person on call fixes or demotes a noisy alert during their week.
- Quarterly paging review ([[paging-report-2026-q3]]).

## Limits

Fewer pages do not mean fewer problems. The reminder queue age alert exists because the [[reminder-outage-2026-03-17]] was a symptom nobody was alerted on.
