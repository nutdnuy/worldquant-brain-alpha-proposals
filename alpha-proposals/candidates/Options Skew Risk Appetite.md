---
title: Options Skew Risk Appetite Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: Options Skew Risk Appetite
alpha_ids:
  - YPWmwWwW
  - LLl6b7O6
  - 58q9RJKo
  - A1k5dzWE
status: hard-pass-family-correlation-review-required
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium-high
tags:
  - worldquant
  - alpha-proposal
  - options-skew
  - risk-appetite
---

# Options Skew Risk Appetite Alpha Proposal

> [!abstract] Research Thesis
> **Options Skew Risk Appetite** uses put-call open-interest regimes to gate implied-volatility skew signals. The thesis is that call-put implied-volatility spreads contain information about risk appetite, demand for convex exposure, and dealer positioning. When put-call open interest indicates a supportive regime, sector-normalized call-minus-put skew can carry a persistent cross-sectional signal.

## Snapshot

| Dimension | Description |
| --- | --- |
| Representative alpha IDs | `YPWmwWwW`, `LLl6b7O6`, `58q9RJKo`, `A1k5dzWE` |
| Core fields | `pcr_oi_270`, `implied_volatility_call_*`, `implied_volatility_put_*` |
| Mechanism | Regime-gated options skew |
| Source sheet | `04_alpha_pass_combined` |
| Status | Hard-pass family; correlation review required |
| Main risk | Variants are extremely correlated with each other |

## Representative Formulas

### 60-Day Skew Gate: `YPWmwWwW` / `58q9RJKo`

```text
trade_when(
  ts_mean(pcr_oi_270, 2) < 1,
  group_zscore(ts_mean((implied_volatility_call_60 - implied_volatility_put_60), 5), sector),
  -1
)
```

### Slower Gate Variant: `LLl6b7O6`

```text
trade_when(
  ts_mean(pcr_oi_270, 4) < 1.05,
  group_zscore(ts_mean((implied_volatility_call_60 - implied_volatility_put_60), 10), sector),
  -1
)
```

### 270-Day Skew With Credit Fallback: `A1k5dzWE`

```text
group_neutralize(
  trade_when(
    ts_mean(pcr_oi_270, 3) < 1,
    group_zscore(ts_mean((implied_volatility_call_270 - implied_volatility_put_270), 3), sector),
    -1 * ts_backfill(probability_non_investment_grade_rating, 120)
  ),
  sector
)
```

## Economic Rationale

Options markets can reflect investor demand for upside participation, downside hedging, and risk-transfer pressure before those forces appear in realized returns. The put-call open-interest gate acts as a market-state filter: the alpha is active when the options book suggests a specific risk-appetite regime. The cross-sectional signal then ranks the smoothed call-minus-put implied-volatility spread within sectors.

This is not a broad volatility factor. It is a conditional skew signal. The strongest variants differ mainly in smoothing, neutralization, and decay settings, so they should be treated as a single family rather than independent proposals.

## Empirical Record

| Alpha | Variant | Sharpe | Fitness | Turnover | Returns | Drawdown | Max abs corr |
| --- | --- | ---: | ---: | ---: | ---: | ---: | ---: |
| `YPWmwWwW` | 60d skew, 2-day gate | `2.69` | `3.49` | `11.45%` | `21.01%` | `8.70%` | `0.9995` |
| `LLl6b7O6` | 60d skew, slower gate | `2.44` | `3.33` | `10.46%` | `23.30%` | `12.94%` | `0.9998` |
| `58q9RJKo` | 60d skew repair | `2.42` | `2.73` | `17.61%` | `22.40%` | `9.64%` | `0.99998` |
| `A1k5dzWE` | 270d skew with credit fallback | `2.17` | `2.37` | `15.56%` | `18.60%` | `11.72%` | `0.99999` |

## Validation Plan

- Treat this as one crowded family for self-correlation review.
- Test whether the signal survives with only one representative, not many near-duplicates.
- Check turnover and option-data availability by universe.
- Verify that the credit fallback in `A1k5dzWE` is not turning the alpha into a mixed credit/options composite.

## Failure Criteria

Demote variants if self-correlation is high, if performance depends on one options tenor, or if transaction costs and options-data timing make the signal impractical.

## Decision

Keep **Options Skew Risk Appetite** as a strong but crowded candidate family. Do not promote every variant; choose one representative after correlation review.

## Sources

- Source workbook: `/Users/nuthdanai/Desktop/alpha-mixing-research/alpha_mixing_research_combined.xlsm`
- Source sheet: `04_alpha_pass_combined`
- Source files recorded in sheet: `tradewhen_iv_family_20260415_attempts.csv`, `tradewhen_iv_repair_20260415_attempts.csv`, `submittable_group1_alphas.xlsm`
