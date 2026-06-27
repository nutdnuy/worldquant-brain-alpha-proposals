---
title: "EPS Revision Shock Cluster 062 - weight_raw implied_volatility_call_270"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-062
member_count: 2
cluster_basis: "exact-expression duplicate"
representative_alpha: "EPS Revision Shock Variant 39"
created: 2026-06-27
updated: 2026-06-27
---

# EPS Revision Shock Cluster 062 - weight_raw implied_volatility_call_270

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **exact-expression duplicate**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** EPS Revision Shock Variant 39 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `exact-expression duplicate` |
| Dominant families | options/implied volatility (2), earnings/EPS/guidance revisions (2), risk/credit/volatility (2), quality/growth/value (2) |
| Common fields | `weight_raw, implied_volatility_call_270, pcr_oi_270, eps_previous_estimate_value, research_development_expense, implied_volatility_put_270, weight_strength, conviction, alphamix, direction, probability_non_investment_grade_rating` |
| Common operators | `ts_backfill, if_else, vec_avg, abs, group_zscore, group_rank, group_neutralize, ts_mean, ts_corr, rank, trade_when` |
| Best recorded Sharpe | `2.26` |
| Best recorded Fitness | `2.56` |
| Median turnover | `15.52%` |
| Representative | EPS Revision Shock Variant 39 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> direction = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)), industry); weight_raw = -(group_rank(rank(ts_corr(vec_avg(eps_previous_estimate_value), ts_backfill(research_development_expense, 120), 60)), sector)); weight_strength = rank(abs(weight_raw)); conviction = if_else(weight_strength > 0.85, 1.30, 1.00); alphamix = direction * conviction; alphamix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `exact-expression duplicate` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `weight_raw, implied_volatility_call_270, pcr_oi_270, eps_previous_estimate_value, research_development_expense, implied_volatility_put_270, weight_strength, conviction, alphamix, direction, probability_non_investment_grade_rating`. |
| Operator overlap | Common operators are `ts_backfill, if_else, vec_avg, abs, group_zscore, group_rank, group_neutralize, ts_mean, ts_corr, rank, trade_when`. |
| Family overlap | Dominant workbook families are options/implied volatility (2), earnings/EPS/guidance revisions (2), risk/credit/volatility (2), quality/growth/value (2). |
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
| 165 | EPS Revision Shock Variant 39 | `vRmLPvwa` | `hard_pass_signal_seed` | `2.26` | `2.56` | `15.52%` | `n/a` | `SELF_CORRELATION` | `dc470da38cc491f5` |
| 166 | EPS Revision Shock Variant 40 | `A1383A7Y` | `hard_pass_signal_seed` | `2.26` | `2.56` | `15.52%` | `n/a` | `SELF_CORRELATION` | `dc470da38cc491f5` |

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
