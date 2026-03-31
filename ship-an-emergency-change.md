---
type: Procedure
belongs_to: "[[code-review-policy]]"
related_to:
  - "[[break-glass-change]]"
  - "[[run-an-incident]]"
  - "[[soc2-control-matrix]]"
_organized: true
---

# Ship An Emergency Change

The break-glass path: how to merge a change to `main` without the required approval when waiting would hurt customers, and how to make it reviewable evidence afterwards. Decided at [[engineering-meeting-2026-04-08]].

## When to use it

> [!warning]
> Use break-glass only when an approved change cannot be had in time and customers are affected now: an active incident, a security fix under exploitation, or a contractual deadline that would otherwise be missed that day. Convenience, a slow reviewer or a Friday afternoon are not reasons.

If any engineer can approve within about 15 minutes, ask them instead. Approval on a phone is fine.

## Who may use it

- Any engineer may ask for a break-glass merge. The on-call primary normally does.
- Only members of the `break-glass` GitHub team can perform it: Nikolas, [[kwabena-asare]], [[teodora-vasilescu]], [[lucia-ferreyra]]. Membership is reviewed in the quarterly access review.
- If the change is part of an incident, the incident commander agrees first ([[run-an-incident]]).

## Steps

1. Open the pull request as usual, with the `break-glass` label and a one-line reason in the description. Link the incident or ticket (`QL-` number).
2. Let CI finish. Do not skip tests unless the incident commander says so, and note it if they do.
3. A break-glass team member merges using the bypass. They must not be the author.
4. Add a row to the [[break-glass-change-log]] within one hour: date, pull request, ticket, reason, who merged, who will review.
5. Post in `#eng-changes` with the pull request link and name the reviewer.
6. The reviewer reviews the merged pull request within one business day and leaves an approving review on it (GitHub allows a review on a merged pull request). Any follow-up fix goes through the normal rule.
7. The reviewer marks the change log row as reviewed with the date.

## Verification

- Since 2026-08 a GitHub Action from [[olu-ajayi|Olu Ajayi]]'s internship ([[intern-project-brief-2026]]) detects merges without an approval and opens a `QL-` ticket if no change log row appears within two hours.
- [[colette-fairbanks]] checks the log against the bypass audit log monthly for the SOC 2 Type II window.

## Record so far

Five uses between 2026-04-30 and 2026-10-23, all reviewed within one business day:

| Date | Ticket | Reason |
| --- | --- | --- |
| 2026-05-12 | QL-1497 | Pingrove changed its webhook signature format; delivery receipts were rejected |
| 2026-06-29 | QL-1579 | SAML clock skew tolerance, the day before SSO launch for Meridale |
| 2026-07-23 | QL-1691 | A new row-level security policy blocked the waitlist job |
| 2026-08-21 | QL-1697 | Configuration for the Meridale dedicated database cutover |
| 2026-10-02 | QL-1702 | Reminder template encoding broke accented names in SMS |

QL-1697 was reviewed 26 hours after merge, inside the business-day limit because it merged on a Friday evening.
