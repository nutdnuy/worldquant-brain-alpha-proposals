---
title: "C024 - EPS Revision Shock - GARP Analyst Value + Credit Curve"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-024
member_count: 5
cluster_basis: "high-similarity field/operator/family cluster"
representative_alpha: "EPS Revision Shock Variant 52"
created: 2026-06-27
updated: 2026-06-27
---

# C024 - EPS Revision Shock - GARP Analyst Value + Credit Curve

> [!abstract] Consolidated Thesis
> This note combines **5** highly similar alpha proposals into one research idea. The consolidation basis is **high-similarity field/operator/family cluster**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** EPS Revision Shock Variant 52 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `5` |
| Cluster basis | `high-similarity field/operator/family cluster` |
| Dominant families | analyst/model scores (5), quality/growth/value (5), earnings/EPS/guidance revisions (5), risk/credit/volatility (2) |
| Common fields | `returns, garp, mdl53_jc5_5year, mdl53_jc5_10year, vector_neut, ern4_fcsterneffct, mdl177_garpanalystmodel_qgp_vfpriceratio, fe, ern4_erneffct1, curve, mdl53_jc5_1year, alpha` |
| Common operators | `scale, group_rank, rank, vec_avg, ts_std_dev, ts_mean, ts_delta, ts_backfill, abs` |
| Best recorded Sharpe | `2.27` |
| Best recorded Fitness | `2.16` |
| Median turnover | `4.74%` |
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
| Expression similarity | `high-similarity field/operator/family cluster` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `returns, garp, mdl53_jc5_5year, mdl53_jc5_10year, vector_neut, ern4_fcsterneffct, mdl177_garpanalystmodel_qgp_vfpriceratio, fe, ern4_erneffct1, curve, mdl53_jc5_1year, alpha`. |
| Operator overlap | Common operators are `scale, group_rank, rank, vec_avg, ts_std_dev, ts_mean, ts_delta, ts_backfill, abs`. |
| Family overlap | Dominant workbook families are analyst/model scores (5), quality/growth/value (5), earnings/EPS/guidance revisions (5), risk/credit/volatility (2). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 5 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 5 |
| pending: `SELF_CORRELATION` | 5 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 224 | EPS Revision Shock Variant 52 | `VkpOXv50` | `hard_pass_signal_seed` | `2.26` | `2.15` | `6.44%` | `n/a` | `SELF_CORRELATION` | `c57fbd2f35c48d75` |
| 230 | EPS Revision Shock Variant 55 | `YPpQnmY6` | `hard_pass_signal_seed` | `2.27` | `2.12` | `4.53%` | `n/a` | `SELF_CORRELATION` | `92daf602b03cb363` |
| 231 | EPS Revision Shock Variant 56 | `2r7JQK65` | `hard_pass_signal_seed` | `2.24` | `2.16` | `4.74%` | `n/a` | `SELF_CORRELATION` | `f3de7f5c7d423c51` |
| 236 | EPS Revision Shock Variant 59 | `GrwkMXQ0` | `hard_pass_signal_seed` | `2.23` | `2.16` | `6.33%` | `n/a` | `SELF_CORRELATION` | `bbe48ede96f006b1` |
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
