---
type: Source
source_type: Documentation
publisher: GitHub
url: https://docs.github.com/en/organizations/keeping-your-organization-secure/managing-security-settings-for-your-organization/reviewing-the-audit-log-for-your-organization
date_accessed: 2026-10-23
belongs_to: "[[soc2-type-2-observation]]"
related_to:
  - "[[soc2-control-matrix]]"
  - "[[code-review-policy]]"
_organized: true
---

# Reviewing The Audit Log For Your Organization

GitHub Docs page on the organization audit log.

## Summary

- The audit log records actions by organization members: actor, action, affected user or repository, country of origin, time.
- Only organization owners can view it.
- Events from the last 180 days are available; the default view shows three months, and older events need a `created` date filter.
- Filtering uses qualifiers such as `action`, `actor`, `repo`, `created`; there is no free-text search.
- Results export as JSON or CSV, within size and time limits.

## Why It Matters

Control CM-01 in the [[soc2-control-matrix]] relies on GitHub records, and branch protection setting changes show up here. The 180-day limit is shorter than the Type II window plus sampling (2026-09-01 to about 2027-03), so [[kwabena-asare]] exports the log monthly to the [[soc2-evidence-folder]]. Without that, Ashcombe could ask in March for September events we can no longer show.

## Source Links

- [Reviewing the audit log for your organization](https://docs.github.com/en/organizations/keeping-your-organization-secure/managing-security-settings-for-your-organization/reviewing-the-audit-log-for-your-organization)
