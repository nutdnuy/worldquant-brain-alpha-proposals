---
title: Earnings Surprise Delta Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: Earnings Surprise Delta
alpha_ids:
  - rKoeVmra
status: hard-pass-self-correlation-pending
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium-high
tags:
  - worldquant
  - alpha-proposal
  - earnings-surprise
  - quantconnect
---

# Earnings Surprise Delta Alpha Proposal

> [!abstract] Research Thesis
> **Earnings Surprise Delta** is a clean earnings-revision alpha that ranks firms by the recent change in standardized unexpected earnings. The thesis is that changes in earnings surprise capture analyst and fundamental information that may be incorporated into prices gradually rather than immediately.

## Snapshot

| Dimension | Description |
| --- | --- |
| Alpha ID | `rKoeVmra` |
| Core field | `mdl177_earningmomentumfactor_sue` |
| Mechanism | Change in standardized unexpected earnings |
| Peer control | `subindustry` group rank |
| Status | Hard checks passed; `SELF_CORRELATION` pending |
| Main risk | Crowded earnings-momentum exposure |

## Formula

```text
sue = ts_delta(ts_backfill(mdl177_earningmomentumfactor_sue, 120), 40);
scale(group_rank(sue, subindustry))
```

## Economic Rationale

Standardized unexpected earnings measures whether realized earnings are high or low relative to prior expectations. A positive change in SUE can indicate improving business fundamentals, analyst underreaction, or delayed investor response to new information. Ranking the signal within subindustry reduces the risk that the alpha is simply buying structurally high-growth sectors.

This construction is deliberately simple. It does not add price momentum, valuation, or volume sleeves. That makes it a useful orthogonal candidate relative to the turnover-state and composite alpha families.

## Empirical Record

| Metric | Recorded value |
| --- | ---: |
| Sharpe | `1.50` |
| Fitness | `1.04` |
| Turnover | `8.60%` |
| Returns | `5.96%` |
| Drawdown | `5.55%` |
| Margin | `0.001385` |
| Failed checks | none |
| Pending checks | `SELF_CORRELATION` |

## Validation Plan

- Confirm that the SUE field is point-in-time and not revised with future earnings information.
- Compare 20-, 40-, and 60-day deltas to test whether the signal depends on one exact lookback.
- Measure exposure to earnings momentum, price momentum, growth, size, and analyst-revision factors.
- Check self-correlation against existing submitted earnings and forecast-error alphas.

## Failure Criteria

Demote this proposal if self-correlation fails, the signal is dominated by one reporting season, or the alpha behaves like generic price momentum rather than earnings-information drift.

## Decision

Keep **Earnings Surprise Delta** as a high-priority clean candidate. It is one of the easiest remaining proposals to explain because the formula, data field, and economic mechanism align directly.

## Sources

- Local pass audit: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/07_research_papers/quantconnect_strategy_library_20260627/generated_alpha_candidates/quantconnect_strategy_library_sue_delta_pass_pool_additions_20260627.csv`
- Local proposal summary: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/06_alpha_catalog/alpha_proposals/alpha_proposal_passed_alphas_20260627.md`
