---
type: Event
date: 2026-04-08
belongs_to: "[[code-review-policy]]"
related_to:
  - "[[hamish-pettigrew]]"
  - "[[patrice-ndour]]"
  - "[[code-review-and-delivery]]"
  - "[[soc2-control-matrix]]"
_organized: true
---

# Engineering Meeting 2026-04-08

The Wednesday engineering meeting where we adopted one recorded approval per pull request and the break-glass path, and where Hamish Pettigrew's dissent on pairing was recorded.

## At a Glance

> [!note]
> Decision: every pull request to `main` in the four production repositories needs one recorded approval from someone other than the author, enforced by GitHub branch protection from 2026-04-30. An emergency change may merge without approval if a second engineer reviews it within one business day and it is logged in the change log. Pair-programmed commits do not count as reviewed. Hamish disagrees and asked that his position be recorded.

## Attendees

[[teodora-vasilescu]], [[kwabena-asare]], [[lucia-ferreyra]], [[min-jae-oh]], [[hamish-pettigrew]], [[ayesha-qureshi]] (third week), [[colette-fairbanks]] for the SOC 2 part, and me. [[patrice-ndour|Patrice Ndour]] of Ashcombe Assurance joined by video for the first 20 minutes. 75 minutes in total.

## Context

The [[soc2-control-matrix]] has a change management control that needs evidence that each production change was reviewed before deployment. A sample I pulled for March 2026 found 23 of 140 merged pull requests in `quaylane-api` with no recorded approval. Most were one-line fixes, dependency bumps or pair-programmed work. The outage three weeks earlier ([[reminder-outage-2026-03-17]]) had involved several hurried fixes under pressure, which made the room more receptive than I expected.

## Discussion

Options on the table, as I wrote them on the board:

1. Two approvals per pull request. Nobody supported it; at seven engineers it would add a day to most changes.
2. Approval only on risky paths (migrations, auth, `quaylane-infra`). Lucia liked it. Kwabena pointed out we would argue about what is risky every week, and Patrice said the auditor would sample across all changes, not only the risky ones.
3. Review after merge for everything within one business day. Patrice said this would be read as an exception process rather than the control itself.
4. One recorded approval before merge, plus an emergency path. Adopted.

**Hamish's position.** Hamish pairs most of his work, often with Min-jae. He argued that a commit written by two engineers at one keyboard has had more review than a pull request skimmed by a third person, and proposed that commits with a `Co-authored-by` trailer satisfy the rule. Min-jae agreed on the substance. Teodora said she would rather have a third pair of eyes on migrations regardless.

**Patrice's position.** Only a recorded approval in the tool counts as evidence. A trailer is written by the author and proves nothing to an auditor; a calendar entry for a pairing session cannot be tied to a specific change. Patrice was clear this is about evidence, not about whether pairing is good practice.

I decided for option 4 without the pairing exception. I said in the meeting that I think Hamish's argument about quality is right and that the rule is about evidence; we cannot get the SOC 2 report for Meridale on a control the auditor will not accept. Hamish asked for his dissent to be recorded. It is, here and in [[should-pair-programmed-commits-count-as-reviewed]].

## Decisions

- One recorded approval on every pull request to `main` in `quaylane-api`, `quaylane-web`, `quaylane-workers` and `quaylane-infra`; author cannot approve; stale approvals dismissed on new commits.
- Code owner review required only in `quaylane-infra` (Kwabena and Teodora as owners).
- Administrators do not bypass by default. A small break-glass team (me, Kwabena, Teodora, Lucia) can merge without approval in an emergency.
- Break-glass changes get a second engineer's review within one business day and a row in the [[break-glass-change-log]].
- Enforcement date 2026-04-30, after Kwabena updates branch protection with Terraform.

## Actions

- [x] Kwabena: branch protection in all four repositories via Terraform (done 2026-04-29, [[branch-protection-settings-export]]).
- [x] Me: write the policy ([[code-review-policy-document]]) and the Procedure ([[ship-an-emergency-change]]).
- [x] Colette: add the change log to the SOC 2 evidence folder.
- [x] Hamish and Min-jae: keep pairing; open the pull request with the pair as co-author and ask a third engineer to approve.

## Follow-up

Break-glass was used 5 times between 2026-04-30 and 2026-10-23. Hamish still disagrees and still records his pair as co-author, which I think is a good habit regardless. My stance on rules like this is in [[review-rules-should-be-boring]].
