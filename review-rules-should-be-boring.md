---
type: Opinion
status: Active
confidence: Medium
belongs_to: "[[code-review-policy]]"
related_to:
  - "[[code-review-and-delivery]]"
  - "[[should-pair-programmed-commits-count-as-reviewed]]"
_organized: true
---

# Review Rules Should Be Boring

## Stance

A team's code review rule should be simple enough to enforce with a setting and to explain in one sentence. The interesting conversations about review quality should happen outside the rule, not inside its exceptions.

## Scope

Rules that exist for evidence or safety: approvals, branch protection, emergency paths. Not how people review, which should stay a matter of judgment and conversation.

## Why I Think This

- At [[engineering-meeting-2026-04-08]] every exception we considered (risky paths only, pairing counts) moved the argument from "was this reviewed" to "did this count", which is worse.
- The one-approval rule took Kwabena an afternoon in Terraform and has needed no interpretation since.
- Hamish's point about pairing is a good point about quality. Folding it into the rule would have made the rule harder to audit without making the code better.

## What Would Change My Mind

- If the simple rule produced rubber-stamp approvals: approvals in under two minutes on large diffs would be a sign. I check this on the [[pr-review-metrics-dashboard]] each quarter.
- If the break-glass path were used more than about once a month, the rule would be too rigid for how we actually work.

## Implications

Keep [[code-review-policy-document]] to one page. Put advice on good reviews in the engineering handbook, not in the policy.
