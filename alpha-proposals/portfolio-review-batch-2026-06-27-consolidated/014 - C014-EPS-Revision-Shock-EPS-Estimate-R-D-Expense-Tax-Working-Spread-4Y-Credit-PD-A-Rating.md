---
title: "C014 - EPS Revision Shock - EPS Estimate + R&D Expense + Tax Working Spread + 4Y Credit PD + A+ Rating"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-014
member_count: 6
cluster_basis: "same-field same-operator variant"
representative_alpha: "EPS Revision Shock Variant 15"
created: 2026-06-27
updated: 2026-06-27
---

# C014 - EPS Revision Shock - EPS Estimate + R&D Expense + Tax Working Spread + 4Y Credit PD + A+ Rating

> [!abstract] Consolidated Thesis
> This note combines **6** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** EPS Revision Shock Variant 15 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `6` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | risk/credit/volatility (6), quality/growth/value (6), earnings/EPS/guidance revisions (6), options/implied volatility (6), tax/accounting fundamentals (6) |
| Common fields | `alpha4, annualized_pd_4_year_jc7, implied_volatility_put_270, eps_previous_estimate_value, research_development_expense, alpha2, pcr_oi_270, implied_volatility_call_270, alpha1, fnd6_txws, probability_dist_a_plus, alpha3` |
| Common operators | `group_zscore, ts_corr, group_rank, ts_mean, rank, vec_avg, trade_when, ts_decay_linear, scale, ts_backfill, group_neutralize` |
| Best recorded Sharpe | `2.34` |
| Best recorded Fitness | `2.9` |
| Median turnover | `12.92%` |
| Representative | EPS Revision Shock Variant 15 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> alpha1 = -(group_rank(rank(ts_corr(vec_avg(eps_previous_estimate_value), ts_backfill(research_development_expense, 120), 60)), sector)); alpha2 = -(group_neutralize(ts_corr(ts_backfill(annualized_pd_4_year_jc7, 63), ts_backfill(probability_dist_a_plus, 63), 10), sector)); alpha3 = group_neutralize(group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector), sector); alpha4 = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)), industry); alpha1_scaled = scale(group_neutralize(alpha1, industry)); alpha2_scaled = scale(group_neutralize(alpha2, industry)); alpha3_scaled = scale(group_neutralize(alpha3, industry)); alpha4_scaled = scale(group_neutralize(alpha4, industry)); alphamix_raw = (alpha1_scaled + alpha2_scaled + alpha3_scaled + alpha4_scaled) / 4; alphamix = scale(alphamix_raw); alphamix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `alpha4, annualized_pd_4_year_jc7, implied_volatility_put_270, eps_previous_estimate_value, research_development_expense, alpha2, pcr_oi_270, implied_volatility_call_270, alpha1, fnd6_txws, probability_dist_a_plus, alpha3`. |
| Operator overlap | Common operators are `group_zscore, ts_corr, group_rank, ts_mean, rank, vec_avg, trade_when, ts_decay_linear, scale, ts_backfill, group_neutralize`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (6), quality/growth/value (6), earnings/EPS/guidance revisions (6), options/implied volatility (6), tax/accounting fundamentals (6). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 6 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 6 |
| pending: `SELF_CORRELATION` | 6 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 70 | EPS Revision Shock Variant 15 | `zqWJqnNG` | `hard_pass_signal_seed` | `2.34` | `2.9` | `12.92%` | `n/a` | `SELF_CORRELATION` | `70e50e39e2c7dffa` |
| 71 | EPS Revision Shock Variant 16 | `npWO1w18` | `hard_pass_signal_seed` | `2.34` | `2.9` | `12.92%` | `n/a` | `SELF_CORRELATION` | `c528ba75c0198e56` |
| 72 | EPS Revision Shock Variant 17 | `kqKLqE3z` | `hard_pass_signal_seed` | `2.34` | `2.9` | `12.92%` | `n/a` | `SELF_CORRELATION` | `76bcb175a47c4ec5` |
| 73 | EPS Revision Shock Variant 18 | `akOWkn2v` | `hard_pass_signal_seed` | `2.34` | `2.9` | `12.92%` | `n/a` | `SELF_CORRELATION` | `fda7302cfa4e73be` |
| 74 | EPS Revision Shock Variant 19 | `QPQlwoWg` | `hard_pass_signal_seed` | `2.34` | `2.9` | `12.92%` | `n/a` | `SELF_CORRELATION` | `1bf7b23a4698bd02` |
| 75 | EPS Revision Shock Variant 20 | `2rKZ3lJZ` | `hard_pass_signal_seed` | `2.34` | `2.9` | `12.92%` | `n/a` | `SELF_CORRELATION` | `1ae3aa54977f6b95` |

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
