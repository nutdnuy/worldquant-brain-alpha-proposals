---
title: EPS Event Revision Coupling Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: EPS Event Revision Coupling
alpha_ids:
  - GrnGL2v3
status: hard-pass-low-correlation-candidate
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium-high
tags:
  - worldquant
  - alpha-proposal
  - eps
  - event-revision
---

# EPS Event Revision Coupling Alpha Proposal

> [!abstract] Research Thesis
> **EPS Event Revision Coupling** measures the long-window correlation between acquisition/event EPS information and revised EPS-related fundamentals. The thesis is that firms whose event-driven EPS information aligns with later EPS revisions may carry slow-moving fundamental information that is not immediately reflected in prices.

## Snapshot

| Dimension | Description |
| --- | --- |
| Alpha ID | `GrnGL2v3` |
| Core fields | `fnd6_eventv110_aqepsq`, `fnd6_newqv1300_spceepsp12` |
| Mechanism | 252-day correlation between event EPS and revised EPS proxy |
| Source sheet | `04_alpha_pass_combined` |
| Status | Hard pass; low workbook PnL-correlation candidate |
| Main risk | Field timing and event-data interpretation |

## Formula

```text
ts_corr(
  rank(ts_backfill(vec_avg(fnd6_eventv110_aqepsq), 120)),
  rank(ts_backfill(fnd6_newqv1300_spceepsp12, 120)),
  252
)
```

## Economic Rationale

The signal is not simply an EPS level or revision rank. It asks whether two related accounting/event channels move together over a long window. If event-linked EPS information and revised EPS proxy data become consistently aligned, that alignment may indicate improving forecast reliability or persistent accounting information flow.

The candidate is notable because the workbook reports much lower maximum absolute PnL correlation than many other pass rows. That makes it more interesting as an orthogonal research candidate than the high-metric but crowded options-skew variants.

## Empirical Record

| Metric | Recorded value |
| --- | ---: |
| Alpha ID | `GrnGL2v3` |
| Sharpe | `1.37` |
| Fitness | `2.50` |
| Turnover | `2.27%` |
| Returns | `41.52%` |
| Drawdown | `23.42%` |
| Margin | `0.036507` |
| Max abs corr in workbook | `0.2143` |

## Validation Plan

- Confirm point-in-time availability for both `fnd6` event/revision fields.
- Test shorter windows such as 126 and 189 days.
- Review whether the high returns are concentrated in a small number of event-heavy names.
- Compare against existing earnings-surprise and forecast-error proposals.

## Failure Criteria

Reject if either input field has lookahead risk, sparse coverage drives concentration, or the signal collapses after event-heavy industries are controlled.

## Decision

Keep **EPS Event Revision Coupling** as a high-priority orthogonality candidate despite a lower Sharpe than some crowded families.

## Sources

- Source workbook: `/Users/nuthdanai/Desktop/alpha-mixing-research/alpha_mixing_research_combined.xlsm`
- Source sheet: `04_alpha_pass_combined`
- Source file recorded in sheet: `submittable_group1_alphas.xlsm`
