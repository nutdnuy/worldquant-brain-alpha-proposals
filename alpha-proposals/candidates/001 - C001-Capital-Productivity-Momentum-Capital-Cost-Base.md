---
title: "C001 - Capital Productivity Momentum - Capital Cost Base"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-001
member_count: 27
cluster_basis: "high-similarity field/operator/family cluster"
representative_alpha: "Capital Productivity Momentum"
created: 2026-06-27
updated: 2026-06-27
---

# C001 - Capital Productivity Momentum - Capital Cost Base

> [!abstract] Consolidated Thesis
> This note combines **27** highly similar alpha proposals into one research idea. The consolidation basis is **high-similarity field/operator/family cluster**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Capital Productivity Momentum is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `27` |
| Cluster basis | `high-similarity field/operator/family cluster` |
| Dominant families | tax/accounting fundamentals (27) |
| Common fields | `cap, c, cogs, g, c0` |
| Common operators | `trade_when, zscore, abs, rank, ts_mean, winsorize` |
| Best recorded Sharpe | `2.03` |
| Best recorded Fitness | `2.89` |
| Median turnover | `3.92%` |
| Representative | Capital Productivity Momentum |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> c0 = zscore(cogs/cap); c = ts_mean(c0, 3); g = trade_when(rank(abs(c)) > 0.85, c, 0); 0.45 * g + 0.55 * rank(c)
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `high-similarity field/operator/family cluster` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `cap, c, cogs, g, c0`. |
| Operator overlap | Common operators are `trade_when, zscore, abs, rank, ts_mean, winsorize`. |
| Family overlap | Dominant workbook families are tax/accounting fundamentals (27). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `failed-checks-strong-signal-repair-candidate` | 24 |
| `recorded-hard-pass-rebuild-candidate` | 3 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `LOW_SHARPE` | 24 |
| failed: `n/a` | 3 |
| pending: `SELF_CORRELATION` | 27 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 156 | Capital Productivity Momentum | `WjWjvxwP` | `hard_pass_signal_seed` | `2.03` | `2.89` | `2.99%` | `n/a` | `SELF_CORRELATION` | `e94566283fe3ca2b` |
| 170 | Capital Productivity Momentum Variant 3 | `KPwPWmgx` | `hard_pass_signal_seed` | `2` | `2.85` | `2.92%` | `n/a` | `SELF_CORRELATION` | `5fdc7384cfdbce14` |
| 169 | Capital Productivity Momentum Variant 2 | `omzEZpd2` | `hard_pass_signal_seed` | `2` | `2.85` | `3.30%` | `n/a` | `SELF_CORRELATION` | `815a4e8e02328fd2` |
| 382 | Capital Productivity Momentum Variant 11 | `LLXMz0ve` | `strong_signal_repair_seed` | `1.98` | `2.76` | `3.76%` | `LOW_SHARPE` | `SELF_CORRELATION` | `7282824465e4d05c` |
| 384 | Capital Productivity Momentum Variant 13 | `6Xqdoo0G` | `strong_signal_repair_seed` | `1.98` | `2.76` | `3.77%` | `LOW_SHARPE` | `SELF_CORRELATION` | `7282824465e4d05c` |
| 383 | Capital Productivity Momentum Variant 12 | `JjXezOml` | `strong_signal_repair_seed` | `1.98` | `2.76` | `3.78%` | `LOW_SHARPE` | `SELF_CORRELATION` | `7282824465e4d05c` |
| 389 | Capital Productivity Momentum Variant 14 | `pwzdMzjj` | `strong_signal_repair_seed` | `1.97` | `2.76` | `3.87%` | `LOW_SHARPE` | `SELF_CORRELATION` | `7282824465e4d05c` |
| 394 | Capital Productivity Momentum Variant 15 | `npzvqbEw` | `strong_signal_repair_seed` | `1.97` | `2.74` | `3.78%` | `LOW_SHARPE` | `SELF_CORRELATION` | `7282824465e4d05c` |
| 395 | Capital Productivity Momentum Variant 16 | `Vklx5qLb` | `strong_signal_repair_seed` | `1.97` | `2.73` | `3.75%` | `LOW_SHARPE` | `SELF_CORRELATION` | `7282824465e4d05c` |
| 396 | Capital Productivity Momentum Variant 17 | `E5a68XvR` | `strong_signal_repair_seed` | `1.95` | `2.75` | `4.01%` | `LOW_SHARPE` | `SELF_CORRELATION` | `7282824465e4d05c` |
| 399 | Capital Productivity Momentum Variant 18 | `ZYlQd0Pn` | `strong_signal_repair_seed` | `1.96` | `2.73` | `3.81%` | `LOW_SHARPE` | `SELF_CORRELATION` | `7282824465e4d05c` |
| 410 | Capital Productivity Momentum Variant 19 | `blP6JwON` | `strong_signal_repair_seed` | `1.93` | `2.73` | `4.08%` | `LOW_SHARPE` | `SELF_CORRELATION` | `7282824465e4d05c` |
| 411 | Capital Productivity Momentum Variant 20 | `RRaEExrn` | `strong_signal_repair_seed` | `1.93` | `2.73` | `4.10%` | `LOW_SHARPE` | `SELF_CORRELATION` | `7282824465e4d05c` |
| 413 | Capital Productivity Momentum Variant 21 | `pwzdZarV` | `strong_signal_repair_seed` | `1.95` | `2.7` | `3.69%` | `LOW_SHARPE` | `SELF_CORRELATION` | `bc1dd8c2e7857dc3` |
| 421 | Capital Productivity Momentum Variant 23 | `omzEPoV2` | `strong_signal_repair_seed` | `1.92` | `2.72` | `3.92%` | `LOW_SHARPE` | `SELF_CORRELATION` | `2ce3695b84a00586` |
| 420 | Capital Productivity Momentum Variant 22 | `pwzdaALV` | `strong_signal_repair_seed` | `1.92` | `2.72` | `4.02%` | `LOW_SHARPE` | `SELF_CORRELATION` | `70abdf1eea0e81d2` |
| 432 | Capital Productivity Momentum Variant 25 | `KP8JVYRz` | `strong_signal_repair_seed` | `1.92` | `2.71` | `4.11%` | `LOW_SHARPE` | `SELF_CORRELATION` | `7282824465e4d05c` |
| 431 | Capital Productivity Momentum Variant 24 | `vRz11dkQ` | `strong_signal_repair_seed` | `1.92` | `2.71` | `4.18%` | `LOW_SHARPE` | `SELF_CORRELATION` | `d34cb75484b13df3` |
| 433 | Capital Productivity Momentum Variant 26 | `886RRgqX` | `strong_signal_repair_seed` | `1.92` | `2.71` | `4.24%` | `LOW_SHARPE` | `SELF_CORRELATION` | `648d39d1edb3f0a6` |
| 441 | Capital Productivity Momentum Variant 27 | `MP8Y0rj6` | `strong_signal_repair_seed` | `1.91` | `2.69` | `4.29%` | `LOW_SHARPE` | `SELF_CORRELATION` | `23f35e14a25aa69d` |
| 442 | Capital Productivity Momentum Variant 28 | `586EjJRM` | `strong_signal_repair_seed` | `1.91` | `2.69` | `4.34%` | `LOW_SHARPE` | `SELF_CORRELATION` | `a507c021312fe823` |
| 445 | Capital Productivity Momentum Variant 29 | `wpzQNWW5` | `strong_signal_repair_seed` | `1.9` | `2.69` | `3.80%` | `LOW_SHARPE` | `SELF_CORRELATION` | `d51b42d7d8ed7787` |
| 461 | Capital Productivity Momentum Variant 30 | `npzvdPQM` | `strong_signal_repair_seed` | `1.9` | `2.67` | `4.38%` | `LOW_SHARPE` | `SELF_CORRELATION` | `69b3fe0f125410fe` |
| 474 | Capital Productivity Momentum Variant 31 | `YPk150ER` | `strong_signal_repair_seed` | `1.89` | `2.65` | `4.42%` | `LOW_SHARPE` | `SELF_CORRELATION` | `edc2be992227d41b` |
| 475 | Capital Productivity Momentum Variant 32 | `KP8J79Gl` | `strong_signal_repair_seed` | `1.89` | `2.65` | `4.45%` | `LOW_SHARPE` | `SELF_CORRELATION` | `ad9f34b00acf0827` |
| 482 | Capital Productivity Momentum Variant 34 | `QPlvN8mr` | `strong_signal_repair_seed` | `1.92` | `2.58` | `3.69%` | `LOW_SHARPE` | `SELF_CORRELATION` | `7282824465e4d05c` |
| 483 | Capital Productivity Momentum Variant 35 | `ZYlQ0qMZ` | `strong_signal_repair_seed` | `1.88` | `2.63` | `4.48%` | `LOW_SHARPE` | `SELF_CORRELATION` | `5d12873a3ddac5bf` |

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
