---
title: "C010 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-010
member_count: 10
cluster_basis: "high-similarity field/operator/family cluster"
representative_alpha: "Options Skew Risk Appetite"
created: 2026-06-27
updated: 2026-06-27
---

# C010 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew

> [!abstract] Consolidated Thesis
> This note combines **10** highly similar alpha proposals into one research idea. The consolidation basis is **high-similarity field/operator/family cluster**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `10` |
| Cluster basis | `high-similarity field/operator/family cluster` |
| Dominant families | risk/credit/volatility (10), options/implied volatility (10), price-volume/liquidity/turnover (2) |
| Common fields | `implied_volatility_put_60, pcr_oi_270, implied_volatility_call_60, returns, direction, weight_raw, conviction, vwap, weight_strength, close, alphamix` |
| Common operators | `trade_when, ts_mean, group_zscore, min, if_else, ts_rank, rank, abs` |
| Best recorded Sharpe | `2.69` |
| Best recorded Fitness | `3.49` |
| Median turnover | `17.58%` |
| Representative | Options Skew Risk Appetite |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> trade_when(ts_mean(pcr_oi_270, 2) < 1, group_zscore(ts_mean((implied_volatility_call_60 - implied_volatility_put_60), 5), sector), -1)
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `high-similarity field/operator/family cluster` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `implied_volatility_put_60, pcr_oi_270, implied_volatility_call_60, returns, direction, weight_raw, conviction, vwap, weight_strength, close, alphamix`. |
| Operator overlap | Common operators are `trade_when, ts_mean, group_zscore, min, if_else, ts_rank, rank, abs`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (10), options/implied volatility (10), price-volume/liquidity/turnover (2). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 10 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 10 |
| pending: `SELF_CORRELATION` | 10 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 12 | Options Skew Risk Appetite | `YPWmwWwW` | `hard_pass_signal_seed` | `2.69` | `3.49` | `11.45%` | `n/a` | `SELF_CORRELATION` | `e072305d448a8ff3` |
| 19 | Options Skew Risk Appetite Variant 4 | `LLl6b7O6` | `hard_pass_signal_seed` | `2.44` | `3.33` | `10.46%` | `n/a` | `SELF_CORRELATION` | `a9d4bd1ca2d0d44d` |
| 20 | Options Skew Risk Appetite Variant 5 | `xAnkAEGw` | `hard_pass_signal_seed` | `2.56` | `3.07` | `16.74%` | `n/a` | `SELF_CORRELATION` | `1813db43deb87e75` |
| 37 | Options Skew Risk Appetite Variant 12 | `e7r0pOz6` | `hard_pass_signal_seed` | `2.6` | `2.79` | `16.27%` | `n/a` | `SELF_CORRELATION` | `fb1932cffa18f6d1` |
| 50 | Options Skew Risk Appetite Variant 20 | `kqLXkmnO` | `hard_pass_signal_seed` | `2.35` | `3` | `13.40%` | `n/a` | `SELF_CORRELATION` | `2e817cb4939bc010` |
| 77 | Options Skew Risk Appetite Variant 27 | `58q9RJKo` | `hard_pass_signal_seed` | `2.42` | `2.73` | `17.61%` | `n/a` | `SELF_CORRELATION` | `e072305d448a8ff3` |
| 87 | Options Skew Risk Appetite Variant 30 | `j2dXlzKE` | `hard_pass_signal_seed` | `2.41` | `2.7` | `17.58%` | `n/a` | `SELF_CORRELATION` | `8577f44b32bf9b97` |
| 103 | Options Skew Risk Appetite Variant 40 | `RRkYKLZe` | `hard_pass_signal_seed` | `2.53` | `2.46` | `17.71%` | `n/a` | `SELF_CORRELATION` | `5a1b9fc9216ae7e7` |
| 152 | Options Skew Risk Appetite Variant 55 | `pw1EJQL3` | `hard_pass_signal_seed` | `2.37` | `2.45` | `20.34%` | `n/a` | `SELF_CORRELATION` | `b1b8a2ced9d0f4d4` |
| 270 | Options Skew Risk Appetite Variant 106 | `om9vwewE` | `hard_pass_signal_seed` | `2.22` | `2.07` | `23.17%` | `n/a` | `SELF_CORRELATION` | `8d91cd8d244504a6` |

## Consolidated Decision

> [!success] Current decision
> Keep the representative as the active research card for this cluster and keep the other members as sibling evidence. Do not submit or promote multiple variants from this cluster unless a later correlation review proves they are genuinely non-redundant.

## Next Experiments

> [!todo] Cluster-level validation
> - Run current-pool self-correlation on the representative first.
> - Compare the representative against the best two sibling variants by exact same 10Y settings.
> - Run one ablation that removes the most fragile gate, threshold, or extra leg.
> - If the cluster contains failed-check variants, repair the failure mode at cluster level rather than tuning each row independently.
> - Keep only variants that improve robustness or lower correlation without changing the economic mechanism.

## Kill Criteria

> [!failure] Collapse or reject the cluster if
> - the representative fails self-correlation and no sibling variant lowers redundancy;
> - all strong variants depend on one narrow parameter or threshold;
> - hard-check failures persist after mechanism-preserving repair;
> - the cluster is explained by a crowded generic factor rather than its stated mechanism.

## Sources

- Source workbook: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/06_alpha_catalog/alpha_signal_library_10y_upgrade/worldquant_alpha_pipeline_10y_workbook_20260624.xlsx`
- Source sheet: `M5_PortfolioReview`
- Enrichment sheet: `05_10YPriorityQueue`
