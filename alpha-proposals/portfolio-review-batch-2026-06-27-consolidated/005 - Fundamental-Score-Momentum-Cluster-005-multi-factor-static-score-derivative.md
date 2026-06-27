---
title: "Fundamental Score Momentum Cluster 005 - multi_factor_static_score_derivative"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-005
member_count: 14
cluster_basis: "same-field same-operator variant"
representative_alpha: "Fundamental Score Momentum"
created: 2026-06-27
updated: 2026-06-27
---

# Fundamental Score Momentum Cluster 005 - multi_factor_static_score_derivative

> [!abstract] Consolidated Thesis
> This note combines **14** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Fundamental Score Momentum is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `14` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | unclassified/structural (14) |
| Common fields | `multi_factor_static_score_derivative` |
| Common operators | `ts_backfill, rank, ts_zscore` |
| Best recorded Sharpe | `2.33` |
| Best recorded Fitness | `4.9` |
| Median turnover | `7.45%` |
| Representative | Fundamental Score Momentum |
| Representative bucket | `strong_signal_repair_seed` |
| Representative failed checks | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` |
| Representative pending checks | `n/a` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> rank(ts_zscore(ts_backfill(ts_backfill(multi_factor_static_score_derivative, 252), 220, k=1), 20))
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `multi_factor_static_score_derivative`. |
| Operator overlap | Common operators are `ts_backfill, rank, ts_zscore`. |
| Family overlap | Dominant workbook families are unclassified/structural (14). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `failed-checks-strong-signal-repair-candidate` | 14 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | 14 |
| pending: `n/a` | 14 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 4 | Fundamental Score Momentum | `om9zb362` | `strong_signal_repair_seed` | `2.33` | `4.9` | `7.01%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `c2da7bf71014f7ab` |
| 5 | Fundamental Score Momentum Variant 2 | `akWAwMdw` | `strong_signal_repair_seed` | `2.33` | `4.9` | `7.01%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `34a8f95e2025b951` |
| 6 | Fundamental Score Momentum Variant 3 | `MP5lQa2a` | `strong_signal_repair_seed` | `2.33` | `4.9` | `7.01%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `d04c015d8f4bc6f3` |
| 7 | Fundamental Score Momentum Variant 4 | `E5r0vkGr` | `strong_signal_repair_seed` | `2.33` | `4.9` | `7.01%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `a405d0bb5d78c2cf` |
| 8 | Fundamental Score Momentum Variant 5 | `88KO8aLa` | `strong_signal_repair_seed` | `2.33` | `4.9` | `7.01%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `ca8fa7351e8e21e4` |
| 446 | Fundamental Score Momentum Variant 8 | `zqJwMavX` | `strong_signal_repair_seed` | `1.81` | `2.81` | `7.45%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `d04c015d8f4bc6f3` |
| 447 | Fundamental Score Momentum Variant 9 | `xAmXkRem` | `strong_signal_repair_seed` | `1.81` | `2.81` | `7.45%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `c2da7bf71014f7ab` |
| 448 | Fundamental Score Momentum Variant 10 | `mLxe2Yk6` | `strong_signal_repair_seed` | `1.81` | `2.81` | `7.45%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `a405d0bb5d78c2cf` |
| 449 | Fundamental Score Momentum Variant 11 | `e7q8adrO` | `strong_signal_repair_seed` | `1.81` | `2.81` | `7.45%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `c2da7bf71014f7ab` |
| 450 | Fundamental Score Momentum Variant 12 | `XgYlVoaz` | `strong_signal_repair_seed` | `1.81` | `2.81` | `7.45%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `a405d0bb5d78c2cf` |
| 451 | Fundamental Score Momentum Variant 13 | `WjWK6Rdj` | `strong_signal_repair_seed` | `1.81` | `2.81` | `7.45%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `d04c015d8f4bc6f3` |
| 452 | Fundamental Score Momentum Variant 14 | `58q6mLWX` | `strong_signal_repair_seed` | `1.81` | `2.81` | `7.45%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `ca8fa7351e8e21e4` |
| 453 | Fundamental Score Momentum Variant 15 | `3qngRbEX` | `strong_signal_repair_seed` | `1.81` | `2.81` | `7.45%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `34a8f95e2025b951` |
| 454 | Fundamental Score Momentum Variant 16 | `3qnYogOz` | `strong_signal_repair_seed` | `1.81` | `2.81` | `7.45%` | `CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `34a8f95e2025b951` |

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
