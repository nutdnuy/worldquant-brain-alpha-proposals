---
title: "C043 - Capital Productivity Momentum - Capital Cost Base + Operating Profit"
type: alpha-cluster-proposal
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
cluster_id: cluster-043
member_count: 3
cluster_basis: "numeric-parameter variant"
representative_alpha: "Capital Productivity Momentum Variant 5"
created: 2026-06-27
updated: 2026-06-27
---

# C043 - Capital Productivity Momentum - Capital Cost Base + Operating Profit

> [!abstract] Consolidated Thesis
> This note combines **3** highly similar alpha proposals into one research idea. The consolidation basis is **numeric-parameter variant**. The purpose is to avoid treating small parameter, field, or wrapper variations as independent alphas before originality, self-correlation, and robustness checks clear.
>
> **Representative candidate.** Capital Productivity Momentum Variant 5 is the current representative because it has the strongest recorded status/priority/metric profile inside this cluster.
>
> **Recommendation.** Treat this cluster as one alpha family. Promote at most one representative unless a sibling variant proves genuinely lower correlation or materially better robustness.

## Cluster Snapshot

| Dimension | Value |
| --- | --- |
| Member count | `3` |
| Cluster basis | `numeric-parameter variant` |
| Dominant families | tax/accounting fundamentals (3) |
| Common fields | `cap, cogs, g, c, op, cost, fnd6_fopo` |
| Common operators | `winsorize, zscore, rank, abs, trade_when, ts_mean, group_neutralize` |
| Best recorded Sharpe | `2` |
| Best recorded Fitness | `2.41` |
| Median turnover | `3.07%` |
| Representative | Capital Productivity Momentum Variant 5 |
| Representative bucket | `hard_pass_signal_seed` |
| Representative failed checks | `n/a` |
| Representative pending checks | `SELF_CORRELATION` |

## Representative Formula

> [!quote] Representative Fast Expression
> ```text
> cost = zscore(winsorize(cogs/cap, std=4)); op = zscore(fnd6_fopo/cap); c = ts_mean(cost - 0.28 * op, 3); g = trade_when(rank(abs(c)) > 0.88, c, 0); group_neutralize(rank(c) * g, industry)
> ```

## Why These Were Combined

| Evidence | Reading |
| --- | --- |
| Expression similarity | `numeric-parameter variant` indicates that these rows are close enough to review as one research family. |
| Field overlap | Common fields are `cap, cogs, g, c, op, cost, fnd6_fopo`. |
| Operator overlap | Common operators are `winsorize, zscore, rank, abs, trade_when, ts_mean, group_neutralize`. |
| Family overlap | Dominant workbook families are tax/accounting fundamentals (3). |
| Originality risk | Multiple rows may be variants of the same economic idea; do not count them as independent pool capacity until current self-correlation and structural similarity checks clear. |

## Status Mix

| Status | Count |
| --- | ---: |
| `failed-checks-strong-signal-repair-candidate` | 2 |
| `recorded-hard-pass-rebuild-candidate` | 1 |

## Check Mix

| Check type | Count |
| --- | ---: |
| failed: `LOW_SHARPE` | 2 |
| failed: `n/a` | 1 |
| pending: `SELF_CORRELATION` | 3 |

## Member Variants

| # | Member label | Source ID | Bucket | Sharpe | Fitness | Turnover | Failed | Pending | Expression hash |
| ---: | --- | --- | --- | ---: | ---: | ---: | --- | --- | --- |
| 258 | Capital Productivity Momentum Variant 5 | `omKAmg6k` | `hard_pass_signal_seed` | `2` | `2.41` | `3.07%` | `n/a` | `SELF_CORRELATION` | `9bc34c9641c958fd` |
| 294 | Capital Productivity Momentum Variant 7 | `58w7XQ3M` | `strong_signal_repair_seed` | `1.96` | `2.35` | `2.96%` | `LOW_SHARPE` | `SELF_CORRELATION` | `5e4aac55f265f94e` |
| 367 | Capital Productivity Momentum Variant 9 | `1Y71Y5GW` | `strong_signal_repair_seed` | `1.89` | `2.25` | `3.15%` | `LOW_SHARPE` | `SELF_CORRELATION` | `3723746d939d09c1` |

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
