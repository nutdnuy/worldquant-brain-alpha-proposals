---
title: Cost Intensity Efficiency Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: Cost Intensity Efficiency
alpha_ids:
  - 0m79mj6q
  - wpzQPApx
status: submitted-active-os-pending
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium
tags:
  - worldquant
  - alpha-proposal
  - cost-efficiency
  - accounting-quality
---

# Cost Intensity Efficiency Alpha Proposal

> [!abstract] Research Thesis
> **Cost Intensity Efficiency** uses cost of goods sold relative to capital as a measure of operating cost intensity. The thesis is that firms with extreme cost intensity, especially after accounting for operating profit, may reflect structural inefficiency or margin pressure that the market prices slowly.

## Snapshot

| Dimension | Description |
| --- | --- |
| Alpha IDs | `0m79mj6q`, `wpzQPApx` |
| Core variable | `cogs / cap` |
| Supporting field | `fnd6_fopo / cap` in the refined variant |
| Trading style | Sparse accounting-quality signal |
| Status | Submitted-active, OS pending in local export |
| Main risk | Sector accounting differences and capital-base denominator risk |

## Formulas

### Refined Cost-Profit Variant: `0m79mj6q`

```text
cost = zscore(winsorize(cogs/cap, std=4));
op = zscore(fnd6_fopo/cap);
c = ts_mean(cost - 0.25 * op, 2);
g = trade_when(rank(abs(c)) > 0.88, c, 0);
group_neutralize(rank(c) * g, industry)
```

### Raw Cost-Intensity Variant: `wpzQPApx`

```text
c0 = zscore(cogs/cap);
c = ts_mean(c0, 3);
g = trade_when(rank(abs(c)) > 0.85, c, 0);
0.35 * g + 0.65 * rank(c)
```

## Economic Rationale

Cost intensity can proxy production efficiency, margin pressure, and capital productivity. High cost relative to capital may indicate weak operating leverage or poor cost discipline. The refined variant offsets part of the raw cost signal with an operating-profit proxy so the alpha is less likely to punish high-cost firms that also earn adequate profit.

The sparse gate is important because accounting ratios are noisy. The proposal is strongest when it focuses on clear cost-intensity tails rather than treating small accounting differences as tradable information.

## Empirical Record

| Alpha | Variant | Sharpe | Fitness | Turnover | Returns | Drawdown |
| --- | --- | ---: | ---: | ---: | ---: | ---: |
| `0m79mj6q` | Cost minus profit adjustment | `2.01` | `2.44` | `3.17%` | `18.39%` | `9.42%` |
| `wpzQPApx` | Raw cost-intensity tail | `2.00` | `2.85` | `2.92%` | `25.45%` | `13.35%` |

## Validation Plan

- Check whether the alpha is dominated by sector accounting structure.
- Test industry and subindustry neutralization variants.
- Confirm that `cogs`, `cap`, and `fnd6_fopo` are point-in-time.
- Review denominator outliers and firms with unusual capital definitions.

## Failure Criteria

Demote if performance disappears after tighter peer neutralization, if results depend on a few industries, or if the signal is mainly a low-quality distress factor.

## Decision

Keep as a strong submitted fundamental proposal family. It is economically readable, low-turnover, and less mixed than the large multi-sleeve composites.

## Sources

- Submitted alpha export: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/01_active_workspaces/Alpha_LLM_Research/generated/brain_alpha_exports/submitted_alpha_details.csv`
- Project memory: `/Users/nuthdanai/Documents/Obsidian Vault/01 Projects/Quant/worldquant-brain/_PROJECT.md`
