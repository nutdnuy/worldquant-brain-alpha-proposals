---
title: "Options Skew Risk Appetite Cluster 063 - implied_volatility_put_30 _s3_cogs_s"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-063
member_count: 2
cluster_basis: "exact-expression duplicate"
representative_alpha: "Options Skew Risk Appetite Variant 62"
created: 2026-06-27
updated: 2026-06-27
---

# Options Skew Risk Appetite Cluster 063 - implied_volatility_put_30 _s3_cogs_s

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **exact-expression duplicate**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 62 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `exact-expression duplicate` |
| Dominant families | options/implied volatility (2), tax/accounting fundamentals (2), price-volume/liquidity/turnover (2), risk/credit/volatility (2), news/sentiment/buzz (2) |
| Common fields | `implied_volatility_put_30, _s3_cogs_s, cogs, s2, cap, _s3_cogs_g, implied_volatility_call_30, close, s3, open, s1, _s3_cogs_r` |
| Common operators | `ts_backfill, zscore, ts_delta, vec_avg, abs, group_zscore, ts_mean, rank, trade_when, ts_sum` |
| Best recorded Sharpe | `2.26` |
| Best recorded Fitness | `2.61` |
| Median turnover | `47.79%` |
| Representative | Options Skew Risk Appetite Variant 62 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> s1 = zscore(group_zscore(ts_mean(implied_volatility_call_30 - implied_volatility_put_30, 5), sector)); s2 = zscore(group_zscore(-ts_mean((close - open) / open, 5), subindustry)); _s3_cogs_r = zscore(cogs/cap); _s3_cogs_s = ts_mean(_s3_cogs_r, 3); _s3_cogs_g = trade_when(rank(abs(_s3_cogs_s)) > 0.85, _s3_cogs_s, 0); s3 = zscore(0.35 * _s3_cogs_g + 0.65 * rank(_s3_cogs_s)); s4 = zscore(rank(ts_sum(vec_avg(nws12_afterhsz_sl), 60)) > 0.5 ? 1 : rank(-ts_delta(close, 2))); s5 = zscore(rank(ts_delta(ts_backfill(fnd6_txtubpospinc, 252) / cap, 60))); zscore(0.25 * s1 + 0.20 * s2 + 0.25 * s3 + 0.15 * s4 + 0.15 * s5)
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `exact-expression duplicate` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `implied_volatility_put_30, _s3_cogs_s, cogs, s2, cap, _s3_cogs_g, implied_volatility_call_30, close, s3, open, s1, _s3_cogs_r`. |
| Operator overlap | Common operators are `ts_backfill, zscore, ts_delta, vec_avg, abs, group_zscore, ts_mean, rank, trade_when, ts_sum`. |
| Family overlap | Dominant workbook families are options/implied volatility (2), tax/accounting fundamentals (2), price-volume/liquidity/turnover (2), risk/credit/volatility (2), news/sentiment/buzz (2). |
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
| 178 | Options Skew Risk Appetite Variant 62 | `npORElgM` | `hard_pass_signal_seed` | `2.12` | `2.61` | `23.12%` | `n/a` | `SELF_CORRELATION` | `5ef507dcdd1a47a0` |
| 295 | Options Skew Risk Appetite Variant 115 | `YPWGPK8q` | `hard_pass_signal_seed` | `2.26` | `1.95` | `47.79%` | `n/a` | `SELF_CORRELATION` | `5ef507dcdd1a47a0` |

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
