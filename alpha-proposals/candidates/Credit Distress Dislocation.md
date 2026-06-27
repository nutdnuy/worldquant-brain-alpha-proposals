---
title: Credit Distress Dislocation Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: Credit Distress Dislocation
alpha_ids:
  - wpewYzp5
status: hard-pass-correlation-review-required
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium
tags:
  - worldquant
  - alpha-proposal
  - credit-risk
  - distress
---

# Credit Distress Dislocation Alpha Proposal

> [!abstract] Research Thesis
> **Credit Distress Dislocation** compares a rating-implied distress proxy with a two-year default-probability model. The thesis is that disagreement between categorical credit-risk signals and model-implied default probability can reveal mispriced credit deterioration or improving balance-sheet risk.

## Snapshot

| Dimension | Description |
| --- | --- |
| Alpha ID | `wpewYzp5` |
| Core fields | `probability_rating_ccc_plus`, `annualized_pd_2_year_jc7` |
| Mechanism | Sector-neutralized credit-risk disagreement |
| Source sheet | `04_alpha_pass_combined` |
| Status | Hard pass; correlation review required |
| Main risk | Credit model field definitions and coverage |

## Formula

```text
-(group_neutralize(
  zscore(ts_backfill(vec_avg(probability_rating_ccc_plus), 250))
  - zscore(ts_backfill(annualized_pd_2_year_jc7, 63)),
  sector
))
```

## Economic Rationale

Credit-risk information is multi-dimensional. Ratings-style probability fields can move differently from model-implied annualized default probability. A spread between the two can indicate delayed recognition of credit deterioration, rating lag, or improving credit quality not yet reflected in one channel.

The negative sign means the alpha rewards one side of the dislocation after sector neutralization. The important research claim is not the raw level of credit risk; it is disagreement between two credit-risk lenses.

## Empirical Record

| Metric | Recorded value |
| --- | ---: |
| Alpha ID | `wpewYzp5` |
| Sharpe | `1.54` |
| Fitness | `2.49` |
| Turnover | `3.65%` |
| Returns | `32.55%` |
| Drawdown | `21.58%` |
| Margin | `0.017835` |
| Max abs corr in workbook | `0.7939` |

## Validation Plan

- Confirm definitions and timing of both credit-risk fields.
- Test whether the signal remains after industry neutralization.
- Review exposure to size, leverage, distress, and low-volatility factors.
- Check correlation against other credit probability and liquidity-risk alphas.

## Failure Criteria

Demote if the signal is a generic distress short, if coverage is too sparse, or if the high correlation cluster makes it redundant.

## Decision

Keep as a credit-risk candidate, but require field-definition and self-correlation review before promotion.

## Sources

- Source workbook: `/Users/nuthdanai/Desktop/alpha-mixing-research/alpha_mixing_research_combined.xlsm`
- Source sheet: `04_alpha_pass_combined`
- Source file recorded in sheet: `submittable_group1_alphas.xlsm`
