---
title: Price Volume Reversal Pressure Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: Price Volume Reversal Pressure
alpha_ids:
  - MPxl3Rp6
  - rKL2M2Xj
  - om98KvNl
status: hard-pass-high-turnover-correlation-review-required
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium
tags:
  - worldquant
  - alpha-proposal
  - price-volume
  - reversal
---

# Price Volume Reversal Pressure Alpha Proposal

> [!abstract] Research Thesis
> **Price Volume Reversal Pressure** combines return behavior with volume or VWAP confirmation. The thesis is that strong price moves accompanied by volume-state information can create short-horizon pressure that later reverses or mean-reverts.

## Snapshot

| Dimension | Description |
| --- | --- |
| Alpha IDs | `MPxl3Rp6`, `rKL2M2Xj`, `om98KvNl` |
| Core fields | `returns`, `volume / adv20`, `vwap`, `close` |
| Mechanism | Price-volume pressure and reversal |
| Source sheet | `04_alpha_pass_combined` |
| Status | Hard pass; high turnover and correlation review required |
| Main risk | Transaction costs and crowded price-volume reversal exposure |

## Representative Formulas

```text
-(ts_mean(returns * min(ts_rank(vwap, 10), ts_rank(close, 10)), 20))
```

```text
zscore(ts_decay_linear(
  group_neutralize(
    rank(add(
      multiply(0.6, reverse(ts_zscore(returns, 120))),
      multiply(0.4, reverse(ts_corr(returns, divide(volume, adv20), 60)))
    )),
    subindustry
  ),
  10
))
```

## Economic Rationale

Price-volume signals are plausible because volume helps distinguish information flow from mechanical price movement. Reversal pressure is stronger when returns are extreme and volume behavior confirms that the move is crowded or exhausted. VWAP and close ranks provide an additional execution-pressure lens.

The family is useful as research memory but less clean than accounting or guidance signals because turnover is high and many variants are tightly correlated.

## Empirical Record

| Alpha | Variant | Sharpe | Fitness | Turnover | Returns | Drawdown | Max abs corr |
| --- | --- | ---: | ---: | ---: | ---: | ---: | ---: |
| `MPxl3Rp6` | VWAP/close pressure reversal | `1.44` | `1.97` | `13.38%` | `24.97%` | `31.79%` | `0.6466` |
| `rKL2M2Xj` | Return-volume reversal blend | `2.12` | `1.31` | `43.63%` | `16.73%` | `6.85%` | `1.0000` |
| `om98KvNl` | Return-volume reversal blend | `2.12` | `1.35` | `39.74%` | `16.07%` | `7.32%` | `0.9998` |

## Validation Plan

- Apply explicit transaction-cost and slippage assumptions.
- Check whether high-turnover variants survive under stricter turnover constraints.
- Test if the VWAP/close variant is less correlated and more useful than the return-volume cluster.
- Review platform reversion warnings before promotion.

## Failure Criteria

Demote if turnover cost overwhelms returns, if the platform flags the expression as a reversion component, or if the signal is redundant with existing price-volume alphas.

## Decision

Keep as a candidate note, but do not prioritize ahead of lower-turnover fundamental or event-data proposals.

## Sources

- Source workbook: `/Users/nuthdanai/Desktop/alpha-mixing-research/alpha_mixing_research_combined.xlsm`
- Source sheet: `04_alpha_pass_combined`
- Source files recorded in sheet: `submittable_group1_alphas.xlsm`, `04_alpha_pass_combined.xlsm`
