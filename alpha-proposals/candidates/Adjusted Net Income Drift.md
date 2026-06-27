---
title: Adjusted Net Income Drift Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: Adjusted Net Income Drift
alpha_ids:
  - rKra0V2j
status: hard-pass-correlation-review-required
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium
tags:
  - worldquant
  - alpha-proposal
  - net-income
  - profitability
---

# Adjusted Net Income Drift Alpha Proposal

> [!abstract] Research Thesis
> **Adjusted Net Income Drift** uses a short decayed adjusted-net-income factor as a profitability information signal. The thesis is that recent adjusted net income contains slow-moving accounting information that can persist after a short smoothing window.

## Snapshot

| Dimension | Description |
| --- | --- |
| Alpha ID | `rKra0V2j` |
| Core field | `anl4_adjusted_netincome_ft` |
| Mechanism | Short decayed adjusted net income |
| Source sheet | `04_alpha_pass_combined` |
| Status | Hard pass; correlation review required |
| Main risk | High PnL correlation to other workbook alphas |

## Formula

```text
zscore(ts_decay_linear(anl4_adjusted_netincome_ft, 3))
```

## Economic Rationale

Adjusted net income is a profitability measure. A short decay can reduce one-day noise while preserving timely accounting information. The z-score turns the field into a cross-sectional profitability signal without adding unrelated sleeves.

This is a simple proposal, but the workbook reports high maximum absolute correlation. It should therefore be treated as a clean mechanism with a correlation caveat, not as automatically independent.

## Empirical Record

| Metric | Recorded value |
| --- | ---: |
| Alpha ID | `rKra0V2j` |
| Sharpe | `1.93` |
| Fitness | `2.47` |
| Turnover | `3.01%` |
| Returns | `20.50%` |
| Drawdown | `11.49%` |
| Margin | `0.013602` |
| Max abs corr in workbook | `0.9945` |

## Validation Plan

- Confirm point-in-time handling and update frequency of `anl4_adjusted_netincome_ft`.
- Test whether the signal remains after industry neutralization.
- Compare against profitability, earnings-surprise, and cost-efficiency proposals.
- Review the high workbook correlation cluster before promotion.

## Failure Criteria

Demote if it duplicates an existing profitability alpha, if correlation cannot be reduced, or if point-in-time review fails.

## Decision

Keep as a clean profitability candidate, but require correlation review before treating it as additive.

## Sources

- Source workbook: `/Users/nuthdanai/Desktop/alpha-mixing-research/alpha_mixing_research_combined.xlsm`
- Source sheet: `04_alpha_pass_combined`
- Source file recorded in sheet: `01_alphas_passed_all.xlsx`
