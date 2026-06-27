---
title: "Options Skew Risk Appetite Cluster 009 - turn"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-009
member_count: 10
cluster_basis: "same-field same-operator variant"
representative_alpha: "Options Skew Risk Appetite Variant 39"
created: 2026-06-27
updated: 2026-06-27
---

# Options Skew Risk Appetite Cluster 009 - turn

> [!abstract] Consolidated Thesis
> This note combines **10** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 39 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `10` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | options/implied volatility (10), tax/accounting fundamentals (10), risk/credit/volatility (10), price-volume/liquidity/turnover (10) |
| Common fields | `raw1, turn, pcr_oi_270, raw2, volume, fnd6_txws, implied_volatility_call_60, ts_av_diff, sharesout, a1, a2, implied_volatility_put_60` |
| Common operators | `ts_backfill, ts_std_dev, scale, winsorize, vec_avg, max, abs, group_zscore, group_rank, ts_decay_linear, ts_mean, rank` |
| Best recorded Sharpe | `2.84` |
| Best recorded Fitness | `2.83` |
| Median turnover | `11.74%` |
| Representative | Options Skew Risk Appetite Variant 39 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> raw1 = trade_when(ts_mean(pcr_oi_270, 2) < 1, group_zscore(ts_mean((implied_volatility_call_60 - implied_volatility_put_60), 5), sector), -1); a1 = rank(raw1); raw2 = group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector); a2 = rank(raw2); turn = ts_mean(winsorize(ts_av_diff(ts_backfill(volume/sharesout, 5), 504), std=4), 30); a3 = rank(abs(turn)) * group_rank(turn, subindustry); v1 = rank(ts_backfill(ts_std_dev(a1 * returns, 60), 120)); v2 = rank(ts_backfill(ts_std_dev(a2 * returns, 60), 120)); w = ts_mean((1/max(v1,0.01))/(1/max(v1,0.01)+1/max(v2,0.01)), 32); mix = scale(0.82 * scale(w*a1 + (1-w)*a2) + 0.18 * scale(a3)); alpha = group_rank(mix, subindustry); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `raw1, turn, pcr_oi_270, raw2, volume, fnd6_txws, implied_volatility_call_60, ts_av_diff, sharesout, a1, a2, implied_volatility_put_60`. |
| Operator overlap | Common operators are `ts_backfill, ts_std_dev, scale, winsorize, vec_avg, max, abs, group_zscore, group_rank, ts_decay_linear, ts_mean, rank`. |
| Family overlap | Dominant workbook families are options/implied volatility (10), tax/accounting fundamentals (10), risk/credit/volatility (10), price-volume/liquidity/turnover (10). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `failed-checks-strong-signal-repair-candidate` | 9 |
| `recorded-hard-pass-rebuild-candidate` | 1 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `LOW_SUB_UNIVERSE_SHARPE` | 9 |
| failed: `n/a` | 1 |
| pending: `SELF_CORRELATION` | 10 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 99 | Options Skew Risk Appetite Variant 39 | `LLpgOnZ2` | `hard_pass_signal_seed` | `2.63` | `2.34` | `11.74%` | `n/a` | `SELF_CORRELATION` | `1b4176ac723231b6` |
| 91 | Options Skew Risk Appetite Variant 31 | `O0pbw6jq` | `strong_signal_repair_seed` | `2.81` | `2.83` | `10.20%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `c5bcf5dd2cea6a14` |
| 94 | Options Skew Risk Appetite Variant 34 | `rKoJ6Eb8` | `strong_signal_repair_seed` | `2.8` | `2.8` | `11.62%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `c5bcf5dd2cea6a14` |
| 95 | Options Skew Risk Appetite Variant 35 | `gJ1Rzq2e` | `strong_signal_repair_seed` | `2.8` | `2.8` | `11.62%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `c5bcf5dd2cea6a14` |
| 98 | Options Skew Risk Appetite Variant 38 | `qMAPe1jE` | `strong_signal_repair_seed` | `2.84` | `2.73` | `12.23%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `c5bcf5dd2cea6a14` |
| 111 | Options Skew Risk Appetite Variant 45 | `88zagPG7` | `strong_signal_repair_seed` | `2.83` | `2.71` | `12.25%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `9442c0e0b0b1d447` |
| 151 | Options Skew Risk Appetite Variant 54 | `QPa2qJ7W` | `strong_signal_repair_seed` | `2.79` | `2.56` | `14.63%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `c5bcf5dd2cea6a14` |
| 162 | Options Skew Risk Appetite Variant 56 | `blLo31JR` | `strong_signal_repair_seed` | `2.67` | `2.69` | `11.32%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `f4b2e25cef7adece` |
| 163 | Options Skew Risk Appetite Variant 57 | `kq31RZ5d` | `strong_signal_repair_seed` | `2.74` | `2.59` | `12.09%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `b6a797f6b3edf8b3` |
| 191 | Options Skew Risk Appetite Variant 70 | `N1pgMWgX` | `strong_signal_repair_seed` | `2.56` | `2.58` | `11.06%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `451bb73c8dca997b` |

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
