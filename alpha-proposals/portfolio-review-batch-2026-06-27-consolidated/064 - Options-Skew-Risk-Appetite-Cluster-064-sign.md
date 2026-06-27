---
title: "Options Skew Risk Appetite Cluster 064 - sign"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-064
member_count: 2
cluster_basis: "same-field same-operator variant"
representative_alpha: "Options Skew Risk Appetite Variant 64"
created: 2026-06-27
updated: 2026-06-27
---

# Options Skew Risk Appetite Cluster 064 - sign

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 64 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | options/implied volatility (2), tax/accounting fundamentals (2), risk/credit/volatility (2), price-volume/liquidity/turnover (2) |
| Common fields | `sign, alpha1, pcr_oi_270, alpha1_raw, returns, volume, fnd6_txws, implied_volatility_call_60, alpha3_raw, alpha2, alpha2_raw, implied_volatility_put_60` |
| Common operators | `ts_rank, zscore, multiply, winsorize, ts_mean, divide, vec_avg, group_zscore, ts_decay_linear, group_rank, group_neutralize, ts_backfill` |
| Best recorded Sharpe | `2.65` |
| Best recorded Fitness | `1.87` |
| Median turnover | `30.23%` |
| Representative | Options Skew Risk Appetite Variant 64 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1_raw = group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector); alpha1 = group_zscore(rank(alpha1_raw), industry); alpha2_raw = trade_when(ts_mean(pcr_oi_270, 2) < 1, group_zscore(ts_mean((implied_volatility_call_60 - implied_volatility_put_60), 5), sector), -1); alpha2 = group_zscore(rank(alpha2_raw), industry); alpha3_raw = -(zscore(ts_decay_linear(group_neutralize(ts_rank(winsorize(multiply(sign(returns), rank(divide(volume, ts_mean(volume, 20)))), std=4), 20), subindustry), 5))); alpha3 = group_zscore(rank(alpha3_raw), industry); alpha_mix = zscore(0.333333 * alpha1 + 0.333333 * alpha2 + 0.333333 * alpha3); alpha_mix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `sign, alpha1, pcr_oi_270, alpha1_raw, returns, volume, fnd6_txws, implied_volatility_call_60, alpha3_raw, alpha2, alpha2_raw, implied_volatility_put_60`. |
| Operator overlap | Common operators are `ts_rank, zscore, multiply, winsorize, ts_mean, divide, vec_avg, group_zscore, ts_decay_linear, group_rank, group_neutralize, ts_backfill`. |
| Family overlap | Dominant workbook families are options/implied volatility (2), tax/accounting fundamentals (2), risk/credit/volatility (2), price-volume/liquidity/turnover (2). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 2 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 2 |
| pending: `SELF_CORRELATION` | 2 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 181 | Options Skew Risk Appetite Variant 64 | `e7rMnb6O` | `hard_pass_signal_seed` | `2.65` | `1.87` | `30.23%` | `n/a` | `SELF_CORRELATION` | `7d3883bc4f5533e0` |
| 381 | Options Skew Risk Appetite Variant 145 | `rKo6d5Qd` | `hard_pass_signal_seed` | `2.32` | `1.64` | `18.58%` | `n/a` | `SELF_CORRELATION` | `393740d98f3196fc` |

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
