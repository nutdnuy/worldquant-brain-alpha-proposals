---
title: "C003 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-003
member_count: 12
cluster_basis: "same-field same-operator variant"
representative_alpha: "Options Skew Risk Appetite Variant 113"
created: 2026-06-27
updated: 2026-06-27
---

# C003 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew

> [!abstract] Consolidated Thesis
> This note combines **12** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 113 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `12` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | risk/credit/volatility (12), options/implied volatility (12) |
| Common fields | `implied_volatility_put_270, implied_volatility_call_270, pcr_oi_270` |
| Common operators | `ts_mean, trade_when, group_zscore` |
| Best recorded Sharpe | `2.16` |
| Best recorded Fitness | `2.33` |
| Median turnover | `17.19%` |
| Representative | Options Skew Risk Appetite Variant 113 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> trade_when(pcr_oi_270 < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 5), sector), -1)
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `implied_volatility_put_270, implied_volatility_call_270, pcr_oi_270`. |
| Operator overlap | Common operators are `ts_mean, trade_when, group_zscore`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (12), options/implied volatility (12). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 12 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 12 |
| pending: `SELF_CORRELATION` | 12 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 289 | Options Skew Risk Appetite Variant 113 | `ZYWxkJPZ` | `hard_pass_signal_seed` | `1.98` | `2.33` | `13.01%` | `n/a` | `SELF_CORRELATION` | `95d56785d90fa2aa` |
| 296 | Options Skew Risk Appetite Variant 116 | `gJoKvq1M` | `hard_pass_signal_seed` | `2.16` | `2.08` | `20.67%` | `n/a` | `SELF_CORRELATION` | `195d75d60dd8dbb2` |
| 297 | Options Skew Risk Appetite Variant 117 | `blMK33M6` | `hard_pass_signal_seed` | `2.16` | `2.08` | `20.67%` | `n/a` | `SELF_CORRELATION` | `195d75d60dd8dbb2` |
| 320 | Options Skew Risk Appetite Variant 124 | `rKLnmnPo` | `hard_pass_signal_seed` | `2.06` | `2.14` | `17.19%` | `n/a` | `SELF_CORRELATION` | `bc6b62203107cb1a` |
| 321 | Options Skew Risk Appetite Variant 125 | `gJoK7lwv` | `hard_pass_signal_seed` | `2.06` | `2.14` | `17.19%` | `n/a` | `SELF_CORRELATION` | `bc6b62203107cb1a` |
| 346 | Options Skew Risk Appetite Variant 132 | `e7qKeVn6` | `hard_pass_signal_seed` | `1.93` | `2.26` | `12.92%` | `n/a` | `SELF_CORRELATION` | `401f33e8d6659192` |
| 347 | Options Skew Risk Appetite Variant 133 | `5892okjM` | `hard_pass_signal_seed` | `1.93` | `2.26` | `12.92%` | `n/a` | `SELF_CORRELATION` | `35cf67179b4133df` |
| 355 | Options Skew Risk Appetite Variant 135 | `xAmQXVNp` | `hard_pass_signal_seed` | `2.04` | `2.09` | `17.31%` | `n/a` | `SELF_CORRELATION` | `bc6b62203107cb1a` |
| 356 | Options Skew Risk Appetite Variant 136 | `vR9o3Z8b` | `hard_pass_signal_seed` | `2.04` | `2.09` | `17.31%` | `n/a` | `SELF_CORRELATION` | `89c51c01fb5caa55` |
| 374 | Options Skew Risk Appetite Variant 141 | `LL62x1A2` | `hard_pass_signal_seed` | `1.96` | `2.13` | `14.97%` | `n/a` | `SELF_CORRELATION` | `12e07191a58befdf` |
| 375 | Options Skew Risk Appetite Variant 142 | `1YnL606m` | `hard_pass_signal_seed` | `1.96` | `2.13` | `14.97%` | `n/a` | `SELF_CORRELATION` | `12e07191a58befdf` |
| 459 | Options Skew Risk Appetite Variant 156 | `6X12bYP7` | `hard_pass_signal_seed` | `2.01` | `1.87` | `20.65%` | `n/a` | `SELF_CORRELATION` | `0afc8ad7b73c4962` |

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
