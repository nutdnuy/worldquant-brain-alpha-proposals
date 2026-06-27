---
title: "C029 - Options Skew Risk Appetite - 30D IV Skew"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-029
member_count: 4
cluster_basis: "numeric-parameter variant"
representative_alpha: "Options Skew Risk Appetite Variant 71"
created: 2026-06-27
updated: 2026-06-27
---

# C029 - Options Skew Risk Appetite - 30D IV Skew

> [!abstract] Consolidated Thesis
> This note combines **4** highly similar alpha proposals into one research idea. The consolidation basis is **numeric-parameter variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 71 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `4` |
| Cluster basis | `numeric-parameter variant` |
| Dominant families | risk/credit/volatility (4), options/implied volatility (4) |
| Common fields | `implied_volatility_call_30, implied_volatility_put_30` |
| Common operators | `group_zscore, ts_mean` |
| Best recorded Sharpe | `2.2` |
| Best recorded Fitness | `2.39` |
| Median turnover | `16.79%` |
| Representative | Options Skew Risk Appetite Variant 71 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> group_zscore(ts_mean(implied_volatility_call_30 - implied_volatility_put_30, 5), sector)
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `numeric-parameter variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `implied_volatility_call_30, implied_volatility_put_30`. |
| Operator overlap | Common operators are `group_zscore, ts_mean`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (4), options/implied volatility (4). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 4 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 4 |
| pending: `SELF_CORRELATION` | 4 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 193 | Options Skew Risk Appetite Variant 71 | `O0kV2NZ1` | `hard_pass_signal_seed` | `2.2` | `2.39` | `16.79%` | `n/a` | `SELF_CORRELATION` | `fc0eaab5582d0ded` |
| 206 | Options Skew Risk Appetite Variant 79 | `j2w7PbQ9` | `hard_pass_signal_seed` | `2.16` | `2.32` | `16.73%` | `n/a` | `SELF_CORRELATION` | `fc0eaab5582d0ded` |
| 207 | Options Skew Risk Appetite Variant 80 | `n/a` | `hard_pass_signal_seed` | `2.16` | `2.32` | `16.73%` | `n/a` | `SELF_CORRELATION` | `fc0eaab5582d0ded` |
| 311 | Options Skew Risk Appetite Variant 120 | `6XYXW2kK` | `hard_pass_signal_seed` | `2.14` | `2.06` | `20.66%` | `n/a` | `SELF_CORRELATION` | `aedece14eb0176f2` |

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
