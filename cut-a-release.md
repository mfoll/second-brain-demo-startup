---
type: Procedure
belongs_to: "[[deliver-the-product]]"
related_to:
  - "[[lucia-ferreyra]]"
  - "[[github-docs-about-releases]]"
  - "[[feature-flag-inventory-v3]]"
_organized: true
---

# Cut A Release

The biweekly release train for `quaylane-api`, `quaylane-web` and `quaylane-workers`. Owned by Lucia Ferreyra since 2026-07-06. Releases go out every second Tuesday; anything merged to `main` by Monday 12:00 is on the train.

## Inputs

- `main` green on CI in all three repositories.
- Every pull request merged since the last release has a recorded approval or a logged break-glass entry (see [[ship-an-emergency-change]]). This is SOC 2 change management evidence.
- The flag list in [[feature-flag-inventory-v3]] or its successor.

## Steps

1. **Monday 12:00, freeze.** Lucia posts the freeze in the engineering channel. Later merges wait for the next train unless they are fixes for the train itself.
2. **Monday afternoon, staging.** Deploy the `main` heads to staging with the Terraform-managed pipeline. Run the smoke suite and the scheduling regression set (about 400 tests on booking, overlap and time zones).
3. **Monday, release notes.** Generate a draft from merged pull requests, as GitHub's release feature allows ([[github-docs-about-releases]]), then rewrite the customer-facing part in plain words with Imani's team.
4. **Tuesday 07:30, tag and deploy.** Tag each repository `vX.Y.Z`, create the GitHub release, deploy workers first, then the API, then the web app.
5. **Tuesday 07:30 to 09:30, watch.** Reminder queue age, error rate, p95 latency of the day view. Roll back on any customer-facing alert.
6. **Tuesday, flags.** Flip any scheduled flags in batches, 30 minutes apart.
7. **Tuesday, close.** Post the summary in the channel, update the change log, and check flags past their removal date.

## Guardrails

- No train during an open incident. The incident commander decides when the train resumes.
- No database migration that touches more than one million rows on a train day. Those run as throttled jobs, a rule from the [[postmortem-review-2026-03-24]].
- Hotfixes between trains follow the same steps 2, 4 and 5 with a patch version.

## Verification

A release is done when the GitHub release exists in all three repositories, the change log has an entry, and customer success has the notes.
