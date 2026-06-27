---
title: "Options Skew Risk Appetite Cluster 012 - weight_raw pcr_oi_270"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-012
member_count: 7
cluster_basis: "same-field same-operator variant"
representative_alpha: "Options Skew Risk Appetite Variant 9"
created: 2026-06-27
updated: 2026-06-27
---

# Options Skew Risk Appetite Cluster 012 - weight_raw pcr_oi_270

> [!abstract] Consolidated Thesis
> This note combines **7** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 9 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `7` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | options/implied volatility (7), tax/accounting fundamentals (7), risk/credit/volatility (7) |
| Common fields | `weight_raw, pcr_oi_270, fnd6_txws, implied_volatility_call_60, weight_strength, conviction, alphamix, direction, implied_volatility_put_60` |
| Common operators | `ts_backfill, if_else, vec_avg, abs, group_zscore, group_rank, ts_decay_linear, ts_mean, rank, trade_when, group_neutralize` |
| Best recorded Sharpe | `2.56` |
| Best recorded Fitness | `2.98` |
| Median turnover | `16.03%` |
| Representative | Options Skew Risk Appetite Variant 9 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> direction = trade_when(ts_mean(pcr_oi_270, 2) < 1, group_zscore(ts_mean((implied_volatility_call_60 - implied_volatility_put_60), 5), sector), -1); weight_raw = group_neutralize(group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector), sector); weight_strength = rank(abs(weight_raw)); conviction = if_else(weight_strength > 0.85, 1.30, 1.00); alphamix = direction * conviction; alphamix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `weight_raw, pcr_oi_270, fnd6_txws, implied_volatility_call_60, weight_strength, conviction, alphamix, direction, implied_volatility_put_60`. |
| Operator overlap | Common operators are `ts_backfill, if_else, vec_avg, abs, group_zscore, group_rank, ts_decay_linear, ts_mean, rank, trade_when, group_neutralize`. |
| Family overlap | Dominant workbook families are options/implied volatility (7), tax/accounting fundamentals (7), risk/credit/volatility (7). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 7 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 7 |
| pending: `SELF_CORRELATION` | 7 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 33 | Options Skew Risk Appetite Variant 9 | `XgKnWwkm` | `hard_pass_signal_seed` | `2.54` | `2.98` | `16.52%` | `n/a` | `SELF_CORRELATION` | `1edea4fcf7aa9fb8` |
| 49 | Options Skew Risk Appetite Variant 19 | `wpelqvkx` | `hard_pass_signal_seed` | `2.46` | `2.79` | `16.59%` | `n/a` | `SELF_CORRELATION` | `b024675e28b49746` |
| 55 | Options Skew Risk Appetite Variant 21 | `P013MZjJ` | `hard_pass_signal_seed` | `2.56` | `2.7` | `16.03%` | `n/a` | `SELF_CORRELATION` | `abebbf83e2fdc43f` |
| 93 | Options Skew Risk Appetite Variant 33 | `e7r0AWWz` | `hard_pass_signal_seed` | `2.5` | `2.55` | `16.09%` | `n/a` | `SELF_CORRELATION` | `119dde98019a1f22` |
| 110 | Options Skew Risk Appetite Variant 44 | `akOnKqlR` | `hard_pass_signal_seed` | `2.16` | `2.95` | `4.07%` | `n/a` | `SELF_CORRELATION` | `07f3dbc7c7e9b9bc` |
| 366 | Options Skew Risk Appetite Variant 139 | `e7r0eMOE` | `hard_pass_signal_seed` | `1.94` | `2.19` | `9.10%` | `n/a` | `SELF_CORRELATION` | `f0fb6ef6eeb797d9` |
| 377 | Options Skew Risk Appetite Variant 143 | `RRr8MA6d` | `hard_pass_signal_seed` | `1.92` | `2.18` | `9.07%` | `n/a` | `SELF_CORRELATION` | `0c258b7bb4d2e555` |

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
