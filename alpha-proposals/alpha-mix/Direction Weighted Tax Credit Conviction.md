---
title: Direction Weighted Tax Credit Conviction
type: alpha-mix-proposal
project: worldquant-brain
status: candidate
created: 2026-06-27
updated: 2026-06-27
representative_alpha: MPxp60Za
related_alpha_ids:
  - MPxp60Za
  - 3qARw6wN
---

# Direction Weighted Tax Credit Conviction

> [!abstract] Proposal
> Keep tax-working-spread momentum as the main return forecast, but allow credit/default-risk information to raise conviction only in the strongest cross-sectional tail. This is a direction-weight design: credit risk sizes the trade, while tax-working-spread remains the sign of the alpha.

## Research Snapshot

| Item | Value |
| --- | --- |
| Representative alpha | `MPxp60Za` |
| Sibling variant | `3qARw6wN` |
| Direction parent | `O0oWakzR` or `3qz0Nnz0` tax-working-spread family |
| Weight parent | `wpewYzp5` or other credit/risk sleeve |
| Parent pair correlation | 0.0082 for `O0oWakzR` and `wpewYzp5` source screen |
| Current status | Hard checks passed; self-correlation pending |

## Evidence

| Alpha ID | Construction | Sharpe | Fitness | Turnover | Returns | Drawdown | Grade |
| --- | --- | ---: | ---: | ---: | ---: | ---: | --- |
| `MPxp60Za` | Tax direction with credit tail conviction | 2.16 | 2.89 | 3.15% | 22.43% | 9.51% | SPECTACULAR |
| `3qARw6wN` | Tax direction with risk-state conviction | 2.36 | 3.11 | 10.12% | 21.76% | 9.74% | SPECTACULAR |

## Construction

The representative keeps the original tax-working-spread direction intact for most names. Credit disagreement only boosts the strongest conviction tail.

```text
direction = group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector);

weight_raw = -(group_neutralize(
    zscore(ts_backfill(vec_avg(probability_rating_ccc_plus), 250))
    - zscore(ts_backfill(annualized_pd_2_year_jc7, 63)),
    sector));

weight_strength = rank(abs(weight_raw));
conviction = if_else(weight_strength > 0.70, 1.10, 1.00);

alphamix = direction * conviction;
alphamix
```

## Why It Should Work

Tax-working-spread momentum is an accounting-based signal. Credit/default disagreement is a financing-risk signal. The thesis is that accounting signals are more valuable when the credit market or default-probability model also indicates that the firm is in an information-sensitive state. The credit sleeve should not flip the tax signal; it should only scale it when credit information suggests higher marginal relevance.

This also explains why the low pair correlation matters. If the credit sleeve is orthogonal to the tax direction, it can act as a state-dependent confidence measure rather than a duplicate factor.

## Main Risks

- The tax-working-spread parent is strong enough that the mix may still self-correlate to the parent family.
- Credit-risk conviction can overweight stressed names and raise drawdown in credit events.
- If the boost threshold is too low, the formula becomes a disguised credit-tax additive mix.

## Validation Plan

- Run self-correlation against `O0oWakzR`, `3qz0Nnz0`, and credit-distress candidates.
- Compare the 0.70/1.10 representative against the 0.85/1.30 stronger-boost variant.
- Check whether the boost improves sub-universe Sharpe or merely raises gross exposure.
- Prefer the lower-turnover representative if both variants have similar self-correlation.

## Sources

- Candidate file: `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/sim_candidates/top3000_dirweight_format_search_r3_tail_grid_O0oWakzR_wpewYzp5.csv`
- Result file: `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/sim_results/top3000_dirweight_format_search_summary_20260608.csv`
- Additional result file: `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/sim_results/top3000_dirweight_diversified_1000_hotmail_w3_partial_47_top_clean_20260608.csv`
