---
title: "Options Skew Risk Appetite Cluster 021 - weight_raw implied_volatility_call_270"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-021
member_count: 5
cluster_basis: "same-field same-operator variant"
representative_alpha: "Options Skew Risk Appetite Variant 6"
created: 2026-06-27
updated: 2026-06-27
---

# Options Skew Risk Appetite Cluster 021 - weight_raw implied_volatility_call_270

> [!abstract] Consolidated Thesis
> This note combines **5** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 6 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `5` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | options/implied volatility (5), risk/credit/volatility (5) |
| Common fields | `weight_raw, implied_volatility_call_270, pcr_oi_270, implied_volatility_call_60, implied_volatility_put_270, weight_strength, conviction, alphamix, direction, probability_non_investment_grade_rating, implied_volatility_put_60` |
| Common operators | `ts_backfill, if_else, abs, group_zscore, ts_mean, rank, trade_when, group_neutralize` |
| Best recorded Sharpe | `2.59` |
| Best recorded Fitness | `3.07` |
| Median turnover | `15.98%` |
| Representative | Options Skew Risk Appetite Variant 6 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> direction = trade_when(ts_mean(pcr_oi_270, 2) < 1, group_zscore(ts_mean((implied_volatility_call_60 - implied_volatility_put_60), 5), sector), -1); weight_raw = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)), sector); weight_strength = rank(abs(weight_raw)); conviction = if_else(weight_strength > 0.85, 1.30, 1.00); alphamix = direction * conviction; alphamix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `weight_raw, implied_volatility_call_270, pcr_oi_270, implied_volatility_call_60, implied_volatility_put_270, weight_strength, conviction, alphamix, direction, probability_non_investment_grade_rating, implied_volatility_put_60`. |
| Operator overlap | Common operators are `ts_backfill, if_else, abs, group_zscore, ts_mean, rank, trade_when, group_neutralize`. |
| Family overlap | Dominant workbook families are options/implied volatility (5), risk/credit/volatility (5). |
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
| 27 | Options Skew Risk Appetite Variant 6 | `GroLg78J` | `hard_pass_signal_seed` | `2.55` | `3.07` | `16.44%` | `n/a` | `SELF_CORRELATION` | `17355dc16431ff3b` |
| 34 | Options Skew Risk Appetite Variant 10 | `omYlAgY6` | `hard_pass_signal_seed` | `2.59` | `2.82` | `15.98%` | `n/a` | `SELF_CORRELATION` | `1f62b6f30b7f6a2e` |
| 38 | Options Skew Risk Appetite Variant 13 | `0m8EYYQ1` | `hard_pass_signal_seed` | `2.59` | `2.82` | `15.98%` | `n/a` | `SELF_CORRELATION` | `a5c4509ed3977051` |
| 175 | Options Skew Risk Appetite Variant 61 | `3qARVNGN` | `hard_pass_signal_seed` | `2.21` | `2.52` | `15.85%` | `n/a` | `SELF_CORRELATION` | `016ec9ff787069ea` |
| 174 | Options Skew Risk Appetite Variant 60 | `A13PWldd` | `hard_pass_signal_seed` | `2.21` | `2.52` | `15.86%` | `n/a` | `SELF_CORRELATION` | `6cc13b09e2bc7098` |

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
