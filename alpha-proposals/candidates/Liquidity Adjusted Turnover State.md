---
title: Liquidity Adjusted Turnover State Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: Liquidity Adjusted Turnover State
alpha_ids:
  - e7ObVMqO
  - QPabgqqG
  - 9qwjd9v9
  - VkpaeVx8
status: hard-pass-family-self-correlation-pending
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium
tags:
  - worldquant
  - alpha-proposal
  - liquidity
  - risk-state
---

# Liquidity Adjusted Turnover State Alpha Proposal

> [!abstract] Research Thesis
> **Liquidity Adjusted Turnover State** extends abnormal turnover pressure with liquidity, stability, or low-risk filters. The thesis is that turnover anomalies are more useful when conditioned on marketability and risk state: the same turnover shock should be treated differently for liquid, stable firms than for volatile or fragile firms.

## Snapshot

| Dimension | Description |
| --- | --- |
| Alpha IDs | `e7ObVMqO`, `QPabgqqG`, `9qwjd9v9`, `VkpaeVx8` |
| Core field | `volume / sharesout` abnormal difference |
| Conditioning variables | `adv20`, return volatility, volume stability |
| Status | Hard checks passed; `SELF_CORRELATION` pending |
| Main risk | Still correlated with the basic turnover-pressure family |

## Representative Formulas

```text
stable = rank(adv20) - rank(ts_std_dev(returns, 60));
turn = ts_backfill(volume/sharesout, 5);
x = winsorize(ts_av_diff(turn, 504), std=4);
y = ts_mean(x, 30);
tv = rank(abs(y)) * group_rank(y, subindustry);
scale(0.65 * scale(tv) + 0.35 * scale(stable))
```

```text
turn = ts_backfill(volume/sharesout, 5);
x = winsorize(ts_av_diff(turn, 504), std=4);
y = ts_mean(x, 25);
tv = rank(abs(y)) * group_rank(y, subindustry);
lowrisk = 1 - rank(ts_std_dev(returns, 60));
scale(tv * (0.8 + 0.4 * lowrisk))
```

## Economic Rationale

Abnormal turnover can represent attention, execution pressure, or informed trading, but the quality of that signal depends on the stock's trading environment. Liquid and stable stocks provide better capacity and less noisy turnover readings. Low-risk conditioning can also reduce the chance that the alpha is merely loading on distressed volatility.

These variants should be treated as a conditioned extension of the abnormal-turnover proposal, not as unrelated alpha ideas. Their role is to improve implementation quality and risk control.

## Empirical Record

| Alpha | Mechanism | Sharpe | Fitness | Turnover | Returns | Drawdown | Pending |
| --- | --- | ---: | ---: | ---: | ---: | ---: | --- |
| `e7ObVMqO` | Stable/liquid turnover | `1.56` | `1.24` | `6.27%` | `7.95%` | `3.60%` | `SELF_CORRELATION` |
| `9qwjd9v9` | Low-risk turnover | `1.51` | `1.18` | `7.95%` | `7.59%` | `5.33%` | `SELF_CORRELATION` |
| `QPabgqqG` | Stable selection turnover | `1.39` | `1.17` | `6.40%` | `8.89%` | `6.91%` | `SELF_CORRELATION` |
| `VkpaeVx8` | Long-window low-risk turnover | `1.33` | `1.03` | `6.98%` | `7.43%` | `6.60%` | `SELF_CORRELATION` |

## Validation Plan

- Compare correlation against the basic turnover-pressure candidates.
- Test whether stability filters improve drawdown or only add noise.
- Check exposure to low-volatility, size, liquidity, and quality factors.
- Review capacity assumptions because liquidity-conditioned alphas can look better than they trade.

## Failure Criteria

Demote if the conditioning term does not reduce risk or correlation, or if the family becomes a disguised low-volatility factor rather than a turnover-state signal.

## Decision

Keep this as a secondary turnover family. It is useful if it lowers implementation risk or correlation; otherwise prefer the cleaner abnormal-turnover proposal.

## Sources

- Quant Slave audit: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/07_research_papers/quant_slave_papers_v1_20260626/generated_alpha_candidates/quant_slave_paper_alpha_pool_additions_20260626.csv`
- Quant Slave result note: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/07_research_papers/quant_slave_papers_v1_20260626/generated_alpha_candidates/quant_slave_paper_alpha_results_20260626.md`
