---
type: Procedure
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[soc2-control-matrix]]"
  - "[[access-review-log]]"
  - "[[principle-of-least-privilege]]"
_organized: true
---

# Run The Quarterly Access Review

How to run control AC-04 from the [[soc2-control-matrix]]: every quarter, confirm who has access to each production-relevant system and remove anything not needed. Written 2026-09-02 as the fix for Type I exception 1; first run on 2026-10-06 ([[quarterly-access-review-2026-10-06]]).

## When

First Tuesday of January, April, July and October. Invites are in the engineering calendar through 2027. If the date cannot hold, move it within the same month and note why in the log; never skip a quarter.

## Who

- Facilitator: Nikolas (backup: [[kwabena-asare]]).
- System reviewers: Kwabena for AWS, RDS roles and the queue console; [[teodora-vasilescu]] for database roles if Kwabena is away; Nikolas for GitHub and the error tracker; [[imani-brooks]] for the support desk and the Pingrove dashboard; [[colette-fairbanks]] for the HR system and shared drive security folders.

## Inputs

- Current staff and contractor list from the HR system, exported by Colette the day before.
- User and role exports from each system (list in the [[access-review-log]] template).

## Steps

1. Open a new tab in the [[access-review-log]] named for the quarter.
2. For each system, paste the export, then mark each grant Keep, Reduce or Remove, with a one-line reason for any admin grant.
3. Cross-check every account against the HR list. Any account for someone who has left is a Remove and a finding.
4. Check service accounts: owner, last use, scope. Unused for 90 days means Remove.
5. Open a ticket for each Remove or Reduce; make the change the same day where possible.
6. Each reviewer signs their system's sheet (name and date in the cell is enough).
7. Save exports and the signed sheet to the [[soc2-evidence-folder]] under `AccessReviews/<YYYY-Qn>/`.
8. Send a three-line summary to the team and, for enterprise customers who asked, to their security contact.

## Verification

Within five business days: every ticket closed, the evidence folder complete, the [[type-2-observation-tracker]] row marked done with the date.

## Guardrails

Do not create a review dated in the past. If a quarter is missed, record it as missed; an auditor will find it anyway.
