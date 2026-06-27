---
title: "C002 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew + Tax Working Spread"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-002
member_count: 27
cluster_basis: "high-similarity field/operator/family cluster"
representative_alpha: "Options Skew Risk Appetite Variant 2"
created: 2026-06-27
updated: 2026-06-27
---

# C002 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew + Tax Working Spread

> [!abstract] Consolidated Thesis
> This note combines **27** highly similar alpha proposals into one research idea. The consolidation basis is **high-similarity field/operator/family cluster**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 2 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `27` |
| Cluster basis | `high-similarity field/operator/family cluster` |
| Dominant families | risk/credit/volatility (27), tax/accounting fundamentals (27), options/implied volatility (27), price-volume/liquidity/turnover (16) |
| Common fields | `implied_volatility_put_60, pcr_oi_270, implied_volatility_call_60, fnd6_txws, volume, raw1, a1, raw2, a2, ts_av_diff, turn, sharesout` |
| Common operators | `ts_decay_linear, group_zscore, group_rank, ts_backfill, rank, vec_avg, trade_when, ts_mean, abs, scale, max, ts_std_dev` |
| Best recorded Sharpe | `2.84` |
| Best recorded Fitness | `3.24` |
| Median turnover | `12.42%` |
| Representative | Options Skew Risk Appetite Variant 2 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1_raw = group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector); alpha1 = zscore(group_rank(alpha1_raw, subindustry)); alpha2_raw = trade_when(ts_mean(pcr_oi_270, 2) < 1, group_zscore(ts_mean((implied_volatility_call_60 - implied_volatility_put_60), 5), sector), -1); alpha2 = group_zscore(zscore(alpha2_raw), sector); alpha3_raw = zscore(ts_decay_linear(group_neutralize(rank(add(multiply(0.6,reverse(ts_zscore(returns,120))),multiply(0.4,reverse(ts_corr(returns,divide(volume,ts_mean(volume, 20)),60))))),subindustry),10)); alpha3 = group_rank(rank(alpha3_raw), subindustry); alpha_mix = group_zscore(0.333333 * alpha1 + 0.333333 * alpha2 + 0.333333 * alpha3, industry); alpha_mix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `high-similarity field/operator/family cluster` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `implied_volatility_put_60, pcr_oi_270, implied_volatility_call_60, fnd6_txws, volume, raw1, a1, raw2, a2, ts_av_diff, turn, sharesout`. |
| Operator overlap | Common operators are `ts_decay_linear, group_zscore, group_rank, ts_backfill, rank, vec_avg, trade_when, ts_mean, abs, scale, max, ts_std_dev`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (27), tax/accounting fundamentals (27), options/implied volatility (27), price-volume/liquidity/turnover (16). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 17 |
| `failed-checks-strong-signal-repair-candidate` | 10 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 17 |
| failed: `LOW_SUB_UNIVERSE_SHARPE` | 10 |
| pending: `SELF_CORRELATION` | 27 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 13 | Options Skew Risk Appetite Variant 2 | `rKo6dQz8` | `hard_pass_signal_seed` | `2.8` | `3.24` | `15.37%` | `n/a` | `SELF_CORRELATION` | `812c7d505ed65b87` |
| 31 | Options Skew Risk Appetite Variant 8 | `JjdanMlO` | `hard_pass_signal_seed` | `2.71` | `2.8` | `18.18%` | `n/a` | `SELF_CORRELATION` | `ef32063d38955a4f` |
| 33 | Options Skew Risk Appetite Variant 9 | `XgKnWwkm` | `hard_pass_signal_seed` | `2.54` | `2.98` | `16.52%` | `n/a` | `SELF_CORRELATION` | `1edea4fcf7aa9fb8` |
| 49 | Options Skew Risk Appetite Variant 19 | `wpelqvkx` | `hard_pass_signal_seed` | `2.46` | `2.79` | `16.59%` | `n/a` | `SELF_CORRELATION` | `b024675e28b49746` |
| 55 | Options Skew Risk Appetite Variant 21 | `P013MZjJ` | `hard_pass_signal_seed` | `2.56` | `2.7` | `16.03%` | `n/a` | `SELF_CORRELATION` | `abebbf83e2fdc43f` |
| 93 | Options Skew Risk Appetite Variant 33 | `e7r0AWWz` | `hard_pass_signal_seed` | `2.5` | `2.55` | `16.09%` | `n/a` | `SELF_CORRELATION` | `119dde98019a1f22` |
| 99 | Options Skew Risk Appetite Variant 39 | `LLpgOnZ2` | `hard_pass_signal_seed` | `2.63` | `2.34` | `11.74%` | `n/a` | `SELF_CORRELATION` | `1b4176ac723231b6` |
| 110 | Options Skew Risk Appetite Variant 44 | `akOnKqlR` | `hard_pass_signal_seed` | `2.16` | `2.95` | `4.07%` | `n/a` | `SELF_CORRELATION` | `07f3dbc7c7e9b9bc` |
| 181 | Options Skew Risk Appetite Variant 64 | `e7rMnb6O` | `hard_pass_signal_seed` | `2.65` | `1.87` | `30.23%` | `n/a` | `SELF_CORRELATION` | `7d3883bc4f5533e0` |
| 190 | Options Skew Risk Appetite Variant 69 | `XgKZ2OZ0` | `hard_pass_signal_seed` | `2.46` | `2.05` | `17.96%` | `n/a` | `SELF_CORRELATION` | `426f8c02d3fe8d31` |
| 195 | Options Skew Risk Appetite Variant 73 | `e7O860jO` | `hard_pass_signal_seed` | `2.38` | `2.13` | `17.62%` | `n/a` | `SELF_CORRELATION` | `410908c1c1847761` |
| 208 | Options Skew Risk Appetite Variant 81 | `Grw0znxx` | `hard_pass_signal_seed` | `2.33` | `2.09` | `12.42%` | `n/a` | `SELF_CORRELATION` | `7dc27a401fc2819a` |
| 215 | Options Skew Risk Appetite Variant 88 | `MPplz70a` | `hard_pass_signal_seed` | `2.34` | `2.06` | `12.62%` | `n/a` | `SELF_CORRELATION` | `d4d06e0a898d6018` |
| 271 | Options Skew Risk Appetite Variant 107 | `QParzYGw` | `hard_pass_signal_seed` | `2.29` | `1.97` | `12.79%` | `n/a` | `SELF_CORRELATION` | `5725b80df20430a7` |
| 366 | Options Skew Risk Appetite Variant 139 | `e7r0eMOE` | `hard_pass_signal_seed` | `1.94` | `2.19` | `9.10%` | `n/a` | `SELF_CORRELATION` | `f0fb6ef6eeb797d9` |
| 377 | Options Skew Risk Appetite Variant 143 | `RRr8MA6d` | `hard_pass_signal_seed` | `1.92` | `2.18` | `9.07%` | `n/a` | `SELF_CORRELATION` | `0c258b7bb4d2e555` |
| 381 | Options Skew Risk Appetite Variant 145 | `rKo6d5Qd` | `hard_pass_signal_seed` | `2.32` | `1.64` | `18.58%` | `n/a` | `SELF_CORRELATION` | `393740d98f3196fc` |
| 91 | Options Skew Risk Appetite Variant 31 | `O0pbw6jq` | `strong_signal_repair_seed` | `2.81` | `2.83` | `10.20%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `c5bcf5dd2cea6a14` |
| 94 | Options Skew Risk Appetite Variant 34 | `rKoJ6Eb8` | `strong_signal_repair_seed` | `2.8` | `2.8` | `11.62%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `c5bcf5dd2cea6a14` |
| 95 | Options Skew Risk Appetite Variant 35 | `gJ1Rzq2e` | `strong_signal_repair_seed` | `2.8` | `2.8` | `11.62%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `c5bcf5dd2cea6a14` |
| 98 | Options Skew Risk Appetite Variant 38 | `qMAPe1jE` | `strong_signal_repair_seed` | `2.84` | `2.73` | `12.23%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `c5bcf5dd2cea6a14` |
| 111 | Options Skew Risk Appetite Variant 45 | `88zagPG7` | `strong_signal_repair_seed` | `2.83` | `2.71` | `12.25%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `9442c0e0b0b1d447` |
| 151 | Options Skew Risk Appetite Variant 54 | `QPa2qJ7W` | `strong_signal_repair_seed` | `2.79` | `2.56` | `14.63%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `c5bcf5dd2cea6a14` |
| 162 | Options Skew Risk Appetite Variant 56 | `blLo31JR` | `strong_signal_repair_seed` | `2.67` | `2.69` | `11.32%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `f4b2e25cef7adece` |
| 163 | Options Skew Risk Appetite Variant 57 | `kq31RZ5d` | `strong_signal_repair_seed` | `2.74` | `2.59` | `12.09%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `b6a797f6b3edf8b3` |
| 191 | Options Skew Risk Appetite Variant 70 | `N1pgMWgX` | `strong_signal_repair_seed` | `2.56` | `2.58` | `11.06%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `451bb73c8dca997b` |
| 406 | Options Skew Risk Appetite Variant 149 | `zq9wGXXE` | `strong_signal_repair_seed` | `2.37` | `2.16` | `12.20%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `e4362ce8fbab4918` |

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
