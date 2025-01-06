---
type: Concept
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[subprocessor-list]]"
  - "[[data-processing-agreement-template]]"
_organized: true
---

# Subprocessor

A third party that processes personal data on our behalf while we process it for our customers. The clinics are the controllers of their patients' contact data; Quaylane is their processor; anyone we pass that data to is a subprocessor.

## Ours

AWS (hosting and database), Pingrove (SMS reminders), our transactional email provider (email reminders), and the error tracker (which may capture request data, so we scrub phone numbers before events leave the API). The list and its change log are in [[subprocessor-list]].

## Why It Matters

- Our [[data-processing-agreement-template]] promises customers 30 days' notice before adding a subprocessor. Meridale's contract repeats this.
- SOC 2 reports carve out subprocessors: their controls are covered by their own reports, which [[colette-fairbanks]] collects in the [[vendor-risk-register]].
- Engineering trap: adding a new SaaS tool that sees customer data is a contractual event, not just a technical choice. The rule since 2026-05: any new tool that could see tenant data goes through Colette before the first API key is created.
