---
title: Core Satellite Positive Region Blend
type: alpha-mix-proposal
project: worldquant-brain
status: candidate-review
created: 2026-06-27
updated: 2026-06-27
representative_alpha: O0p0WdPd
related_alpha_ids:
  - O0p0WdPd
  - JjpMkM8m
---

# Core Satellite Positive Region Blend

> [!abstract] Proposal
> Build a workbook-only core-satellite blend that preserves a proven multi-leg core while adding a smaller diversifier sleeve. The construction is explicitly designed around historical positive-IQC regions, residualized satellites, and fixed weights rather than a free-form optimizer.

## Research Snapshot

| Item | Value |
| --- | --- |
| Representative alpha | `O0p0WdPd` |
| Secondary variant | `JjpMkM8m` |
| Construction | Four-sleeve core-satellite weighted blend |
| Source | Workbook `04_alpha_pass_combined` derived mix run |
| Current status | Hard checks passed; high-correlation review required |

## Evidence

| Alpha ID | Sharpe | Fitness | Turnover | Returns | Drawdown | Self-Correlation Note | Status |
| --- | ---: | ---: | ---: | ---: | ---: | --- | --- |
| `O0p0WdPd` | 2.30 | 2.15 | 9.74% | 10.89% | 4.07% | Later poll showed max self-corr around 0.7049 | Borderline review |
| `JjpMkM8m` | 1.51 | 1.28 | 7.19% | 8.93% | 6.21% | Later poll showed max self-corr around 0.9981 vs submitted cluster | Deferred despite hard checks |

## Construction

The representative combines four sleeves: options/credit stress, receivable-growth quality, price-volume reversal, and a residualized event/analyst satellite. The satellite is partially orthogonalized against the first two core sleeves.

```text
p1_raw = group_neutralize(trade_when(ts_mean(pcr_oi_270, 3) < 1,
    group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector),
    -1 * ts_backfill(probability_non_investment_grade_rating, 120)), industry);
p1 = group_zscore(rank(p1_raw), industry);

p2_raw = -(ts_corr(rank(ts_backfill(mdl77_historicalgrowthfactor_y3speq4rqsr, 63)),
    rank(ts_backfill(unexpected_change_accounts_receivable, 63)), 126));
p2 = group_zscore(rank(p2_raw), industry);

p3_raw = zscore(ts_decay_linear(group_neutralize(rank(add(
    multiply(0.70, reverse(ts_zscore(returns, 120))),
    multiply(0.30, reverse(ts_corr(returns, divide(volume, adv20), 60)))
)), subindustry), 10));
p3 = group_zscore(rank(p3_raw), industry);

p4_raw = -(ts_corr(rank(ts_backfill(vec_avg(fnd6_newqeventv110_lqpl1q), 120)),
    rank(ts_backfill(vec_avg(anl4_dez1basicafv4_est), 21)), 252));
p4b = group_zscore(rank(p4_raw), industry);
p4 = group_zscore(p4b - 0.08 * p1 - 0.06 * p2, industry);

alpha_mix = group_rank(0.2550 * p1 + 0.3230 * p2 + 0.2720 * p3 + 0.1500 * p4, sector);
alpha_mix
```

## Why It Should Work

The core-satellite structure is financially coherent because it does not give every sleeve equal authority. The core sleeves capture risk appetite, receivable quality, and price-volume reversal. The satellite adds an event/analyst component, but it is deliberately residualized against the dominant core sleeves so that it contributes marginal information rather than simply increasing common exposure.

The representative also shows a useful tradeoff: hard checks passed and metrics are strong, but self-correlation is close to the platform threshold. This makes the family useful as a research frontier even if it is not immediately promotion-ready.

## Main Risks

- The mix is close to a submitted or crowded region; self-correlation is the binding constraint.
- Fixed weights can be overfit to the discovered positive region.
- The high operator count and four-sleeve structure may be harder to explain than simpler alpha mixes.

## Validation Plan

- Treat `O0p0WdPd` as the representative and `JjpMkM8m` as negative evidence for high-correlation variants.
- Test smaller satellite weights and stronger residualization before any promotion.
- Compare against the three-sleeve core without `p4`.
- Kill variants whose self-correlation remains above threshold after preserving only the marginal satellite idea.

## Sources

- Source workbook: `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/alpha_mixing_research_combined.xlsm`
- Run folder: `/Users/nuthdanai/Desktop/alpha-mixing-research/temp_submit_runs/mixed_alpha_candidates/fresh_from_workbook_20260616_round10_small_satellite_oneworker/`
- Follow-up run folder: `/Users/nuthdanai/Desktop/alpha-mixing-research/temp_submit_runs/mixed_alpha_candidates/fresh_from_workbook_20260617_round12_wpew_positive_region_oneworker/`
