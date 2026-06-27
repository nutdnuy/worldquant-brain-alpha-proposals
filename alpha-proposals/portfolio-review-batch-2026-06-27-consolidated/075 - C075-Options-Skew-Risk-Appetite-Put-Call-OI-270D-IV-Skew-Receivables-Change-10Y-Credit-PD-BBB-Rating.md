---
title: "C075 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Receivables Change + 10Y Credit PD + BBB+ Rating"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-075
member_count: 2
cluster_basis: "exact-expression duplicate"
representative_alpha: "Options Skew Risk Appetite Variant 137"
created: 2026-06-27
updated: 2026-06-27
---

# C075 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Receivables Change + 10Y Credit PD + BBB+ Rating

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **exact-expression duplicate**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 137 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `exact-expression duplicate` |
| Dominant families | risk/credit/volatility (2), analyst/model scores (2), tax/accounting fundamentals (2), options/implied volatility (2) |
| Common fields | `alpha3_raw, alpha2_raw, alpha1_raw, implied_volatility_put_270, annualized_pd_10_year_jc7, anl4_netdebt_number, pcr_oi_270, implied_volatility_call_270, alpha1, probability_non_investment_grade_rating, probability_rating_bbb_plus, anl4_detailrecv4_est` |
| Common operators | `max, group_zscore, ts_corr, rank, vec_avg, ts_mean, trade_when, ts_std_dev, scale, ts_backfill, group_neutralize` |
| Best recorded Sharpe | `1.93` |
| Best recorded Fitness | `2.21` |
| Median turnover | `8.24%` |
| Representative | Options Skew Risk Appetite Variant 137 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1_raw = -(ts_corr(rank(ts_backfill(annualized_pd_10_year_jc7, 63)), rank(ts_backfill(vec_avg(probability_rating_bbb_plus), 250)), 60)); alpha2_raw = -(ts_corr(rank(ts_backfill(anl4_netdebt_number, 120)), rank(ts_backfill(vec_avg(anl4_detailrecv4_est), 21)), 126)); alpha3_raw = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)), sector); alpha1 = scale(normalize(alpha1_raw, useStd=true, limit=3)); alpha2 = scale(normalize(alpha2_raw, useStd=true, limit=3)); alpha3 = scale(normalize(alpha3_raw, useStd=true, limit=3)); vol1 = ts_backfill(ts_std_dev(alpha1 * returns, 60), 120); vol2 = ts_backfill(ts_std_dev(alpha2 * returns, 60), 120); vol3 = ts_backfill(ts_std_dev(alpha3 * returns, 60), 120); iv1 = 1 / max(vol1, 0.0001); iv2 = 1 / max(vol2, 0.0001); iv3 = 1 / max(vol3, 0.0001); iv_sum = iv1 + iv2 + iv3; w1_raw = iv1 / iv_sum; w2_raw = iv2 / iv_sum; w3_raw = iv3 / iv_sum; w1 = ts_mean(w1_raw, 20); w2 = ts_mean(w2_raw, 20); w3 = ts_mean(w3_raw, 20); alpha = scale(w1 * alpha1 + w2 * alpha2 + w3 * alpha3); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `exact-expression duplicate` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha3_raw, alpha2_raw, alpha1_raw, implied_volatility_put_270, annualized_pd_10_year_jc7, anl4_netdebt_number, pcr_oi_270, implied_volatility_call_270, alpha1, probability_non_investment_grade_rating, probability_rating_bbb_plus, anl4_detailrecv4_est`. |
| Operator overlap | Common operators are `max, group_zscore, ts_corr, rank, vec_avg, ts_mean, trade_when, ts_std_dev, scale, ts_backfill, group_neutralize`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (2), analyst/model scores (2), tax/accounting fundamentals (2), options/implied volatility (2). |
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
| 363 | Options Skew Risk Appetite Variant 137 | `omYGOV7m` | `hard_pass_signal_seed` | `1.93` | `2.21` | `8.24%` | `n/a` | `SELF_CORRELATION` | `b63d6e2fca8cf122` |
| 364 | Options Skew Risk Appetite Variant 138 | `omY9YnPl` | `hard_pass_signal_seed` | `1.93` | `2.21` | `8.24%` | `n/a` | `SELF_CORRELATION` | `b63d6e2fca8cf122` |

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
