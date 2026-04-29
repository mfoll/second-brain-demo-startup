---
type: Source
source_type: Documentation
url: https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches
publisher: GitHub
date_accessed: 2026-04-13
belongs_to: "[[code-review-policy]]"
related_to:
  - "[[branch-protection-settings-export]]"
  - "[[code-review-and-delivery]]"
_organized: true
---

# About protected branches

GitHub Docs page on branch protection rules.

## Summary

Branch protection rules control who can push to important branches and which conditions must be met first. For pull request reviews, a rule can require a set number of approvals from people with write access or from code owners; optionally dismiss approvals when new commits change the diff; require code owner review; and require that someone other than the last pusher approves the latest push. By default, repository administrators and roles with the bypass permission are not bound by these restrictions unless "Do not allow bypassing the above settings" is enabled.

## Why It Matters

The reference [[kwabena-asare]] used to set up the [[code-review-policy]] in Terraform. The default administrator bypass was the detail that mattered: without turning it off, the rule would have had an unlogged exception path, and the break-glass team would have been every admin.

## Source Links

- [About protected branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)
