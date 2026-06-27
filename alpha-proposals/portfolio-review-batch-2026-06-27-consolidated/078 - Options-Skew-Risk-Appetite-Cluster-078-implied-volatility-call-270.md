---
title: "Options Skew Risk Appetite Cluster 078 - implied_volatility_call_270"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-078
member_count: 2
cluster_basis: "same-field same-operator variant"
representative_alpha: "Options Skew Risk Appetite Variant 126"
created: 2026-06-27
updated: 2026-06-27
---

# Options Skew Risk Appetite Cluster 078 - implied_volatility_call_270

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 126 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | options/implied volatility (2), risk/credit/volatility (2), price-volume/liquidity/turnover (2) |
| Common fields | `alpha1, implied_volatility_call_270, pcr_oi_270, alpha3, alpha4, returns, fnd6_newqeventv110_dpactq, implied_volatility_put_270, alpha2, annualized_pd_10_year_jc7, probability_non_investment_grade_rating, probability_dist_a` |
| Common operators | `ts_rank, scale, ts_mean, vec_avg, group_zscore, min, group_rank, group_neutralize, ts_backfill, ts_corr, rank, trade_when` |
| Best recorded Sharpe | `1.9` |
| Best recorded Fitness | `2.35` |
| Median turnover | `12.65%` |
| Representative | Options Skew Risk Appetite Variant 126 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1 = -(ts_corr(rank(ts_backfill(annualized_pd_10_year_jc7, 63)), rank(ts_backfill(probability_dist_a, 63)), 30)); alpha2 = group_rank(ts_arg_min(ts_backfill(vec_avg(fnd6_newqeventv110_dpactq), 120), 5), sector); alpha3 = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)), sector); alpha4 = -(ts_mean( returns * min(ts_rank(vwap, 10), ts_rank(close, 10)), 20)); alpha1_scaled = scale(group_neutralize(alpha1, industry)); alpha2_scaled = scale(group_neutralize(alpha2, industry)); alpha3_scaled = scale(group_neutralize(alpha3, industry)); alpha4_scaled = scale(group_neutralize(alpha4, industry)); alphamix_raw = (alpha1_scaled + alpha2_scaled + alpha3_scaled + alpha4_scaled) / 4; alphamix = scale(alphamix_raw); alphamix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha1, implied_volatility_call_270, pcr_oi_270, alpha3, alpha4, returns, fnd6_newqeventv110_dpactq, implied_volatility_put_270, alpha2, annualized_pd_10_year_jc7, probability_non_investment_grade_rating, probability_dist_a`. |
| Operator overlap | Common operators are `ts_rank, scale, ts_mean, vec_avg, group_zscore, min, group_rank, group_neutralize, ts_backfill, ts_corr, rank, trade_when`. |
| Family overlap | Dominant workbook families are options/implied volatility (2), risk/credit/volatility (2), price-volume/liquidity/turnover (2). |
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
| 324 | Options Skew Risk Appetite Variant 126 | `vRmepoLz` | `hard_pass_signal_seed` | `1.9` | `2.35` | `12.65%` | `n/a` | `SELF_CORRELATION` | `9eedf8aede336227` |
| 325 | Options Skew Risk Appetite Variant 127 | `LLRgmMje` | `hard_pass_signal_seed` | `1.9` | `2.35` | `12.65%` | `n/a` | `SELF_CORRELATION` | `c877a95a6d67edee` |

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
