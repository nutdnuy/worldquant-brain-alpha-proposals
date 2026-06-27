---
title: Abnormal Turnover Pressure Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: Abnormal Turnover Pressure
alpha_ids:
  - WjpbYzno
  - kq3ovj3k
  - O0pNM8W1
  - LLpZQN96
  - 3q6X5YkO
status: hard-pass-family-self-correlation-pending
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium-high
tags:
  - worldquant
  - alpha-proposal
  - turnover
  - liquidity-pressure
---

# Abnormal Turnover Pressure Alpha Proposal

> [!abstract] Research Thesis
> **Abnormal Turnover Pressure** captures unusual trading intensity relative to a long historical baseline. The thesis is that persistent deviations in `volume / sharesout` can reveal investor attention, liquidity demand, inventory pressure, or execution-cost regimes that are not fully captured by price returns alone.

## Snapshot

| Dimension | Description |
| --- | --- |
| Alpha IDs | `WjpbYzno`, `kq3ovj3k`, `O0pNM8W1`, `LLpZQN96`, `3q6X5YkO` |
| Core field | `volume / sharesout` |
| Core operator | `ts_av_diff(..., 504)` |
| Signal family | Abnormal turnover / liquidity pressure |
| Status | Hard checks passed; `SELF_CORRELATION` pending |
| Main risk | High correlation among variants |

## Representative Formulas

### Continuous Pressure: `WjpbYzno`

```text
turn = ts_backfill(volume/sharesout, 5);
x = winsorize(ts_av_diff(turn, 504), std=4);
y = ts_mean(x, 30);
group_rank(rank(abs(y)) * group_rank(y, subindustry), subindustry)
```

### Sparse Pressure: `kq3ovj3k` / `O0pNM8W1`

```text
turn = ts_backfill(volume/sharesout, 5);
x = winsorize(ts_av_diff(turn, 504), std=4);
y = ts_mean(x, 30);
z = rank(abs(y)) * group_rank(y, subindustry);
trade_when(rank(abs(y)) > 0.78, z, -1)
```

### Faster Smoothing: `LLpZQN96`

```text
turn = ts_backfill(volume/sharesout, 5);
x = winsorize(ts_av_diff(turn, 504), std=4);
y = ts_mean(x, 20);
group_rank(rank(abs(y)) * group_rank(y, subindustry), subindustry)
```

### Volatility-Filtered Turnover: `3q6X5YkO`

```text
turnover = ts_backfill(volume, 126, k=1)/ts_backfill(sharesout, 252, k=1);
core = winsorize(ts_av_diff(turnover, 504), std=4);
signal = ts_mean(core, 15);
filtered = trade_when(ts_rank(ts_std_dev(core, 63), 252) < 0.85, signal, 0);
group_neutralize(filtered, market)
```

## Economic Rationale

Turnover is a behavioral and market-microstructure variable. A stock trading materially above or below its long-run turnover baseline may be experiencing attention shocks, liquidity rebalancing, informed trading, or temporary execution pressure. The alpha does not trade raw volume. It scales by shares outstanding, compares to a long baseline, smooths the result, and ranks the signal within peers.

The magnitude term `rank(abs(y))` is important because small turnover deviations are likely noise. The family rewards stronger abnormal turnover states and uses peer ranking to reduce sector and liquidity-level bias.

## Empirical Record

| Alpha | Variant | Sharpe | Fitness | Turnover | Returns | Drawdown | Pending |
| --- | --- | ---: | ---: | ---: | ---: | ---: | --- |
| `WjpbYzno` | Continuous 30-day pressure | `1.75` | `1.29` | `9.85%` | `6.76%` | `3.59%` | `SELF_CORRELATION` |
| `LLpZQN96` | Continuous 20-day pressure | `1.65` | `1.19` | `12.08%` | `6.54%` | `3.80%` | `SELF_CORRELATION` |
| `3q6X5YkO` | Volatility-filtered pressure | `1.46` | `2.12` | `6.04%` | `26.48%` | `18.88%` | n/a |
| `kq3ovj3k` | Sparse threshold `0.78` | `1.54` | `1.13` | `2.38%` | `6.77%` | `4.29%` | `SELF_CORRELATION` |
| `O0pNM8W1` | Sparse threshold `0.82` | `1.40` | `1.03` | `2.21%` | `6.72%` | `5.46%` | `SELF_CORRELATION` |

## Validation Plan

- Treat this as one family for self-correlation review; do not submit highly correlated variants blindly.
- Test transaction-cost sensitivity, especially for the continuous variants.
- Compare 20-, 25-, and 30-day smoothing windows.
- Check whether the sign is robust across industries and liquidity buckets.

## Failure Criteria

Demote individual variants if self-correlation is high, if the signal is just a liquidity-size proxy, or if turnover costs consume the recorded edge.

## Decision

Keep **Abnormal Turnover Pressure** as one family proposal. Use the sparse versions when correlation or turnover control matters; use the continuous versions when stronger signal exposure is needed.

## Sources

- Passed-alpha summary: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/06_alpha_catalog/alpha_proposals/alpha_proposal_passed_alphas_20260627.md`
- Quant Slave audit: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/07_research_papers/quant_slave_papers_v1_20260626/generated_alpha_candidates/quant_slave_paper_alpha_pool_additions_20260626.csv`
- Agentic loop note: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/06_alpha_catalog/alpha_proposals/alpha_proposal_agentic_loop_round1_20260627.md`
- Source workbook: `/Users/nuthdanai/Desktop/alpha-mixing-research/alpha_mixing_research_combined.xlsm`, sheet `04_alpha_pass_combined`
