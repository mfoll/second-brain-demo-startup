---
type: Source
source_type: Documentation
publisher: GitHub Docs
url: https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases
date_accessed: 2026-10-22
belongs_to: "[[deliver-the-product]]"
related_to:
  - "[[cut-a-release]]"
  - "[[lucia-ferreyra]]"
_organized: true
---

# About Releases

GitHub Docs page on releases.

## Summary

A GitHub release packages a deployable version of software and is based on a Git tag that marks a point in the repository's history. Releases carry release notes, written by hand, generated automatically or produced from a custom template, and may include binary assets. GitHub also provides source archives of the tagged commit.

## Why It Matters

Lucia moved the release train onto GitHub releases in 2026-07 when she took it over. Each train tags `quaylane-api`, `quaylane-web` and `quaylane-workers` and creates a release with generated notes, which then get rewritten for customers. The releases double as a change record for the SOC 2 change management evidence. See [[cut-a-release]].

## Key Details

- Release equals tag plus notes; we do not attach binaries.
- Generated notes list merged pull requests, which we cross-check against recorded approvals.

## Caveats

Release notes generated from pull request titles are only as good as the titles.

## Source Links

- [About releases](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases)
