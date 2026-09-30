---
type: Source
source_type: Internal spreadsheet
date_accessed: 2026-09-29
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[colette-fairbanks]]"
  - "[[subprocessor-list]]"
  - "[[subprocessor]]"
_organized: true
---

# Vendor Risk Register

[[colette-fairbanks]]'s register of every vendor that touches Quaylane's systems or data, created 2026-05 after the readiness review found no vendor risk process ([[soc2-readiness-review-2026-04-20]]).

## Contents

- 31 vendors, each with: what it does for us, data it can see (none, staff data, customer staff data, patient contact data), risk tier (low, medium, high), its own assurance report (SOC 2, ISO 27001, none), contract owner, review date.
- High tier, 4 vendors: AWS, Pingrove, the transactional email provider, the error tracker. These are also our subprocessors.
- Medium tier, 9 vendors, including GitHub, the CI service and the HR system.

## Review Rule

High-tier vendors reviewed annually: collect their latest assurance report, read the exceptions, note anything that affects us. Pingrove's 2026 review noted its documented rate limit of 50 messages per second per account, which mattered in the March outage; [[bettina-solberg]] confirmed it in writing.

## Why It Matters

Our SOC 2 carves out subprocessors, so their own reports are part of our evidence. Prospects ask for this list in questionnaires.

## Source Location

Shared drive, `Security/Vendors/vendor-risk-register.xlsx`. Owner Colette Fairbanks.
