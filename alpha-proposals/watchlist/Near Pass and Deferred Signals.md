---
title: Near Pass and Deferred Signals
type: alpha-proposal-watchlist
project: worldquant-brain
status: active
created: 2026-06-27
updated: 2026-06-27
source_confidence: medium
tags:
  - worldquant
  - alpha-watchlist
  - near-pass
  - deferred-composite
---

# Near Pass and Deferred Signals

> [!summary] Purpose
> This note keeps useful signals that should not become standalone active proposals yet. Reasons include near-pass status, high expected self-correlation, or multi-sleeve construction that looks like alpha mixing rather than a clean economic mechanism.

## Near-Pass Signals Worth Repair

| Alpha ID | Family | Sharpe | Fitness | Failed checks | Why keep |
| --- | --- | ---: | ---: | --- | --- |
| `QPabzj8X` | Trading volume threshold | `1.38` | `0.99` | `LOW_FITNESS` | Closest near-pass; directly related to volume/turnover thesis. |
| `LLpN3rE9` | Volume-tail turnover | `1.16` | `0.92` | `LOW_SHARPE`; `LOW_FITNESS` | Positive direction with nonlinear volume-tail lineage. |
| `akdbg6ex` | Volume-regime scaling | `1.14` | `0.89` | `LOW_SHARPE`; `LOW_FITNESS` | Useful for risk-regime repair ideas. |
| `A1wNEwEQ` | Volume-width state | `1.07` | `0.82` | `LOW_SHARPE`; `LOW_FITNESS` | Positive direction, but too weak for proposal promotion. |

## Deferred Multi-Sleeve Candidates

| Alpha ID | Reason to defer |
| --- | --- |
| `GrwbXz1P` | Strong metrics, but combines macro curve, earnings yield, and turnover state. Keep as a portfolio candidate, not a clean proposal note. |
| `qMAdpkRA` | Very strong submitted metrics, but uses many sleeves: valuation, earnings yield, volume/news, forecast error, confidence, and curve. Defer until decomposed. |
| `gJ1PQNpg` | Strong submitted metrics, but mixes tax working spread, GARP, forecast confidence, and dynamic weighting. Defer as composite. |
| `leVQkljN` | Strong submitted metrics, but uses options skew, tax working spread, turnover, and dynamic weighting. Defer as composite. |

## Operating Rule

- Promote a watchlist item only if it can be expressed as one readable economic mechanism.
- Do not write long academic proposals for alpha-mix outputs with many unrelated fields.
- If a composite is important, first decompose it into source sleeves and write proposals for the economically clean sleeves.

## Sources

- Passed-alpha summary: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/06_alpha_catalog/alpha_proposals/alpha_proposal_passed_alphas_20260627.md`
- Quant Slave result note: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/07_research_papers/quant_slave_papers_v1_20260626/generated_alpha_candidates/quant_slave_paper_alpha_results_20260626.md`
- Submitted alpha export: `/Users/nuthdanai/Desktop/02_Quant_Investment/WorldQuant_Brain_AI_Alpha_Collection_2026-06-23/01_active_workspaces/Alpha_LLM_Research/generated/brain_alpha_exports/submitted_alpha_details.csv`
