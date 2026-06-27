---
title: "EPS Revision Shock Cluster 018 - mdl177_2_earningmomentumfactor400_fy1epssk"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-018
member_count: 6
cluster_basis: "same-field same-operator variant"
representative_alpha: "EPS Revision Shock Variant 138"
created: 2026-06-27
updated: 2026-06-27
---

# EPS Revision Shock Cluster 018 - mdl177_2_earningmomentumfactor400_fy1epssk

> [!abstract] Consolidated Thesis
> This note combines **6** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** EPS Revision Shock Variant 138 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `6` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | quality/growth/value (6), options/implied volatility (6), analyst/model scores (6), risk/credit/volatility (6), earnings/EPS/guidance revisions (6) |
| Common fields | `alpha1, mdl177_2_earningmomentumfactor400_fy1epsskew, alpha1_raw, annualized_pd_10_year_jm5, mdl77_2gdna_sighc, probability_dist_aaa, useStd, alpha3_raw, mdl77_ohistoricalgrowthfactor_fcfequity, mdl77_valueanalystmodelqva_epmodule, alpha2_raw, normalize` |
| Common operators | `signed_power, zscore, scale, winsorize, ts_std_dev, ts_mean, max, ts_backfill, ts_corr, rank, group_neutralize` |
| Best recorded Sharpe | `2.02` |
| Best recorded Fitness | `1.98` |
| Median turnover | `12.32%` |
| Representative | EPS Revision Shock Variant 138 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1_raw = -(ts_corr(rank(mdl177_2_earningmomentumfactor400_fy1epsskew), rank(ts_backfill(mdl77_2gdna_sighc, 250)), 20)); alpha2_raw = -(ts_corr(rank(ts_backfill(probability_dist_aaa, 63)), rank(ts_backfill(annualized_pd_10_year_jm5, 63)), 60)); alpha3_raw = winsorize(zscore(signed_power(winsorize(zscore(mdl77_valueanalystmodelqva_epmodule - mdl77_ohistoricalgrowthfactor_fcfequity), std=4), 1.5)), std=4); alpha1 = scale(normalize(alpha1_raw, useStd=true, limit=3)); alpha2 = scale(normalize(alpha2_raw, useStd=true, limit=3)); alpha3 = scale(normalize(alpha3_raw, useStd=true, limit=3)); vol1 = ts_backfill(ts_std_dev(alpha1 * returns, 60), 120); vol2 = ts_backfill(ts_std_dev(alpha2 * returns, 60), 120); vol3 = ts_backfill(ts_std_dev(alpha3 * returns, 60), 120); iv1 = 1 / max(vol1, 0.0001); iv2 = 1 / max(vol2, 0.0001); iv3 = 1 / max(vol3, 0.0001); iv_sum = iv1 + iv2 + iv3; w1_raw = iv1 / iv_sum; w2_raw = iv2 / iv_sum; w3_raw = iv3 / iv_sum; w1 = ts_mean(w1_raw, 20); w2 = ts_mean(w2_raw, 20); w3 = ts_mean(w3_raw, 20); alpha = scale(w1 * alpha1 + w2 * alpha2 + w3 * alpha3); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha1, mdl177_2_earningmomentumfactor400_fy1epsskew, alpha1_raw, annualized_pd_10_year_jm5, mdl77_2gdna_sighc, probability_dist_aaa, useStd, alpha3_raw, mdl77_ohistoricalgrowthfactor_fcfequity, mdl77_valueanalystmodelqva_epmodule, alpha2_raw, normalize`. |
| Operator overlap | Common operators are `signed_power, zscore, scale, winsorize, ts_std_dev, ts_mean, max, ts_backfill, ts_corr, rank, group_neutralize`. |
| Family overlap | Dominant workbook families are quality/growth/value (6), options/implied volatility (6), analyst/model scores (6), risk/credit/volatility (6), earnings/EPS/guidance revisions (6). |
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
| 400 | EPS Revision Shock Variant 138 | `QPQz2wGQ` | `hard_pass_signal_seed` | `2.02` | `1.98` | `12.32%` | `n/a` | `SELF_CORRELATION` | `509060eb8c1acfba` |
| 403 | EPS Revision Shock Variant 141 | `1YgaQX2R` | `hard_pass_signal_seed` | `2.02` | `1.98` | `12.32%` | `n/a` | `SELF_CORRELATION` | `509060eb8c1acfba` |
| 401 | EPS Revision Shock Variant 139 | `6XEaAkXO` | `hard_pass_signal_seed` | `2.02` | `1.98` | `12.33%` | `n/a` | `SELF_CORRELATION` | `32cab9d547270345` |
| 402 | EPS Revision Shock Variant 140 | `58v5pVRJ` | `hard_pass_signal_seed` | `2.02` | `1.98` | `12.33%` | `n/a` | `SELF_CORRELATION` | `32cab9d547270345` |
| 418 | EPS Revision Shock Variant 147 | `YPAzb9zo` | `hard_pass_signal_seed` | `2` | `1.95` | `12.17%` | `n/a` | `SELF_CORRELATION` | `8441311789feed5f` |
| 419 | EPS Revision Shock Variant 148 | `1YgoYqlW` | `hard_pass_signal_seed` | `2` | `1.95` | `12.17%` | `n/a` | `SELF_CORRELATION` | `8441311789feed5f` |

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
