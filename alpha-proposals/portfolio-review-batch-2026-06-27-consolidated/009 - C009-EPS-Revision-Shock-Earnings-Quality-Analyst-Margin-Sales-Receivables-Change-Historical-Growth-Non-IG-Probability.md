---
title: "C009 - EPS Revision Shock - Earnings Quality + Analyst Margin Sales + Receivables Change + Historical Growth + Non-IG Probability"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-009
member_count: 11
cluster_basis: "same-field same-operator variant"
representative_alpha: "EPS Revision Shock Variant 28"
created: 2026-06-27
updated: 2026-06-27
---

# C009 - EPS Revision Shock - Earnings Quality + Analyst Margin Sales + Receivables Change + Historical Growth + Non-IG Probability

> [!abstract] Consolidated Thesis
> This note combines **11** highly similar alpha proposals into one research idea. The consolidation basis is **same-field same-operator variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** EPS Revision Shock Variant 28 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `11` |
| Cluster basis | `same-field same-operator variant` |
| Dominant families | risk/credit/volatility (11), price-volume/liquidity/turnover (11), analyst/model scores (11), quality/growth/value (11), earnings/EPS/guidance revisions (11), options/implied volatility (11), tax/accounting fundamentals (11) |
| Common fields | `returns, unexpected_change_accounts_receivable, implied_volatility_put_270, volume, p1_raw, implied_volatility_call_270, pcr_oi_270, mdl77_historicalgrowthfactor_y3speq4rqsr, reverse, probability_non_investment_grade_rating, p2_raw, p3_raw` |
| Common operators | `ts_decay_linear, multiply, divide, group_zscore, ts_corr, zscore, add, rank, ts_zscore, ts_mean, trade_when, ts_backfill` |
| Best recorded Sharpe | `2.48` |
| Best recorded Fitness | `2.25` |
| Median turnover | `7.36%` |
| Representative | EPS Revision Shock Variant 28 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> p1_raw = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)), industry); p2_raw = -(ts_corr(rank(ts_backfill(mdl77_historicalgrowthfactor_y3speq4rqsr, 63)), rank(ts_backfill(unexpected_change_accounts_receivable, 63)), 126)); p3_raw = zscore(ts_decay_linear(group_neutralize(rank(add(multiply(0.70,reverse(ts_zscore(returns,120))),multiply(0.30,reverse(ts_corr(returns,divide(volume,adv20),60))))),subindustry),10)); p4_raw = -(mdl177_valuemomemtummodel_earningsqualitymodule - mdl77_2growthanalystmodel_qga_opmarginsales); p1 = group_zscore(rank(p1_raw), industry); p2 = group_zscore(rank(p2_raw), industry); p3 = group_zscore(rank(p3_raw), industry); p4 = group_zscore(rank(p4_raw), industry); alpha_mix = rank(group_neutralize(0.2600 * p1 + 0.2400 * p2 + 0.1000 * p3 + 0.4000 * p4, industry)); alpha_mix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `same-field same-operator variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `returns, unexpected_change_accounts_receivable, implied_volatility_put_270, volume, p1_raw, implied_volatility_call_270, pcr_oi_270, mdl77_historicalgrowthfactor_y3speq4rqsr, reverse, probability_non_investment_grade_rating, p2_raw, p3_raw`. |
| Operator overlap | Common operators are `ts_decay_linear, multiply, divide, group_zscore, ts_corr, zscore, add, rank, ts_zscore, ts_mean, trade_when, ts_backfill`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (11), price-volume/liquidity/turnover (11), analyst/model scores (11), quality/growth/value (11), earnings/EPS/guidance revisions (11), options/implied volatility (11), tax/accounting fundamentals (11). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 11 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 11 |
| pending: `SELF_CORRELATION` | 11 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 146 | EPS Revision Shock Variant 28 | `LLpP52xm` | `hard_pass_signal_seed` | `2.48` | `2.25` | `8.74%` | `n/a` | `SELF_CORRELATION` | `f6c3378e748868af` |
| 157 | EPS Revision Shock Variant 36 | `blLYbkmM` | `hard_pass_signal_seed` | `2.45` | `2.22` | `7.91%` | `n/a` | `SELF_CORRELATION` | `46ef2906f04009f0` |
| 167 | EPS Revision Shock Variant 41 | `9qwzErkV` | `hard_pass_signal_seed` | `2.44` | `2.22` | `8.28%` | `n/a` | `SELF_CORRELATION` | `69088fe2e1fa4419` |
| 172 | EPS Revision Shock Variant 42 | `YPpjb3zW` | `hard_pass_signal_seed` | `2.42` | `2.19` | `8.21%` | `n/a` | `SELF_CORRELATION` | `3153d8ef1972a38d` |
| 176 | EPS Revision Shock Variant 43 | `pw6qPb8g` | `hard_pass_signal_seed` | `2.39` | `2.15` | `7.35%` | `n/a` | `SELF_CORRELATION` | `01e306f87d414736` |
| 182 | EPS Revision Shock Variant 45 | `E5wZRjN1` | `hard_pass_signal_seed` | `2.38` | `2.12` | `7.00%` | `n/a` | `SELF_CORRELATION` | `1afa52e333169143` |
| 186 | EPS Revision Shock Variant 46 | `WjpEbVdx` | `hard_pass_signal_seed` | `2.35` | `2.11` | `7.65%` | `n/a` | `SELF_CORRELATION` | `546f55f1655a4972` |
| 192 | EPS Revision Shock Variant 47 | `KPbKm0gx` | `hard_pass_signal_seed` | `2.35` | `2.09` | `7.36%` | `n/a` | `SELF_CORRELATION` | `6b55bd3184c804d2` |
| 223 | EPS Revision Shock Variant 51 | `akdrxbL5` | `hard_pass_signal_seed` | `2.28` | `2` | `6.32%` | `n/a` | `SELF_CORRELATION` | `a60b9071cf8a5d6b` |
| 283 | EPS Revision Shock Variant 82 | `QPa1blLr` | `hard_pass_signal_seed` | `2.22` | `1.93` | `6.60%` | `n/a` | `SELF_CORRELATION` | `fa834421e1f836f0` |
| 387 | EPS Revision Shock Variant 134 | `LLpPZb8M` | `hard_pass_signal_seed` | `2.11` | `1.77` | `5.20%` | `n/a` | `SELF_CORRELATION` | `99bb9c3d44dab1fc` |

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
