---
type: Source
source_type: Internal configuration
date_accessed: 2026-04-29
belongs_to: "[[code-review-policy]]"
related_to:
  - "[[github-docs-about-protected-branches]]"
  - "[[kwabena-asare]]"
_organized: true
---

# Branch Protection Settings Export

The branch protection settings for `main` in `quaylane-api`, `quaylane-web`, `quaylane-workers` and `quaylane-infra`, as applied by [[kwabena-asare]] through Terraform on 2026-04-29.

## Key Details

- Require a pull request before merging: on. Required approvals: 1.
- Dismiss stale approvals when new commits are pushed: on.
- Require review from code owners: on in `quaylane-infra` only.
- Require status checks: CI test and lint jobs.
- Do not allow bypassing the above settings: on, with a bypass list holding only the `break-glass` team.
- Force pushes and deletions of `main`: blocked.

## Why It Matters

This is the control as it actually exists, as opposed to the policy text. The behavior of each option is described in [[github-docs-about-protected-branches]] and [[github-docs-about-code-owners]].

## Caveats

Settings drift is possible if someone edits them in the GitHub interface. Terraform plan runs nightly in CI and fails on drift.

## Source Location

`quaylane-infra` repository, `github/branch_protection.tf`, plus a JSON export in the SOC 2 evidence folder dated 2026-04-29.
