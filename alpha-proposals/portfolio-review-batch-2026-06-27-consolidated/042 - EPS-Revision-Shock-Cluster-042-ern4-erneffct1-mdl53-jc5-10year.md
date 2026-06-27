---
title: "EPS Revision Shock Cluster 042 - ern4_erneffct1 mdl53_jc5_10year"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-042
member_count: 3
cluster_basis: "high-similarity field/operator/family cluster"
representative_alpha: "EPS Revision Shock Variant 55"
created: 2026-06-27
updated: 2026-06-27
---

# EPS Revision Shock Cluster 042 - ern4_erneffct1 mdl53_jc5_10year

> [!abstract] Consolidated Thesis
> This note combines **3** highly similar alpha proposals into one research idea. The consolidation basis is **high-similarity field/operator/family cluster**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** EPS Revision Shock Variant 55 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `3` |
| Cluster basis | `high-similarity field/operator/family cluster` |
| Dominant families | analyst/model scores (3), earnings/EPS/guidance revisions (3), quality/growth/value (3) |
| Common fields | `ern4_erneffct1, mdl53_jc5_10year, mdl53_jc5_1year, mdl177_garpanalystmodel_qgp_vfpriceratio, returns, mdl53_jc5_5year, fe, ern4_fcsterneffct, curve, garp, vector_neut, alpha` |
| Common operators | `ts_std_dev, scale, vec_avg, group_rank, ts_mean, rank` |
| Best recorded Sharpe | `2.27` |
| Best recorded Fitness | `2.16` |
| Median turnover | `4.62%` |
| Representative | EPS Revision Shock Variant 55 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> garp = rank(vector_neut(-mdl177_garpanalystmodel_qgp_vfpriceratio * ts_std_dev(mdl177_garpanalystmodel_qgp_vfpriceratio, 30), rank(ts_std_dev(returns, 252)))); fe = group_rank(ts_mean(vec_avg(ern4_fcsterneffct) - vec_avg(ern4_erneffct1), 63), industry); curve = group_rank(((mdl53_jc5_1year + mdl53_jc5_10year) / 2 - mdl53_jc5_5year), industry); alpha = scale(0.24 * scale(garp) + 0.46 * scale(fe) + 0.30 * scale(curve)); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `high-similarity field/operator/family cluster` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `ern4_erneffct1, mdl53_jc5_10year, mdl53_jc5_1year, mdl177_garpanalystmodel_qgp_vfpriceratio, returns, mdl53_jc5_5year, fe, ern4_fcsterneffct, curve, garp, vector_neut, alpha`. |
| Operator overlap | Common operators are `ts_std_dev, scale, vec_avg, group_rank, ts_mean, rank`. |
| Family overlap | Dominant workbook families are analyst/model scores (3), earnings/EPS/guidance revisions (3), quality/growth/value (3). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 3 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 3 |
| pending: `SELF_CORRELATION` | 3 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 230 | EPS Revision Shock Variant 55 | `YPpQnmY6` | `hard_pass_signal_seed` | `2.27` | `2.12` | `4.53%` | `n/a` | `SELF_CORRELATION` | `92daf602b03cb363` |
| 231 | EPS Revision Shock Variant 56 | `2r7JQK65` | `hard_pass_signal_seed` | `2.24` | `2.16` | `4.74%` | `n/a` | `SELF_CORRELATION` | `f3de7f5c7d423c51` |
| 285 | EPS Revision Shock Variant 83 | `ZYprqvY1` | `hard_pass_signal_seed` | `2.2` | `2.06` | `4.62%` | `n/a` | `SELF_CORRELATION` | `31b3621b04933ea5` |

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
