---
title: Alpha Proposal Index
type: alpha-proposal-index
project: worldquant-brain
status: active
created: 2026-06-27
updated: 2026-06-27
---

# Alpha Proposal Index

> [!summary] Canonical use
> Use this page as the entry point for alpha proposal notes. The active proposal library is organized into `submitted/`, `candidates/`, and `watchlist/`. Generated review batches are excluded from this library unless explicitly regenerated for audit work.

## Active Submitted Proposals

| Proposal | Alpha ID | Mechanism | Status |
| --- | --- | --- | --- |
| [Capital Productivity Momentum](submitted/Capital%20Productivity%20Momentum.md) | `akdlx0Kw` | Operating income over capital, level plus improvement | Submitted-active, OS pending |
| [Goodwill Burden Delta](submitted/Goodwill%20Burden%20Delta.md) | `Wjpb7KAj` | Goodwill-to-sales burden plus 126-day deterioration | Submitted-active, self-correlation pending |

## Candidate Proposal Families

| Proposal | Alpha IDs | Mechanism | Status |
| --- | --- | --- | --- |
| [Earnings Surprise Delta](candidates/Earnings%20Surprise%20Delta.md) | `rKoeVmra` | Change in standardized unexpected earnings | Hard pass, self-correlation pending |
| [Options Skew Risk Appetite](candidates/Options%20Skew%20Risk%20Appetite.md) | `YPWmwWwW`, `LLl6b7O6`, `58q9RJKo`, `A1k5dzWE` | Regime-gated options implied-volatility skew | Hard-pass family, correlation review required |
| [Tax Working Spread Momentum](candidates/Tax%20Working%20Spread%20Momentum.md) | `O0oWakzR`, `3qz0Nnz0` | Decayed tax-working-spread accounting signal | Hard-pass family, correlation review required |
| [EPS Event Revision Coupling](candidates/EPS%20Event%20Revision%20Coupling.md) | `GrnGL2v3` | Event EPS and revised EPS correlation | Hard pass, low workbook correlation |
| [Credit Distress Dislocation](candidates/Credit%20Distress%20Dislocation.md) | `wpewYzp5` | Rating/default-probability disagreement | Hard pass, correlation review required |
| [Liquidity Risk Variability](candidates/Liquidity%20Risk%20Variability.md) | `RRrZAmln` | Volatility of liquidity-risk model exposure | Hard pass, low workbook correlation |
| [Free Cash Flow Guidance Timing](candidates/Free%20Cash%20Flow%20Guidance%20Timing.md) | `6XRoavlY` | Recency of free-cash-flow guidance maximum | Hard pass, low workbook correlation |
| [News Inefficiency Underreaction](candidates/News%20Inefficiency%20Underreaction.md) | `zq983pX8`, `3q7XjEV0` | News attention reversal and earnings-news residual | Hard pass, self-correlation pending |
| [Abnormal Turnover Pressure](candidates/Abnormal%20Turnover%20Pressure.md) | `WjpbYzno`, `kq3ovj3k`, `O0pNM8W1`, `LLpZQN96`, `3q6X5YkO` | Abnormal turnover versus long baseline | Hard-pass family, self-correlation pending |
| [Liquidity Adjusted Turnover State](candidates/Liquidity%20Adjusted%20Turnover%20State.md) | `e7ObVMqO`, `QPabgqqG`, `9qwjd9v9`, `VkpaeVx8` | Turnover state conditioned on liquidity or risk | Hard-pass family, self-correlation pending |
| [Sparse Cashflow Value](candidates/Sparse%20Cashflow%20Value.md) | `leVzzjMl` | Enterprise value to operating cash flow with sparse activation | Submitted-active, OS pending |
| [Cost Intensity Efficiency](candidates/Cost%20Intensity%20Efficiency.md) | `0m79mj6q`, `wpzQPApx`, `WjWjvxwP`, `omzEZpd2`, `mLzokak9` | Cost intensity relative to capital | Submitted-active plus workbook hard-pass variants |
| [Forecast Error Underreaction](candidates/Forecast%20Error%20Underreaction.md) | `78wQj2lZ`, `wpR1jYJ5` | Analyst forecast error smoothing | Submitted-active, OS pending |
| [Price Volume Reversal Pressure](candidates/Price%20Volume%20Reversal%20Pressure.md) | `MPxl3Rp6`, `rKL2M2Xj`, `om98KvNl` | Return-volume reversal pressure | Hard pass, high-turnover review required |
| [Adjusted Net Income Drift](candidates/Adjusted%20Net%20Income%20Drift.md) | `rKra0V2j` | Short-decayed adjusted net income | Hard pass, correlation review required |

## Watchlist

| Note | Scope |
| --- | --- |
| [Near Pass and Deferred Signals](watchlist/Near%20Pass%20and%20Deferred%20Signals.md) | Near-pass signals and deferred multi-sleeve composites. |

## Operating Rule

- Keep only hand-polished, reader-facing proposal notes in this folder.
- Put active submitted proposals under `submitted/`.
- Put hard-pass or research candidates under `candidates/`.
- Put near-pass or deferred composite ideas under `watchlist/`.
- Do not restore generated batch folders here unless the user explicitly asks for a review batch.
- If a generated batch is needed again, regenerate from the source workbook or source artifacts rather than treating old batch notes as canonical.

## Source Reminder

The source workbook and simulation artifacts remain the canonical data source for regeneration. These proposal notes are research writeups, not investment advice or claims of future returns.
