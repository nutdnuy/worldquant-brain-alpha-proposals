---
title: "C004 - EPS Revision Shock - GARP Analyst Value + FCF Estimate + Tax Working Spread"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-004
member_count: 20
cluster_basis: "high-similarity field/operator/family cluster"
representative_alpha: "EPS Revision Shock"
created: 2026-06-27
updated: 2026-06-27
---

# C004 - EPS Revision Shock - GARP Analyst Value + FCF Estimate + Tax Working Spread

> [!abstract] Consolidated Thesis
> This note combines **20** highly similar alpha proposals into one research idea. The consolidation basis is **high-similarity field/operator/family cluster**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** EPS Revision Shock is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `20` |
| Cluster basis | `high-similarity field/operator/family cluster` |
| Dominant families | risk/credit/volatility (20), price-volume/liquidity/turnover (20), analyst/model scores (20), quality/growth/value (20), earnings/EPS/guidance revisions (20), tax/accounting fundamentals (20), options/implied volatility (2) |
| Common fields | `returns, min_free_cash_flow_per_share_guidance, tx_alpha, vector_neut, fnd6_txws, tx_dir, mdl177_garpanalystmodel_qgp_vfpriceratio, tx_conf, garp_alpha, volatility, garp_signal, tx_q` |
| Common operators | `if_else, group_rank, rank, ts_arg_max, abs, vec_avg, ts_mean, ts_decay_linear, ts_std_dev, scale, ts_backfill, group_neutralize` |
| Best recorded Sharpe | `2.76` |
| Best recorded Fitness | `3.53` |
| Median turnover | `4.96%` |
| Representative | EPS Revision Shock |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> tx_dir = group_neutralize(group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector), sector); tx_conf = group_rank(ts_arg_max(min_free_cash_flow_per_share_guidance, 10), sector); tx_alpha = scale(tx_dir * if_else(rank(abs(tx_conf)) > 0.85, 1.25, 1.00)); garp_signal = -mdl177_garpanalystmodel_qgp_vfpriceratio * ts_std_dev(mdl177_garpanalystmodel_qgp_vfpriceratio, 30); volatility = rank(ts_std_dev(returns, 252)); garp_alpha = scale(rank(vector_neut(garp_signal, volatility)) - 0.5); tx_q = rank(ts_mean(tx_alpha * returns, 40) / ts_std_dev(tx_alpha * returns, 40)); garp_q = rank(ts_mean(garp_alpha * returns, 40) / ts_std_dev(garp_alpha * returns, 40)); wg = 0.15 + 0.35 * ts_mean(garp_q / (tx_q + garp_q + 0.0001), 20); blend = (1 - wg) * tx_alpha + wg * garp_alpha; alpha = scale(vector_neut(blend, tx_conf)); alpha
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `high-similarity field/operator/family cluster` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `returns, min_free_cash_flow_per_share_guidance, tx_alpha, vector_neut, fnd6_txws, tx_dir, mdl177_garpanalystmodel_qgp_vfpriceratio, tx_conf, garp_alpha, volatility, garp_signal, tx_q`. |
| Operator overlap | Common operators are `if_else, group_rank, rank, ts_arg_max, abs, vec_avg, ts_mean, ts_decay_linear, ts_std_dev, scale, ts_backfill, group_neutralize`. |
| Family overlap | Dominant workbook families are risk/credit/volatility (20), price-volume/liquidity/turnover (20), analyst/model scores (20), quality/growth/value (20), earnings/EPS/guidance revisions (20), tax/accounting fundamentals (20), options/implied volatility (2). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `failed-checks-strong-signal-repair-candidate` | 12 |
| `recorded-hard-pass-rebuild-candidate` | 8 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `LOW_SUB_UNIVERSE_SHARPE` | 12 |
| failed: `n/a` | 8 |
| pending: `SELF_CORRELATION` | 16 |
| pending: `n/a` | 4 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 9 | EPS Revision Shock | `E5waraEG` | `hard_pass_signal_seed` | `2.76` | `3.53` | `4.45%` | `n/a` | `SELF_CORRELATION` | `4a751a65d77d26d5` |
| 10 | EPS Revision Shock Variant 2 | `1Y7m1Vzk` | `hard_pass_signal_seed` | `2.76` | `3.53` | `4.45%` | `n/a` | `SELF_CORRELATION` | `04b5fa9d93cb5a93` |
| 17 | EPS Revision Shock Variant 4 | `blLPokGR` | `hard_pass_signal_seed` | `2.65` | `3.21` | `4.84%` | `n/a` | `SELF_CORRELATION` | `6cb9277d212d26b8` |
| 25 | EPS Revision Shock Variant 10 | `vRLzklvQ` | `hard_pass_signal_seed` | `2.57` | `3.09` | `4.83%` | `n/a` | `SELF_CORRELATION` | `907731217758678b` |
| 26 | EPS Revision Shock Variant 11 | `YPpk5GZJ` | `hard_pass_signal_seed` | `2.54` | `3.11` | `5.68%` | `n/a` | `SELF_CORRELATION` | `ea7e08e088286564` |
| 28 | EPS Revision Shock Variant 12 | `gJ1PmmvJ` | `hard_pass_signal_seed` | `2.56` | `3.05` | `4.74%` | `n/a` | `SELF_CORRELATION` | `b9123307835fe142` |
| 29 | EPS Revision Shock Variant 13 | `pw6zVMNg` | `hard_pass_signal_seed` | `2.56` | `3.04` | `4.96%` | `n/a` | `SELF_CORRELATION` | `b9123307835fe142` |
| 54 | EPS Revision Shock Variant 14 | `E5walqZP` | `hard_pass_signal_seed` | `2.45` | `2.85` | `5.96%` | `n/a` | `SELF_CORRELATION` | `3e7ec2281d5c6381` |
| 126 | EPS Revision Shock Variant 22 | `kq3mXEkd` | `strong_signal_repair_seed` | `2.52` | `2.97` | `4.86%` | `LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `93fc85dc1468b738` |
| 128 | EPS Revision Shock Variant 23 | `LLpX6ngn` | `strong_signal_repair_seed` | `2.53` | `2.99` | `4.64%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `93fc85dc1468b738` |
| 132 | EPS Revision Shock Variant 24 | `WjpXA5PZ` | `strong_signal_repair_seed` | `2.5` | `2.93` | `4.88%` | `LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `1dfc726b7e8c00dd` |
| 136 | EPS Revision Shock Variant 25 | `akdPPN16` | `strong_signal_repair_seed` | `2.52` | `2.97` | `4.86%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `93fc85dc1468b738` |
| 158 | EPS Revision Shock Variant 37 | `qMAzdJ8O` | `strong_signal_repair_seed` | `2.53` | `2.88` | `5.14%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `c13ec405941a1cae` |
| 164 | EPS Revision Shock Variant 38 | `blLPNGep` | `strong_signal_repair_seed` | `2.49` | `2.92` | `5.04%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `6592867eb4ed5324` |
| 180 | EPS Revision Shock Variant 44 | `rKoz2jro` | `strong_signal_repair_seed` | `2.41` | `2.78` | `4.95%` | `LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `45bba0401a536589` |
| 205 | EPS Revision Shock Variant 48 | `O0pmo0qd` | `strong_signal_repair_seed` | `2.36` | `2.73` | `6.93%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `f073d268e1ce93e8` |
| 287 | EPS Revision Shock Variant 84 | `e7O28Zld` | `strong_signal_repair_seed` | `2.27` | `2.55` | `5.03%` | `LOW_SUB_UNIVERSE_SHARPE` | `n/a` | `8de0cabf5fb62ea7` |
| 312 | EPS Revision Shock Variant 97 | `omKz3Ka6` | `strong_signal_repair_seed` | `2.27` | `2.55` | `5.26%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `614a277a2edd0155` |
| 326 | EPS Revision Shock Variant 102 | `E5waY8r0` | `strong_signal_repair_seed` | `2.29` | `2.49` | `5.37%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `8de0cabf5fb62ea7` |
| 479 | EPS Revision Shock Variant 176 | `npgz7e6a` | `strong_signal_repair_seed` | `2.13` | `2.31` | `6.44%` | `LOW_SUB_UNIVERSE_SHARPE` | `SELF_CORRELATION` | `7dd745d2051bd262` |

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
