---
type: Procedure
belongs_to: "[[customer-feedback-loop]]"
related_to:
  - "[[customer-feedback-log]]"
  - "[[imani-brooks]]"
_organized: true
---

# Triage Customer Feedback

Weekly triage of new rows in the [[customer-feedback-log]], run by customer success on Thursdays with an engineer joining for 20 minutes.

## Steps

1. Filter rows with status `new`.
2. For each row, check the summary is one line in our own words and contains no patient detail. Rewrite or remove anything that does.
3. Apply one to three tags from the tag list. Create a new tag only with Imani's approval.
4. Add `segment` from the account record.
5. If it is a bug, open a `QL-` ticket and link it; the row stays for the pattern.
6. If it signals churn risk, tag `churn-risk` and tell the account owner the same day.
7. Set status to `tagged`.

## Engineering's 20 minutes

- Link existing tickets and say whether anything is already in progress.
- Flag requests that look small but are not (anything touching the [[appointment-slot-model]] or reminders).

## Monthly

On the last Tuesday, export accounts and items per tag for the product review. Accounts first, items second, per [[feedback-volume-is-not-priority]].
