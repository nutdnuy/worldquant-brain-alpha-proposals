---
title: Direction Weighted Options Skew Conviction
type: alpha-mix-proposal
project: worldquant-brain
status: candidate
created: 2026-06-27
updated: 2026-06-27
representative_alpha: xAnkAEGw
---

# Direction Weighted Options Skew Conviction

> [!abstract] Proposal
> Use options implied-volatility skew as the trade direction, but use a separate price-volume reversal signal only as a conviction multiplier. This avoids treating the second alpha as an independent signed forecast and instead uses it to size exposure when liquidity/price pressure confirms the options signal.

## Research Snapshot

| Item | Value |
| --- | --- |
| Representative alpha | `xAnkAEGw` |
| Direction parent | `58q9RJKo` |
| Weight parent | `MPxl3Rp6` |
| Direction family | Options volatility |
| Weight family | Price-volume |
| Parent pair correlation | 0.0338 in source screen |
| Current status | Hard checks passed; self-correlation pending |

## Evidence

| Alpha ID | Sharpe | Fitness | Turnover | Returns | Drawdown | Grade | Pending |
| --- | ---: | ---: | ---: | ---: | ---: | --- | --- |
| `xAnkAEGw` | 2.56 | 3.07 | 16.74% | 24.03% | 9.95% | SPECTACULAR | SELF_CORRELATION |

## Construction

The direction leg is a put-call implied volatility spread. The weight leg is a price-volume pressure measure, transformed into a top-tail conviction multiplier. The second sleeve changes position size, not sign.

```text
direction = trade_when(ts_mean(pcr_oi_270, 2) < 1,
    group_zscore(ts_mean((implied_volatility_call_60 - implied_volatility_put_60), 5), sector),
    -1);

weight_raw = -(ts_mean(returns * min(ts_rank(vwap, 10), ts_rank(close, 10)), 20));
weight_strength = rank(abs(weight_raw));
conviction = if_else(weight_strength > 0.85, 1.30, 1.00);

alphamix = direction * conviction;
alphamix
```

## Why It Should Work

Options skew can proxy investor demand for upside versus downside protection. Price-volume pressure can proxy where recent trading pressure is large enough to make that options signal actionable. The construction is economically cleaner than a raw additive mix because the price-volume leg does not reverse the options signal; it only increases conviction when cross-sectional pressure is extreme.

The low parent pair correlation is important. It means the weight leg is not simply a disguised copy of the options direction. If the price-volume measure identifies names where the options signal is more likely to be realized, the product form can improve fitness without creating an entirely new unstable direction.

## Main Risks

- The options-skew direction is likely to be correlated with other options-volatility proposals.
- Multiplicative conviction can amplify tail exposure if the weight signal spikes during stress regimes.
- The construction must be checked against high turnover and crowding in options-related families.

## Validation Plan

- Compare against the direction-only parent `58q9RJKo`.
- Test alternative conviction thresholds around 0.80, 0.85, and 0.90.
- Check whether the PnL improvement comes from higher returns or only from larger exposure.
- Reject if self-correlation is explained by the options leg and the multiplier adds no independent value.

## Sources

- Candidate file: `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/sim_candidates/top3000_dirweight_diversified_1000_tail_t0p85_b1p30.csv`
- Result files: `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/sim_results/top3000_dirweight_diversified_1000_hotmail_w3_partial_47_top_clean_20260608.csv`, `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/sim_results/top3000_dirweight_diversified_1000_hotmail_w3_partial_47_enriched_20260608.csv`
