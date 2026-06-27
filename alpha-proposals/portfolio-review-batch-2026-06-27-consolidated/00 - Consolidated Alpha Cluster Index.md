---
title: Consolidated Alpha Cluster Index - Portfolio Review 2026-06-27
type: alpha-cluster-index
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
source_count: 517
cluster_count: 12
singleton_count: 30
filtered_mixed_composite_count: 397
created: 2026-06-27
updated: 2026-06-27
---

# Consolidated Alpha Cluster Index - Portfolio Review 2026-06-27

> [!abstract] Scope
> This index consolidates highly similar alphas from the 517-card proposal library. The source workbook remains canonical, and this folder is the Obsidian-facing deduplicated research view for cleaner single-mechanism alpha proposals. Multi-field composite candidates that appear to come from alpha mixing are excluded from this canonical proposal layer.

## Summary

| Dimension | Count |
| --- | ---: |
| Source proposal cards | 517 |
| Clean source rows after mixed-composite filter | 120 |
| Clean multi-member clusters | 12 |
| Rows inside clean clusters | 90 |
| Clean singleton rows kept separate | 30 |
| Mixed-composite source rows filtered out | 397 |
| Total clean review units | 42 |

## Merge Criteria

Rows were merged only when at least one conservative rule was true:

- exact expression duplicate;
- same expression after replacing numeric parameters with placeholders;
- same reader-facing base family plus high field, operator, token, and factor-family similarity;
- same base family and same field set with highly similar operator structure.
- second-pass merge when already-consolidated clusters share the same reader-facing base family and distinctive mechanism signature.

## Mixed-Composite Filter

Candidates are excluded from this canonical proposal view when the representative expression meets any of these conditions:

- more than three distinctive field labels are needed to describe the idea;
- more than eight raw data fields appear in the expression after local helper variables are ignored;
- the expression uses `alpha_mix`, `weight_raw`, `weight_strength`, or at least four `p#/alpha#` component assignments.

The filtered rows remain recoverable from the source workbook, but they are intentionally not exposed here as proposal notes because they read as composite alpha-mix artifacts rather than standalone economic hypotheses.

## Cluster Basis Coverage

| Basis | Count |
| --- | ---: |
| same-field same-operator variant | 5 |
| numeric-parameter variant | 4 |
| high-similarity field/operator/family cluster | 2 |
| exact-expression duplicate | 1 |

## Dominant Family Coverage

| Family | Counted member rows |
| --- | ---: |
| tax/accounting fundamentals | 38 |
| risk/credit/volatility | 26 |
| options/implied volatility | 26 |
| unclassified/structural | 14 |
| price-volume/liquidity/turnover | 11 |
| earnings/EPS/guidance revisions | 4 |
| execution cost | 2 |
| quality/growth/value | 2 |
| analyst/model scores | 2 |
| execution cost; threshold/no-trade region | 1 |
| trading volume alpha | 1 |
| liquidity/turnover | 1 |
| risk/volatility scaling | 1 |
| mean-variance/risk scaling | 1 |

## Consolidated Clusters

| Cluster | Members | Basis | Representative | Best Sharpe | Best Fitness |
| --- | ---: | --- | --- | ---: | ---: |
| [[001 - C001-Capital-Productivity-Momentum-Capital-Cost-Base|C001 - Capital Productivity Momentum - Capital Cost Base]] | 27 | high-similarity field/operator/family cluster | Capital Productivity Momentum | `2.03` | `2.89` |
| [[002 - C002-Fundamental-Score-Momentum-Multi-Factor-Score-Delta|C002 - Fundamental Score Momentum - Multi-Factor Score Delta]] | 14 | same-field same-operator variant | Fundamental Score Momentum | `2.33` | `4.9` |
| [[003 - C003-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew|C003 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew]] | 12 | same-field same-operator variant | Options Skew Risk Appetite Variant 113 | `2.16` | `2.33` |
| [[004 - C004-Price-Volume-Reversal-Price-Liquidity|C004 - Price Volume Reversal - Price Liquidity]] | 8 | high-similarity field/operator/family cluster | Price Volume Reversal Variant 7 | `1.75` | `2.86` |
| [[005 - C005-Options-Skew-Risk-Appetite-Put-Call-OI-60D-IV-Skew|C005 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew]] | 8 | same-field same-operator variant | Options Skew Risk Appetite | `2.69` | `3.49` |
| [[006 - C006-Options-Skew-Risk-Appetite-30D-IV-Skew|C006 - Options Skew Risk Appetite - 30D IV Skew]] | 4 | numeric-parameter variant | Options Skew Risk Appetite Variant 71 | `2.2` | `2.39` |
| [[007 - C007-EPS-Revision-Shock-EPS-Estimate|C007 - EPS Revision Shock - EPS Estimate]] | 4 | numeric-parameter variant | EPS Revision Shock Variant 135 | `2.36` | `1.59` |
| [[008 - C008-Cross-Sectional-Signal-Momentum-Tax-Working-Spread|C008 - Cross Sectional Signal Momentum - Tax Working Spread]] | 3 | exact-expression duplicate | Cross Sectional Signal Momentum Variant 5 | `2.11` | `2.84` |
| [[009 - C009-Capital-Productivity-Momentum-Capital-Cost-Base-Operating-Profit|C009 - Capital Productivity Momentum - Capital Cost Base + Operating Profit]] | 3 | numeric-parameter variant | Capital Productivity Momentum Variant 5 | `2` | `2.41` |
| [[010 - C010-Tax-Cash-Flow-Capital-Momentum-Tax-Book-Cash-Flow-Capital-Cost-Base|C010 - Tax Cash Flow Capital Momentum - Tax Book Cash Flow + Capital Cost Base]] | 3 | numeric-parameter variant | Tax Cash Flow Capital Momentum Variant 2 | `2.78` | `4.44` |
| [[011 - C011-Options-Skew-Risk-Appetite-Put-Call-OI-60D-IV-Skew-Capital-Cost-Base|C011 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew + Capital Cost Base]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 82 | `2.09` | `2.41` |
| [[012 - C012-Cross-Sectional-Signal-Momentum-F-Score-Growth|C012 - Cross Sectional Signal Momentum - F-Score Growth]] | 2 | same-field same-operator variant | Cross Sectional Signal Momentum Variant 3 | `4.97` | `1.46` |

## Singletons

- [[99 - Alpha Proposal Singletons|Alpha Proposal Singletons]]
