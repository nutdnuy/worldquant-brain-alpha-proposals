---
title: "Options Skew Risk Appetite Cluster 066 - cogs"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-066
member_count: 2
cluster_basis: "same-field same-operator variant"
representative_alpha: "Options Skew Risk Appetite Variant 82"
created: 2026-06-27
updated: 2026-06-27
---

# Options Skew Risk Appetite Cluster 066 - cogs

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 82 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | options/implied volatility (2), tax/accounting fundamentals (2), risk/credit/volatility (2) |
| Common fields | `raw1, cogs, pcr_oi_270, raw2, cap, implied_volatility_call_60, a2, a1, raw2_g, raw2_c, implied_volatility_put_60, raw2_c0` |
| Common operators | `zscore, scale, abs, group_zscore, ts_mean, rank, trade_when, group_neutralize` |
| Best recorded Sharpe | `2.09` |
| Best recorded Fitness | `2.41` |
| Median turnover | `14.55%` |
| Representative | Options Skew Risk Appetite Variant 82 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> raw1 = trade_when(ts_mean(pcr_oi_270, 2) < 1, group_zscore(ts_mean((implied_volatility_call_60 - implied_volatility_put_60), 5), sector), -1); a1 = rank(raw1); raw2_c0 = zscore(cogs/cap); raw2_c = ts_mean(raw2_c0, 3); raw2_g = trade_when(rank(abs(raw2_c)) > 0.85, raw2_c, 0); raw2 = 0.45 * raw2_g + 0.55 * rank(raw2_c); a2 = rank(raw2); alpha = scale(0.569915 * a1 + 0.430085 * a2); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `raw1, cogs, pcr_oi_270, raw2, cap, implied_volatility_call_60, a2, a1, raw2_g, raw2_c, implied_volatility_put_60, raw2_c0`. |
| Operator overlap | Common operators are `zscore, scale, abs, group_zscore, ts_mean, rank, trade_when, group_neutralize`. |
| Family overlap | Dominant workbook families are options/implied volatility (2), tax/accounting fundamentals (2), risk/credit/volatility (2). |
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
| 209 | Options Skew Risk Appetite Variant 82 | `LLpbz9W6` | `hard_pass_signal_seed` | `2.09` | `2.41` | `14.55%` | `n/a` | `SELF_CORRELATION` | `887a5e4a37938d3f` |
| 217 | Options Skew Risk Appetite Variant 90 | `wpRwGPWd` | `hard_pass_signal_seed` | `2.08` | `2.4` | `14.50%` | `n/a` | `SELF_CORRELATION` | `2a705f1c59d7f44c` |

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
