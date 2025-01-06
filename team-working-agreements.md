---
type: Note
belongs_to: "[[lead-engineering-team]]"
related_to:
  - "[[written-async-updates]]"
  - "[[write-before-you-meet]]"
_organized: true
---

# Team Working Agreements

The engineering team's working agreements, last revised at the 2026-07 retro after Bram joined. Kept short on purpose; anyone may propose a change at a retro.

## Communication

- Written updates in `#eng-updates` by 10:30 ([[written-async-updates]]).
- Live sync Tuesday and Thursday at 14:00, 30 minutes. Thursday opens with "anything stuck for more than a day".
- Decisions start from a written proposal shared at least a day before ([[write-before-you-meet]]).
- Core overlap hours 11:00 to 15:00; outside them, nobody is expected to answer quickly unless on call.

## Code

- One recorded approval on every pull request to `main` ([[code-review-policy]]).
- Pull requests under about 400 changed lines where possible; split refactors from behavior changes.
- Pairing is encouraged; the pair goes in as co-author and a third engineer approves.

## On call

- Follow the [[on-call-handbook]]. Swaps are your business; update PagerDuty.

## Retros

- Every six weeks, run by a rotating facilitator. Actions get an owner and a date or they are not actions.
