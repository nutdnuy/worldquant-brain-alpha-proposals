---
title: Free Cash Flow Guidance Timing Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: Free Cash Flow Guidance Timing
alpha_ids:
  - 6XRoavlY
status: hard-pass-low-correlation-candidate
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium
tags:
  - worldquant
  - alpha-proposal
  - free-cash-flow
  - guidance
---

# Free Cash Flow Guidance Timing Alpha Proposal

> [!abstract] Research Thesis
> **Free Cash Flow Guidance Timing** ranks firms by the recent timing of maximum free-cash-flow-per-share guidance. The thesis is that the timing pattern of guidance revisions can proxy management confidence, cash-generation expectations, and investor underreaction to forward cash-flow information.

## Snapshot

| Dimension | Description |
| --- | --- |
| Alpha ID | `6XRoavlY` |
| Core field | `min_free_cash_flow_per_share_guidance` |
| Mechanism | Sector-ranked recency of maximum guidance value |
| Source sheet | `04_alpha_pass_combined` |
| Status | Hard pass; low workbook correlation |
| Main risk | Guidance-field timing and sparse coverage |

## Formula

```text
group_rank(ts_arg_max(min_free_cash_flow_per_share_guidance, 10), sector)
```

## Economic Rationale

Free cash flow guidance is forward-looking. The recency of the strongest guidance value can reveal whether cash-flow expectations have recently improved or whether the best information is stale. Sector ranking controls for industry-level differences in guidance frequency and cash-flow cyclicality.

The alpha is simple and low-dimensional. Its main research value is that it uses a management-guidance channel rather than price, volume, or broad accounting ratios.

## Empirical Record

| Metric | Recorded value |
| --- | ---: |
| Alpha ID | `6XRoavlY` |
| Sharpe | `1.35` |
| Fitness | `2.13` |
| Turnover | `10.66%` |
| Returns | `31.06%` |
| Drawdown | `27.44%` |
| Margin | `0.005829` |
| Max abs corr in workbook | `0.3859` |

## Validation Plan

- Confirm that guidance timestamps are point-in-time.
- Review coverage by sector and market cap.
- Test `ts_arg_max` windows of 5, 10, and 20 days.
- Check whether high returns are concentrated in names with sparse guidance updates.

## Failure Criteria

Demote if guidance data is stale, sparse, or revised with lookahead, or if drawdown is too high for the recorded return profile.

## Decision

Keep as a low-correlation guidance candidate. It needs data-timing validation before any submission decision.

## Sources

- Source workbook: `/Users/nuthdanai/Desktop/alpha-mixing-research/alpha_mixing_research_combined.xlsm`
- Source sheet: `04_alpha_pass_combined`
- Source file recorded in sheet: `submittable_group1_alphas.xlsm`
