---
title: "C059 - Price Volume Reversal - Price Liquidity + Net Debt + B Rating + 1Y Credit PD + Receivables Change"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-059
member_count: 2
cluster_basis: "same-field same-operator variant"
representative_alpha: "Price Volume Reversal Variant 4"
created: 2026-06-27
updated: 2026-06-27
---

# C059 - Price Volume Reversal - Price Liquidity + Net Debt + B Rating + 1Y Credit PD + Receivables Change

> [!abstract] Consolidated Thesis
> This note combines **2** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Price Volume Reversal Variant 4 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `2` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | risk/credit/volatility (2), analyst/model scores (2), tax/accounting fundamentals (2), price-volume/liquidity/turnover (2) |
| Common fields | `returns, probability_dist_b, volume, anl4_netdebt_number, p1_raw, reverse, p1, p2, annualized_pd_1_year_jc7, p2_raw, p3_raw, anl4_detailrecv4_est` |
| Common operators | `multiply, divide, add, zscore, ts_corr, rank, ts_zscore, vec_avg, ts_decay_linear, ts_backfill, group_neutralize, scale` |
| Best recorded Sharpe | `2.35` |
| Best recorded Fitness | `2.2` |
| Median turnover | `17.41%` |
| Representative | Price Volume Reversal Variant 4 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> p1_raw = -(ts_corr(rank(ts_backfill(anl4_netdebt_number, 120)), rank(ts_backfill(vec_avg(anl4_detailrecv4_est), 21)), 126)); p1 = rank(p1_raw); p2_raw = -(ts_corr(rank(ts_backfill(probability_dist_b, 63)), rank(ts_backfill(annualized_pd_1_year_jc7, 63)), 5)); p2 = rank(p2_raw); p3_raw = zscore(ts_decay_linear(group_neutralize(rank(add(multiply(0.70,reverse(ts_zscore(returns,120))),multiply(0.30,reverse(ts_corr(returns,divide(volume,adv20),60))))),subindustry),10)); p3 = rank(p3_raw); alpha_mix = scale(group_neutralize(0.4336 * p1 + 0.4472 * p2 + 0.1192 * p3, industry)); alpha_mix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `returns, probability_dist_b, volume, anl4_netdebt_number, p1_raw, reverse, p1, p2, annualized_pd_1_year_jc7, p2_raw, p3_raw, anl4_detailrecv4_est`. |
| Operator overlap | Common operators are `multiply, divide, add, zscore, ts_corr, rank, ts_zscore, vec_avg, ts_decay_linear, ts_backfill, group_neutralize, scale`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (2), analyst/model scores (2), tax/accounting fundamentals (2), price-volume/liquidity/turnover (2). |
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
| 189 | Price Volume Reversal Variant 4 | `E5KdoKQr` | `hard_pass_signal_seed` | `2.35` | `2.2` | `17.41%` | `n/a` | `SELF_CORRELATION` | `51a1f0a95c0e2b92` |
| 273 | Price Volume Reversal Variant 5 | `RRrg0lAj` | `hard_pass_signal_seed` | `2.27` | `1.99` | `17.12%` | `n/a` | `SELF_CORRELATION` | `e862975b11b013e4` |

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
