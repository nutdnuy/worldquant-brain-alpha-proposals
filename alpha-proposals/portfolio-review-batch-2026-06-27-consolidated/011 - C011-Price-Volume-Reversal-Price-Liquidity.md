---
title: "C011 - Price Volume Reversal - Price Liquidity"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-011
member_count: 8
cluster_basis: "high-similarity field/operator/family cluster"
representative_alpha: "Price Volume Reversal Variant 7"
created: 2026-06-27
updated: 2026-06-27
---

# C011 - Price Volume Reversal - Price Liquidity

> [!abstract] Consolidated Thesis
> This note combines **8** highly similar alpha proposals into one research idea. The consolidation basis is **high-similarity field/operator/family cluster**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Price Volume Reversal Variant 7 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `8` |
| Cluster basis | `high-similarity field/operator/family cluster` |
| Dominant families | price-volume/liquidity/turnover (7), execution cost (2), execution cost; threshold/no-trade region (1), liquidity/turnover (1), trading volume alpha (1), risk/volatility scaling (1), mean-variance/risk scaling (1) |
| Common fields | `ts_av_diff, turn, volume, y, x, sharesout, z, change_day, close, vwap, ts_decay_exp_window, returns` |
| Common operators | `rank, winsorize, group_rank, abs, ts_mean, ts_backfill, trade_when, scale, ts_std_dev` |
| Best recorded Sharpe | `1.75` |
| Best recorded Fitness | `2.86` |
| Median turnover | `6.98%` |
| Representative | Price Volume Reversal Variant 7 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `n/a` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> change_day = (vwap - close) / close; ts_decay_exp_window(rank(change_day), 4)
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `high-similarity field/operator/family cluster` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `ts_av_diff, turn, volume, y, x, sharesout, z, change_day, close, vwap, ts_decay_exp_window, returns`. |
| Operator overlap | Common operators are `rank, winsorize, group_rank, abs, ts_mean, ts_backfill, trade_when, scale, ts_std_dev`. |
| Family overlap | Dominant workbook families are price-volume/liquidity/turnover (7), execution cost (2), execution cost; threshold/no-trade region (1), liquidity/turnover (1), trading volume alpha (1), risk/volatility scaling (1), mean-variance/risk scaling (1). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 7 |
| `research-trend-candidate` | 1 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 7 |
| failed: `LOW_FITNESS` | 1 |
| pending: `SELF_CORRELATION` | 6 |
| pending: `n/a` | 2 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 385 | Price Volume Reversal Variant 7 | `alpha_092` | `hard_pass_signal_seed` | `1.4` | `2.86` | `n/a` | `n/a` | `n/a` | `32369fa3c6d47b9b` |
| 386 | Price Volume Reversal Variant 8 | `alpha_027` | `hard_pass_signal_seed` | `1.4` | `2.86` | `n/a` | `n/a` | `n/a` | `32369fa3c6d47b9b` |
| 504 | Price Volume Reversal Variant 12 | `WjpbYzno` | `paper_hard_pass_signal_seed` | `1.75` | `1.29` | `9.85%` | `n/a` | `SELF_CORRELATION` | `dfe1ba5e597094cf` |
| 509 | Price Volume Reversal Variant 16 | `9qwjd9v9` | `paper_hard_pass_signal_seed` | `1.51` | `1.18` | `7.95%` | `n/a` | `SELF_CORRELATION` | `bdeaa6a0d499aab5` |
| 505 | Price Volume Reversal Variant 13 | `kq3ovj3k` | `paper_hard_pass_signal_seed` | `1.54` | `1.13` | `2.38%` | `n/a` | `SELF_CORRELATION` | `dce8ff8dc35c2cd3` |
| 507 | Price Volume Reversal Variant 14 | `O0pNM8W1` | `paper_hard_pass_signal_seed` | `1.4` | `1.03` | `2.21%` | `n/a` | `SELF_CORRELATION` | `82fe3b78b82b632b` |
| 511 | Price Volume Reversal Variant 18 | `VkpaeVx8` | `paper_hard_pass_signal_seed` | `1.33` | `1.03` | `6.98%` | `n/a` | `SELF_CORRELATION` | `d78ac5f898723079` |
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
