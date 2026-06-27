---
title: Forecast Error Underreaction Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: Forecast Error Underreaction
alpha_ids:
  - 78wQj2lZ
  - wpR1jYJ5
status: submitted-active-os-pending
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium-high
tags:
  - worldquant
  - alpha-proposal
  - earnings-forecast
  - analyst-expectations
---

# Forecast Error Underreaction Alpha Proposal

> [!abstract] Research Thesis
> **Forecast Error Underreaction** ranks firms by the smoothed difference between forecasted and realized earnings-effect fields. The thesis is that analyst forecast error and earnings-effect revisions may be incorporated slowly, creating a medium-horizon information-drift signal.

## Snapshot

| Dimension | Description |
| --- | --- |
| Alpha IDs | `78wQj2lZ`, `wpR1jYJ5` |
| Core variable | `vec_avg(ern4_fcsterneffct) - vec_avg(ern4_erneffct1)` |
| Smoothing windows | `63` and `126` |
| Peer control | `industry` group rank |
| Status | Submitted-active, OS pending in local export |
| Main risk | Overlap with earnings-surprise and analyst-revision alphas |

## Formulas

```text
forecast_error = vec_avg(ern4_fcsterneffct) - vec_avg(ern4_erneffct1);
group_rank(ts_mean(forecast_error, 126), industry)
```

```text
forecast_error = vec_avg(ern4_fcsterneffct) - vec_avg(ern4_erneffct1);
group_rank(ts_mean(forecast_error, 63), industry)
```

## Economic Rationale

Forecast errors are a direct window into expectation revision. If analysts or investors underreact to the gap between expected and realized earnings effects, the error can carry information beyond the announcement date. The use of industry ranking controls for structural differences in earnings cyclicality and reporting behavior.

The 126-day version is slower and cleaner; the 63-day version is more responsive. They should be treated as sibling variants rather than separate theses.

## Empirical Record

| Alpha | Window | Sharpe | Fitness | Turnover | Returns | Drawdown |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| `78wQj2lZ` | `126` | `1.87` | `1.31` | `2.32%` | `6.18%` | `3.87%` |
| `wpR1jYJ5` | `63` | `1.70` | `1.10` | `2.96%` | `5.27%` | `3.46%` |

## Validation Plan

- Confirm data timing for forecast and realized earnings-effect fields.
- Compare 63-, 126-, and 189-day smoothing windows.
- Check self-correlation against SUE, earnings revision, and forecast-confidence alphas.
- Review whether the signal is concentrated around earnings season.

## Failure Criteria

Reject if timing review suggests leakage, if performance is just earnings-announcement drift already captured elsewhere, or if self-correlation against submitted earnings alphas is too high.

## Decision

Keep **Forecast Error Underreaction** as a clean earnings-information proposal. It should be reviewed together with **Earnings Surprise Delta** for correlation, not treated as fully independent.

## Sources

- Submitted alpha export: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/01_active_workspaces/Alpha_LLM_Research/generated/brain_alpha_exports/submitted_alpha_details.csv`
- Project memory: `/Users/nuthdanai/Documents/Obsidian Vault/01 Projects/Quant/worldquant-brain/_PROJECT.md`
