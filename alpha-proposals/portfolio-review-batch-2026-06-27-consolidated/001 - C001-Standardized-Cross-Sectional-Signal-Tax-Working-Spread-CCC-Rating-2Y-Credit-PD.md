---
title: "C001 - Standardized Cross Sectional Signal - Tax Working Spread + CCC+ Rating + 2Y Credit PD"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-001
member_count: 43
cluster_basis: "same-field same-operator variant"
representative_alpha: "Standardized Cross Sectional Signal"
created: 2026-06-27
updated: 2026-06-27
---

# C001 - Standardized Cross Sectional Signal - Tax Working Spread + CCC+ Rating + 2Y Credit PD

> [!abstract] Consolidated Thesis
> This note combines **43** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Standardized Cross Sectional Signal is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `43` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | risk/credit/volatility (43), tax/accounting fundamentals (43) |
| Common fields | `probability_rating_ccc_plus, direction, annualized_pd_2_year_jc7, weight_raw, fnd6_txws, conviction, weight_strength, alphamix` |
| Common operators | `if_else, group_rank, zscore, rank, abs, vec_avg, ts_decay_linear, ts_backfill, group_neutralize` |
| Best recorded Sharpe | `2.31` |
| Best recorded Fitness | `3.16` |
| Median turnover | `3.31%` |
| Representative | Standardized Cross Sectional Signal |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> direction = group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector); weight_raw = -(group_neutralize(zscore(ts_backfill(vec_avg(probability_rating_ccc_plus), 250)) - zscore(ts_backfill(annualized_pd_2_year_jc7, 63)), sector)); weight_strength = rank(abs(weight_raw)); conviction = if_else(weight_strength > 0.85, 1.30, 1.00); alphamix = direction * conviction; alphamix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `probability_rating_ccc_plus, direction, annualized_pd_2_year_jc7, weight_raw, fnd6_txws, conviction, weight_strength, alphamix`. |
| Operator overlap | Common operators are `if_else, group_rank, zscore, rank, abs, vec_avg, ts_decay_linear, ts_backfill, group_neutralize`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (43), tax/accounting fundamentals (43). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 43 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 43 |
| pending: `SELF_CORRELATION` | 43 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 42 | Standardized Cross Sectional Signal | `9qRObzYq` | `hard_pass_signal_seed` | `2.31` | `3.16` | `3.45%` | `n/a` | `SELF_CORRELATION` | `de487a6535958df1` |
| 43 | Standardized Cross Sectional Signal Variant 2 | `88LzVA5v` | `hard_pass_signal_seed` | `2.31` | `3.16` | `3.45%` | `n/a` | `SELF_CORRELATION` | `de487a6535958df1` |
| 44 | Standardized Cross Sectional Signal Variant 3 | `n/a` | `hard_pass_signal_seed` | `2.31` | `3.16` | `3.45%` | `n/a` | `SELF_CORRELATION` | `de487a6535958df1` |
| 51 | Standardized Cross Sectional Signal Variant 4 | `YPAp8P9R` | `hard_pass_signal_seed` | `2.27` | `3.1` | `3.30%` | `n/a` | `SELF_CORRELATION` | `6e9d3baefe43cc28` |
| 52 | Standardized Cross Sectional Signal Variant 5 | `RRrwqMGe` | `hard_pass_signal_seed` | `2.27` | `3.1` | `3.30%` | `n/a` | `SELF_CORRELATION` | `6e9d3baefe43cc28` |
| 53 | Standardized Cross Sectional Signal Variant 6 | `n/a` | `hard_pass_signal_seed` | `2.27` | `3.1` | `3.30%` | `n/a` | `SELF_CORRELATION` | `6e9d3baefe43cc28` |
| 56 | Standardized Cross Sectional Signal Variant 7 | `A13wLrgg` | `hard_pass_signal_seed` | `2.28` | `3.07` | `3.45%` | `n/a` | `SELF_CORRELATION` | `34d28df87d233bfd` |
| 57 | Standardized Cross Sectional Signal Variant 8 | `1YgA1JwW` | `hard_pass_signal_seed` | `2.28` | `3.07` | `3.45%` | `n/a` | `SELF_CORRELATION` | `34d28df87d233bfd` |
| 58 | Standardized Cross Sectional Signal Variant 9 | `n/a` | `hard_pass_signal_seed` | `2.28` | `3.07` | `3.45%` | `n/a` | `SELF_CORRELATION` | `34d28df87d233bfd` |
| 60 | Standardized Cross Sectional Signal Variant 10 | `omYKPqmm` | `hard_pass_signal_seed` | `2.27` | `3.07` | `3.38%` | `n/a` | `SELF_CORRELATION` | `4f815671fea934e4` |
| 61 | Standardized Cross Sectional Signal Variant 11 | `E5KPYaK9` | `hard_pass_signal_seed` | `2.27` | `3.07` | `3.38%` | `n/a` | `SELF_CORRELATION` | `4f815671fea934e4` |
| 62 | Standardized Cross Sectional Signal Variant 12 | `n/a` | `hard_pass_signal_seed` | `2.27` | `3.07` | `3.38%` | `n/a` | `SELF_CORRELATION` | `4f815671fea934e4` |
| 66 | Standardized Cross Sectional Signal Variant 13 | `rKWMELo1` | `hard_pass_signal_seed` | `2.25` | `3.05` | `3.31%` | `n/a` | `SELF_CORRELATION` | `d3486f74557427cd` |
| 67 | Standardized Cross Sectional Signal Variant 14 | `0m87YE3p` | `hard_pass_signal_seed` | `2.25` | `3.05` | `3.31%` | `n/a` | `SELF_CORRELATION` | `d3486f74557427cd` |
| 68 | Standardized Cross Sectional Signal Variant 15 | `n/a` | `hard_pass_signal_seed` | `2.25` | `3.05` | `3.31%` | `n/a` | `SELF_CORRELATION` | `d3486f74557427cd` |
| 78 | Standardized Cross Sectional Signal Variant 16 | `vRmLYeJd` | `hard_pass_signal_seed` | `2.24` | `2.97` | `3.43%` | `n/a` | `SELF_CORRELATION` | `d4f684432d49b673` |
| 79 | Standardized Cross Sectional Signal Variant 17 | `78dR0Nl8` | `hard_pass_signal_seed` | `2.24` | `2.97` | `3.43%` | `n/a` | `SELF_CORRELATION` | `d4f684432d49b673` |
| 80 | Standardized Cross Sectional Signal Variant 18 | `n/a` | `hard_pass_signal_seed` | `2.24` | `2.97` | `3.43%` | `n/a` | `SELF_CORRELATION` | `d4f684432d49b673` |
| 84 | Standardized Cross Sectional Signal Variant 19 | `npW5Y78l` | `hard_pass_signal_seed` | `2.22` | `2.97` | `3.30%` | `n/a` | `SELF_CORRELATION` | `22b5df72dbff7241` |
| 85 | Standardized Cross Sectional Signal Variant 20 | `RRrp5Y3a` | `hard_pass_signal_seed` | `2.22` | `2.97` | `3.30%` | `n/a` | `SELF_CORRELATION` | `22b5df72dbff7241` |
| 86 | Standardized Cross Sectional Signal Variant 21 | `n/a` | `hard_pass_signal_seed` | `2.22` | `2.97` | `3.30%` | `n/a` | `SELF_CORRELATION` | `22b5df72dbff7241` |
| 88 | Standardized Cross Sectional Signal Variant 22 | `bl9L6YGR` | `hard_pass_signal_seed` | `2.2` | `2.98` | `3.14%` | `n/a` | `SELF_CORRELATION` | `c51df8b5adae59ce` |
| 89 | Standardized Cross Sectional Signal Variant 23 | `A138YmKY` | `hard_pass_signal_seed` | `2.2` | `2.98` | `3.14%` | `n/a` | `SELF_CORRELATION` | `c51df8b5adae59ce` |
| 90 | Standardized Cross Sectional Signal Variant 24 | `n/a` | `hard_pass_signal_seed` | `2.2` | `2.98` | `3.14%` | `n/a` | `SELF_CORRELATION` | `c51df8b5adae59ce` |
| 100 | Standardized Cross Sectional Signal Variant 25 | `j2gKWpL5` | `hard_pass_signal_seed` | `2.18` | `2.94` | `3.14%` | `n/a` | `SELF_CORRELATION` | `9afb1071277afc01` |
| 101 | Standardized Cross Sectional Signal Variant 26 | `LLRp8PEa` | `hard_pass_signal_seed` | `2.18` | `2.94` | `3.14%` | `n/a` | `SELF_CORRELATION` | `9afb1071277afc01` |
| 102 | Standardized Cross Sectional Signal Variant 27 | `n/a` | `hard_pass_signal_seed` | `2.18` | `2.94` | `3.14%` | `n/a` | `SELF_CORRELATION` | `9afb1071277afc01` |
| 104 | Standardized Cross Sectional Signal Variant 28 | `Vk8bqN7Y` | `hard_pass_signal_seed` | `2.22` | `2.87` | `3.61%` | `n/a` | `SELF_CORRELATION` | `3f5f940c1fe6e83c` |
| 105 | Standardized Cross Sectional Signal Variant 29 | `GrowWXOO` | `hard_pass_signal_seed` | `2.22` | `2.87` | `3.61%` | `n/a` | `SELF_CORRELATION` | `3f5f940c1fe6e83c` |
| 106 | Standardized Cross Sectional Signal Variant 30 | `n/a` | `hard_pass_signal_seed` | `2.22` | `2.87` | `3.61%` | `n/a` | `SELF_CORRELATION` | `3f5f940c1fe6e83c` |
| 112 | Standardized Cross Sectional Signal Variant 31 | `6XEL18VO` | `hard_pass_signal_seed` | `2.18` | `2.88` | `3.31%` | `n/a` | `SELF_CORRELATION` | `b3a4cc4bbab9282c` |
| 113 | Standardized Cross Sectional Signal Variant 32 | `1Yg7WxWR` | `hard_pass_signal_seed` | `2.18` | `2.88` | `3.31%` | `n/a` | `SELF_CORRELATION` | `b3a4cc4bbab9282c` |
| 114 | Standardized Cross Sectional Signal Variant 33 | `n/a` | `hard_pass_signal_seed` | `2.18` | `2.88` | `3.31%` | `n/a` | `SELF_CORRELATION` | `b3a4cc4bbab9282c` |
| 115 | Standardized Cross Sectional Signal Variant 34 | `pw7eEgKv` | `hard_pass_signal_seed` | `2.16` | `2.89` | `3.15%` | `n/a` | `SELF_CORRELATION` | `a29eab42bd045b9c` |
| 116 | Standardized Cross Sectional Signal Variant 35 | `MPxp60Za` | `hard_pass_signal_seed` | `2.16` | `2.89` | `3.15%` | `n/a` | `SELF_CORRELATION` | `a29eab42bd045b9c` |
| 117 | Standardized Cross Sectional Signal Variant 36 | `n/a` | `hard_pass_signal_seed` | `2.16` | `2.89` | `3.15%` | `n/a` | `SELF_CORRELATION` | `a29eab42bd045b9c` |
| 120 | Standardized Cross Sectional Signal Variant 37 | `e7rZKqOl` | `hard_pass_signal_seed` | `2.18` | `2.83` | `3.43%` | `n/a` | `SELF_CORRELATION` | `69a17011716c534a` |
| 121 | Standardized Cross Sectional Signal Variant 38 | `N1OpPZMq` | `hard_pass_signal_seed` | `2.18` | `2.83` | `3.43%` | `n/a` | `SELF_CORRELATION` | `69a17011716c534a` |
| 122 | Standardized Cross Sectional Signal Variant 39 | `n/a` | `hard_pass_signal_seed` | `2.18` | `2.83` | `3.43%` | `n/a` | `SELF_CORRELATION` | `69a17011716c534a` |
| 129 | Standardized Cross Sectional Signal Variant 40 | `pw7eok7g` | `hard_pass_signal_seed` | `2.2` | `2.75` | `4.15%` | `n/a` | `SELF_CORRELATION` | `734d2f06b0d4ada4` |
| 130 | Standardized Cross Sectional Signal Variant 41 | `LLRpMk2a` | `hard_pass_signal_seed` | `2.2` | `2.75` | `4.15%` | `n/a` | `SELF_CORRELATION` | `734d2f06b0d4ada4` |
| 131 | Standardized Cross Sectional Signal Variant 42 | `n/a` | `hard_pass_signal_seed` | `2.2` | `2.75` | `4.15%` | `n/a` | `SELF_CORRELATION` | `734d2f06b0d4ada4` |
| 160 | Standardized Cross Sectional Signal Variant 43 | `N1Orkpg8` | `hard_pass_signal_seed` | `2.09` | `2.8` | `3.02%` | `n/a` | `SELF_CORRELATION` | `2bd6714cb8f74f1a` |

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
