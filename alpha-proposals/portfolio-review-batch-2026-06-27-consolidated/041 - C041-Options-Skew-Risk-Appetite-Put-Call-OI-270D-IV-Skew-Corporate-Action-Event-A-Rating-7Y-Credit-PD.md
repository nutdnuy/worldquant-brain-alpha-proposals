---
title: "C041 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Corporate Action Event + A- Rating + 7Y Credit PD"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-041
member_count: 3
cluster_basis: "same-field same-operator variant"
representative_alpha: "Options Skew Risk Appetite Variant 108"
created: 2026-06-27
updated: 2026-06-27
---

# C041 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Corporate Action Event + A- Rating + 7Y Credit PD

> [!abstract] Consolidated Thesis
> This note combines **3** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 108 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `3` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | risk/credit/volatility (3), price-volume/liquidity/turnover (3), options/implied volatility (3) |
| Common fields | `alpha4, annualized_pd_7_year_jc7, returns, fnd6_newqeventv110_dpactq, implied_volatility_put_270, alpha2, pcr_oi_270, implied_volatility_call_270, alpha1, probability_non_investment_grade_rating, alpha3, probability_dist_a_minus` |
| Common operators | `min, ts_rank, ts_arg_min, group_zscore, ts_corr, group_rank, rank, vec_avg, ts_mean, trade_when, scale, ts_backfill` |
| Best recorded Sharpe | `1.94` |
| Best recorded Fitness | `2.43` |
| Median turnover | `11.69%` |
| Representative | Options Skew Risk Appetite Variant 108 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1 = -(ts_corr(rank(ts_backfill(probability_dist_a_minus, 63)), rank(ts_backfill(annualized_pd_7_year_jc7, 63)), 252)); alpha2 = group_rank(ts_arg_min(ts_backfill(vec_avg(fnd6_newqeventv110_dpactq), 120), 5), sector); alpha3 = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)), sector); alpha4 = -(ts_mean( returns * min(ts_rank(vwap, 10), ts_rank(close, 10)), 20)); alpha1_scaled = scale(group_neutralize(alpha1, industry)); alpha2_scaled = scale(group_neutralize(alpha2, industry)); alpha3_scaled = scale(group_neutralize(alpha3, industry)); alpha4_scaled = scale(group_neutralize(alpha4, industry)); alphamix_raw = (alpha1_scaled + alpha2_scaled + alpha3_scaled + alpha4_scaled) / 4; alphamix = scale(alphamix_raw); alphamix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha4, annualized_pd_7_year_jc7, returns, fnd6_newqeventv110_dpactq, implied_volatility_put_270, alpha2, pcr_oi_270, implied_volatility_call_270, alpha1, probability_non_investment_grade_rating, alpha3, probability_dist_a_minus`. |
| Operator overlap | Common operators are `min, ts_rank, ts_arg_min, group_zscore, ts_corr, group_rank, rank, vec_avg, ts_mean, trade_when, scale, ts_backfill`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (3), price-volume/liquidity/turnover (3), options/implied volatility (3). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 3 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 3 |
| pending: `SELF_CORRELATION` | 3 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 276 | Options Skew Risk Appetite Variant 108 | `gJ3oadwJ` | `hard_pass_signal_seed` | `1.94` | `2.43` | `11.69%` | `n/a` | `SELF_CORRELATION` | `5f1ce26225d072a4` |
| 277 | Options Skew Risk Appetite Variant 109 | `d5Ql9qLX` | `hard_pass_signal_seed` | `1.94` | `2.43` | `11.69%` | `n/a` | `SELF_CORRELATION` | `33866b8512254205` |
| 278 | Options Skew Risk Appetite Variant 110 | `akOWaAvx` | `hard_pass_signal_seed` | `1.94` | `2.43` | `11.69%` | `n/a` | `SELF_CORRELATION` | `036ce5947a0f7bf2` |

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
