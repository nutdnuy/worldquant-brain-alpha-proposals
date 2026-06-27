---
title: "Price Volume Reversal Cluster 037 - turn volume"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-037
member_count: 4
cluster_basis: "high-similarity field/operator/family cluster"
representative_alpha: "Price Volume Reversal Variant 12"
created: 2026-06-27
updated: 2026-06-27
---

# Price Volume Reversal Cluster 037 - turn volume

> [!abstract] Consolidated Thesis
> This note combines **4** highly similar alpha proposals into one research idea. The consolidation basis is **high-similarity field/operator/family cluster**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Price Volume Reversal Variant 12 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `4` |
| Cluster basis | `high-similarity field/operator/family cluster` |
| Dominant families | price-volume/liquidity/turnover (3), execution cost (2), execution cost; threshold/no-trade region (1), liquidity/turnover (1), trading volume alpha (1) |
| Common fields | `turn, volume, y, ts_av_diff, sharesout, x, z` |
| Common operators | `winsorize, ts_mean, abs, group_rank, ts_backfill, rank, trade_when` |
| Best recorded Sharpe | `1.75` |
| Best recorded Fitness | `1.29` |
| Median turnover | `2.43%` |
| Representative | Price Volume Reversal Variant 12 |
| Representative bucket | `paper_hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> turn = ts_backfill(volume/sharesout, 5); x = winsorize(ts_av_diff(turn, 504), std=4); y = ts_mean(x, 30); group_rank(rank(abs(y)) * group_rank(y, subindustry), subindustry)
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `high-similarity field/operator/family cluster` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `turn, volume, y, ts_av_diff, sharesout, x, z`. |
| Operator overlap | Common operators are `winsorize, ts_mean, abs, group_rank, ts_backfill, rank, trade_when`. |
| Family overlap | Dominant workbook families are price-volume/liquidity/turnover (3), execution cost (2), execution cost; threshold/no-trade region (1), liquidity/turnover (1), trading volume alpha (1). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 3 |
| `research-trend-candidate` | 1 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 3 |
| failed: `LOW_FITNESS` | 1 |
| pending: `SELF_CORRELATION` | 4 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 504 | Price Volume Reversal Variant 12 | `WjpbYzno` | `paper_hard_pass_signal_seed` | `1.75` | `1.29` | `9.85%` | `n/a` | `SELF_CORRELATION` | `dfe1ba5e597094cf` |
| 505 | Price Volume Reversal Variant 13 | `kq3ovj3k` | `paper_hard_pass_signal_seed` | `1.54` | `1.13` | `2.38%` | `n/a` | `SELF_CORRELATION` | `dce8ff8dc35c2cd3` |
| 507 | Price Volume Reversal Variant 14 | `O0pNM8W1` | `paper_hard_pass_signal_seed` | `1.4` | `1.03` | `2.21%` | `n/a` | `SELF_CORRELATION` | `82fe3b78b82b632b` |
| 515 | Price Volume Reversal Variant 22 | `QPabzj8X` | `paper_trend_candidate` | `1.38` | `0.99` | `2.43%` | `LOW_FITNESS` | `SELF_CORRELATION` | `555d93b0c494f948` |

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
