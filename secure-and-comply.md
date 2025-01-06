---
type: Responsibility
status: Active
related_to:
  - "[[security-and-privacy]]"
  - "[[colette-fairbanks]]"
has:
  - "[[soc2-type-2-observation]]"
  - "[[soc2-control-matrix]]"
  - "[[answer-a-security-questionnaire]]"
_organized: true
---

# Secure And Comply

The security program of Quaylane as I carry it as head of engineering: the SOC 2 examinations, customer security questionnaires, vendor risk and the privacy questions that come with storing clinics' patient contact data. It has no end date because every new enterprise contract, auditor cycle and vendor brings it back.

## Scope

- SOC 2: the [[soc2-type-1-audit]] (done), the [[soc2-type-2-observation]] (running) and whatever follows in 2027.
- Customer security questionnaires, starting with the [[meridale-security-questionnaire]], and the answer library behind [[answer-a-security-questionnaire]].
- Vendor risk and subprocessors ([[vendor-risk-register]], [[subprocessor-list]]).
- Privacy questions with [[abigail-ferris]], our external counsel, phrased against "the data protection law" and our customer contracts.
- Not here: tenant isolation architecture lives under [[run-the-platform]]; the code review rule lives under [[lead-engineering-team]] even though SOC 2 is the reason it exists.

## Current State

- SOC 2 Type I report issued 2026-08-28 by Ashcombe Assurance with two exceptions ([[soc2-type-1-report]]). Meridale's 2026-09-30 deadline met.
- Type II observation window runs 2026-09-01 to 2027-02-28. The goal is to repeat neither exception.
- First quarterly access review was completed and evidenced on 2026-10-06 ([[quarterly-access-review-2026-10-06]]). The laptop wipe gap is closed by MDM remote wipe plus a recycler certificate ([[soc2-exceptions-remediation-plan]]).
- [[colette-fairbanks]] owns HR and vendor controls; I own engineering, change management and access. [[patrice-ndour]] is our audit lead at Ashcombe.
- Questionnaire volume is growing: 9 received in 2026 so far, against 3 in 2025.

## Active Projects and Workflows

- [[soc2-type-2-observation]]
- [[run-the-quarterly-access-review]], next due 2027-01-05
- [[answer-a-security-questionnaire]]
- Security line in [[engineering-budget-2027]]

## Next Actions

- [ ] Keep every Type II sample clean through 2027-02-28; check the evidence folder monthly with Colette.
- [ ] Decide whether to budget a compliance automation tool for 2027 ([[should-we-buy-a-compliance-automation-platform]]).
- [ ] Get a written retention position for reminder message logs from Abigail ([[how-long-should-we-retain-reminder-message-logs]]).
- [ ] Commission the 2027 penetration test before the Type II report period closes.

## Maintenance Log

- 2026-10-06: First quarterly access review evidenced; exception 1 remediated.
- 2026-08-28: Type I report issued with two exceptions.
- 2026-02-02: SOC 2 Type I project started with Ashcombe Assurance.
- 2025-09-15: Meridale's 186-question security questionnaire received; this area became real work.
