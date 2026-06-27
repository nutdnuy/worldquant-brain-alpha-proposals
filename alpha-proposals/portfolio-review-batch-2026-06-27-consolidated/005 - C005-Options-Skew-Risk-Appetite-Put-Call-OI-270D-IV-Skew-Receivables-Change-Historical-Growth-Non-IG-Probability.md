---
title: "C005 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Receivables Change + Historical Growth + Non-IG Probability"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-005
member_count: 16
cluster_basis: "high-similarity field/operator/family cluster"
representative_alpha: "Options Skew Risk Appetite Variant 24"
created: 2026-06-27
updated: 2026-06-27
---

# C005 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Receivables Change + Historical Growth + Non-IG Probability

> [!abstract] Consolidated Thesis
> This note combines **16** highly similar alpha proposals into one research idea. The consolidation basis is **high-similarity field/operator/family cluster**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Options Skew Risk Appetite Variant 24 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `16` |
| Cluster basis | `high-similarity field/operator/family cluster` |
| Dominant families | risk/credit/volatility (16), price-volume/liquidity/turnover (16), analyst/model scores (16), quality/growth/value (16), options/implied volatility (16) |
| Common fields | `unexpected_change_accounts_receivable, implied_volatility_put_270, p1_raw, implied_volatility_call_270, pcr_oi_270, mdl77_historicalgrowthfactor_y3speq4rqsr, probability_non_investment_grade_rating, p2_raw, p3_raw, returns, volume, reverse` |
| Common operators | `ts_decay_linear, multiply, divide, group_zscore, ts_corr, zscore, rank, ts_mean, trade_when, ts_backfill, group_neutralize, add` |
| Best recorded Sharpe | `2.59` |
| Best recorded Fitness | `2.59` |
| Median turnover | `12.79%` |
| Representative | Options Skew Risk Appetite Variant 24 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> p1_raw = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1, group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector), -1 * ts_backfill(probability_non_investment_grade_rating, 120)), industry); p2_raw = -(ts_corr(rank(ts_backfill(mdl77_historicalgrowthfactor_y3speq4rqsr, 63)), rank(ts_backfill(unexpected_change_accounts_receivable, 63)), 126)); p3_raw = zscore(ts_decay_linear(group_neutralize(rank(add(multiply(0.70,reverse(ts_zscore(returns,120))),multiply(0.30,reverse(ts_corr(returns,divide(volume,adv20),60))))),subindustry),10)); p1 = group_zscore(zscore(p1_raw), sector); p2 = group_zscore(rank(p2_raw), industry); p3 = group_zscore(rank(p3_raw), industry); alpha_mix = group_zscore(0.4300 * p1 + 0.4300 * p2 + 0.1400 * p3, industry); alpha_mix
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `high-similarity field/operator/family cluster` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `unexpected_change_accounts_receivable, implied_volatility_put_270, p1_raw, implied_volatility_call_270, pcr_oi_270, mdl77_historicalgrowthfactor_y3speq4rqsr, probability_non_investment_grade_rating, p2_raw, p3_raw, returns, volume, reverse`. |
| Operator overlap | Common operators are `ts_decay_linear, multiply, divide, group_zscore, ts_corr, zscore, rank, ts_mean, trade_when, ts_backfill, group_neutralize, add`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (16), price-volume/liquidity/turnover (16), analyst/model scores (16), quality/growth/value (16), options/implied volatility (16). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `recorded-hard-pass-rebuild-candidate` | 16 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `n/a` | 16 |
| pending: `SELF_CORRELATION` | 16 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 65 | Options Skew Risk Appetite Variant 24 | `xAnZkq9g` | `hard_pass_signal_seed` | `2.59` | `2.59` | `10.84%` | `n/a` | `SELF_CORRELATION` | `4148c146f86c65c3` |
| 82 | Options Skew Risk Appetite Variant 28 | `A13A3XJl` | `hard_pass_signal_seed` | `2.54` | `2.56` | `11.11%` | `n/a` | `SELF_CORRELATION` | `633a8fca192815ad` |
| 97 | Options Skew Risk Appetite Variant 37 | `Jjd9pgal` | `hard_pass_signal_seed` | `2.49` | `2.53` | `11.54%` | `n/a` | `SELF_CORRELATION` | `f14c349977b5418a` |
| 185 | Options Skew Risk Appetite Variant 67 | `omYdw0GJ` | `hard_pass_signal_seed` | `2.32` | `2.26` | `13.15%` | `n/a` | `SELF_CORRELATION` | `18010ea8a84e4f61` |
| 194 | Options Skew Risk Appetite Variant 72 | `0m8Jpm18` | `hard_pass_signal_seed` | `2.37` | `2.16` | `13.45%` | `n/a` | `SELF_CORRELATION` | `df422dda1204f5f9` |
| 201 | Options Skew Risk Appetite Variant 77 | `pw6wgnZ6` | `hard_pass_signal_seed` | `2.26` | `2.22` | `12.79%` | `n/a` | `SELF_CORRELATION` | `46ed8665b0b48676` |
| 216 | Options Skew Risk Appetite Variant 89 | `9qRnrdo9` | `hard_pass_signal_seed` | `2.33` | `2.07` | `13.71%` | `n/a` | `SELF_CORRELATION` | `11196e48d5e19382` |
| 255 | Options Skew Risk Appetite Variant 103 | `akOp1dOv` | `hard_pass_signal_seed` | `2.3` | `2.03` | `12.80%` | `n/a` | `SELF_CORRELATION` | `ff59039dfd82b3be` |
| 288 | Options Skew Risk Appetite Variant 112 | `58vXwPq5` | `hard_pass_signal_seed` | `2.26` | `1.96` | `12.35%` | `n/a` | `SELF_CORRELATION` | `aa4f8e20d71b08ee` |
| 333 | Options Skew Risk Appetite Variant 130 | `E5w53K3L` | `hard_pass_signal_seed` | `2.43` | `1.61` | `25.79%` | `n/a` | `SELF_CORRELATION` | `844c9f906ed049b1` |
| 373 | Options Skew Risk Appetite Variant 140 | `P01VpXVE` | `hard_pass_signal_seed` | `2.17` | `1.85` | `12.69%` | `n/a` | `SELF_CORRELATION` | `83c8a781ae64090d` |
| 390 | Options Skew Risk Appetite Variant 146 | `qMXRl1qj` | `hard_pass_signal_seed` | `2.2` | `1.75` | `10.79%` | `n/a` | `SELF_CORRELATION` | `07a4e28ac77f6723` |
| 398 | Options Skew Risk Appetite Variant 148 | `88LweVeo` | `hard_pass_signal_seed` | `2.15` | `1.81` | `13.27%` | `n/a` | `SELF_CORRELATION` | `979bad58571a3ef0` |
| 458 | Options Skew Risk Appetite Variant 155 | `LLRQp5v6` | `hard_pass_signal_seed` | `2.1` | `1.75` | `13.05%` | `n/a` | `SELF_CORRELATION` | `31d4511142e0ed8f` |
| 492 | Options Skew Risk Appetite Variant 161 | `3qAN7oo6` | `hard_pass_signal_seed` | `2.09` | `1.64` | `11.44%` | `n/a` | `SELF_CORRELATION` | `d3b3ef071bbb8562` |
| 495 | Options Skew Risk Appetite Variant 162 | `vRmQLRZG` | `hard_pass_signal_seed` | `2.09` | `1.63` | `11.26%` | `n/a` | `SELF_CORRELATION` | `006184bb6e11dc4a` |

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
