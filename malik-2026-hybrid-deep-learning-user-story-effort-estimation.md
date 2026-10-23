---
type: Source
source_type: Scientific paper
url: https://doi.org/10.1371/journal.pone.0353348
doi: 10.1371/journal.pone.0353348
pmid: "42467725"
licence: CC BY
date_accessed: 2026-10-22
belongs_to: "[[deliver-the-product]]"
related_to:
  - "[[booking-widget-estimate]]"
  - "[[lessons-from-the-version-3-slip]]"
_organized: true
---

# A hybrid deep learning model for user story effort estimation.

Malik S, Hamid M, Saleem M. PLoS One, 2026.

## Summary

The authors build a dataset of 6,956 user stories from several sources, cleaned to 4,079, and train a model combining a pre-trained BERT encoder with an LSTM to predict story effort. It outperforms machine learning baselines on error metrics, and when outputs are mapped to Fibonacci story points it classifies 72% correctly. They also wrap the model as a web-based decision support tool.

## Why It Matters

I read it while writing the [[booking-widget-estimate]], curious whether estimation tooling would have helped with the version 3 slip. My conclusion is no: our feature estimates were roughly right; the plan failed on capacity, as [[lessons-from-the-version-3-slip]] says. Story-level estimation, automated or not, does not see two engineers leaving for platform work.

## Key Details

- Dataset: 4,079 cleaned user stories.
- 72% accuracy after mapping to Fibonacci points.

## Caveats

Accuracy on public story datasets says little about a 7-person team's estimates. We do not use story points.

## Source Links

- [DOI 10.1371/journal.pone.0353348](https://doi.org/10.1371/journal.pone.0353348), PMID 42467725
