---
title: Tax Working Spread Momentum Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: Tax Working Spread Momentum
alpha_ids:
  - O0oWakzR
  - 3qz0Nnz0
status: hard-pass-family-correlation-review-required
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium
tags:
  - worldquant
  - alpha-proposal
  - tax-working-spread
  - accounting
---

# Tax Working Spread Momentum Alpha Proposal

> [!abstract] Research Thesis
> **Tax Working Spread Momentum** ranks firms by the recent decayed level of `fnd6_txws`. The thesis is that tax-working-spread style accounting information can proxy operating quality, tax efficiency, or working-capital pressure that is slow-moving and not fully reflected in prices.

## Snapshot

| Dimension | Description |
| --- | --- |
| Alpha IDs | `O0oWakzR`, `3qz0Nnz0` |
| Core field | `fnd6_txws` |
| Mechanism | Decayed accounting spread ranked within sector |
| Source sheet | `04_alpha_pass_combined` |
| Status | Hard-pass family; correlation review required |
| Main risk | Field interpretation and high sibling correlation |

## Formulas

```text
group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector)
```

```text
group_neutralize(
  group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector),
  sector
)
```

## Economic Rationale

Accounting spreads tied to tax and working-capital behavior can reveal persistent operational differences. A decayed backfilled signal fits the reporting frequency of fundamental data: it does not assume that the market reacts instantly to each update, and it keeps the signal slow enough for a fundamental horizon.

The two variants are nearly the same economic idea. One uses sector ranking directly, while the other additionally neutralizes the ranked value by sector.

## Empirical Record

| Alpha | Sharpe | Fitness | Turnover | Returns | Drawdown | Max abs corr |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| `O0oWakzR` | `2.11` | `2.84` | `2.95%` | `22.71%` | `9.72%` | `0.9999` |
| `3qz0Nnz0` | `2.08` | `2.78` | `2.95%` | `22.40%` | `9.74%` | `0.9999` |

## Validation Plan

- Identify the exact economic definition of `fnd6_txws`.
- Confirm point-in-time handling and update frequency.
- Test industry versus sector ranking.
- Review correlation to other accounting-quality and tax-related signals.

## Failure Criteria

Demote if the field definition is unclear, if the signal is a sector artifact, or if sibling self-correlation makes only one version usable.

## Decision

Keep one representative of this family. It is economically plausible but needs field-definition review before being treated as a high-confidence accounting proposal.

## Sources

- Source workbook: `/Users/nuthdanai/Desktop/alpha-mixing-research/alpha_mixing_research_combined.xlsm`
- Source sheet: `04_alpha_pass_combined`
- Source file recorded in sheet: `submittable_group1_alphas.xlsm`
