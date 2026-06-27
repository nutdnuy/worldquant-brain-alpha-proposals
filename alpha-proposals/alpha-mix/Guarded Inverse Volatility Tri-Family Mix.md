---
title: Guarded Inverse Volatility Tri-Family Mix
type: alpha-mix-proposal
project: worldquant-brain
status: candidate
created: 2026-06-27
updated: 2026-06-27
representative_alpha: 9qRAp3g9
related_alpha_ids:
  - 9qRAp3g9
  - zqWJrvM1
---

# Guarded Inverse Volatility Tri-Family Mix

> [!abstract] Proposal
> Combine three economically distinct alpha sleeves and allocate more weight to the sleeve whose recent realized alpha-return volatility is lower. The hypothesis is that a risk-balanced blend can preserve multiple weakly related edges while avoiding domination by the noisiest sleeve.

## Research Snapshot

| Item | Value |
| --- | --- |
| Representative alpha | `9qRAp3g9` |
| Sibling variant | `zqWJrvM1` |
| Construction | Guarded inverse-volatility three-family mix |
| Parent sleeves | analyst estimate, tax-working-spread fundamental, value/quality composite |
| Universe | USA TOP3000 |
| Delay | 1 |
| Neutralization | Industry-level internal or platform neutralization depending on run |
| Current status | Hard checks passed; self-correlation pending |

## Evidence

| Alpha ID | Sharpe | Fitness | Turnover | Returns | Drawdown | Grade | Pending |
| --- | ---: | ---: | ---: | ---: | ---: | --- | --- |
| `9qRAp3g9` | 2.72 | 2.94 | 4.19% | 14.62% | 4.01% | SPECTACULAR | SELF_CORRELATION |
| `zqWJrvM1` | 2.72 | 2.94 | 4.15% | 14.58% | 3.92% | SPECTACULAR | SELF_CORRELATION |

## Construction

The representative expression creates three normalized sleeves. The first uses an earnings-estimate and R&D interaction, the second uses decayed tax-working-spread information, and the third uses a value-quality model spread. Each sleeve is standardized, then weighted by the inverse of its recent 60-day alpha-return volatility.

```text
alpha1_raw = -(group_rank(rank(ts_corr(vec_avg(eps_previous_estimate_value), ts_backfill(research_development_expense, 120), 60)), sector));
alpha2_raw = group_neutralize(group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector), sector);
alpha3_raw = -(mdl177_valuemomemtummodel_earningsqualitymodule - mdl77_2growthanalystmodel_qga_opmarginsales);

alpha1 = scale(normalize(alpha1_raw, useStd=true, limit=3));
alpha2 = scale(normalize(alpha2_raw, useStd=true, limit=3));
alpha3 = scale(normalize(alpha3_raw, useStd=true, limit=3));

vol1 = ts_backfill(ts_std_dev(alpha1 * returns, 60), 120);
vol2 = ts_backfill(ts_std_dev(alpha2 * returns, 60), 120);
vol3 = ts_backfill(ts_std_dev(alpha3 * returns, 60), 120);

iv1 = 1 / max(vol1, 0.0001);
iv2 = 1 / max(vol2, 0.0001);
iv3 = 1 / max(vol3, 0.0001);
iv_sum = iv1 + iv2 + iv3;

w1 = ts_mean(iv1 / iv_sum, 20);
w2 = ts_mean(iv2 / iv_sum, 20);
w3 = ts_mean(iv3 / iv_sum, 20);

alpha = scale(w1 * alpha1 + w2 * alpha2 + w3 * alpha3);
alpha
```

## Why It Should Work

This mix has a plausible portfolio-construction rationale. Analyst-estimate disagreement, tax-accounting momentum, and value-quality spreads are not the same economic channel. A fixed equal-weight blend can still be dominated by whichever sleeve has higher realized volatility; inverse-volatility weighting tries to keep each sleeve's risk contribution closer. The 20-day smoothing of weights also reduces the risk that a single noisy day reallocates the whole signal.

Financially, this is similar to a factor risk-parity portfolio at the alpha-sleeve level. It does not assume one parent signal is always superior. It assumes relative sleeve stability carries information about which sleeve should receive marginal capital at a given time.

## Main Risks

- The inverse-volatility estimator may be unstable if sleeve returns are sparse or nonstationary.
- The mix can inherit hidden crowding from the tax-working-spread parent if that sleeve receives persistent high weight.
- Strong in-sample metrics do not prove out-of-sample robustness; self-correlation remains the main promotion gate.

## Validation Plan

- Compare the representative against each parent sleeve and against a simple equal-weight version.
- Check current self-correlation against submitted and candidate pools.
- Run a sleeve contribution analysis by year to confirm no single sleeve explains most PnL.
- Kill the proposal if the inverse-volatility weights collapse to one sleeve or if the best sibling is effectively a duplicate.

## Sources

- Candidate file: `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/sim_candidates/top3000_guarded_invvol3_candidates_300.csv`
- Result files: `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/sim_results/top3000_guarded_invvol3_combined_150_shortlist.csv`, `/Users/nuthdanai/Desktop/alpha-mixing-research/outputs/sim_results/top3000_guarded_invvol3_combined_158_completed.csv`
