---
title: "Price Volume Momentum Cluster 084 - returns"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-084
member_count: 2
cluster_basis: "exact-expression duplicate"
representative_alpha: "Price Volume Momentum Variant 12"
created: 2026-06-27
updated: 2026-06-27
---

# Price Volume Momentum Cluster 084 - returns

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **exact-expression duplicate**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Price Volume Momentum Variant 12 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `exact-expression duplicate` |
| Dominant families | price-volume/liquidity/turnover (2), analyst/model scores (2), risk/credit/volatility (2), news/sentiment/buzz (2) |
| Common fields | `alpha1, returns, probability_dist_aa_plus, alpha3, alpha1_scaled, nws12_afterhsz_sl, alpha2_avg_news, vwap, close, alpha2, mdl53_ms5_6month, alpha2_scaled` |
| Common operators | `ts_rank, ts_std_dev, scale, ts_mean, ts_delta, vec_avg, max, min, group_neutralize, ts_backfill, ts_corr, rank` |
| Best recorded Sharpe | `2` |
| Best recorded Fitness | `1.94` |
| Median turnover | `16.92%` |
| Representative | Price Volume Momentum Variant 12 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1 = -(ts_corr(rank(ts_backfill(probability_dist_aa_plus, 63)), rank(ts_backfill(mdl53_ms5_6month, 21)), 20)); alpha2_avg_news = vec_avg(nws12_afterhsz_sl); alpha2 = rank(ts_sum(alpha2_avg_news, 60)) > 0.5 ? 1 : rank(-ts_delta(close, 2)); alpha3 = -(ts_mean( returns * min(ts_rank(vwap, 10), ts_rank(close, 10)), 20)); alpha1_scaled = scale(group_neutralize(alpha1, industry)); alpha2_scaled = scale(group_neutralize(alpha2, industry)); alpha3_scaled = scale(group_neutralize(alpha3, industry)); alpha1_ret = alpha1_scaled * returns; alpha2_ret = alpha2_scaled * returns; alpha3_ret = alpha3_scaled * returns; alpha1_score = rank(ts_mean(alpha1_ret, 30) / max(ts_std_dev(alpha1_ret, 30), 0.0001)); alpha2_score = rank(ts_mean(alpha2_ret, 30) / max(ts_std_dev(alpha2_ret, 30), 0.0001)); alpha3_score = rank(ts_mean(alpha3_ret, 30) / max(ts_std_dev(alpha3_ret, 30), 0.0001)); w_sum = alpha1_score + alpha2_score + alpha3_score + 0.0001; alpha1_w = alpha1_score / w_sum; alpha2_w = alpha2_score / w_sum; alpha3_w = alpha3_score / w_sum; alphamix_raw = alpha1_w * alpha1_scaled + alpha2_w * alpha2_scaled + alpha3_w * alpha3_scaled; alphamix = scale(group_neutralize(alphamix_raw, industry)); alphamix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `exact-expression duplicate` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha1, returns, probability_dist_aa_plus, alpha3, alpha1_scaled, nws12_afterhsz_sl, alpha2_avg_news, vwap, close, alpha2, mdl53_ms5_6month, alpha2_scaled`. |
| Operator overlap | Common operators are `ts_rank, ts_std_dev, scale, ts_mean, ts_delta, vec_avg, max, min, group_neutralize, ts_backfill, ts_corr, rank`. |
| Family overlap | Dominant workbook families are price-volume/liquidity/turnover (2), analyst/model scores (2), risk/credit/volatility (2), news/sentiment/buzz (2). |
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
| 425 | Price Volume Momentum Variant 12 | `O092ep87` | `hard_pass_signal_seed` | `2` | `1.94` | `16.92%` | `n/a` | `SELF_CORRELATION` | `9fa48df957867f02` |
| 426 | Price Volume Momentum Variant 13 | `2rKLbLV6` | `hard_pass_signal_seed` | `2` | `1.94` | `16.92%` | `n/a` | `SELF_CORRELATION` | `9fa48df957867f02` |

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
