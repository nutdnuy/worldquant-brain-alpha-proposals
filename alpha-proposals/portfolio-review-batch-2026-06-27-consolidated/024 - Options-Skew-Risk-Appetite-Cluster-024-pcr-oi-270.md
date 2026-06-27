---
title: "Options Skew Risk Appetite Cluster 024 - pcr_oi_270"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-024
member_count: 4
cluster_basis: "same-field same-operator variant"
representative_alpha: "Options Skew Risk Appetite Variant 2"
created: 2026-06-27
updated: 2026-06-27
---

# Options Skew Risk Appetite Cluster 024 - pcr_oi_270

> [!abstract] Consolidated Thesis
> This note combines **4** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 2 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `4` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | options/implied volatility (4), tax/accounting fundamentals (4), risk/credit/volatility (4), price-volume/liquidity/turnover (4) |
| Common fields | `alpha1, pcr_oi_270, alpha1_raw, returns, volume, fnd6_txws, implied_volatility_call_60, alpha3_raw, alpha2, alpha2_raw, implied_volatility_put_60, reverse` |
| Common operators | `zscore, multiply, ts_mean, add, ts_zscore, divide, vec_avg, group_zscore, ts_decay_linear, group_rank, group_neutralize, ts_backfill` |
| Best recorded Sharpe | `2.8` |
| Best recorded Fitness | `3.24` |
| Median turnover | `17.96%` |
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
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha1, pcr_oi_270, alpha1_raw, returns, volume, fnd6_txws, implied_volatility_call_60, alpha3_raw, alpha2, alpha2_raw, implied_volatility_put_60, reverse`. |
| Operator overlap | Common operators are `zscore, multiply, ts_mean, add, ts_zscore, divide, vec_avg, group_zscore, ts_decay_linear, group_rank, group_neutralize, ts_backfill`. |
| Family overlap | Dominant workbook families are options/implied volatility (4), tax/accounting fundamentals (4), risk/credit/volatility (4), price-volume/liquidity/turnover (4). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 4 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 4 |
| pending: `SELF_CORRELATION` | 4 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 13 | Options Skew Risk Appetite Variant 2 | `rKo6dQz8` | `hard_pass_signal_seed` | `2.8` | `3.24` | `15.37%` | `n/a` | `SELF_CORRELATION` | `812c7d505ed65b87` |
| 31 | Options Skew Risk Appetite Variant 8 | `JjdanMlO` | `hard_pass_signal_seed` | `2.71` | `2.8` | `18.18%` | `n/a` | `SELF_CORRELATION` | `ef32063d38955a4f` |
| 190 | Options Skew Risk Appetite Variant 69 | `XgKZ2OZ0` | `hard_pass_signal_seed` | `2.46` | `2.05` | `17.96%` | `n/a` | `SELF_CORRELATION` | `426f8c02d3fe8d31` |
| 195 | Options Skew Risk Appetite Variant 73 | `e7O860jO` | `hard_pass_signal_seed` | `2.38` | `2.13` | `17.62%` | `n/a` | `SELF_CORRELATION` | `410908c1c1847761` |

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
