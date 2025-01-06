---
type: Concept
belongs_to: "[[engineering-metrics]]"
related_to:
  - "[[devops-research-and-assessment]]"
  - "[[which-engineering-metrics-should-we-show-the-board]]"
_organized: true
---

# DORA Four Keys

The four delivery measures popularized by the DevOps Research and Assessment program ([[devops-research-and-assessment]]): deployment frequency, lead time for changes, change failure rate, and time to restore service.

## How I use them

I log them by hand once a month since 2026-05, from GitHub Actions deploy runs and the incident list. It takes 20 minutes and nobody else sees the sheet. Q3 2026:

- Deployment frequency: about 11 production deploys a week across the four repositories.
- Lead time for changes: median 1.4 days from first commit to production.
- Change failure rate: about 6% of deploys led to a rollback or a fix within 24 hours.
- Time to restore: median 47 minutes over 5 incidents.

## Caveats

- Small numbers: five incidents make a median, not a trend.
- Change failure rate depends on what we call a failure; I count rollbacks and hotfixes, not bugs found a week later.
- These measure the delivery system, never individuals. See [[goodharts-law]].
