---
type: Concept
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[soc2-type-1-report]]"
  - "[[soc2-exceptions-remediation-plan]]"
_organized: true
---

# Control Exception

In a SOC 2 report, an exception is a case where the auditor found a control not designed, not implemented, or (in a Type II) not operating as described. It is printed in the report with management's response.

## What It Is Not

An exception is not a failed audit. The report still carries an opinion; the reader decides how much the exception matters. A qualified opinion is the serious outcome, when exceptions are bad enough that the criteria are not met.

## Our Two

From the [[soc2-type-1-report]]: no completed quarterly access review as of the as-of date (AC-04), and one leaver's laptop returned without a wipe record (HR-07). Neither involved customer data leaving our control. Both were recurring or per-event controls, which is the pattern I now watch for: a control that runs once a quarter or once per leaver is easy to design and easy to forget.

## How We Handle One

1. Accept the finding as stated; do not argue wording.
2. Write management's response with a dated fix.
3. Tell affected customers before they ask ([[samir-haddad]] got the plan two days after the report).
4. Test the fix inside the next observation window ([[soc2-exceptions-remediation-plan]]).
