---
title: "C048 - Tax Cash Flow Capital Momentum - Tax Book Cash Flow + Capital Cost Base"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-048
member_count: 3
cluster_basis: "numeric-parameter variant"
representative_alpha: "Tax Cash Flow Capital Momentum Variant 2"
created: 2026-06-27
updated: 2026-06-27
---

# C048 - Tax Cash Flow Capital Momentum - Tax Book Cash Flow + Capital Cost Base

> [!abstract] Consolidated Thesis
> This note combines **3** highly similar alpha proposals into one research idea. The consolidation basis is **numeric-parameter variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Tax Cash Flow Capital Momentum Variant 2 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `3` |
| Cluster basis | `numeric-parameter variant` |
| Dominant families | tax/accounting fundamentals (3) |
| Common fields | `fnd6_txbcof, cap` |
| Common operators | `ts_delta, zscore` |
| Best recorded Sharpe | `2.78` |
| Best recorded Fitness | `4.44` |
| Median turnover | `8.17%` |
| Representative | Tax Cash Flow Capital Momentum Variant 2 |
| Representative bucket | `strong_signal_repair_seed` |
| Representative failed checks | `CONCENTRATED_WEIGHT` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> zscore(ts_delta(fnd6_txbcof, 66) / cap)
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `numeric-parameter variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `fnd6_txbcof, cap`. |
| Operator overlap | Common operators are `ts_delta, zscore`. |
| Family overlap | Dominant workbook families are tax/accounting fundamentals (3). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `failed-checks-strong-signal-repair-candidate` | 3 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `CONCENTRATED_WEIGHT` | 3 |
| pending: `SELF_CORRELATION` | 2 |
| pending: `n/a` | 1 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 3 | Tax Cash Flow Capital Momentum Variant 2 | `RRkMXYV1` | `strong_signal_repair_seed` | `2.78` | `4.44` | `8.28%` | `CONCENTRATED_WEIGHT` | `SELF_CORRELATION` | `bbb4fbae47b47be4` |
| 48 | Tax Cash Flow Capital Momentum Variant 3 | `0mQ6mArG` | `strong_signal_repair_seed` | `2.41` | `3.63` | `8.03%` | `CONCENTRATED_WEIGHT` | `n/a` | `e70c968e71b922b0` |
| 59 | Tax Cash Flow Capital Momentum Variant 4 | `1YnevYkX` | `strong_signal_repair_seed` | `2.38` | `3.6` | `8.17%` | `CONCENTRATED_WEIGHT` | `SELF_CORRELATION` | `bbb4fbae47b47be4` |

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
