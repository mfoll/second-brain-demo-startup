---
type: Source
source_type: Scientific paper
url: https://doi.org/10.3390/s25113396
doi: 10.3390/s25113396
pmid: 40968945
licence: CC BY
date_accessed: 2026-10-15
belongs_to: "[[observability-overhaul]]"
related_to:
  - "[[kohyarnejadfard-2022-anomaly-detection-microservice-tracing]]"
  - "[[small-teams-should-buy-observability]]"
_organized: true
---

# Multi-Dimensional Anomaly Detection and Fault Localization in Microservice Architectures: A Dual-Channel Deep Learning Approach with Causal Inference for Intelligent Sensing

## Summary

Xing, Wang and Liu, Sensors, 2025. Proposes a deep learning framework combining temporal convolutional networks and variational autoencoders, with causal inference to trace fault propagation across services. The authors report about 95% detection accuracy and a 43% reduction in average troubleshooting time against the methods they compared.

## Why It Matters

Mostly a reminder of scale: this is data-center tooling. For Quaylane's API and workers, the cheaper win is the one in [[small-teams-should-buy-observability]]: complete traces and a few good alerts. Filed so I stop re-reading papers like it.

## Caveats

Evaluation on benchmark data; claims not checked against anything we run.

## Source Links

- [DOI 10.3390/s25113396](https://doi.org/10.3390/s25113396), PMID 40968945.
