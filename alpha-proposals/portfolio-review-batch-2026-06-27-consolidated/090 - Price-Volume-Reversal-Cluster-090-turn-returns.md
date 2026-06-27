---
title: "Price Volume Reversal Cluster 090 - turn returns"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-090
member_count: 2
cluster_basis: "numeric-parameter variant"
representative_alpha: "Price Volume Reversal Variant 16"
created: 2026-06-27
updated: 2026-06-27
---

# Price Volume Reversal Cluster 090 - turn returns

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **numeric-parameter variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Price Volume Reversal Variant 16 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `numeric-parameter variant` |
| Dominant families | price-volume/liquidity/turnover (2), risk/volatility scaling (1), mean-variance/risk scaling (1) |
| Common fields | `turn, returns, volume, tv, y, ts_av_diff, sharesout, x, lowrisk` |
| Common operators | `ts_std_dev, scale, winsorize, ts_mean, abs, group_rank, ts_backfill, rank` |
| Best recorded Sharpe | `1.51` |
| Best recorded Fitness | `1.18` |
| Median turnover | `7.95%` |
| Representative | Price Volume Reversal Variant 16 |
| Representative bucket | `paper_hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> turn = ts_backfill(volume/sharesout, 5); x = winsorize(ts_av_diff(turn, 504), std=4); y = ts_mean(x, 25); tv = rank(abs(y)) * group_rank(y, subindustry); lowrisk = 1 - rank(ts_std_dev(returns, 60)); scale(tv * (0.8 + 0.4 * lowrisk))
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `numeric-parameter variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `turn, returns, volume, tv, y, ts_av_diff, sharesout, x, lowrisk`. |
| Operator overlap | Common operators are `ts_std_dev, scale, winsorize, ts_mean, abs, group_rank, ts_backfill, rank`. |
| Family overlap | Dominant workbook families are price-volume/liquidity/turnover (2), risk/volatility scaling (1), mean-variance/risk scaling (1). |
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
| 509 | Price Volume Reversal Variant 16 | `9qwjd9v9` | `paper_hard_pass_signal_seed` | `1.51` | `1.18` | `7.95%` | `n/a` | `SELF_CORRELATION` | `bdeaa6a0d499aab5` |
| 511 | Price Volume Reversal Variant 18 | `VkpaeVx8` | `paper_hard_pass_signal_seed` | `1.33` | `1.03` | `6.98%` | `n/a` | `SELF_CORRELATION` | `d78ac5f898723079` |

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
