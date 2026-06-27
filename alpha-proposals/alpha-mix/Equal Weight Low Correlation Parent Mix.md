---
title: Equal Weight Low Correlation Parent Mix
type: alpha-mix-proposal
project: worldquant-brain
status: candidate
created: 2026-06-27
updated: 2026-06-27
representative_alpha: JjdanMlO
related_alpha_ids:
  - JjdanMlO
  - XgKZ2OZ0
  - e7rMnb6O
---

# Equal Weight Low Correlation Parent Mix

> [!abstract] Proposal
> Build a simple normalized three-leg mix from parents in different alpha families: tax-working-spread fundamentals, options-skew risk appetite, and price-volume reversal. The central claim is that a low-correlation blend can preserve parent signal strength while reducing dependence on any single mechanism.

## Research Snapshot

| Item | Value |
| --- | --- |
| Representative alpha | `JjdanMlO` |
| Sibling variants | `XgKZ2OZ0`, `e7rMnb6O` |
| Construction | Equal-weight normalized parent mix |
| Parent families | fundamental, mixed/options composite, price-volume |
| Parent return correlation screen | Max parent correlation around 0.018 in the source candidate file |
| Current status | Hard checks passed; self-correlation pending |

## Evidence

| Alpha ID | Parent IDs | Sharpe | Fitness | Turnover | Returns | Drawdown | Grade |
| --- | --- | ---: | ---: | ---: | ---: | ---: | --- |
| `JjdanMlO` | `3qz0Nnz0`; `YPWmwWwW`; `npo8eZww` | 2.71 | 2.80 | 18.18% | 19.38% | 7.91% | SPECTACULAR |
| `XgKZ2OZ0` | `O0oWakzR`; `YPWmwWwW`; `npo8eZww` | 2.46 | 2.05 | 17.96% | 12.48% | 5.55% | EXCELLENT |
| `e7rMnb6O` | `O0oWakzR`; `YPWmwWwW`; `omvNmmKv` | 2.65 | 1.87 | 30.23% | 15.05% | 5.59% | GOOD |

## Construction

The representative ranks or z-scores each parent sleeve after applying family-level neutralization, then combines the sleeves with equal weights.

```text
alpha1_raw = group_neutralize(group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector), sector);
alpha1 = group_zscore(zscore(alpha1_raw), sector);

alpha2_raw = trade_when(ts_mean(pcr_oi_270, 2) < 1,
    group_zscore(ts_mean((implied_volatility_call_60 - implied_volatility_put_60), 5), sector),
    -1);
alpha2 = group_zscore(zscore(alpha2_raw), sector);

alpha3_raw = zscore(ts_decay_linear(group_neutralize(rank(add(
    multiply(0.6, reverse(ts_zscore(returns, 120))),
    multiply(0.4, reverse(ts_corr(returns, divide(volume, ts_mean(volume, 20)), 60)))
)), subindustry), 10));
alpha3 = group_zscore(zscore(alpha3_raw), sector);

alpha_mix = group_zscore(0.333333 * alpha1 + 0.333333 * alpha2 + 0.333333 * alpha3, industry);
alpha_mix
```

## Why It Should Work

The proposal is intentionally simple. It does not estimate optimized weights from the full sample; it uses equal allocation after normalization. That lowers the chance that the mix is merely overfit to a past return surface. The three sleeves also represent different economic forces: tax/accounting momentum, options-implied risk appetite, and price-volume reversal pressure.

If each parent signal captures a different investor behavior, the equal-weight mix should reduce path dependency. A poor regime for one sleeve can be offset by another sleeve without fully abandoning the original economic rationale.

## Main Risks

- Equal weighting can dilute the strongest parent if one sleeve is materially weaker out of sample.
- Options-skew parents may dominate the self-correlation comparison if their PnL is crowded.
- The price-volume sleeve adds turnover; `e7rMnb6O` shows that sibling variants can drift toward higher turnover.

## Validation Plan

- Compare the mix against each parent and a two-leg version that excludes the weakest sleeve.
- Recompute parent return correlations using current PnL, not only source-file parent screens.
- Keep only one representative unless sibling self-correlation is materially lower.
- Kill if the equal-weight blend passes only because of one parent sleeve.

## Sources

- Candidate file: `/Users/nuthdanai/Desktop/alpha-mixing-research/temp_submit_runs/mixed_alpha_candidates/mixed_alpha_candidates_20260614.csv`
- Verification file: `/Users/nuthdanai/Desktop/alpha-mixing-research/temp_submit_runs/mixed_alpha_candidates/verify_existing_top_20260615/input_ids.csv`
