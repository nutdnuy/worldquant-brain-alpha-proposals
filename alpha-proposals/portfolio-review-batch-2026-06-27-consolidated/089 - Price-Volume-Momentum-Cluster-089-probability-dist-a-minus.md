---
title: "Price Volume Momentum Cluster 089 - probability_dist_a_minus"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-089
member_count: 2
cluster_basis: "same-field same-operator variant"
representative_alpha: "Price Volume Momentum Variant 15"
created: 2026-06-27
updated: 2026-06-27
---

# Price Volume Momentum Cluster 089 - probability_dist_a_minus

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Price Volume Momentum Variant 15 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | tax/accounting fundamentals (2), risk/credit/volatility (2) |
| Common fields | `probability_dist_a_minus, alpha1, alpha1_scaled, alpha3, alpha1_ret, returns, fnd6_txws, alpha3_scaled, alpha2, annualized_pd_6_month_jc7, unsystematic_risk_last_60_days, alpha2_scaled` |
| Common operators | `ts_std_dev, scale, ts_mean, ts_zscore, ts_delta, vec_avg, max, ts_decay_linear, group_rank, group_neutralize, ts_backfill, ts_corr` |
| Best recorded Sharpe | `1.8` |
| Best recorded Fitness | `2.08` |
| Median turnover | `10.14%` |
| Representative | Price Volume Momentum Variant 15 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1 = -(group_neutralize(ts_corr(ts_backfill(annualized_pd_6_month_jc7, 63), ts_backfill(probability_dist_a_minus, 63), 126), sector)); alpha2 = group_neutralize(group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector), sector); alpha3 = group_rank(ts_zscore(ts_delta(ts_backfill(unsystematic_risk_last_60_days, 20), 90), 90), sector); alpha1_scaled = scale(group_neutralize(alpha1, industry)); alpha2_scaled = scale(group_neutralize(alpha2, industry)); alpha3_scaled = scale(group_neutralize(alpha3, industry)); alpha1_ret = alpha1_scaled * returns; alpha2_ret = alpha2_scaled * returns; alpha3_ret = alpha3_scaled * returns; alpha1_score = rank(ts_mean(alpha1_ret, 30) / max(ts_std_dev(alpha1_ret, 30), 0.0001)); alpha2_score = rank(ts_mean(alpha2_ret, 30) / max(ts_std_dev(alpha2_ret, 30), 0.0001)); alpha3_score = rank(ts_mean(alpha3_ret, 30) / max(ts_std_dev(alpha3_ret, 30), 0.0001)); w_sum = alpha1_score + alpha2_score + alpha3_score + 0.0001; alpha1_w = alpha1_score / w_sum; alpha2_w = alpha2_score / w_sum; alpha3_w = alpha3_score / w_sum; alphamix_raw = alpha1_w * alpha1_scaled + alpha2_w * alpha2_scaled + alpha3_w * alpha3_scaled; alphamix = scale(group_neutralize(alphamix_raw, industry)); alphamix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `probability_dist_a_minus, alpha1, alpha1_scaled, alpha3, alpha1_ret, returns, fnd6_txws, alpha3_scaled, alpha2, annualized_pd_6_month_jc7, unsystematic_risk_last_60_days, alpha2_scaled`. |
| Operator overlap | Common operators are `ts_std_dev, scale, ts_mean, ts_zscore, ts_delta, vec_avg, max, ts_decay_linear, group_rank, group_neutralize, ts_backfill, ts_corr`. |
| Family overlap | Dominant workbook families are tax/accounting fundamentals (2), risk/credit/volatility (2). |
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
| 480 | Price Volume Momentum Variant 15 | `rKWrjrAE` | `hard_pass_signal_seed` | `1.8` | `2.08` | `10.14%` | `n/a` | `SELF_CORRELATION` | `5ed7698d4fc0fd45` |
| 481 | Price Volume Momentum Variant 16 | `3qAnRQvg` | `hard_pass_signal_seed` | `1.8` | `2.08` | `10.14%` | `n/a` | `SELF_CORRELATION` | `19df80345f71e33f` |

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
