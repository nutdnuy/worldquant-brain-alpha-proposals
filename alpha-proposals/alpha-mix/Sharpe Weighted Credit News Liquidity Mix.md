---
title: Sharpe Weighted Credit News Liquidity Mix
type: alpha-mix-proposal
project: worldquant-brain
status: candidate
created: 2026-06-27
updated: 2026-06-27
representative_alpha: e7rdMLNp
related_alpha_ids:
  - e7rdMLNp
  - 6XEwNkdE
---

# Sharpe Weighted Credit News Liquidity Mix

> [!abstract] Proposal
> Combine three distinct sleeves and let their weights respond to a rolling 30-day realized alpha-return Sharpe proxy. The representative uses credit-rating disagreement, news/price reaction, and price-volume liquidity pressure.

## Research Snapshot

| Item | Value |
| --- | --- |
| Representative alpha | `e7rdMLNp` |
| Sibling variant | `6XEwNkdE` |
| Construction | Three-sleeve rolling Sharpe-weighted mix |
| Parent families | Credit rating, news/mixed composite, price-volume |
| Weight signal | Rank of 30-day mean alpha return divided by 30-day alpha-return volatility |
| Current status | Hard checks passed; self-correlation pending |

## Evidence

| Alpha ID | Parent Sleeves | Sharpe | Fitness | Turnover | Returns | Drawdown | Grade |
| --- | --- | ---: | ---: | ---: | ---: | ---: | --- |
| `e7rdMLNp` | `akO2bAe6`; `rKL78jAd`; `MPxl3Rp6` | 2.17 | 2.55 | 15.60% | 21.46% | 11.87% | SPECTACULAR |
| `6XEwNkdE` | `1YLWnJY6`; `omYwKErv`; `MPxl3Rp6` | 2.14 | 2.88 | 8.94% | 22.63% | 8.99% | SPECTACULAR |

## Construction

Each sleeve is neutralized and scaled. The mix then computes a 30-day realized performance proxy for each sleeve and allocates weights proportionally to the ranked scores.

```text
alpha1 = -(ts_corr(rank(ts_backfill(annualized_pd_7_year_jc7, 63)), rank(ts_backfill(probability_dist_aaa, 63)), 20));
alpha2 = rank(ts_sum(vec_avg(nws12_afterhsz_sl), 60)) > 0.5 ? 1 : rank(-ts_delta(close, 2));
alpha3 = -(ts_mean(returns * min(ts_rank(vwap, 10), ts_rank(close, 10)), 20));

alpha1_scaled = scale(group_neutralize(alpha1, industry));
alpha2_scaled = scale(group_neutralize(alpha2, industry));
alpha3_scaled = scale(group_neutralize(alpha3, industry));

alpha1_score = rank(ts_mean(alpha1_scaled * returns, 30) / max(ts_std_dev(alpha1_scaled * returns, 30), 0.0001));
alpha2_score = rank(ts_mean(alpha2_scaled * returns, 30) / max(ts_std_dev(alpha2_scaled * returns, 30), 0.0001));
alpha3_score = rank(ts_mean(alpha3_scaled * returns, 30) / max(ts_std_dev(alpha3_scaled * returns, 30), 0.0001));

w_sum = alpha1_score + alpha2_score + alpha3_score + 0.0001;
alphamix_raw = (alpha1_score / w_sum) * alpha1_scaled
             + (alpha2_score / w_sum) * alpha2_scaled
             + (alpha3_score / w_sum) * alpha3_scaled;
alphamix = scale(group_neutralize(alphamix_raw, industry));
alphamix
```

## Why It Should Work

The financial intuition is regime allocation. Credit-rating disagreement, news reaction, and price-volume pressure are not expected to work equally in all periods. A rolling realized alpha-return Sharpe proxy gives more weight to the sleeve that is currently producing cleaner payoff relative to noise, while retaining diversification across all three sleeves.

The design is more adaptive than equal weighting but still interpretable. It does not use a complex optimizer; it ranks recent sleeve quality and normalizes weights. That keeps the mechanism close to a time-varying factor allocation rule.

## Main Risks

- The 30-day window may chase short-lived performance and overreact after lucky runs.
- Multiplying alpha sleeves by same-period returns can introduce fragile feedback if not interpreted as a historical realized-quality proxy.
- The mix can become crowded if the price-volume sleeve receives high weight during liquidity stress.

## Validation Plan

- Compare against equal-weight and inverse-volatility versions using the same three sleeves.
- Inspect yearly sleeve weights to confirm they rotate rather than collapse.
- Re-run with 20-day and 60-day score windows.
- Reject if the rolling score improves in-sample metrics but worsens test-period Sharpe or self-correlation.

## Sources

- Candidate files: `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/sim_candidates/top3000_sharpe30w3_candidates_100.csv`, `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/sim_results/top3000_sharpe30w3_extra300_sim_results_stopped_20260608_211646.csv`
- Result files: `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/sim_results/top3000_sharpe30w3_candidates_100_sim_results_merged.csv`, `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/sim_results/top3000_sharpe30w3_extra300_sim_results_stopped_20260608_211646.csv`
