---
title: "Price Volume Reversal Cluster 052 - change_day close"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-052
member_count: 2
cluster_basis: "exact-expression duplicate"
representative_alpha: "Price Volume Reversal Variant 7"
created: 2026-06-27
updated: 2026-06-27
---

# Price Volume Reversal Cluster 052 - change_day close

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **exact-expression duplicate**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Price Volume Reversal Variant 7 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `exact-expression duplicate` |
| Dominant families | price-volume/liquidity/turnover (2) |
| Common fields | `change_day, close, vwap, ts_decay_exp_window` |
| Common operators | `rank` |
| Best recorded Sharpe | `1.4` |
| Best recorded Fitness | `2.86` |
| Median turnover | `n/a` |
| Representative | Price Volume Reversal Variant 7 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `n/a` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> change_day = (vwap - close) / close; ts_decay_exp_window(rank(change_day), 4)
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `exact-expression duplicate` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `change_day, close, vwap, ts_decay_exp_window`. |
| Operator overlap | Common operators are `rank`. |
| Family overlap | Dominant workbook families are price-volume/liquidity/turnover (2). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 2 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 2 |
| pending: `n/a` | 2 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 385 | Price Volume Reversal Variant 7 | `alpha_092` | `hard_pass_signal_seed` | `1.4` | `2.86` | `n/a` | `n/a` | `n/a` | `32369fa3c6d47b9b` |
| 386 | Price Volume Reversal Variant 8 | `alpha_027` | `hard_pass_signal_seed` | `1.4` | `2.86` | `n/a` | `n/a` | `n/a` | `32369fa3c6d47b9b` |

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
