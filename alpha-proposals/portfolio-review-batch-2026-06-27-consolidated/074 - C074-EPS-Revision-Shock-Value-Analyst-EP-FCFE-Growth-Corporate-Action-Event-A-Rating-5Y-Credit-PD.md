---
title: "C074 - EPS Revision Shock - Value Analyst EP + FCFE Growth + Corporate Action Event + A- Rating + 5Y Credit PD"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-074
member_count: 2
cluster_basis: "exact-expression duplicate"
representative_alpha: "EPS Revision Shock Variant 123"
created: 2026-06-27
updated: 2026-06-27
---

# C074 - EPS Revision Shock - Value Analyst EP + FCFE Growth + Corporate Action Event + A- Rating + 5Y Credit PD

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **exact-expression duplicate**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** EPS Revision Shock Variant 123 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `exact-expression duplicate` |
| Dominant families | risk/credit/volatility (2), analyst/model scores (2), quality/growth/value (2), options/implied volatility (2) |
| Common fields | `alpha3_raw, alpha2_raw, alpha1_raw, fnd6_newqeventv110_dpactq, alpha1, annualized_pd_5_year_jc7, normalize, mdl77_ohistoricalgrowthfactor_fcfequity, limit, useStd, mdl77_valueanalystmodelqva_epmodule, probability_dist_a_minus` |
| Common operators | `ts_arg_min, winsorize, max, ts_corr, group_rank, zscore, signed_power, rank, vec_avg, ts_mean, ts_std_dev, scale` |
| Best recorded Sharpe | `2.02` |
| Best recorded Fitness | `2.11` |
| Median turnover | `5.41%` |
| Representative | EPS Revision Shock Variant 123 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1_raw = -(ts_corr(rank(ts_backfill(probability_dist_a_minus, 63)), rank(ts_backfill(annualized_pd_5_year_jc7, 63)), 60)); alpha2_raw = group_rank(ts_arg_min(ts_backfill(vec_avg(fnd6_newqeventv110_dpactq), 120), 5), sector); alpha3_raw = signed_power(winsorize(zscore(group_neutralize(mdl77_valueanalystmodelqva_epmodule - mdl77_ohistoricalgrowthfactor_fcfequity, sector)), std=4), 1.5); alpha1 = scale(normalize(alpha1_raw, useStd=true, limit=3)); alpha2 = scale(normalize(alpha2_raw, useStd=true, limit=3)); alpha3 = scale(normalize(alpha3_raw, useStd=true, limit=3)); vol1 = ts_backfill(ts_std_dev(alpha1 * returns, 60), 120); vol2 = ts_backfill(ts_std_dev(alpha2 * returns, 60), 120); vol3 = ts_backfill(ts_std_dev(alpha3 * returns, 60), 120); iv1 = 1 / max(vol1, 0.0001); iv2 = 1 / max(vol2, 0.0001); iv3 = 1 / max(vol3, 0.0001); iv_sum = iv1 + iv2 + iv3; w1_raw = iv1 / iv_sum; w2_raw = iv2 / iv_sum; w3_raw = iv3 / iv_sum; w1 = ts_mean(w1_raw, 20); w2 = ts_mean(w2_raw, 20); w3 = ts_mean(w3_raw, 20); alpha = scale(w1 * alpha1 + w2 * alpha2 + w3 * alpha3); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `exact-expression duplicate` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha3_raw, alpha2_raw, alpha1_raw, fnd6_newqeventv110_dpactq, alpha1, annualized_pd_5_year_jc7, normalize, mdl77_ohistoricalgrowthfactor_fcfequity, limit, useStd, mdl77_valueanalystmodelqva_epmodule, probability_dist_a_minus`. |
| Operator overlap | Common operators are `ts_arg_min, winsorize, max, ts_corr, group_rank, zscore, signed_power, rank, vec_avg, ts_mean, ts_std_dev, scale`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (2), analyst/model scores (2), quality/growth/value (2), options/implied volatility (2). |
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
| 359 | EPS Revision Shock Variant 123 | `d5Qzd2jX` | `hard_pass_signal_seed` | `2.02` | `2.11` | `5.41%` | `n/a` | `SELF_CORRELATION` | `80c30c4cee8f5530` |
| 360 | EPS Revision Shock Variant 124 | `O09bKoav` | `hard_pass_signal_seed` | `2.02` | `2.11` | `5.41%` | `n/a` | `SELF_CORRELATION` | `80c30c4cee8f5530` |

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
