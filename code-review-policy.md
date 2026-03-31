---
type: Project
status: Completed
start: 2026-03-23
end: 2026-04-30
belongs_to: "[[lead-engineering-team]]"
related_to:
  - "[[code-review-and-delivery]]"
  - "[[soc2-type-1-audit]]"
  - "[[hamish-pettigrew]]"
has:
  - "[[engineering-meeting-2026-04-08]]"
  - "[[ship-an-emergency-change]]"
  - "[[code-review-policy-document]]"
  - "[[break-glass-change-log]]"
_organized: true
---

# Code Review Policy

A written code review rule for every production repository, enforced by GitHub branch protection, with a break-glass path for emergencies. It exists because SOC 2 change management needs evidence that each production change was reviewed, and because before April 2026 review at Quaylane was a habit, not a rule.

## Outcome

A written code review policy enforced by branch protection on all production repositories (`quaylane-api`, `quaylane-web`, `quaylane-workers`, `quaylane-infra`), with a break-glass path for emergencies. Reached on 2026-04-30.

## Current State

- The rule: one recorded approval on every pull request to `main`, from someone other than the author; stale approvals are dismissed when new commits change the diff. Code owner review is required only in `quaylane-infra`.
- Break-glass: an emergency change may merge without approval if a second engineer reviews it within one business day and it is logged in the [[break-glass-change-log]]. Used 5 times between 2026-04-30 and 2026-10-23, all reviewed in time.
- [[hamish-pettigrew|Hamish Pettigrew]] still disagrees that pair-programmed commits need a separate approval. He records his pair as co-author anyway. The question is recorded as answered for now in [[should-pair-programmed-commits-count-as-reviewed]].
- The policy is now operated through [[ship-an-emergency-change]] and the SOC 2 Type II observation window ([[soc2-type-2-observation]]).

## Scope and Boundaries

In scope: the rule, its enforcement in GitHub, the emergency path, the change log. Out of scope: who reviews what (left to the team), review quality standards, and the auditor's evidence sampling, which belongs to [[soc2-type-1-audit]] and its successor.

## Working Context

The trigger was the change management row of the [[soc2-control-matrix]]. In March 2026, 23 of 140 merged pull requests in `quaylane-api` had no recorded approval, mostly small fixes and pair-programmed work. [[patrice-ndour|Patrice Ndour]] of Ashcombe Assurance told us that only a recorded approval in the tool counts as evidence; a commit trailer or a calendar entry for a pairing session does not.

Options considered at [[engineering-meeting-2026-04-08]]:

- Two approvals per pull request: rejected as too slow for a team of seven.
- Review after merge within a day for everything: rejected because the auditor would treat it as an exception path, not the control.
- Approval only for risky paths (migrations, auth, infra): rejected because the boundary would be argued about every week and is hard to evidence.
- Pairing counts as review (Hamish's proposal): rejected on Patrice's evidence position. Recorded as dissent, not overruled silently.
- One recorded approval plus a break-glass path: adopted.

Branch protection settings as applied are kept in [[branch-protection-settings-export]]. The GitHub behavior we rely on is documented in [[github-docs-about-protected-branches]] and [[github-docs-approving-a-pull-request-with-required-reviews]].

## Active Workflows

- [[ship-an-emergency-change]] for any merge that bypasses review.
- Monthly check of the change log against bypass merges, automated since 2026-08 by [[olu-ajayi|Olu Ajayi]]'s internship project ([[intern-project-brief-2026]]).

## Next Actions

- [ ] Review the five break-glass uses with Kwabena at the end of the Type II window to see if any pattern needs a tooling fix.
- [ ] Revisit pairing evidence with Patrice if GitHub ever records co-authored review natively.

## Open Questions

- [[should-pair-programmed-commits-count-as-reviewed]]
- [[should-engineers-use-ai-assistants-on-production-code]], since agent-written pull requests add a new reviewer question.

## Important Notes

- [[engineering-meeting-2026-04-08]]
- [[code-review-policy-document]]
- [[break-glass-change]]
- [[review-rules-should-be-boring]]

## Maintenance Log

- 2026-04-30: Branch protection enforced on all four repositories; project closed.
- 2026-04-08: Rule and break-glass path decided; Hamish's dissent recorded.
- 2026-03-23: Started after the change management gap showed up in the control matrix.
