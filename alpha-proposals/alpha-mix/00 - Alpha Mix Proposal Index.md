---
title: Alpha Mix Proposal Index
type: alpha-mix-proposal-index
project: worldquant-brain
status: active
created: 2026-06-27
updated: 2026-06-27
---

# Alpha Mix Proposal Index

> [!summary] Scope
> This section contains alpha-mix proposals: composite signals that combine multiple alpha sleeves, parent families, or dynamic weighting rules. They are intentionally separated from single-mechanism candidates because their main research question is portfolio construction, not only standalone economic signal discovery.

## Active Mix Proposals

| Proposal | Representative Alpha IDs | Mix Construction | Status |
| --- | --- | --- | --- |
| [Guarded Inverse Volatility Tri-Family Mix](Guarded%20Inverse%20Volatility%20Tri-Family%20Mix.md) | `9qRAp3g9`, `zqWJrvM1` | Three distinct families weighted by inverse realized sleeve volatility | Hard pass, self-correlation pending |
| [Equal Weight Low Correlation Parent Mix](Equal%20Weight%20Low%20Correlation%20Parent%20Mix.md) | `JjdanMlO`, `XgKZ2OZ0`, `e7rMnb6O` | Equal-weight normalized blend of low-correlation parent alphas | Hard pass, self-correlation pending |
| [Direction Weighted Options Skew Conviction](Direction%20Weighted%20Options%20Skew%20Conviction.md) | `xAnkAEGw` | Options-skew direction with price-volume conviction boost | Hard pass, self-correlation pending |
| [Direction Weighted Tax Credit Conviction](Direction%20Weighted%20Tax%20Credit%20Conviction.md) | `MPxp60Za`, `3qARw6wN` | Tax-working-spread direction with credit or risk conviction weight | Hard pass, self-correlation pending |
| [Sharpe Weighted Credit News Liquidity Mix](Sharpe%20Weighted%20Credit%20News%20Liquidity%20Mix.md) | `e7rdMLNp`, `6XEwNkdE` | Three-sleeve blend with rolling 30-day realized Sharpe proxy weights | Hard pass, self-correlation pending |
| [Core Satellite Positive Region Blend](Core%20Satellite%20Positive%20Region%20Blend.md) | `O0p0WdPd`, `JjpMkM8m` | Workbook-only core-satellite mix around historically positive parent regions | Hard pass metrics, high-correlation review required |

## Deferred Mix Frontier

| Proposal | Representative Candidate | Reason Deferred |
| --- | --- | --- |
| [Dynamic Tax GARP Allocation Frontier](Dynamic%20Tax%20GARP%20Allocation%20Frontier.md) | `thememix_009` to `thememix_020` family | Research frontier between hard-check pass, self-correlation reduction, and sub-universe Sharpe repair |

## Research Rule

- Treat every mix note as a portfolio-construction hypothesis.
- Do not count sibling mix variants as independent capacity until self-correlation and parent-correlation checks clear.
- Prefer one representative per mix mechanism unless a sibling materially improves robustness or correlation.
- Record failed or near-pass frontier variants because they show the tradeoff surface for future repair.
