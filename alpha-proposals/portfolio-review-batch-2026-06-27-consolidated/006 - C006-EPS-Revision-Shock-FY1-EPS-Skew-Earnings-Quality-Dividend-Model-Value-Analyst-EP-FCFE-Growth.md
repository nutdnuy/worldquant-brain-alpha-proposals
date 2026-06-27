---
title: "C006 - EPS Revision Shock - FY1 EPS Skew + Earnings Quality + Dividend Model + Value Analyst EP + FCFE Growth"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-006
member_count: 14
cluster_basis: "same-field same-operator variant"
representative_alpha: "EPS Revision Shock Variant 111"
created: 2026-06-27
updated: 2026-06-27
---

# C006 - EPS Revision Shock - FY1 EPS Skew + Earnings Quality + Dividend Model + Value Analyst EP + FCFE Growth

> [!abstract] Consolidated Thesis
> This note combines **14** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** EPS Revision Shock Variant 111 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `14` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | analyst/model scores (14), quality/growth/value (14), earnings/EPS/guidance revisions (14), options/implied volatility (14) |
| Common fields | `alpha3_raw, alpha2_raw, alpha1_raw, mdl77_2gdna_sighc, mdl177_2_earningmomentumfactor400_fy1epsskew, mdl77_2valuemomemtummodel_earningsqualitymodule, mdl177_fangma_dvm_usa_fangma_dvm2, alpha1, normalize, mdl77_ohistoricalgrowthfactor_fcfequity, useStd, mdl77_valueanalystmodelqva_epmodule` |
| Common operators | `winsorize, max, ts_corr, zscore, signed_power, abs, rank, ts_mean, ts_std_dev, scale, ts_backfill, group_neutralize` |
| Best recorded Sharpe | `2.13` |
| Best recorded Fitness | `2.01` |
| Median turnover | `12.08%` |
| Representative | EPS Revision Shock Variant 111 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1_raw = -(ts_corr(rank(mdl177_2_earningmomentumfactor400_fy1epsskew), rank(ts_backfill(mdl77_2gdna_sighc, 250)), 20)); alpha2_raw = -((mdl77_2valuemomemtummodel_earningsqualitymodule - ts_backfill(mdl177_fangma_dvm_usa_fangma_dvm2, 21)) / (abs(mdl77_2valuemomemtummodel_earningsqualitymodule) + abs(ts_backfill(mdl177_fangma_dvm_usa_fangma_dvm2, 21)) + 0.0001)); alpha3_raw = signed_power(winsorize(zscore(group_neutralize(mdl77_valueanalystmodelqva_epmodule - mdl77_ohistoricalgrowthfactor_fcfequity, industry)), std=4), 1.5); alpha1 = scale(normalize(alpha1_raw, useStd=true, limit=3)); alpha2 = scale(normalize(alpha2_raw, useStd=true, limit=3)); alpha3 = scale(normalize(alpha3_raw, useStd=true, limit=3)); vol1 = ts_backfill(ts_std_dev(alpha1 * returns, 60), 120); vol2 = ts_backfill(ts_std_dev(alpha2 * returns, 60), 120); vol3 = ts_backfill(ts_std_dev(alpha3 * returns, 60), 120); iv1 = 1 / max(vol1, 0.0001); iv2 = 1 / max(vol2, 0.0001); iv3 = 1 / max(vol3, 0.0001); iv_sum = iv1 + iv2 + iv3; w1_raw = iv1 / iv_sum; w2_raw = iv2 / iv_sum; w3_raw = iv3 / iv_sum; w1 = ts_mean(w1_raw, 20); w2 = ts_mean(w2_raw, 20); w3 = ts_mean(w3_raw, 20); alpha = scale(w1 * alpha1 + w2 * alpha2 + w3 * alpha3); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha3_raw, alpha2_raw, alpha1_raw, mdl77_2gdna_sighc, mdl177_2_earningmomentumfactor400_fy1epsskew, mdl77_2valuemomemtummodel_earningsqualitymodule, mdl177_fangma_dvm_usa_fangma_dvm2, alpha1, normalize, mdl77_ohistoricalgrowthfactor_fcfequity, useStd, mdl77_valueanalystmodelqva_epmodule`. |
| Operator overlap | Common operators are `winsorize, max, ts_corr, zscore, signed_power, abs, rank, ts_mean, ts_std_dev, scale, ts_backfill, group_neutralize`. |
| Family overlap | Dominant workbook families are analyst/model scores (14), quality/growth/value (14), earnings/EPS/guidance revisions (14), options/implied volatility (14). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 14 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 14 |
| pending: `SELF_CORRELATION` | 14 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 340 | EPS Revision Shock Variant 111 | `YPA2V1mA` | `hard_pass_signal_seed` | `2.13` | `2.01` | `11.93%` | `n/a` | `SELF_CORRELATION` | `ec86f40895bfd77f` |
| 342 | EPS Revision Shock Variant 113 | `E5KzvVvJ` | `hard_pass_signal_seed` | `2.13` | `2.01` | `11.93%` | `n/a` | `SELF_CORRELATION` | `ec86f40895bfd77f` |
| 334 | EPS Revision Shock Variant 105 | `wpenjoal` | `hard_pass_signal_seed` | `2.13` | `2.01` | `12.07%` | `n/a` | `SELF_CORRELATION` | `2222be47e624f323` |
| 335 | EPS Revision Shock Variant 106 | `vRmG5EVz` | `hard_pass_signal_seed` | `2.13` | `2.01` | `12.07%` | `n/a` | `SELF_CORRELATION` | `80fc84bf606755da` |
| 336 | EPS Revision Shock Variant 107 | `mLX78Nvx` | `hard_pass_signal_seed` | `2.13` | `2.01` | `12.07%` | `n/a` | `SELF_CORRELATION` | `2222be47e624f323` |
| 337 | EPS Revision Shock Variant 108 | `le0Qx7zn` | `hard_pass_signal_seed` | `2.13` | `2.01` | `12.07%` | `n/a` | `SELF_CORRELATION` | `80fc84bf606755da` |
| 343 | EPS Revision Shock Variant 114 | `88LJpMlo` | `hard_pass_signal_seed` | `2.13` | `2.01` | `12.26%` | `n/a` | `SELF_CORRELATION` | `5ba99c3d110c1621` |
| 338 | EPS Revision Shock Variant 109 | `le0QN9XO` | `hard_pass_signal_seed` | `2.13` | `2.01` | `12.26%` | `n/a` | `SELF_CORRELATION` | `5ba99c3d110c1621` |
| 339 | EPS Revision Shock Variant 110 | `e7rGdoml` | `hard_pass_signal_seed` | `2.13` | `2.01` | `12.26%` | `n/a` | `SELF_CORRELATION` | `90dacc68d006bc28` |
| 341 | EPS Revision Shock Variant 112 | `KPLX0YRg` | `hard_pass_signal_seed` | `2.13` | `2.01` | `12.26%` | `n/a` | `SELF_CORRELATION` | `90dacc68d006bc28` |
| 352 | EPS Revision Shock Variant 119 | `WjgWxVoN` | `hard_pass_signal_seed` | `2.12` | `1.99` | `12.15%` | `n/a` | `SELF_CORRELATION` | `086983b2e9d42654` |
| 353 | EPS Revision Shock Variant 120 | `78dm0P8x` | `hard_pass_signal_seed` | `2.12` | `1.99` | `12.15%` | `n/a` | `SELF_CORRELATION` | `086983b2e9d42654` |
| 361 | EPS Revision Shock Variant 125 | `e7rdKXzz` | `hard_pass_signal_seed` | `2.11` | `1.98` | `12.08%` | `n/a` | `SELF_CORRELATION` | `8cab763d79268180` |
| 362 | EPS Revision Shock Variant 126 | `RRrzrmOj` | `hard_pass_signal_seed` | `2.11` | `1.98` | `12.08%` | `n/a` | `SELF_CORRELATION` | `8cab763d79268180` |

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
