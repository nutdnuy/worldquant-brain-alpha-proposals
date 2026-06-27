---
title: News Inefficiency Underreaction Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: News Inefficiency Underreaction
alpha_ids:
  - zq983pX8
  - 3q7XjEV0
status: hard-pass-self-correlation-pending
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium-high
tags:
  - worldquant
  - alpha-proposal
  - news
  - attention
  - underreaction
---

# News Inefficiency Underreaction Alpha Proposal

> [!abstract] Research Thesis
> **News Inefficiency Underreaction** is a paper-derived news alpha family. It tests whether news signals retain cross-sectional information after controlling for known drivers such as recent returns, firm size, and sales change, and whether high-attention news events create short-horizon reversal pressure.

## Snapshot

| Dimension | Description |
| --- | --- |
| Alpha IDs | `zq983pX8`, `3q7XjEV0` |
| Source prior | EX07, "The Inefficient Pricing of News" |
| Signal family | News attention / news residual |
| Best headline candidate | `zq983pX8`, Sharpe `1.83`, Fitness `1.06` |
| Cleaner candidate | `3q7XjEV0`, Sharpe `1.34`, Fitness `1.00` |
| Status | Hard checks passed; `SELF_CORRELATION` pending |
| Main risk | High turnover and event-data fragility |

## Formulas

### High-Attention Reversal: `zq983pX8`

```text
attn = rank(vec_avg(nws18_event_relevance)) + rank(ts_backfill(scl12_buzz, 20));
move = rank(ts_sum(returns, 5));
group_rank(-move * attn, industry)
```

### Earnings-News Residual: `3q7XjEV0`

```text
news = rank(ts_mean(rp_css_earnings, 20) + ts_mean(rp_ess_earnings, 20) + ts_mean(rp_nip_earnings, 20));
known = 0.40 * rank(ts_sum(returns, 63)) + 0.30 * rank(cap) + 0.30 * rank(ts_delta(ts_backfill(sales, 252), 126));
group_rank(news - known, industry)
```

## Economic Rationale

News is public, but attention and interpretation are not uniform. The residual version asks whether earnings-news tone contains incremental information after controlling for recent returns, size, and fundamental sales change. The attention-reversal version asks whether highly visible news events create short-horizon overreaction that subsequently mean-reverts.

The two alphas should be reviewed together, not as unrelated ideas. They share the same information channel but use different market-behavior assumptions: underreaction to earnings news versus overreaction after high attention.

## Empirical Record

| Alpha | Mechanism | Sharpe | Fitness | Turnover | Returns | Drawdown | Pending |
| --- | --- | ---: | ---: | ---: | ---: | ---: | --- |
| `zq983pX8` | High-attention reversal | `1.83` | `1.06` | `42.22%` | `14.04%` | `9.90%` | `SELF_CORRELATION` |
| `3q7XjEV0` | Earnings-news residual | `1.34` | `1.00` | `8.52%` | `7.01%` | `9.57%` | `SELF_CORRELATION` |

## Validation Plan

- Confirm event-field timing and avoid news timestamp leakage.
- Review turnover and transaction-cost sensitivity for `zq983pX8`.
- Test whether the residual candidate remains useful after neutralizing momentum and size more explicitly.
- Compare self-correlation against existing news, buzz, earnings, and reversal alphas.

## Failure Criteria

Reject the family if performance depends on stale event timestamps, turnover costs erase the edge, or the alpha reduces to generic reversal without news conditioning.

## Decision

Keep both candidates as one proposal family. Prioritize `3q7XjEV0` for cleaner economics and lower turnover; treat `zq983pX8` as a higher-Sharpe but higher-friction variant.

## Sources

- Local paper card: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/07_research_papers/worldquant_brain_research_papers_for_users_20260626/knowledge/cards/ex07-the-inefficient-pricing-of-news.md`
- Simulation result note: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/07_research_papers/worldquant_brain_research_papers_for_users_20260626/generated_alpha_candidates/ex07_pure_news_proxy_sim_result_20260626.md`
- Pool audit: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/07_research_papers/worldquant_brain_research_papers_for_users_20260626/generated_alpha_candidates/paper_alpha_pool_additions_20260626.csv`
