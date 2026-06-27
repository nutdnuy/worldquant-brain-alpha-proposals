---
title: "EPS Revision Shock Cluster 068 - ern4_erneffct1 mdl53_jc5_10year"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-068
member_count: 2
cluster_basis: "numeric-parameter variant"
representative_alpha: "EPS Revision Shock Variant 52"
created: 2026-06-27
updated: 2026-06-27
---

# EPS Revision Shock Cluster 068 - ern4_erneffct1 mdl53_jc5_10year

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **numeric-parameter variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** EPS Revision Shock Variant 52 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `numeric-parameter variant` |
| Dominant families | analyst/model scores (2), earnings/EPS/guidance revisions (2), risk/credit/volatility (2), quality/growth/value (2) |
| Common fields | `ern4_erneffct1, mdl53_jc5_10year, mdl53_jc5_1year, mdl177_garpanalystmodel_qgp_vfpriceratio, returns, mdl53_jc5_5year, fe, ern4_fcsterneffct, orig, curve, garp, vector_neut` |
| Common operators | `ts_std_dev, ts_backfill, scale, ts_delta, vec_avg, abs, group_rank, ts_mean, rank` |
| Best recorded Sharpe | `2.26` |
| Best recorded Fitness | `2.16` |
| Median turnover | `6.44%` |
| Representative | EPS Revision Shock Variant 52 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> garp = rank(vector_neut(-mdl177_garpanalystmodel_qgp_vfpriceratio * ts_std_dev(mdl177_garpanalystmodel_qgp_vfpriceratio, 30), rank(ts_std_dev(returns, 252)))); fe = group_rank(ts_mean(vec_avg(ern4_fcsterneffct) - vec_avg(ern4_erneffct1), 63), industry); curve = group_rank(((mdl53_jc5_1year + mdl53_jc5_10year) / 2 - mdl53_jc5_5year), industry); orig = scale(0.44 * scale(garp) + 0.34 * scale(fe) + 0.22 * scale(curve)); epsgap = group_rank(ts_backfill(abs(fnd7_ointfund_qxspeo - fnd7_ointhstfund_hqxspeo), 504), industry); idio = group_rank(ts_delta(ts_backfill(unsystematic_risk_last_30_days, 120), 20), industry); rr = scale(0.42 * scale(epsgap) + 0.34 * scale(idio) + 0.24 * scale(fe)); alpha = scale(0.52 * scale(orig) + 0.48 * scale(rr)); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `numeric-parameter variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `ern4_erneffct1, mdl53_jc5_10year, mdl53_jc5_1year, mdl177_garpanalystmodel_qgp_vfpriceratio, returns, mdl53_jc5_5year, fe, ern4_fcsterneffct, orig, curve, garp, vector_neut`. |
| Operator overlap | Common operators are `ts_std_dev, ts_backfill, scale, ts_delta, vec_avg, abs, group_rank, ts_mean, rank`. |
| Family overlap | Dominant workbook families are analyst/model scores (2), earnings/EPS/guidance revisions (2), risk/credit/volatility (2), quality/growth/value (2). |
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
| 224 | EPS Revision Shock Variant 52 | `VkpOXv50` | `hard_pass_signal_seed` | `2.26` | `2.15` | `6.44%` | `n/a` | `SELF_CORRELATION` | `c57fbd2f35c48d75` |
| 236 | EPS Revision Shock Variant 59 | `GrwkMXQ0` | `hard_pass_signal_seed` | `2.23` | `2.16` | `6.33%` | `n/a` | `SELF_CORRELATION` | `bbe48ede96f006b1` |

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
