---
title: "Cross Sectional Signal Momentum Cluster 056 - weight_raw fnd6_txws"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-056
member_count: 2
cluster_basis: "same-field same-operator variant"
representative_alpha: "Cross Sectional Signal Momentum Variant 4"
created: 2026-06-27
updated: 2026-06-27
---

# Cross Sectional Signal Momentum Cluster 056 - weight_raw fnd6_txws

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Cross Sectional Signal Momentum Variant 4 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | tax/accounting fundamentals (2), risk/credit/volatility (2) |
| Common fields | `weight_raw, fnd6_txws, weight_strength, conviction, alphamix, direction, unsystematic_risk_last_60_days` |
| Common operators | `if_else, ts_zscore, ts_delta, vec_avg, abs, ts_decay_linear, group_rank, ts_backfill, rank, group_neutralize` |
| Best recorded Sharpe | `2.36` |
| Best recorded Fitness | `3.11` |
| Median turnover | `10.12%` |
| Representative | Cross Sectional Signal Momentum Variant 4 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> direction = group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector); weight_raw = group_rank(ts_zscore(ts_delta(ts_backfill(unsystematic_risk_last_60_days, 20), 90), 90), sector); weight_strength = rank(abs(weight_raw)); conviction = if_else(weight_strength > 0.85, 1.30, 1.00); alphamix = direction * conviction; alphamix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `weight_raw, fnd6_txws, weight_strength, conviction, alphamix, direction, unsystematic_risk_last_60_days`. |
| Operator overlap | Common operators are `if_else, ts_zscore, ts_delta, vec_avg, abs, ts_decay_linear, group_rank, ts_backfill, rank, group_neutralize`. |
| Family overlap | Dominant workbook families are tax/accounting fundamentals (2), risk/credit/volatility (2). |
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
| 41 | Cross Sectional Signal Momentum Variant 4 | `3qARw6wN` | `hard_pass_signal_seed` | `2.36` | `3.11` | `10.12%` | `n/a` | `SELF_CORRELATION` | `d4f1bca19ca1500e` |
| 142 | Cross Sectional Signal Momentum Variant 8 | `WjgG7VAN` | `hard_pass_signal_seed` | `2.11` | `2.83` | `4.11%` | `n/a` | `SELF_CORRELATION` | `ce357f376f016b49` |

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
