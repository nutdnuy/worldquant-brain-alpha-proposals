---
title: "EPS Revision Shock Cluster 019 - annualized_pd_7_year_jc7"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-019
member_count: 6
cluster_basis: "high-similarity field/operator/family cluster"
representative_alpha: "EPS Revision Shock Variant 142"
created: 2026-06-27
updated: 2026-06-27
---

# EPS Revision Shock Cluster 019 - annualized_pd_7_year_jc7

> [!abstract] Consolidated Thesis
> This note combines **6** highly similar alpha proposals into one research idea. The consolidation basis is **high-similarity field/operator/family cluster**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** EPS Revision Shock Variant 142 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `6` |
| Cluster basis | `high-similarity field/operator/family cluster` |
| Dominant families | quality/growth/value (6), options/implied volatility (6), tax/accounting fundamentals (6), analyst/model scores (6), risk/credit/volatility (6) |
| Common fields | `alpha1, annualized_pd_7_year_jc7, alpha1_raw, anl4_detailrecv4_est, anl4_netdebt_number, alpha3_raw, useStd, mdl77_ohistoricalgrowthfactor_fcfequity, mdl77_valueanalystmodelqva_epmodule, alpha2_raw, normalize, probability_dist_aaa` |
| Common operators | `ts_std_dev, scale, ts_mean, vec_avg, max, ts_backfill, ts_corr, rank, group_neutralize` |
| Best recorded Sharpe | `1.96` |
| Best recorded Fitness | `2.05` |
| Median turnover | `9.43%` |
| Representative | EPS Revision Shock Variant 142 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1_raw = -(ts_corr(rank(ts_backfill(probability_dist_a_minus, 63)), rank(ts_backfill(annualized_pd_7_year_jc7, 63)), 252)); alpha2_raw = -(ts_corr(rank(ts_backfill(anl4_netdebt_number, 120)), rank(ts_backfill(vec_avg(anl4_detailrecv4_est), 21)), 126)); alpha3_raw = group_neutralize(mdl77_valueanalystmodelqva_epmodule - mdl77_ohistoricalgrowthfactor_fcfequity, sector); alpha1 = scale(normalize(alpha1_raw, useStd=true, limit=3)); alpha2 = scale(normalize(alpha2_raw, useStd=true, limit=3)); alpha3 = scale(normalize(alpha3_raw, useStd=true, limit=3)); vol1 = ts_backfill(ts_std_dev(alpha1 * returns, 60), 120); vol2 = ts_backfill(ts_std_dev(alpha2 * returns, 60), 120); vol3 = ts_backfill(ts_std_dev(alpha3 * returns, 60), 120); iv1 = 1 / max(vol1, 0.0001); iv2 = 1 / max(vol2, 0.0001); iv3 = 1 / max(vol3, 0.0001); iv_sum = iv1 + iv2 + iv3; w1_raw = iv1 / iv_sum; w2_raw = iv2 / iv_sum; w3_raw = iv3 / iv_sum; w1 = ts_mean(w1_raw, 20); w2 = ts_mean(w2_raw, 20); w3 = ts_mean(w3_raw, 20); alpha = scale(w1 * alpha1 + w2 * alpha2 + w3 * alpha3); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `high-similarity field/operator/family cluster` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha1, annualized_pd_7_year_jc7, alpha1_raw, anl4_detailrecv4_est, anl4_netdebt_number, alpha3_raw, useStd, mdl77_ohistoricalgrowthfactor_fcfequity, mdl77_valueanalystmodelqva_epmodule, alpha2_raw, normalize, probability_dist_aaa`. |
| Operator overlap | Common operators are `ts_std_dev, scale, ts_mean, vec_avg, max, ts_backfill, ts_corr, rank, group_neutralize`. |
| Family overlap | Dominant workbook families are quality/growth/value (6), options/implied volatility (6), tax/accounting fundamentals (6), analyst/model scores (6), risk/credit/volatility (6). |
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
| 404 | EPS Revision Shock Variant 142 | `Jjd533EW` | `hard_pass_signal_seed` | `1.96` | `2.05` | `5.84%` | `n/a` | `SELF_CORRELATION` | `ba40a6df5b395ba8` |
| 405 | EPS Revision Shock Variant 143 | `58v579wM` | `hard_pass_signal_seed` | `1.96` | `2.05` | `5.84%` | `n/a` | `SELF_CORRELATION` | `ba40a6df5b395ba8` |
| 488 | EPS Revision Shock Variant 177 | `Wjga8AQx` | `hard_pass_signal_seed` | `1.89` | `1.93` | `9.52%` | `n/a` | `SELF_CORRELATION` | `207b895b94e624a8` |
| 493 | EPS Revision Shock Variant 181 | `78dmxX9Z` | `hard_pass_signal_seed` | `1.88` | `1.92` | `9.52%` | `n/a` | `SELF_CORRELATION` | `207b895b94e624a8` |
| 498 | EPS Revision Shock Variant 183 | `wpeGYlK1` | `hard_pass_signal_seed` | `1.88` | `1.91` | `9.43%` | `n/a` | `SELF_CORRELATION` | `a2f406fc9486a403` |
| 499 | EPS Revision Shock Variant 184 | `QPQ2xRvM` | `hard_pass_signal_seed` | `1.88` | `1.91` | `9.43%` | `n/a` | `SELF_CORRELATION` | `a2f406fc9486a403` |

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
