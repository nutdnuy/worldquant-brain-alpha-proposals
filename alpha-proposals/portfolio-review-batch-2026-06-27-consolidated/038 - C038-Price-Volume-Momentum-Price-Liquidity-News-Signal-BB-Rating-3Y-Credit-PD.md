---
title: "C038 - Price Volume Momentum - Price Liquidity + News Signal + BB+ Rating + 3Y Credit PD"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-038
member_count: 3
cluster_basis: "high-similarity field/operator/family cluster"
representative_alpha: "Price Volume Momentum Variant 3"
created: 2026-06-27
updated: 2026-06-27
---

# C038 - Price Volume Momentum - Price Liquidity + News Signal + BB+ Rating + 3Y Credit PD

> [!abstract] Consolidated Thesis
> This note combines **3** highly similar alpha proposals into one research idea. The consolidation basis is **high-similarity field/operator/family cluster**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Price Volume Momentum Variant 3 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `3` |
| Cluster basis | `high-similarity field/operator/family cluster` |
| Dominant families | risk/credit/volatility (3), news/sentiment/buzz (3), price-volume/liquidity/turnover (3) |
| Common fields | `alpha3, returns, alpha1_scaled, alpha2, alpha1, alpha2_scaled, nws12_afterhsz_sl, vwap, close, annualized_pd_3_year_jc7, alpha3_scaled, probability_rating_bb` |
| Common operators | `ts_delta, min, ts_rank, max, ts_corr, rank, ts_sum, vec_avg, ts_mean, ts_std_dev, scale, ts_backfill` |
| Best recorded Sharpe | `2.18` |
| Best recorded Fitness | `2.6` |
| Median turnover | `12.57%` |
| Representative | Price Volume Momentum Variant 3 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1 = -rank(ts_corr(rank(ts_backfill(probability_dist_bb_plus, 63)), rank(ts_backfill(annualized_pd_3_year_jc7, 63)), 30)); alpha2 = rank(ts_sum(vec_avg(nws12_afterhsz_sl), 60)) > 0.5 ? 1 : rank(-ts_delta(close, 2)); alpha3 = -(ts_mean( returns * min(ts_rank(vwap, 10), ts_rank(close, 10)), 20)); alpha1_scaled = scale(group_neutralize(alpha1, industry)); alpha2_scaled = scale(group_neutralize(alpha2, industry)); alpha3_scaled = scale(group_neutralize(alpha3, industry)); alpha1_ret = alpha1_scaled * returns; alpha2_ret = alpha2_scaled * returns; alpha3_ret = alpha3_scaled * returns; alpha1_score = rank(ts_mean(alpha1_ret, 30) / max(ts_std_dev(alpha1_ret, 30), 0.0001)); alpha2_score = rank(ts_mean(alpha2_ret, 30) / max(ts_std_dev(alpha2_ret, 30), 0.0001)); alpha3_score = rank(ts_mean(alpha3_ret, 30) / max(ts_std_dev(alpha3_ret, 30), 0.0001)); w_sum = alpha1_score + alpha2_score + alpha3_score + 0.0001; alpha1_w = alpha1_score / w_sum; alpha2_w = alpha2_score / w_sum; alpha3_w = alpha3_score / w_sum; alphamix_raw = alpha1_w * alpha1_scaled + alpha2_w * alpha2_scaled + alpha3_w * alpha3_scaled; alphamix = scale(group_neutralize(alphamix_raw, industry)); alphamix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `high-similarity field/operator/family cluster` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha3, returns, alpha1_scaled, alpha2, alpha1, alpha2_scaled, nws12_afterhsz_sl, vwap, close, annualized_pd_3_year_jc7, alpha3_scaled, probability_rating_bb`. |
| Operator overlap | Common operators are `ts_delta, min, ts_rank, max, ts_corr, rank, ts_sum, vec_avg, ts_mean, ts_std_dev, scale, ts_backfill`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (3), news/sentiment/buzz (3), price-volume/liquidity/turnover (3). |
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
| 188 | Price Volume Momentum Variant 3 | `omY3b7a6` | `hard_pass_signal_seed` | `2.18` | `2.44` | `14.55%` | `n/a` | `SELF_CORRELATION` | `ab119d5ff6516636` |
| 199 | Price Volume Momentum Variant 4 | `bl9omavN` | `hard_pass_signal_seed` | `2` | `2.6` | `12.57%` | `n/a` | `SELF_CORRELATION` | `761673b87622f193` |
| 202 | Price Volume Momentum Variant 5 | `RRrpvb7d` | `hard_pass_signal_seed` | `1.99` | `2.58` | `12.57%` | `n/a` | `SELF_CORRELATION` | `9d8210c958f19662` |

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
