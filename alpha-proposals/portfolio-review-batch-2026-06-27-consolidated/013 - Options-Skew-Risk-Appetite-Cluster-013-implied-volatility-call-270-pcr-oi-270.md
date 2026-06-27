---
title: "Options Skew Risk Appetite Cluster 013 - implied_volatility_call_270 pcr_oi_270"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-013
member_count: 7
cluster_basis: "same-field same-operator variant"
representative_alpha: "Options Skew Risk Appetite Variant 78"
created: 2026-06-27
updated: 2026-06-27
---

# Options Skew Risk Appetite Cluster 013 - implied_volatility_call_270 pcr_oi_270

> [!abstract] Consolidated Thesis
> This note combines **7** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 78 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `7` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | quality/growth/value (7), options/implied volatility (7), analyst/model scores (7), price-volume/liquidity/turnover (7), risk/credit/volatility (7) |
| Common fields | `implied_volatility_call_270, pcr_oi_270, mdl77_historicalgrowthfactor_y3speq4rqsr, p1_raw, p3_raw, implied_volatility_put_270, p1, p2_raw, probability_non_investment_grade_rating, p2, unexpected_change_accounts_receivable, reverse` |
| Common operators | `ts_backfill, zscore, multiply, add, ts_zscore, divide, vec_avg, group_zscore, ts_decay_linear, group_rank, group_neutralize, ts_mean` |
| Best recorded Sharpe | `2.3` |
| Best recorded Fitness | `2.15` |
| Median turnover | `9.84%` |
| Representative | Options Skew Risk Appetite Variant 78 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> p1_raw = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)), industry); p1 = group_zscore(rank(p1_raw), industry); p2_raw = -(ts_corr(rank(ts_backfill(mdl77_historicalgrowthfactor_y3speq4rqsr, 63)), rank(ts_backfill(unexpected_change_accounts_receivable, 63)), 126)); p2 = group_zscore(rank(p2_raw), industry); p3_raw = zscore(ts_decay_linear(group_neutralize(rank(add(multiply(0.70,reverse(ts_zscore(returns,120))),multiply(0.30,reverse(ts_corr(returns,divide(volume,adv20),60))))),subindustry),10)); p3 = group_zscore(rank(p3_raw), industry); p4_raw = -(ts_corr(rank(ts_backfill(vec_avg(fnd6_newqeventv110_lqpl1q), 120)), rank(ts_backfill(vec_avg(anl4_dez1basicafv4_est), 21)), 252)); p4b = group_zscore(rank(p4_raw), industry); p4 = group_zscore(p4b - 0.08 * p1 - 0.06 * p2, industry); alpha_mix = group_rank(0.2550 * p1 + 0.3230 * p2 + 0.2720 * p3 + 0.1500 * p4, sector); alpha_mix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `implied_volatility_call_270, pcr_oi_270, mdl77_historicalgrowthfactor_y3speq4rqsr, p1_raw, p3_raw, implied_volatility_put_270, p1, p2_raw, probability_non_investment_grade_rating, p2, unexpected_change_accounts_receivable, reverse`. |
| Operator overlap | Common operators are `ts_backfill, zscore, multiply, add, ts_zscore, divide, vec_avg, group_zscore, ts_decay_linear, group_rank, group_neutralize, ts_mean`. |
| Family overlap | Dominant workbook families are quality/growth/value (7), options/implied volatility (7), analyst/model scores (7), price-volume/liquidity/turnover (7), risk/credit/volatility (7). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 7 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 7 |
| pending: `SELF_CORRELATION` | 7 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 203 | Options Skew Risk Appetite Variant 78 | `O0p0WdPd` | `hard_pass_signal_seed` | `2.3` | `2.15` | `9.74%` | `n/a` | `SELF_CORRELATION` | `1f827a27243db514` |
| 213 | Options Skew Risk Appetite Variant 86 | `MPpPg52L` | `hard_pass_signal_seed` | `2.29` | `2.13` | `9.42%` | `n/a` | `SELF_CORRELATION` | `b0b748f433f72bf2` |
| 212 | Options Skew Risk Appetite Variant 85 | `blLlzk7p` | `hard_pass_signal_seed` | `2.29` | `2.13` | `9.84%` | `n/a` | `SELF_CORRELATION` | `5ed13d13d88cc677` |
| 214 | Options Skew Risk Appetite Variant 87 | `0m7mNjgK` | `hard_pass_signal_seed` | `2.29` | `2.13` | `9.91%` | `n/a` | `SELF_CORRELATION` | `3b125b81cbb3d963` |
| 225 | Options Skew Risk Appetite Variant 93 | `Vkpkm25b` | `hard_pass_signal_seed` | `2.28` | `2.12` | `9.96%` | `n/a` | `SELF_CORRELATION` | `972766a2fc8fcc12` |
| 227 | Options Skew Risk Appetite Variant 95 | `GrwrQgw0` | `hard_pass_signal_seed` | `2.28` | `2.11` | `8.96%` | `n/a` | `SELF_CORRELATION` | `8e8955fd9bf28207` |
| 246 | Options Skew Risk Appetite Variant 100 | `JjpjoA5m` | `hard_pass_signal_seed` | `2.27` | `2.1` | `10.00%` | `n/a` | `SELF_CORRELATION` | `6e6b32e648cc2b28` |

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
