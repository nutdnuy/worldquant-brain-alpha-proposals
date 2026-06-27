---
title: "Options Skew Risk Appetite Cluster 030 - pcr_oi_270"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-030
member_count: 4
cluster_basis: "same-field same-operator variant"
representative_alpha: "Options Skew Risk Appetite Variant 81"
created: 2026-06-27
updated: 2026-06-27
---

# Options Skew Risk Appetite Cluster 030 - pcr_oi_270

> [!abstract] Consolidated Thesis
> This note combines **4** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 81 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `4` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | options/implied volatility (4), tax/accounting fundamentals (4), risk/credit/volatility (4) |
| Common fields | `raw1, pcr_oi_270, raw2, returns, fnd6_txws, implied_volatility_call_60, vscore1, vol1, vol2, a1, a2, implied_volatility_put_60` |
| Common operators | `ts_backfill, ts_std_dev, scale, vec_avg, max, group_zscore, group_rank, ts_decay_linear, ts_mean, rank, trade_when, min` |
| Best recorded Sharpe | `2.37` |
| Best recorded Fitness | `2.16` |
| Median turnover | `12.62%` |
| Representative | Options Skew Risk Appetite Variant 81 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> raw1 = trade_when(ts_mean(pcr_oi_270, 2) < 1, group_zscore(ts_mean((implied_volatility_call_60 - implied_volatility_put_60), 5), sector), -1); a1 = rank(raw1); raw2 = group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector); a2 = rank(raw2); vol1 = ts_backfill(ts_std_dev(a1 * returns, 60), 120); vscore1 = rank(vol1); vol2 = ts_backfill(ts_std_dev(a2 * returns, 60), 120); vscore2 = rank(vol2); iv1 = (1 / max(vscore1, 0.01)); iv2 = (1 / max(vscore2, 0.01)); w_raw = iv1 / (iv1 + iv2); w = ts_mean(min(max(w_raw, 0.12), 0.88), 32); alpha = scale(w * a1 + (1 - w) * a2); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `raw1, pcr_oi_270, raw2, returns, fnd6_txws, implied_volatility_call_60, vscore1, vol1, vol2, a1, a2, implied_volatility_put_60`. |
| Operator overlap | Common operators are `ts_backfill, ts_std_dev, scale, vec_avg, max, group_zscore, group_rank, ts_decay_linear, ts_mean, rank, trade_when, min`. |
| Family overlap | Dominant workbook families are options/implied volatility (4), tax/accounting fundamentals (4), risk/credit/volatility (4). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 3 |
| `failed-checks-strong-signal-repair-candidate` | 1 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 3 |
| failed: `LOW_SUB_UNIVERSE_SHARPE` | 1 |
| pending: `SELF_CORRELATION` | 4 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 208 | Options Skew Risk Appetite Variant 81 | `Grw0znxx` | `hard_pass_signal_seed` | `2.33` | `2.09` | `12.42%` | `n/a` | `SELF_CORRELATION` | `7dc27a401fc2819a` |
| 215 | Options Skew Risk Appetite Variant 88 | `MPplz70a` | `hard_pass_signal_seed` | `2.34` | `2.06` | `12.62%` | `n/a` | `SELF_CORRELATION` | `d4d06e0a898d6018` |
| 271 | Options Skew Risk Appetite Variant 107 | `QParzYGw` | `hard_pass_signal_seed` | `2.29` | `1.97` | `12.79%` | `n/a` | `SELF_CORRELATION` | `5725b80df20430a7` |
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
