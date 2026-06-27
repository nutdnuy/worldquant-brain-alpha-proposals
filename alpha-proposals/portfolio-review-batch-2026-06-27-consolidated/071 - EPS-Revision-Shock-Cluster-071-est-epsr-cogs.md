---
title: "EPS Revision Shock Cluster 071 - est_epsr cogs"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-071
member_count: 2
cluster_basis: "same-field same-operator variant"
representative_alpha: "EPS Revision Shock Variant 75"
created: 2026-06-27
updated: 2026-06-27
---

# EPS Revision Shock Cluster 071 - est_epsr cogs

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** EPS Revision Shock Variant 75 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | price-volume/liquidity/turnover (2), tax/accounting fundamentals (2), earnings/EPS/guidance revisions (2), analyst/model scores (1) |
| Common fields | `est_epsr, cogs, ey, c, cap, fnd6_fopo, close, cost, fe, op, cogs_leg, ern4_fcsterneffct` |
| Common operators | `ts_rank, zscore, ts_backfill, winsorize, scale, vec_avg, abs, group_rank, group_neutralize, ts_mean, rank, trade_when` |
| Best recorded Sharpe | `2` |
| Best recorded Fitness | `2.39` |
| Median turnover | `10.33%` |
| Representative | EPS Revision Shock Variant 75 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> cost = zscore(winsorize(cogs/cap, std=4)); op = zscore(fnd6_fopo/cap); c = ts_mean(cost - 0.25 * op, 2); cogs_leg = group_neutralize(rank(c) * trade_when(rank(abs(c)) > 0.88, c, 0), industry); ey = group_rank(ts_rank(ts_mean(ts_backfill(est_epsr / close, 120), 5), 60), industry); fe = group_rank(ts_mean(vec_avg(ern4_fcsterneffct) - vec_avg(ern4_erneffct1), 63), industry); alpha = trade_when(rank(abs(c)) > 0.65, scale(0.40 * scale(cogs_leg) + 0.36 * scale(ey) + 0.24 * scale(fe)), -1); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `est_epsr, cogs, ey, c, cap, fnd6_fopo, close, cost, fe, op, cogs_leg, ern4_fcsterneffct`. |
| Operator overlap | Common operators are `ts_rank, zscore, ts_backfill, winsorize, scale, vec_avg, abs, group_rank, group_neutralize, ts_mean, rank, trade_when`. |
| Family overlap | Dominant workbook families are price-volume/liquidity/turnover (2), tax/accounting fundamentals (2), earnings/EPS/guidance revisions (2), analyst/model scores (1). |
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
| 264 | EPS Revision Shock Variant 75 | `vRLdzPdd` | `hard_pass_signal_seed` | `2` | `2.39` | `3.17%` | `n/a` | `SELF_CORRELATION` | `75f26dd6472eedf2` |
| 438 | EPS Revision Shock Variant 159 | `blLvWenR` | `hard_pass_signal_seed` | `1.93` | `2` | `10.33%` | `n/a` | `SELF_CORRELATION` | `505f19d3af6dfd3a` |

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
