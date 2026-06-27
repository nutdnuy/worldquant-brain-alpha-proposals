---
title: Dynamic Tax GARP Allocation Frontier
type: alpha-mix-proposal
project: worldquant-brain
status: deferred-frontier
created: 2026-06-27
updated: 2026-06-27
representative_candidate: thememix_011_txws_garp_dynamic_mid
---

# Dynamic Tax GARP Allocation Frontier

> [!abstract] Proposal
> Dynamically allocate between a tax-working-spread core and a GARP value-price instability sleeve using short-window realized alpha-quality proxies. This is currently a frontier note rather than an active candidate because the family trades off hard-check pass, self-correlation reduction, and sub-universe Sharpe.

## Research Snapshot

| Item | Value |
| --- | --- |
| Representative candidate | `thememix_011_txws_garp_dynamic_mid` |
| Related variants | `thememix_009` to `thememix_020` family |
| Construction | Dynamic weight between tax core and GARP sleeve |
| Core fields | `fnd6_txws`, `min_free_cash_flow_per_share_guidance`, `mdl177_garpanalystmodel_qgp_vfpriceratio`, `returns` |
| Current status | Deferred frontier; not a clean active proposal yet |

## Construction

The candidate builds a tax-working-spread alpha, a GARP value-price instability alpha, then shifts weight toward the sleeve with better recent realized alpha quality.

```text
tx_dir = group_neutralize(group_rank(ts_decay_linear(ts_backfill(vec_avg(fnd6_txws), 120), 10), sector), sector);
tx_conf = group_rank(ts_arg_max(min_free_cash_flow_per_share_guidance, 10), sector);
tx_alpha = scale(tx_dir * if_else(rank(abs(tx_conf)) > 0.85, 1.25, 1.00));

garp_signal = -mdl177_garpanalystmodel_qgp_vfpriceratio * ts_std_dev(mdl177_garpanalystmodel_qgp_vfpriceratio, 30);
volatility = rank(ts_std_dev(returns, 252));
garp_alpha = scale(rank(vector_neut(garp_signal, volatility)) - 0.5);

tx_q = rank(ts_mean(tx_alpha * returns, 40) / ts_std_dev(tx_alpha * returns, 40));
garp_q = rank(ts_mean(garp_alpha * returns, 40) / ts_std_dev(garp_alpha * returns, 40));
wg = 0.22 + 0.45 * ts_mean(garp_q / (tx_q + garp_q + 0.0001), 20);

alpha = scale((1 - wg) * tx_alpha + wg * garp_alpha);
alpha
```

## Why It Might Work

The tax-working-spread core is a strong accounting signal but can become self-correlated to existing tax/FCF proposals. The GARP sleeve changes the economic carrier by adding valuation instability and volatility neutralization. Dynamic weighting lets the formula retain the tax core when it is working, but shift toward GARP when recent realized quality favors the alternative sleeve.

This is economically plausible because tax accounting and value-price instability respond to different investor information sets. The goal is not to maximize standalone Sharpe at any cost; it is to find a point where the alpha keeps enough performance while lowering structural overlap with existing submissions.

## Frontier Evidence

The source notes show a clear tradeoff:

| Variant Family | Observation |
| --- | --- |
| Soft dynamic blend | Hard-check pass, but self-correlation still around 0.7955 in notes |
| Midpoint dynamic blend | Lower self-correlation geometry around 0.7024, but near sub-universe Sharpe miss |
| Decay/truncation repairs | Attempt to repair the small sub-universe miss without changing the mechanism |
| TxWS shave variants | Partial anti-crowd subtraction tries to reduce correlation while preserving the tax core |

## Main Risks

- The realized-quality weighting may chase recent sleeve noise.
- The tax leg may remain too dominant for self-correlation.
- Aggressive residualization can destroy the tax core and cause sub-universe failure.

## Next Experiment

- Retest the 20% and 25% tax-direction shave variants with the same settings and current self-correlation.
- Compare against a static 70/30 tax/GARP blend to isolate whether dynamic weighting adds value.
- Keep the variant only if it clears self-correlation without sacrificing sub-universe Sharpe.

## Sources

- Candidate files: `/Users/nuthdanai/Desktop/alpha-mixing-research/temp_submit_runs/mixed_alpha_candidates/single_thematic_mix_txws_garp_dynamic_soft_20260621.csv`, `/Users/nuthdanai/Desktop/alpha-mixing-research/temp_submit_runs/mixed_alpha_candidates/single_thematic_mix_txws_garp_dynamic_mid_20260621.csv`, and related `single_thematic_mix_txws_garp_dynamic_*` variants.
