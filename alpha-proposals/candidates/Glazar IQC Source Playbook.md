---
title: Glazar IQC Source Playbook Alpha Proposal
type: alpha-proposal
project: worldquant-brain
alpha_name: Glazar IQC Source Playbook
alpha_ids: []
status: external-source-intake-not-simulated
created: 2026-06-29
updated: 2026-06-29
source_confidence: medium
tags:
  - worldquant
  - alpha-proposal
  - external-source
  - price-volume
  - fundamentals
  - news-sentiment
  - iqc
---

# Glazar IQC Source Playbook Alpha Proposal

> [!abstract] Research Thesis
> James Glazar's public WorldQuant IQC project page and linked notes are useful as an external source pack for BRAIN idea generation. The source points toward reusable mechanisms across volatility-gated price reversion, competitor-relative returns, social/news vector smoothing, and simple fundamental value/efficiency factors. This note is a source-intake proposal only; no local BRAIN simulation was run for these candidates.

## Snapshot

| Dimension | Description |
| --- | --- |
| Source | James Glazar WorldQuant project page plus linked notes |
| Local status | External source ingested; not locally simulated |
| Core source mechanisms | Price-volume reversion, high-volatility trade gating, social/news activity, simple fundamental value and efficiency |
| Confirmed current fields | `rel_ret_comp`, `scl12_alltype_buzzvec`, `nws12_afterhsz_sl`, `snt_buzz_ret`, `retained_earnings`, `ebit`, `capex`, `enterprise_value`, `ebitda` |
| Fields needing remap | Legacy/model names such as `fam_est_eps_rank`, `mdf_eg3`, `mdf_sg3`, `mdf_rds`, `mdf_oey`, `mdf_nps`, `mdf_gry` |
| Status | Research queue candidate, not hard pass |
| Main risk | Formula copying, stale field names, high turnover, price-reversion self-correlation |

## Fact From Source

- The main page describes a WorldQuant IQC project and links to seminar notes, alpha idea notes, and submitted-alpha examples.
- The linked notes emphasize BRAIN settings such as region, universe, decay, delay, truncation, and neutralization, plus metrics such as Sharpe, turnover, fitness, returns, drawdown, and margin.
- The notes repeatedly point to price-volume ideas, high-volatility gating, vector aggregation for news/social data, and simple fundamental ratios.
- The source-reported performance numbers are external examples. They are not local simulation results and should not enter the passed-alpha pool without rerunning under the current BRAIN account, current field catalog, and current competition settings.

## Assumptions

- The source mechanisms are more valuable than the literal formulas because several field names in the old examples are not available in the current USA TOP3000 Delay 1 catalog.
- Candidate variants should start from current confirmed fields, then use legacy/model fields only after explicit field remapping.
- Existing local candidates already cover parts of this territory, so correlation review matters more than producing more superficially different price-volume formulas.

## Interpretation

This source is best treated as a compact IQC practitioner playbook rather than a primary academic paper. It reinforces four useful local research directions:

1. Price-volume reversal should be gated by volatility or smoothed with decay to avoid high-turnover noise.
2. Relative company return fields can create a peer/competitor residual signal that differs from raw return reversal.
3. News and social vector fields need aggregation first, then smoothing or gating to control turnover.
4. Simple fundamental value/efficiency ratios can remain useful if the sign, neutralization group, and sparse-data handling are validated.

## Candidate Queue

> [!warning] Generated variants
> These are local candidate sketches derived from the source mechanisms, not accepted alphas. Static validation, BRAIN simulation, and self-correlation review are still required.

### GLAZAR-IQC-001 - Volatility-Gated Return Reversion

```text
base = -ts_regression(returns, ts_delay(returns, 1), 252, 0, 0);
gate = ts_rank(ts_std_dev(returns, 22), 252) > 0.55;
trade_when(gate, rank(base), -1)
```

- Test settings: USA TOP3000, Delay 1, decay 3/5/10, truncation 0.01-0.05.
- Compare against: `Price Volume Reversal Pressure`.
- Kill criteria: `REVERSION_COMPONENT`, high turnover after costs, or high correlation to existing price-volume alphas.

