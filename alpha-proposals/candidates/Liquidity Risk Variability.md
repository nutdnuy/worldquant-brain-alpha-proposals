---
title: Liquidity Risk Variability Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: Liquidity Risk Variability
alpha_ids:
  - RRrZAmln
status: hard-pass-low-correlation-candidate
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium-high
tags:
  - worldquant
  - alpha-proposal
  - liquidity-risk
  - risk-model
---

# Liquidity Risk Variability Alpha Proposal

> [!abstract] Research Thesis
> **Liquidity Risk Variability** penalizes high variability in a liquidity-risk model factor. The thesis is that unstable liquidity-risk exposure can signal fragile marketability, uncertain financing conditions, or changing crowding pressure that investors price slowly.

## Snapshot

| Dimension | Description |
| --- | --- |
| Alpha ID | `RRrZAmln` |
| Core field | `mdl77_liquidityriskfactor_astcomp` |
| Mechanism | Negative industry-neutralized 20-day volatility of liquidity-risk exposure |
| Source sheet | `04_alpha_pass_combined` |
| Status | Hard pass; low workbook correlation |
| Main risk | Risk-model field interpretability |

## Formula

```text
-(group_neutralize(
  ts_std_dev(ts_backfill(mdl77_liquidityriskfactor_astcomp, 63), 20),
  industry
))
```

## Economic Rationale

Liquidity risk is not only a level variable. The stability of liquidity-risk exposure can matter because investors may demand compensation for names whose marketability changes abruptly. Penalizing high short-window variability favors firms with more stable liquidity-risk profiles and avoids direct dependence on raw volume alone.

This proposal is distinct from the abnormal-turnover families because it uses a model liquidity-risk factor rather than `volume / sharesout`.

## Empirical Record

| Metric | Recorded value |
| --- | ---: |
| Alpha ID | `RRrZAmln` |
| Sharpe | `1.94` |
| Fitness | `2.37` |
| Turnover | `12.39%` |
| Returns | `18.72%` |
| Drawdown | `10.58%` |
| Margin | `0.003022` |
| Max abs corr in workbook | `0.3905` |

## Validation Plan

- Confirm the field definition and whether it is point-in-time.
- Compare 10-, 20-, and 40-day variability windows.
- Check exposure to low-volatility, size, and liquidity factors.
- Review capacity and slippage assumptions.

## Failure Criteria

Reject if the field is not interpretable, if the signal is just a low-volatility proxy, or if liquidity costs erase the edge.

## Decision

Keep **Liquidity Risk Variability** as a clean low-correlation risk-model proposal.

## Sources

- Source workbook: `/Users/nuthdanai/Desktop/alpha-mixing-research/alpha_mixing_research_combined.xlsm`
- Source sheet: `04_alpha_pass_combined`
- Source file recorded in sheet: `submittable_group1_alphas.xlsm`
