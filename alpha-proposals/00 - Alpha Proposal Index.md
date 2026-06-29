---
title: Alpha Proposal Index
type: alpha-proposal-index
project: worldquant-brain
status: active
created: 2026-06-27
updated: 2026-06-29
---

# Alpha Proposal Index

> [!summary] Canonical use
> Use this page as the entry point for alpha proposal notes. The active proposal library is organized into `submitted/`, `candidates/`, `alpha-mix/`, and `watchlist/`. Generated review batches are excluded from this library unless explicitly regenerated for audit work.

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
| [Glazar IQC Source Playbook](candidates/Glazar%20IQC%20Source%20Playbook.md) | n/a | External IQC source pack for price-volume, news/social, and fundamental-value candidates | External source intake, simulation queue required |

## Alpha Mix Proposals

> [!note] Separate construction layer
> Alpha mix notes are composite portfolio-construction hypotheses. They live in `alpha-mix/` so they are not confused with single-mechanism alpha candidates.

| Proposal | Representative Alpha IDs | Mix Construction | Status |
| --- | --- | --- | --- |
| [Alpha Mix Proposal Index](alpha-mix/00%20-%20Alpha%20Mix%20Proposal%20Index.md) | n/a | Entry point for composite alpha-mix notes | Active index |
| [Guarded Inverse Volatility Tri-Family Mix](alpha-mix/Guarded%20Inverse%20Volatility%20Tri-Family%20Mix.md) | `9qRAp3g9`, `zqWJrvM1` | Three distinct families weighted by inverse realized sleeve volatility | Hard pass, self-correlation pending |
| [Equal Weight Low Correlation Parent Mix](alpha-mix/Equal%20Weight%20Low%20Correlation%20Parent%20Mix.md) | `JjdanMlO`, `XgKZ2OZ0`, `e7rMnb6O` | Equal-weight normalized blend of low-correlation parent alphas | Hard pass, self-correlation pending |
| [Direction Weighted Options Skew Conviction](alpha-mix/Direction%20Weighted%20Options%20Skew%20Conviction.md) | `xAnkAEGw` | Options-skew direction with price-volume conviction boost | Hard pass, self-correlation pending |
| [Direction Weighted Tax Credit Conviction](alpha-mix/Direction%20Weighted%20Tax%20Credit%20Conviction.md) | `MPxp60Za`, `3qARw6wN` | Tax-working-spread direction with credit or risk conviction weight | Hard pass, self-correlation pending |
| [Sharpe Weighted Credit News Liquidity Mix](alpha-mix/Sharpe%20Weighted%20Credit%20News%20Liquidity%20Mix.md) | `e7rdMLNp`, `6XEwNkdE` | Three-sleeve rolling Sharpe-proxy weight mix | Hard pass, self-correlation pending |
| [Core Satellite Positive Region Blend](alpha-mix/Core%20Satellite%20Positive%20Region%20Blend.md) | `O0p0WdPd`, `JjpMkM8m` | Workbook-only core-satellite weighted blend | Hard pass metrics, high-correlation review required |
| [Dynamic Tax GARP Allocation Frontier](alpha-mix/Dynamic%20Tax%20GARP%20Allocation%20Frontier.md) | `thememix_009` to `thememix_020` | Dynamic tax/GARP allocation frontier | Deferred frontier |

## Restored Consolidated Review Units

> [!note] Flattened restore
> These notes were restored from the prior consolidated portfolio review batch, but the generated batch folder itself was not restored. They now live directly inside `candidates/` so the active proposal library has one navigable structure.

| Restored note | Scope |
| --- | --- |
| [Consolidated Alpha Cluster Index](candidates/00%20-%20Consolidated%20Alpha%20Cluster%20Index.md) | Deduplicated review index: 12 clean multi-member clusters, 30 singleton rows, 397 mixed-composite rows filtered out |
| [C001 - Capital Productivity Momentum - Capital Cost Base](candidates/001%20-%20C001-Capital-Productivity-Momentum-Capital-Cost-Base.md) | 27-member tax/accounting capital-cost-base cluster |
| [C002 - Fundamental Score Momentum - Multi-Factor Score Delta](candidates/002%20-%20C002-Fundamental-Score-Momentum-Multi-Factor-Score-Delta.md) | 14-member multi-factor score-delta cluster |
| [C003 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew](candidates/003%20-%20C003-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew.md) | 12-member options-skew cluster |
| [C004 - Price Volume Reversal - Price Liquidity](candidates/004%20-%20C004-Price-Volume-Reversal-Price-Liquidity.md) | 8-member price-liquidity reversal cluster |
| [C005 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew](candidates/005%20-%20C005-Options-Skew-Risk-Appetite-Put-Call-OI-60D-IV-Skew.md) | 8-member options-skew cluster |
| [C006 - Options Skew Risk Appetite - 30D IV Skew](candidates/006%20-%20C006-Options-Skew-Risk-Appetite-30D-IV-Skew.md) | 4-member options IV skew cluster |
| [C007 - EPS Revision Shock - EPS Estimate](candidates/007%20-%20C007-EPS-Revision-Shock-EPS-Estimate.md) | 4-member EPS estimate revision cluster |
| [C008 - Cross Sectional Signal Momentum - Tax Working Spread](candidates/008%20-%20C008-Cross-Sectional-Signal-Momentum-Tax-Working-Spread.md) | 3-member tax-working-spread duplicate cluster |
| [C009 - Capital Productivity Momentum - Capital Cost Base + Operating Profit](candidates/009%20-%20C009-Capital-Productivity-Momentum-Capital-Cost-Base-Operating-Profit.md) | 3-member capital productivity plus operating-profit cluster |
| [C010 - Tax Cash Flow Capital Momentum - Tax Book Cash Flow + Capital Cost Base](candidates/010%20-%20C010-Tax-Cash-Flow-Capital-Momentum-Tax-Book-Cash-Flow-Capital-Cost-Base.md) | 3-member tax-cash-flow capital cluster |
| [C011 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew + Capital Cost Base](candidates/011%20-%20C011-Options-Skew-Risk-Appetite-Put-Call-OI-60D-IV-Skew-Capital-Cost-Base.md) | 2-member options-skew plus capital-cost-base cluster |
| [C012 - Cross Sectional Signal Momentum - F-Score Growth](candidates/012%20-%20C012-Cross-Sectional-Signal-Momentum-F-Score-Growth.md) | 2-member F-score growth cluster |
| [Alpha Proposal Singletons](candidates/99%20-%20Alpha%20Proposal%20Singletons.md) | 30 clean singleton proposal rows kept separate from merged clusters |

## Watchlist

| Note | Scope |
| --- | --- |
| [Near Pass and Deferred Signals](watchlist/Near%20Pass%20and%20Deferred%20Signals.md) | Near-pass signals and deferred multi-sleeve composites. |

## Operating Rule

- Keep only hand-polished, reader-facing proposal notes in this folder.
- Put active submitted proposals under `submitted/`.
- Put hard-pass or research candidates under `candidates/`.
- Put composite alpha-mix proposals under `alpha-mix/`.
- Put near-pass or deferred composite ideas under `watchlist/`.
- Do not restore generated batch folders here unless the user explicitly asks for a review batch.
- If a generated batch is needed again, regenerate from the source workbook or source artifacts rather than treating old batch notes as canonical.

## Source Reminder

The source workbook and simulation artifacts remain the canonical data source for regeneration. These proposal notes are research writeups, not investment advice or claims of future returns.
