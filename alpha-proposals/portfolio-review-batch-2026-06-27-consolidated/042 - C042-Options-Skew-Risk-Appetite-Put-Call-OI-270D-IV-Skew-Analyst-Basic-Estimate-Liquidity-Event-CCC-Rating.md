---
title: "C042 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Analyst Basic Estimate + Liquidity Event + CCC+ Rating"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-042
member_count: 3
cluster_basis: "same-field same-operator variant"
representative_alpha: "Options Skew Risk Appetite Variant 150"
created: 2026-06-27
updated: 2026-06-27
---

# C042 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Analyst Basic Estimate + Liquidity Event + CCC+ Rating

> [!abstract] Consolidated Thesis
> This note combines **3** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 150 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `3` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | risk/credit/volatility (3), analyst/model scores (3), price-volume/liquidity/turnover (3), options/implied volatility (3) |
| Common fields | `alpha4, probability_rating_ccc_plus, implied_volatility_put_270, alpha2, pcr_oi_270, implied_volatility_call_270, annualized_pd_2_year_jc7, alpha1, anl4_dez1basicafv4_est, fnd6_newqeventv110_lqpl1q, probability_non_investment_grade_rating, alpha3` |
| Common operators | `min, ts_rank, group_zscore, ts_corr, zscore, rank, vec_avg, ts_mean, trade_when, scale, ts_backfill, group_neutralize` |
| Best recorded Sharpe | `1.64` |
| Best recorded Fitness | `2.46` |
| Median turnover | `6.80%` |
| Representative | Options Skew Risk Appetite Variant 150 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1 = -(group_neutralize(zscore(ts_backfill(vec_avg(probability_rating_ccc_plus), 250)) - zscore(ts_backfill(annualized_pd_2_year_jc7, 63)), sector)); alpha2 = -(ts_corr(rank(ts_backfill(vec_avg(fnd6_newqeventv110_lqpl1q), 120)), rank(ts_backfill(vec_avg(anl4_dez1basicafv4_est), 21)), 252)); alpha3 = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)), sector); alpha4 = -(ts_mean( returns * min(ts_rank(vwap, 10), ts_rank(close, 10)), 20)); alpha1_scaled = scale(group_neutralize(alpha1, industry)); alpha2_scaled = scale(group_neutralize(alpha2, industry)); alpha3_scaled = scale(group_neutralize(alpha3, industry)); alpha4_scaled = scale(group_neutralize(alpha4, industry)); alphamix_raw = (alpha1_scaled + alpha2_scaled + alpha3_scaled + alpha4_scaled) / 4; alphamix = scale(alphamix_raw); alphamix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha4, probability_rating_ccc_plus, implied_volatility_put_270, alpha2, pcr_oi_270, implied_volatility_call_270, annualized_pd_2_year_jc7, alpha1, anl4_dez1basicafv4_est, fnd6_newqeventv110_lqpl1q, probability_non_investment_grade_rating, alpha3`. |
| Operator overlap | Common operators are `min, ts_rank, group_zscore, ts_corr, zscore, rank, vec_avg, ts_mean, trade_when, scale, ts_backfill, group_neutralize`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (3), analyst/model scores (3), price-volume/liquidity/turnover (3), options/implied volatility (3). |
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
| 407 | Options Skew Risk Appetite Variant 150 | `Jjd5wNzE` | `hard_pass_signal_seed` | `1.64` | `2.46` | `6.80%` | `n/a` | `SELF_CORRELATION` | `ad940be16e52b069` |
| 408 | Options Skew Risk Appetite Variant 151 | `Gro3apRO` | `hard_pass_signal_seed` | `1.64` | `2.46` | `6.80%` | `n/a` | `SELF_CORRELATION` | `48ffa73e36c1cf48` |
| 409 | Options Skew Risk Appetite Variant 152 | `3qAnrw06` | `hard_pass_signal_seed` | `1.64` | `2.46` | `6.80%` | `n/a` | `SELF_CORRELATION` | `5b336c7eb4319465` |

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
