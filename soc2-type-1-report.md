---
type: Source
source_type: Audit report
date_accessed: 2026-08-28
belongs_to: "[[soc2-type-1-audit]]"
related_to:
  - "[[meridale-clinic-group]]"
  - "[[soc2-exceptions-remediation-plan]]"
  - "[[patrice-ndour]]"
  - "[[control-exception]]"
_organized: true
---

# SOC 2 Type I Report

Quaylane's first SOC 2 report: a Type I examination by Ashcombe Assurance on the Security, Availability and Confidentiality criteria, as of 2026-07-31, issued on 2026-08-28. It met Meridale's contract condition of a Type I report by 2026-09-30 with a month to spare.

## Summary

Ashcombe's opinion is that the description of the Quaylane system is fairly presented and the controls were suitably designed and implemented as of 2026-07-31, with two exceptions. A Type I says nothing about whether controls operated over time; that is the job of the [[soc2-type-2-observation]] ([[soc2-type-1-vs-type-2]]).

## Why It Matters

- It closed the third Meridale condition. [[samir-haddad]] received it under NDA on 2026-09-02.
- It answered the SOC 2 timeline question from Copperwell's diligence ([[technical-diligence-call-2026-08-19]]).
- [[dana-prescott]] now shares it with enterprise prospects under NDA instead of answering audit sections of questionnaires one by one.
- The two exceptions define what the Type II must prove.

## Key Details

The two exceptions, as summarized in our remediation plan ([[soc2-exceptions-remediation-plan]]):

1. **AC-04 Quarterly access review.** The control was designed and assigned, but no completed review existed as of 2026-07-31; the first one had been scheduled for 2026-07 and slipped behind fieldwork preparation. Remediation: first review completed and evidenced on 2026-10-06 ([[quarterly-access-review-2026-10-06]]).
2. **HR-07 Offboarding.** For one leaver in 2026-06, the laptop was returned but there was no record that it had been wiped. Remediation: MDM remote wipe enforced on all company laptops from 2026-09-08 and a wipe certificate from the recycler for every returned device, filed by [[colette-fairbanks]].

Management's response to each exception is printed in the report, written by me and Colette and reviewed by [[patrice-ndour]] for tone, not content.

Other facts: 58 controls in the [[soc2-control-matrix]]; fieldwork 2026-08-03 to 2026-08-14 ([[soc2-fieldwork-2026-08-03]]); subprocessors carved out (AWS, Pingrove, the email provider), meaning their controls are covered by their own reports, not ours.

## Caveats

The report is confidential and shared only under NDA. Do not quote it in marketing or put it in a public trust page. Exceptions in a Type I are not failures of the whole report, but customers read them, and Samir did.

## Source Location

Final PDF and management letter in the [[soc2-evidence-folder]] under `Reports/2026-Type1/`. Shared copies are watermarked per recipient by Colette. Data room copy for investors in the [[seed-extension-data-room]].
