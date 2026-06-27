---
title: "C084 - Cross Sectional Signal Momentum - F-Score Growth"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-084
member_count: 2
cluster_basis: "same-field same-operator variant"
representative_alpha: "Cross Sectional Signal Momentum Variant 3"
created: 2026-06-27
updated: 2026-06-27
---

# C084 - Cross Sectional Signal Momentum - F-Score Growth

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Cross Sectional Signal Momentum Variant 3 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | analyst/model scores (2), quality/growth/value (2) |
| Common fields | `fscore_growth` |
| Common operators | `ts_delta, rank` |
| Best recorded Sharpe | `4.97` |
| Best recorded Fitness | `1.46` |
| Median turnover | `100.00%` |
| Representative | Cross Sectional Signal Momentum Variant 3 |
| Representative bucket | `strong_signal_repair_seed` |
| Representative failed checks | `HIGH_TURNOVER; CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> -rank(ts_delta(fscore_growth, 10))
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `fscore_growth`. |
| Operator overlap | Common operators are `ts_delta, rank`. |
| Family overlap | Dominant workbook families are analyst/model scores (2), quality/growth/value (2). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `failed-checks-strong-signal-repair-candidate` | 2 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `HIGH_TURNOVER; CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | 2 |
| pending: `SELF_CORRELATION` | 2 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 36 | Cross Sectional Signal Momentum Variant 3 | `KP6W9kMp` | `strong_signal_repair_seed` | `4.97` | `1.35` | `100.00%` | `HIGH_TURNOVER; CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `3f0a652f780cdb35` |
| 290 | Cross Sectional Signal Momentum Variant 13 | `qMdQ6k8v` | `strong_signal_repair_seed` | `3.88` | `1.46` | `100.00%` | `HIGH_TURNOVER; CONCENTRATED_WEIGHT; LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `1709d0e279bca5df` |

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
