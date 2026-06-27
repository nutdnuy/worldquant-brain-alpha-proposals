---
title: "Cross Sectional Signal Momentum Cluster 041 - fnd6_txws"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-041
member_count: 3
cluster_basis: "exact-expression duplicate"
representative_alpha: "Cross Sectional Signal Momentum Variant 5"
created: 2026-06-27
updated: 2026-06-27
---

# Cross Sectional Signal Momentum Cluster 041 - fnd6_txws

> [!abstract] Consolidated Thesis
> This note combines **3** highly similar alpha proposals into one research idea. The consolidation basis is **exact-expression duplicate**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Cross Sectional Signal Momentum Variant 5 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `3` |
| Cluster basis | `exact-expression duplicate` |
| Dominant families | tax/accounting fundamentals (3) |
| Common fields | `fnd6_txws` |
| Common operators | `ts_decay_linear, vec_avg, group_rank, ts_backfill` |
| Best recorded Sharpe | `2.11` |
| Best recorded Fitness | `2.84` |
| Median turnover | `2.95%` |
| Representative | Cross Sectional Signal Momentum Variant 5 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector)
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `exact-expression duplicate` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `fnd6_txws`. |
| Operator overlap | Common operators are `ts_decay_linear, vec_avg, group_rank, ts_backfill`. |
| Family overlap | Dominant workbook families are tax/accounting fundamentals (3). |
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
| 139 | Cross Sectional Signal Momentum Variant 5 | `78dRQq52` | `hard_pass_signal_seed` | `2.11` | `2.84` | `2.95%` | `n/a` | `SELF_CORRELATION` | `c7047756232a2ed9` |
| 140 | Cross Sectional Signal Momentum Variant 6 | `3qA7jYE0` | `hard_pass_signal_seed` | `2.11` | `2.84` | `2.95%` | `n/a` | `SELF_CORRELATION` | `c7047756232a2ed9` |
| 141 | Cross Sectional Signal Momentum Variant 7 | `n/a` | `hard_pass_signal_seed` | `2.11` | `2.84` | `2.95%` | `n/a` | `SELF_CORRELATION` | `c7047756232a2ed9` |

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