### GLAZAR-IQC-002 - Competitor Relative Return Residual

```text
peer = winsorize(ts_backfill(rel_ret_comp, 20), std=4);
stock = winsorize(returns, std=4);
group_rank(ts_zscore(peer - stock, 20), subindustry)
```

- Test settings: USA TOP3000, Delay 1, market vs subindustry neutralization.
- Compare against: price-volume and peer-relative families.
- Kill criteria: signal collapses after industry/subindustry neutralization or behaves like raw market reversal.

### GLAZAR-IQC-003 - Social Buzz Activity Reversion

```text
buzz = ts_backfill(vec_sum(scl12_alltype_buzzvec), 20);
group_rank(-ts_av_diff(buzz, 60), subindustry)
```

- Test settings: USA TOP3000, Delay 1, decay 5/10/15, truncation 0.05-0.10.
- Compare against: `News Inefficiency Underreaction`.
- Kill criteria: high turnover, sparse vector coverage, or concentrated weights.

### GLAZAR-IQC-004 - News After-Hours Pressure

```text
news = ts_sum(vec_avg(nws12_afterhsz_sl), 60);
price = -ts_delta(close, 2);
trade_when(rank(news) > 0.50, rank(price), -1)
```

- Test settings: USA TOP3000, Delay 1 first; Delay 0 only if explicitly needed later.
- Compare against: existing pure-news proxy candidates.
- Kill criteria: high turnover, D0 dependency, or weak train/test stability.

### GLAZAR-IQC-005 - Fundamental Efficiency Value

```text
eff = winsorize(ebit / capex, std=4);
group_rank(-ts_zscore(eff, 252), industry)
```

- Test settings: USA TOP1000/TOP3000, Delay 1, industry/subindustry neutralization, decay 5/10.
- Compare against: `Cost Intensity Efficiency` and `Capital Productivity Momentum`.
- Kill criteria: sparse `capex`, sign instability, or redundancy with existing cost/capital families.

### GLAZAR-IQC-006 - Enterprise Value Stress

```text
value_stress = ts_zscore(enterprise_value / ebitda, 63);
group_rank(-value_stress, industry)
```

- Test settings: USA TOP3000, Delay 1, decay 5/10, truncation 0.01.
- Compare against: value, profitability, and capital-productivity families.
- Kill criteria: denominator instability, low sub-universe Sharpe, or hidden size/sector exposure.

## Validation Plan

1. Run static field/operator validation for the six candidate sketches.
2. Create a small simulation batch only after removing or remapping unavailable legacy/model fields.
3. Start with USA TOP3000 Delay 1; do not use Delay 0 unless the source timing truly requires same-day processing.
4. Record Sharpe, Fitness, Turnover, Returns, Drawdown, Margin, failed checks, pending checks, and alpha IDs.
5. Compare correlation against existing `Price Volume Reversal Pressure`, `News Inefficiency Underreaction`, `Cost Intensity Efficiency`, and `Capital Productivity Momentum`.
6. Promote only candidates with empty hard-check failures and useful incremental mechanism diversity.

## Failure Criteria

Demote this source pack if the viable ideas are either unknown-field artifacts, raw price-reversion clones, high-turnover signals that fail cost realism, or high-correlation variants of existing submitted/candidate families.

## Decision

Add to the candidate proposal library as an external source-intake queue. Prioritize a controlled six-candidate validation batch only after current hard-pass candidates have been reviewed for self-correlation and submission priority.

## Sources

- Main project page: https://jglazar.github.io/projects/wq_project/
- Seminar notes: https://github.com/jglazar/notes/blob/main/quant_interview/worldquant_seminar.md
- Alpha idea notes: https://github.com/jglazar/notes/blob/main/quant_interview/alpha_ideas.md
- Submitted alpha notes: https://github.com/jglazar/notes/blob/main/quant_interview/submitted_alphas.md
