---
title: "Options Skew Risk Appetite Cluster 076 - annualized_pd_4_year_jc7"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-076
member_count: 2
cluster_basis: "exact-expression duplicate"
representative_alpha: "Options Skew Risk Appetite Variant 122"
created: 2026-06-27
updated: 2026-06-27
---

# Options Skew Risk Appetite Cluster 076 - annualized_pd_4_year_jc7

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **exact-expression duplicate**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 122 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `exact-expression duplicate` |
| Dominant families | options/implied volatility (2), tax/accounting fundamentals (2), risk/credit/volatility (2) |
| Common fields | `annualized_pd_4_year_jc7, alpha1, implied_volatility_call_270, pcr_oi_270, alpha1_raw, fnd6_txws, implied_volatility_put_270, alpha3_raw, alpha2_raw, probability_non_investment_grade_rating, probability_dist_a_plus, normalize` |
| Common operators | `ts_std_dev, scale, ts_mean, vec_avg, max, group_zscore, ts_decay_linear, group_rank, group_neutralize, ts_backfill, ts_corr, trade_when` |
| Best recorded Sharpe | `2.07` |
| Best recorded Fitness | `2.13` |
| Median turnover | `15.56%` |
| Representative | Options Skew Risk Appetite Variant 122 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1_raw = -(group_neutralize(ts_corr(ts_backfill(annualized_pd_4_year_jc7, 63), ts_backfill(probability_dist_a_plus, 63), 10), sector)); alpha2_raw = group_neutralize(group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector), sector); alpha3_raw = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)), sector); alpha1 = scale(normalize(alpha1_raw, useStd=true, limit=3)); alpha2 = scale(normalize(alpha2_raw, useStd=true, limit=3)); alpha3 = scale(normalize(alpha3_raw, useStd=true, limit=3)); vol1 = ts_backfill(ts_std_dev(alpha1 * returns, 60), 120); vol2 = ts_backfill(ts_std_dev(alpha2 * returns, 60), 120); vol3 = ts_backfill(ts_std_dev(alpha3 * returns, 60), 120); iv1 = 1 / max(vol1, 0.0001); iv2 = 1 / max(vol2, 0.0001); iv3 = 1 / max(vol3, 0.0001); iv_sum = iv1 + iv2 + iv3; w1_raw = iv1 / iv_sum; w2_raw = iv2 / iv_sum; w3_raw = iv3 / iv_sum; w1 = ts_mean(w1_raw, 20); w2 = ts_mean(w2_raw, 20); w3 = ts_mean(w3_raw, 20); alpha = scale(w1 * alpha1 + w2 * alpha2 + w3 * alpha3); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `exact-expression duplicate` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `annualized_pd_4_year_jc7, alpha1, implied_volatility_call_270, pcr_oi_270, alpha1_raw, fnd6_txws, implied_volatility_put_270, alpha3_raw, alpha2_raw, probability_non_investment_grade_rating, probability_dist_a_plus, normalize`. |
| Operator overlap | Common operators are `ts_std_dev, scale, ts_mean, vec_avg, max, group_zscore, ts_decay_linear, group_rank, group_neutralize, ts_backfill, ts_corr, trade_when`. |
| Family overlap | Dominant workbook families are options/implied volatility (2), tax/accounting fundamentals (2), risk/credit/volatility (2). |
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
| 315 | Options Skew Risk Appetite Variant 122 | `pw71VVrb` | `hard_pass_signal_seed` | `2.07` | `2.13` | `15.56%` | `n/a` | `SELF_CORRELATION` | `ffe84159aa3a8c7e` |
| 316 | Options Skew Risk Appetite Variant 123 | `YPAzGaLv` | `hard_pass_signal_seed` | `2.07` | `2.13` | `15.56%` | `n/a` | `SELF_CORRELATION` | `ffe84159aa3a8c7e` |

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
