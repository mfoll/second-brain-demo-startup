---
type: Question
status: Answered
belongs_to: "[[code-review-policy]]"
related_to:
  - "[[hamish-pettigrew]]"
  - "[[pair-programming]]"
  - "[[engineering-meeting-2026-04-08]]"
_organized: true
---

# Should Pair-Programmed Commits Count As Reviewed?

Raised by [[hamish-pettigrew|Hamish Pettigrew]] when we wrote the [[code-review-policy]]: if two engineers wrote a change together, does it still need a third engineer's recorded approval?

## Current Answer

> [!info]
> No, as working policy since [[engineering-meeting-2026-04-08]]. A pull request needs one recorded approval from someone other than its author, and a co-author trailer does not count. The reason is evidence, not quality: [[patrice-ndour|Patrice Ndour]] of Ashcombe Assurance accepts only an approval recorded in GitHub as proof of review for SOC 2 change management.

## Why it is still worth keeping findable

Hamish disagrees and asked for that to be on record. His argument is about quality, and I think it is largely right: two people at one keyboard catch more than a third person skimming a diff, and the research on review I have read ([[code-review]], [[di-biase-2019-effects-of-change-decomposition-on-code-review]]) suggests reviewers of large diffs miss a lot. In practice he and Min-jae open their paired pull requests with each other as co-author and ask a third engineer for approval, usually a fast one.

## What would reopen it

- GitHub recording a co-authored review natively in a way the auditor accepts.
- An auditor or a later SOC 2 examination accepting pairing session logs tied to commits.
- Evidence from the Type II window that the third approval is pure ceremony on paired work. I have not seen that yet; two paired pull requests in Q3 got real comments from the third reviewer.

## Related

- [[review-rules-should-be-boring]]
- [[pair-programming]]
