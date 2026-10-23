---
type: Source
source_type: Scientific paper
url: https://doi.org/10.1186/s13677-022-00296-4
doi: 10.1186/s13677-022-00296-4
pmid: 35979413
licence: CC BY
date_accessed: 2026-10-15
belongs_to: "[[observability-overhaul]]"
related_to:
  - "[[reliability-and-incidents]]"
  - "[[xing-2025-microservice-anomaly-detection-fault-localization]]"
_organized: true
---

# Anomaly detection in microservice environments using distributed tracing data analysis and NLP

## Summary

Kohyarnejadfard, Aloise, Azhari and Dagenais, Journal of Cloud Computing, 2022. The authors treat sequences of events inside trace spans like text and use NLP methods to flag performance anomalies and release-over-release regressions without prior knowledge of the system. On real datasets they report an F-score of about 0.98 and faster root cause analysis through visualization in Trace Compass.

## Why It Matters

Read while writing the restart plan for the [[observability-overhaul]]. The useful point for us is the premise, not the model: detection and regression hunting depend on having complete traces, which is exactly what we lack in the workers. Nothing here is a project for a team of eight.

## Caveats

Research prototype evaluated on datasets unlike ours; I have not read the full methods section.

## Source Links

- [DOI 10.1186/s13677-022-00296-4](https://doi.org/10.1186/s13677-022-00296-4), PMID 35979413.
