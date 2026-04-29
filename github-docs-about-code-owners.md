---
type: Source
source_type: Documentation
url: https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners
publisher: GitHub
date_accessed: 2026-04-13
belongs_to: "[[code-review-policy]]"
related_to:
  - "[[branch-protection-settings-export]]"
_organized: true
---

# About code owners

GitHub Docs page on CODEOWNERS files.

## Summary

A CODEOWNERS file names the people or teams responsible for paths in a repository. It lives in `.github/`, the root or `docs/`, and GitHub uses the first one it finds in that order. Each line pairs a gitignore-style pattern with owners, and the last matching pattern takes precedence. With "Require review from Code Owners" enabled in branch protection, approval from any one listed owner satisfies the requirement.

## Why It Matters

We require code owner review only in `quaylane-infra`, with Kwabena and Teodora as owners (and Bram since 2026-08). The "any one owner" behavior was the reason we accepted it: requiring all owners would have blocked infrastructure changes whenever one of two people was away. A candidate place to hand off migration reviews ([[what-should-i-stop-doing-as-head-of-engineering]]).

## Source Links

- [About code owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners)
