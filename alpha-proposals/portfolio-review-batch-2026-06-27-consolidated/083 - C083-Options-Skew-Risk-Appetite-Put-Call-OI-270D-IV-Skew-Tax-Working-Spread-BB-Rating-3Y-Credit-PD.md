---
title: "C083 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Tax Working Spread + BB+ Rating + 3Y Credit PD"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-083
member_count: 2
cluster_basis: "exact-expression duplicate"
representative_alpha: "Options Skew Risk Appetite Variant 131"
created: 2026-06-27
updated: 2026-06-27
---

# C083 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Tax Working Spread + BB+ Rating + 3Y Credit PD

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **exact-expression duplicate**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 131 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `exact-expression duplicate` |
| Dominant families | risk/credit/volatility (2), tax/accounting fundamentals (2), options/implied volatility (2) |
| Common fields | `alpha3_raw, alpha2_raw, probability_dist_bb_plus, alpha1_raw, implied_volatility_put_270, pcr_oi_270, implied_volatility_call_270, alpha1, fnd6_txws, normalize, probability_non_investment_grade_rating, annualized_pd_3_year_jc7` |
| Common operators | `max, group_zscore, ts_corr, group_rank, ts_mean, rank, vec_avg, trade_when, ts_decay_linear, ts_std_dev, scale, ts_backfill` |
| Best recorded Sharpe | `2.26` |
| Best recorded Fitness | `2.49` |
| Median turnover | `10.80%` |
| Representative | Options Skew Risk Appetite Variant 131 |
| Representative bucket | `strong_signal_repair_seed` |
| Representative failed checks | `LOW_SUB_UNIVERSE_SHARPE` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1_raw = -rank(ts_corr(rank(ts_backfill(probability_dist_bb_plus, 63)), rank(ts_backfill(annualized_pd_3_year_jc7, 63)), 30)); alpha2_raw = group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector); alpha3_raw = trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)); alpha1 = scale(normalize(alpha1_raw, useStd=true, limit=3)); alpha2 = scale(normalize(alpha2_raw, useStd=true, limit=3)); alpha3 = scale(normalize(alpha3_raw, useStd=true, limit=3)); vol1 = ts_backfill(ts_std_dev(alpha1 * returns, 60), 120); vol2 = ts_backfill(ts_std_dev(alpha2 * returns, 60), 120); vol3 = ts_backfill(ts_std_dev(alpha3 * returns, 60), 120); iv1 = 1 / max(vol1, 0.0001); iv2 = 1 / max(vol2, 0.0001); iv3 = 1 / max(vol3, 0.0001); iv_sum = iv1 + iv2 + iv3; w1_raw = iv1 / iv_sum; w2_raw = iv2 / iv_sum; w3_raw = iv3 / iv_sum; w1 = ts_mean(w1_raw, 20); w2 = ts_mean(w2_raw, 20); w3 = ts_mean(w3_raw, 20); alpha = scale(w1 * alpha1 + w2 * alpha2 + w3 * alpha3); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `exact-expression duplicate` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha3_raw, alpha2_raw, probability_dist_bb_plus, alpha1_raw, implied_volatility_put_270, pcr_oi_270, implied_volatility_call_270, alpha1, fnd6_txws, normalize, probability_non_investment_grade_rating, annualized_pd_3_year_jc7`. |
| Operator overlap | Common operators are `max, group_zscore, ts_corr, group_rank, ts_mean, rank, vec_avg, trade_when, ts_decay_linear, ts_std_dev, scale, ts_backfill`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (2), tax/accounting fundamentals (2), options/implied volatility (2). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `failed-checks-strong-signal-repair-candidate` | 2 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `LOW_SUB_UNIVERSE_SHARPE` | 2 |
| pending: `SELF_CORRELATION` | 2 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 345 | Options Skew Risk Appetite Variant 131 | `npWOoLzd` | `strong_signal_repair_seed` | `2.26` | `2.49` | `10.80%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `aadd01d82db3c20d` |
| 354 | Options Skew Risk Appetite Variant 134 | `N1Ozvbbo` | `strong_signal_repair_seed` | `2.25` | `2.48` | `10.79%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `aadd01d82db3c20d` |

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
