---
title: "Options Skew Risk Appetite Cluster 015 - implied_volatility_call_270"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-015
member_count: 6
cluster_basis: "high-similarity field/operator/family cluster"
representative_alpha: "Options Skew Risk Appetite Variant 41"
created: 2026-06-27
updated: 2026-06-27
---

# Options Skew Risk Appetite Cluster 015 - implied_volatility_call_270

> [!abstract] Consolidated Thesis
> This note combines **6** highly similar alpha proposals into one research idea. The consolidation basis is **high-similarity field/operator/family cluster**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 41 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `6` |
| Cluster basis | `high-similarity field/operator/family cluster` |
| Dominant families | options/implied volatility (6), tax/accounting fundamentals (6), analyst/model scores (6), price-volume/liquidity/turnover (6), risk/credit/volatility (6) |
| Common fields | `alpha1, implied_volatility_call_270, annualized_pd_7_year_jc7, anl4_detailrecv4_est, alpha3, pcr_oi_270, alpha4, implied_volatility_put_270, anl4_netdebt_number, alpha2, probability_non_investment_grade_rating, probability_dist_a_minus` |
| Common operators | `ts_rank, scale, ts_mean, vec_avg, group_zscore, min, group_neutralize, ts_backfill, ts_corr, rank, trade_when` |
| Best recorded Sharpe | `2.19` |
| Best recorded Fitness | `2.91` |
| Median turnover | `10.88%` |
| Representative | Options Skew Risk Appetite Variant 41 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1 = -(ts_corr(rank(ts_backfill(probability_dist_a_minus, 63)), rank(ts_backfill(annualized_pd_7_year_jc7, 63)), 252)); alpha2 = -(ts_corr(rank(ts_backfill(anl4_netdebt_number, 120)), rank(ts_backfill(vec_avg(anl4_detailrecv4_est), 21)), 126)); alpha3 = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)), sector); alpha4 = -(ts_mean( returns * min(ts_rank(vwap, 10), ts_rank(close, 10)), 20)); alpha1_scaled = scale(group_neutralize(alpha1, industry)); alpha2_scaled = scale(group_neutralize(alpha2, industry)); alpha3_scaled = scale(group_neutralize(alpha3, industry)); alpha4_scaled = scale(group_neutralize(alpha4, industry)); alphamix_raw = (alpha1_scaled + alpha2_scaled + alpha3_scaled + alpha4_scaled) / 4; alphamix = scale(alphamix_raw); alphamix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `high-similarity field/operator/family cluster` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha1, implied_volatility_call_270, annualized_pd_7_year_jc7, anl4_detailrecv4_est, alpha3, pcr_oi_270, alpha4, implied_volatility_put_270, anl4_netdebt_number, alpha2, probability_non_investment_grade_rating, probability_dist_a_minus`. |
| Operator overlap | Common operators are `ts_rank, scale, ts_mean, vec_avg, group_zscore, min, group_neutralize, ts_backfill, ts_corr, rank, trade_when`. |
| Family overlap | Dominant workbook families are options/implied volatility (6), tax/accounting fundamentals (6), analyst/model scores (6), price-volume/liquidity/turnover (6), risk/credit/volatility (6). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 6 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 6 |
| pending: `SELF_CORRELATION` | 6 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 107 | Options Skew Risk Appetite Variant 41 | `Vk8Yp2kJ` | `hard_pass_signal_seed` | `2.19` | `2.91` | `9.62%` | `n/a` | `SELF_CORRELATION` | `d2096aa1caf5499a` |
| 108 | Options Skew Risk Appetite Variant 42 | `9qRAR3me` | `hard_pass_signal_seed` | `2.19` | `2.91` | `9.62%` | `n/a` | `SELF_CORRELATION` | `4e21f590e9be7bac` |
| 109 | Options Skew Risk Appetite Variant 43 | `78dK1kzQ` | `hard_pass_signal_seed` | `2.19` | `2.91` | `9.62%` | `n/a` | `SELF_CORRELATION` | `f493fbe11a2f4d88` |
| 143 | Options Skew Risk Appetite Variant 51 | `vRmJYLxQ` | `hard_pass_signal_seed` | `2.13` | `2.8` | `10.88%` | `n/a` | `SELF_CORRELATION` | `6ff29b9393f11fc0` |
| 144 | Options Skew Risk Appetite Variant 52 | `e7rq1M76` | `hard_pass_signal_seed` | `2.13` | `2.8` | `10.88%` | `n/a` | `SELF_CORRELATION` | `e9698ad2d38ef8c9` |
| 145 | Options Skew Risk Appetite Variant 53 | `d5QlYvkj` | `hard_pass_signal_seed` | `2.13` | `2.8` | `10.88%` | `n/a` | `SELF_CORRELATION` | `e28fd289588b3f21` |

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
