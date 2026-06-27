---
title: "Options Skew Risk Appetite Cluster 039 - sign implied_volatility_call_270"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-039
member_count: 3
cluster_basis: "same-field same-operator variant"
representative_alpha: "Options Skew Risk Appetite Variant 67"
created: 2026-06-27
updated: 2026-06-27
---

# Options Skew Risk Appetite Cluster 039 - sign implied_volatility_call_270

> [!abstract] Consolidated Thesis
> This note combines **3** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 67 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `3` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | quality/growth/value (3), options/implied volatility (3), analyst/model scores (3), price-volume/liquidity/turnover (3), risk/credit/volatility (3) |
| Common fields | `sign, implied_volatility_call_270, pcr_oi_270, mdl77_historicalgrowthfactor_y3speq4rqsr, p1_raw, p3_raw, implied_volatility_put_270, p1, p2_raw, probability_non_investment_grade_rating, p2, unexpected_change_accounts_receivable` |
| Common operators | `ts_backfill, zscore, ts_rank, winsorize, multiply, divide, group_zscore, ts_decay_linear, group_neutralize, ts_mean, ts_corr, rank` |
| Best recorded Sharpe | `2.43` |
| Best recorded Fitness | `2.26` |
| Median turnover | `13.15%` |
| Representative | Options Skew Risk Appetite Variant 67 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> p1_raw = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)), industry); p1 = scale(group_neutralize(p1_raw, industry)); p2_raw = -(ts_corr(rank(ts_backfill(mdl77_historicalgrowthfactor_y3speq4rqsr, 63)), rank(ts_backfill(unexpected_change_accounts_receivable, 63)), 126)); p2 = scale(group_neutralize(p2_raw, industry)); p3_raw = -(zscore(ts_decay_linear(group_neutralize(ts_rank(winsorize(multiply(sign(returns), rank(divide(volume, adv20))), std=4), 20), subindustry), 5))); p3 = scale(group_neutralize(p3_raw, industry)); alpha_mix = group_zscore(0.4746 * p1 + 0.3989 * p2 + 0.1266 * p3, industry); alpha_mix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `sign, implied_volatility_call_270, pcr_oi_270, mdl77_historicalgrowthfactor_y3speq4rqsr, p1_raw, p3_raw, implied_volatility_put_270, p1, p2_raw, probability_non_investment_grade_rating, p2, unexpected_change_accounts_receivable`. |
| Operator overlap | Common operators are `ts_backfill, zscore, ts_rank, winsorize, multiply, divide, group_zscore, ts_decay_linear, group_neutralize, ts_mean, ts_corr, rank`. |
| Family overlap | Dominant workbook families are quality/growth/value (3), options/implied volatility (3), analyst/model scores (3), price-volume/liquidity/turnover (3), risk/credit/volatility (3). |
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
| 185 | Options Skew Risk Appetite Variant 67 | `omYdw0GJ` | `hard_pass_signal_seed` | `2.32` | `2.26` | `13.15%` | `n/a` | `SELF_CORRELATION` | `18010ea8a84e4f61` |
| 201 | Options Skew Risk Appetite Variant 77 | `pw6wgnZ6` | `hard_pass_signal_seed` | `2.26` | `2.22` | `12.79%` | `n/a` | `SELF_CORRELATION` | `46ed8665b0b48676` |
| 333 | Options Skew Risk Appetite Variant 130 | `E5w53K3L` | `hard_pass_signal_seed` | `2.43` | `1.61` | `25.79%` | `n/a` | `SELF_CORRELATION` | `844c9f906ed049b1` |

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
