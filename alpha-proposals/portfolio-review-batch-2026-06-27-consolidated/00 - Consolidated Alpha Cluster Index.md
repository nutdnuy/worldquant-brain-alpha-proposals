---
title: Consolidated Alpha Cluster Index - Portfolio Review 2026-06-27
type: alpha-cluster-index
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
source_count: 517
cluster_count: 84
singleton_count: 80
created: 2026-06-27
updated: 2026-06-27
---

# Consolidated Alpha Cluster Index - Portfolio Review 2026-06-27

> [!abstract] Scope
> This index consolidates highly similar alphas from the 517-card proposal library. The source workbook remains canonical, and this folder is the Obsidian-facing deduplicated research view so very similar variants are reviewed as one alpha family.

## Summary

| Dimension | Count |
| --- | ---: |
| Source proposal cards | 517 |
| Consolidated multi-member clusters | 84 |
| Rows inside consolidated clusters | 437 |
| Singleton rows kept separate | 80 |
| Total consolidated review units | 164 |

## Merge Criteria

Rows were merged only when at least one conservative rule was true:

- exact expression duplicate;
- same expression after replacing numeric parameters with placeholders;
- same reader-facing base family plus high field, operator, token, and factor-family similarity;
- same base family and same field set with highly similar operator structure.
- second-pass merge when already-consolidated clusters share the same reader-facing base family and distinctive mechanism signature.

## Cluster Basis Coverage

| Basis | Count |
| --- | ---: |
| same-field same-operator variant | 38 |
| exact-expression duplicate | 24 |
| high-similarity field/operator/family cluster | 18 |
| numeric-parameter variant | 4 |

## Dominant Family Coverage

| Family | Counted member rows |
| --- | ---: |
| risk/credit/volatility | 346 |
| options/implied volatility | 272 |
| tax/accounting fundamentals | 211 |
| analyst/model scores | 207 |
| quality/growth/value | 195 |
| price-volume/liquidity/turnover | 168 |
| earnings/EPS/guidance revisions | 136 |
| news/sentiment/buzz | 20 |
| unclassified/structural | 14 |
| execution cost | 2 |
| execution cost; threshold/no-trade region | 1 |
| liquidity/turnover | 1 |
| trading volume alpha | 1 |
| risk/volatility scaling | 1 |
| mean-variance/risk scaling | 1 |

## Consolidated Clusters

| Cluster | Members | Basis | Representative | Best Sharpe | Best Fitness |
| --- | ---: | --- | --- | ---: | ---: |
| [[001 - C001-Standardized-Cross-Sectional-Signal-Tax-Working-Spread-CCC-Rating-2Y-Credit-PD|C001 - Standardized Cross Sectional Signal - Tax Working Spread + CCC+ Rating + 2Y Credit PD]] | 43 | same-field same-operator variant | Standardized Cross Sectional Signal | `2.31` | `3.16` |
| [[002 - C002-Options-Skew-Risk-Appetite-Put-Call-OI-60D-IV-Skew-Tax-Working-Spread|C002 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew + Tax Working Spread]] | 27 | high-similarity field/operator/family cluster | Options Skew Risk Appetite Variant 2 | `2.84` | `3.24` |
| [[003 - C003-Capital-Productivity-Momentum-Capital-Cost-Base|C003 - Capital Productivity Momentum - Capital Cost Base]] | 27 | high-similarity field/operator/family cluster | Capital Productivity Momentum | `2.03` | `2.89` |
| [[004 - C004-EPS-Revision-Shock-GARP-Analyst-Value-FCF-Estimate-Tax-Working-Spread|C004 - EPS Revision Shock - GARP Analyst Value + FCF Estimate + Tax Working Spread]] | 20 | high-similarity field/operator/family cluster | EPS Revision Shock | `2.76` | `3.53` |
| [[005 - C005-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew-Receivables-Change-Historical-Growth-Non-IG-Probability|C005 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Receivables Change + Historical Growth + Non-IG Probability]] | 16 | high-similarity field/operator/family cluster | Options Skew Risk Appetite Variant 24 | `2.59` | `2.59` |
| [[006 - C006-EPS-Revision-Shock-FY1-EPS-Skew-Earnings-Quality-Dividend-Model-Value-Analyst-EP-FCFE-Growth|C006 - EPS Revision Shock - FY1 EPS Skew + Earnings Quality + Dividend Model + Value Analyst EP + FCFE Growth]] | 14 | same-field same-operator variant | EPS Revision Shock Variant 111 | `2.13` | `2.01` |
| [[007 - C007-Fundamental-Score-Momentum-Multi-Factor-Score-Delta|C007 - Fundamental Score Momentum - Multi-Factor Score Delta]] | 14 | same-field same-operator variant | Fundamental Score Momentum | `2.33` | `4.9` |
| [[008 - C008-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew|C008 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew]] | 12 | same-field same-operator variant | Options Skew Risk Appetite Variant 113 | `2.16` | `2.33` |
| [[009 - C009-EPS-Revision-Shock-Earnings-Quality-Analyst-Margin-Sales-Receivables-Change-Historical-Growth-Non-IG-Probability|C009 - EPS Revision Shock - Earnings Quality + Analyst Margin Sales + Receivables Change + Historical Growth + Non-IG Probability]] | 11 | same-field same-operator variant | EPS Revision Shock Variant 28 | `2.48` | `2.25` |
| [[010 - C010-Options-Skew-Risk-Appetite-Put-Call-OI-60D-IV-Skew|C010 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew]] | 10 | high-similarity field/operator/family cluster | Options Skew Risk Appetite | `2.69` | `3.49` |
| [[011 - C011-Price-Volume-Reversal-Price-Liquidity|C011 - Price Volume Reversal - Price Liquidity]] | 8 | high-similarity field/operator/family cluster | Price Volume Reversal Variant 7 | `1.75` | `2.86` |
| [[012 - C012-EPS-Revision-Shock-Value-Analyst-EP-FCFE-Growth-BB-Rating-10Y-Credit-PD|C012 - EPS Revision Shock - Value Analyst EP + FCFE Growth + BB+ Rating + 10Y Credit PD]] | 8 | same-field same-operator variant | EPS Revision Shock Variant 89 | `1.98` | `2.3` |
| [[013 - C013-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew-Receivables-Change-Historical-Growth-Analyst-Basic-Estimate|C013 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Receivables Change + Historical Growth + Analyst Basic Estimate]] | 7 | same-field same-operator variant | Options Skew Risk Appetite Variant 78 | `2.3` | `2.15` |
| [[014 - C014-EPS-Revision-Shock-EPS-Estimate-R-D-Expense-Tax-Working-Spread-4Y-Credit-PD-A-Rating|C014 - EPS Revision Shock - EPS Estimate + R&D Expense + Tax Working Spread + 4Y Credit PD + A+ Rating]] | 6 | same-field same-operator variant | EPS Revision Shock Variant 15 | `2.34` | `2.9` |
| [[015 - C015-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew-Receivables-Change-A-Rating-7Y-Credit-PD|C015 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Receivables Change + A- Rating + 7Y Credit PD]] | 6 | high-similarity field/operator/family cluster | Options Skew Risk Appetite Variant 41 | `2.19` | `2.91` |
| [[016 - C016-EPS-Revision-Shock-Reported-EPS-Value-Analyst-EP-FCFE-Growth-BB-Rating-3Y-Credit-PD|C016 - EPS Revision Shock - Reported EPS + Value Analyst EP + FCFE Growth + BB+ Rating + 3Y Credit PD]] | 6 | high-similarity field/operator/family cluster | EPS Revision Shock Variant 31 | `2.35` | `2.5` |
| [[017 - C017-EPS-Revision-Shock-EPS-Estimate-Value-Analyst-EP-FCFE-Growth-R-D-Expense-10Y-Credit-PD|C017 - EPS Revision Shock - EPS Estimate + Value Analyst EP + FCFE Growth + R&D Expense + 10Y Credit PD]] | 6 | high-similarity field/operator/family cluster | EPS Revision Shock Variant 62 | `2.16` | `2.25` |
| [[018 - C018-EPS-Revision-Shock-EPS-Estimate-Value-Analyst-EP-FCFE-Growth-R-D-Expense-BBB-Rating|C018 - EPS Revision Shock - EPS Estimate + Value Analyst EP + FCFE Growth + R&D Expense + BBB+ Rating]] | 6 | high-similarity field/operator/family cluster | EPS Revision Shock Variant 129 | `2.06` | `2` |
| [[019 - C019-EPS-Revision-Shock-FY1-EPS-Skew-Value-Analyst-EP-FCFE-Growth-Growth-Signal-AAA-Rating|C019 - EPS Revision Shock - FY1 EPS Skew + Value Analyst EP + FCFE Growth + Growth Signal + AAA Rating]] | 6 | same-field same-operator variant | EPS Revision Shock Variant 138 | `2.02` | `1.98` |
| [[020 - C020-EPS-Revision-Shock-Value-Analyst-EP-FCFE-Growth-Receivables-Change-A-Rating-7Y-Credit-PD|C020 - EPS Revision Shock - Value Analyst EP + FCFE Growth + Receivables Change + A- Rating + 7Y Credit PD]] | 6 | high-similarity field/operator/family cluster | EPS Revision Shock Variant 142 | `1.96` | `2.05` |
| [[021 - C021-EPS-Revision-Shock-Value-Analyst-EP-FCFE-Growth-A-Rating-7Y-Credit-PD|C021 - EPS Revision Shock - Value Analyst EP + FCFE Growth + A- Rating + 7Y Credit PD]] | 6 | high-similarity field/operator/family cluster | EPS Revision Shock Variant 156 | `1.89` | `2.08` |
| [[022 - C022-Options-Skew-Risk-Appetite-Put-Call-OI-60D-IV-Skew-270D-IV-Skew-Non-IG-Probability|C022 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew + 270D IV Skew + Non-IG Probability]] | 5 | same-field same-operator variant | Options Skew Risk Appetite Variant 6 | `2.59` | `3.07` |
| [[023 - C023-Options-Skew-Risk-Appetite-Put-Call-OI-60D-IV-Skew-Asset-Liquidity-Risk|C023 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew + Asset Liquidity Risk]] | 5 | same-field same-operator variant | Options Skew Risk Appetite Variant 15 | `2.52` | `2.91` |
| [[024 - C024-EPS-Revision-Shock-GARP-Analyst-Value-Credit-Curve|C024 - EPS Revision Shock - GARP Analyst Value + Credit Curve]] | 5 | high-similarity field/operator/family cluster | EPS Revision Shock Variant 52 | `2.27` | `2.16` |
| [[025 - C025-EPS-Revision-Shock-Analyst-Basic-Estimate-Value-Analyst-EP-FCFE-Growth-Liquidity-Event-CCC-Rating|C025 - EPS Revision Shock - Analyst Basic Estimate + Value Analyst EP + FCFE Growth + Liquidity Event + CCC+ Rating]] | 5 | same-field same-operator variant | EPS Revision Shock Variant 103 | `1.69` | `2.61` |
| [[026 - C026-EPS-Revision-Shock-EPS-Estimate-Earnings-Quality-Analyst-Margin-Sales-R-D-Expense-Tax-Working-Spread|C026 - EPS Revision Shock - EPS Estimate + Earnings Quality + Analyst Margin Sales + R&D Expense + Tax Working Spread]] | 4 | same-field same-operator variant | EPS Revision Shock Variant 6 | `2.72` | `2.94` |
| [[027 - C027-Price-Volume-Momentum-Price-Liquidity-News-Signal-A-Rating-7Y-Credit-PD|C027 - Price Volume Momentum - Price Liquidity + News Signal + A- Rating + 7Y Credit PD]] | 4 | high-similarity field/operator/family cluster | Price Volume Momentum | `2.21` | `2.82` |
| [[028 - C028-EPS-Revision-Shock-EPS-Estimate-R-D-Expense-Tax-Working-Spread-Non-IG-Probability-Put-Call-OI|C028 - EPS Revision Shock - EPS Estimate + R&D Expense + Tax Working Spread + Non-IG Probability + Put-Call OI]] | 4 | same-field same-operator variant | EPS Revision Shock Variant 26 | `2.35` | `2.52` |
| [[029 - C029-Options-Skew-Risk-Appetite-30D-IV-Skew|C029 - Options Skew Risk Appetite - 30D IV Skew]] | 4 | numeric-parameter variant | Options Skew Risk Appetite Variant 71 | `2.2` | `2.39` |
| [[030 - C030-EPS-Revision-Shock-Earnings-Quality-Analyst-Margin-Sales-Tax-Working-Spread-6M-Credit-PD-A-Rating|C030 - EPS Revision Shock - Earnings Quality + Analyst Margin Sales + Tax Working Spread + 6M Credit PD + A- Rating]] | 4 | same-field same-operator variant | EPS Revision Shock Variant 49 | `2.06` | `2.42` |
| [[031 - C031-EPS-Revision-Shock-Earnings-Quality-Analyst-Margin-Sales-OCF-Growth-4Y-Credit-PD-A-Rating|C031 - EPS Revision Shock - Earnings Quality + Analyst Margin Sales + OCF Growth + 4Y Credit PD + A+ Rating]] | 4 | same-field same-operator variant | EPS Revision Shock Variant 53 | `2.16` | `2.27` |
| [[032 - C032-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew-Tax-Working-Spread-6M-Credit-PD-A-Rating|C032 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Tax Working Spread + 6M Credit PD + A- Rating]] | 4 | same-field same-operator variant | Options Skew Risk Appetite Variant 99 | `2.05` | `2.4` |
| [[033 - C033-EPS-Revision-Shock-Value-Analyst-EP-FCFE-Growth-Corporate-Action-Event-7Y-Credit-PD-AAA-Rating|C033 - EPS Revision Shock - Value Analyst EP + FCFE Growth + Corporate Action Event + 7Y Credit PD + AAA Rating]] | 4 | same-field same-operator variant | EPS Revision Shock Variant 65 | `2.13` | `2.29` |
| [[034 - C034-EPS-Revision-Shock-EPS-Estimate|C034 - EPS Revision Shock - EPS Estimate]] | 4 | numeric-parameter variant | EPS Revision Shock Variant 135 | `2.36` | `1.59` |
| [[035 - C035-EPS-Revision-Shock-EPS-Estimate-Value-Analyst-EP-FCFE-Growth-R-D-Expense-6M-Credit-PD|C035 - EPS Revision Shock - EPS Estimate + Value Analyst EP + FCFE Growth + R&D Expense + 6M Credit PD]] | 4 | same-field same-operator variant | EPS Revision Shock Variant 152 | `1.88` | `2.1` |
| [[036 - C036-EPS-Revision-Shock-Value-Analyst-EP-FCFE-Growth-Corporate-Action-Event-10Y-Credit-PD-BBB-Rating|C036 - EPS Revision Shock - Value Analyst EP + FCFE Growth + Corporate Action Event + 10Y Credit PD + BBB+ Rating]] | 4 | high-similarity field/operator/family cluster | EPS Revision Shock Variant 171 | `1.84` | `2.08` |
| [[037 - C037-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew-Receivables-Change-10Y-Credit-PD-A-Rating|C037 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Receivables Change + 10Y Credit PD + A Rating]] | 3 | same-field same-operator variant | Options Skew Risk Appetite Variant 48 | `2.14` | `2.82` |
| [[038 - C038-Price-Volume-Momentum-Price-Liquidity-News-Signal-BB-Rating-3Y-Credit-PD|C038 - Price Volume Momentum - Price Liquidity + News Signal + BB+ Rating + 3Y Credit PD]] | 3 | high-similarity field/operator/family cluster | Price Volume Momentum Variant 3 | `2.18` | `2.6` |
| [[039 - C039-Cross-Sectional-Signal-Momentum-Tax-Working-Spread|C039 - Cross Sectional Signal Momentum - Tax Working Spread]] | 3 | exact-expression duplicate | Cross Sectional Signal Momentum Variant 5 | `2.11` | `2.84` |
| [[040 - C040-EPS-Revision-Shock-EPS-Estimate-R-D-Expense-A-Rating-7Y-Credit-PD-Non-IG-Probability|C040 - EPS Revision Shock - EPS Estimate + R&D Expense + A- Rating + 7Y Credit PD + Non-IG Probability]] | 3 | same-field same-operator variant | EPS Revision Shock Variant 69 | `1.99` | `2.45` |
| [[041 - C041-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew-Corporate-Action-Event-A-Rating-7Y-Credit-PD|C041 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Corporate Action Event + A- Rating + 7Y Credit PD]] | 3 | same-field same-operator variant | Options Skew Risk Appetite Variant 108 | `1.94` | `2.43` |
| [[042 - C042-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew-Analyst-Basic-Estimate-Liquidity-Event-CCC-Rating|C042 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Analyst Basic Estimate + Liquidity Event + CCC+ Rating]] | 3 | same-field same-operator variant | Options Skew Risk Appetite Variant 150 | `1.64` | `2.46` |
| [[043 - C043-Capital-Productivity-Momentum-Capital-Cost-Base-Operating-Profit|C043 - Capital Productivity Momentum - Capital Cost Base + Operating Profit]] | 3 | numeric-parameter variant | Capital Productivity Momentum Variant 5 | `2` | `2.41` |
| [[044 - C044-EPS-Revision-Shock-EPS-Estimate-R-D-Expense-CCC-Rating-2Y-Credit-PD-Non-IG-Probability|C044 - EPS Revision Shock - EPS Estimate + R&D Expense + CCC+ Rating + 2Y Credit PD + Non-IG Probability]] | 3 | same-field same-operator variant | EPS Revision Shock Variant 167 | `1.61` | `2.39` |
| [[045 - C045-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew-Earnings-Quality-Dividend-Model-CCC-Rating|C045 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Earnings Quality + Dividend Model + CCC+ Rating]] | 3 | same-field same-operator variant | Options Skew Risk Appetite Variant 157 | `1.6` | `2.4` |
| [[046 - C046-Price-Volume-Momentum-Price-Liquidity-News-Signal-6M-Credit-PD-A-Rating-Tax-Working-Spread|C046 - Price Volume Momentum - Price Liquidity + News Signal + 6M Credit PD + A- Rating + Tax Working Spread]] | 3 | high-similarity field/operator/family cluster | Price Volume Momentum Variant 17 | `1.8` | `2.06` |
| [[047 - C047-EPS-Revision-Shock-Reported-EPS-CCC-Rating-2Y-Credit-PD-Non-IG-Probability-Put-Call-OI|C047 - EPS Revision Shock - Reported EPS + CCC+ Rating + 2Y Credit PD + Non-IG Probability + Put-Call OI]] | 3 | same-field same-operator variant | EPS Revision Shock Variant 178 | `1.58` | `2.34` |
| [[048 - C048-Tax-Cash-Flow-Capital-Momentum-Tax-Book-Cash-Flow-Capital-Cost-Base|C048 - Tax Cash Flow Capital Momentum - Tax Book Cash Flow + Capital Cost Base]] | 3 | numeric-parameter variant | Tax Cash Flow Capital Momentum Variant 2 | `2.78` | `4.44` |
| [[049 - C049-Options-Skew-Risk-Appetite-Put-Call-OI-60D-IV-Skew-Asset-Span-Ratio-OCF-Growth|C049 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew + Asset Span Ratio + OCF Growth]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 7 | `2.58` | `3.05` |
| [[050 - C050-Options-Skew-Risk-Appetite-Put-Call-OI-60D-IV-Skew-AA-Rating-Credit-Curve|C050 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew + AA+ Rating + Credit Curve]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 11 | `2.55` | `2.94` |
| [[051 - C051-Cross-Sectional-Signal-Momentum-Tax-Working-Spread-60D-Idio-Risk|C051 - Cross Sectional Signal Momentum - Tax Working Spread + 60D Idio Risk]] | 2 | same-field same-operator variant | Cross Sectional Signal Momentum Variant 4 | `2.36` | `3.11` |
| [[052 - C052-Options-Skew-Risk-Appetite-Put-Call-OI-60D-IV-Skew-CCC-Rating-2Y-Credit-PD|C052 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew + CCC+ Rating + 2Y Credit PD]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 18 | `2.5` | `2.82` |
| [[053 - C053-Options-Skew-Risk-Appetite-Put-Call-OI-60D-IV-Skew-Dividend-Model-News-Volatility|C053 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew + Dividend Model + News Volatility]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 22 | `2.48` | `2.79` |
| [[054 - C054-Price-Volume-Reversal-Price-Liquidity-A-Rating-7Y-Credit-PD-FCF-Estimate-PTP-Estimate|C054 - Price Volume Reversal - Price Liquidity + A- Rating + 7Y Credit PD + FCF Estimate + PTP Estimate]] | 2 | exact-expression duplicate | Price Volume Reversal Variant 2 | `2.14` | `2.88` |
| [[055 - C055-EPS-Revision-Shock-Earnings-Quality-Analyst-Margin-Sales-Tax-Working-Spread-4Y-Credit-PD-A-Rating|C055 - EPS Revision Shock - Earnings Quality + Analyst Margin Sales + Tax Working Spread + 4Y Credit PD + A+ Rating]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 34 | `2.27` | `2.58` |
| [[056 - C056-Cross-Sectional-Signal-Momentum-Tax-Working-Spread-FCF-Estimate|C056 - Cross Sectional Signal Momentum - Tax Working Spread + FCF Estimate]] | 2 | exact-expression duplicate | Cross Sectional Signal Momentum Variant 9 | `2.09` | `2.8` |
| [[057 - C057-EPS-Revision-Shock-EPS-Estimate-R-D-Expense-Non-IG-Probability-Put-Call-OI-270D-IV-Skew|C057 - EPS Revision Shock - EPS Estimate + R&D Expense + Non-IG Probability + Put-Call OI + 270D IV Skew]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 39 | `2.26` | `2.56` |
| [[058 - C058-Options-Skew-Risk-Appetite-30D-IV-Skew-News-Signal-Capital-Cost-Base|C058 - Options Skew Risk Appetite - 30D IV Skew + News Signal + Capital Cost Base]] | 2 | exact-expression duplicate | Options Skew Risk Appetite Variant 62 | `2.26` | `2.61` |
| [[059 - C059-Price-Volume-Reversal-Price-Liquidity-Net-Debt-B-Rating-1Y-Credit-PD-Receivables-Change|C059 - Price Volume Reversal - Price Liquidity + Net Debt + B Rating + 1Y Credit PD + Receivables Change]] | 2 | same-field same-operator variant | Price Volume Reversal Variant 4 | `2.35` | `2.2` |
| [[060 - C060-Options-Skew-Risk-Appetite-Put-Call-OI-60D-IV-Skew-Capital-Cost-Base|C060 - Options Skew Risk Appetite - Put-Call OI + 60D IV Skew + Capital Cost Base]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 82 | `2.09` | `2.41` |
| [[061 - C061-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew-Non-IG-Probability-5Y-Credit-PD-10Y-Credit-PD|C061 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Non-IG Probability + 5Y Credit PD + 10Y Credit PD]] | 2 | exact-expression duplicate | Options Skew Risk Appetite Variant 83 | `2.14` | `2.34` |
| [[062 - C062-EPS-Revision-Shock-Value-Analyst-EP-FCFE-Growth-BB-Rating-3Y-Credit-PD|C062 - EPS Revision Shock - Value Analyst EP + FCFE Growth + BB Rating + 3Y Credit PD]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 68 | `2.05` | `2.37` |
| [[063 - C063-EPS-Revision-Shock-Value-Analyst-EP-FCFE-Growth-Corporate-Action-Event-10Y-Credit-PD-A-Rating|C063 - EPS Revision Shock - Value Analyst EP + FCFE Growth + Corporate Action Event + 10Y Credit PD + A Rating]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 73 | `2.11` | `2.26` |
| [[064 - C064-EPS-Revision-Shock-EPS-Estimate-Capital-Cost-Base-Operating-Profit|C064 - EPS Revision Shock - EPS Estimate + Capital Cost Base + Operating Profit]] | 2 | same-field same-operator variant | EPS Revision Shock Variant 75 | `2` | `2.39` |
| [[065 - C065-Price-Volume-Momentum-Price-Liquidity-News-Signal-10Y-Credit-PD-BBB-Rating|C065 - Price Volume Momentum - Price Liquidity + News Signal + 10Y Credit PD + BBB+ Rating]] | 2 | exact-expression duplicate | Price Volume Momentum Variant 9 | `1.91` | `2.51` |
| [[066 - C066-EPS-Revision-Shock-EPS-Estimate-Reported-EPS-Value-Analyst-EP-FCFE-Growth-R-D-Expense|C066 - EPS Revision Shock - EPS Estimate + Reported EPS + Value Analyst EP + FCFE Growth + R&D Expense]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 78 | `2.18` | `2.11` |
| [[067 - C067-EPS-Revision-Shock-Value-Analyst-EP-FCFE-Growth-Corporate-Action-Event-AAA-Rating-7Y-Credit-PD|C067 - EPS Revision Shock - Value Analyst EP + FCFE Growth + Corporate Action Event + AAA Rating + 7Y Credit PD]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 87 | `2.07` | `2.19` |
| [[068 - C068-Options-Skew-Risk-Appetite-30D-IV-Skew-Asset-Liquidity-Risk|C068 - Options Skew Risk Appetite - 30D IV Skew + Asset Liquidity Risk]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 119 | `2.18` | `2.37` |
| [[069 - C069-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew-Tax-Working-Spread-4Y-Credit-PD-A-Rating|C069 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Tax Working Spread + 4Y Credit PD + A+ Rating]] | 2 | exact-expression duplicate | Options Skew Risk Appetite Variant 122 | `2.07` | `2.13` |
| [[070 - C070-EPS-Revision-Shock-Earnings-Quality-Dividend-Model-Value-Analyst-EP-FCFE-Growth-6M-Credit-PD|C070 - EPS Revision Shock - Earnings Quality + Dividend Model + Value Analyst EP + FCFE Growth + 6M Credit PD]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 100 | `2.03` | `2.18` |
| [[071 - C071-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew-Corporate-Action-Event-10Y-Credit-PD-A-Rating|C071 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Corporate Action Event + 10Y Credit PD + A Rating]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 126 | `1.9` | `2.35` |
| [[072 - C072-Price-Volume-Momentum-Price-Liquidity-News-Signal-4Y-Credit-PD-A-Rating|C072 - Price Volume Momentum - Price Liquidity + News Signal + 4Y Credit PD + A+ Rating]] | 2 | high-similarity field/operator/family cluster | Price Volume Momentum Variant 10 | `2.08` | `2.1` |
| [[073 - C073-EPS-Revision-Shock-Earnings-Quality-Analyst-Margin-Sales-OCF-Growth-Credit-Curve-Asset-Span-Ratio|C073 - EPS Revision Shock - Earnings Quality + Analyst Margin Sales + OCF Growth + Credit Curve + Asset Span Ratio]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 121 | `2.09` | `2.02` |
| [[074 - C074-EPS-Revision-Shock-Value-Analyst-EP-FCFE-Growth-Corporate-Action-Event-A-Rating-5Y-Credit-PD|C074 - EPS Revision Shock - Value Analyst EP + FCFE Growth + Corporate Action Event + A- Rating + 5Y Credit PD]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 123 | `2.02` | `2.11` |
| [[075 - C075-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew-Receivables-Change-10Y-Credit-PD-BBB-Rating|C075 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Receivables Change + 10Y Credit PD + BBB+ Rating]] | 2 | exact-expression duplicate | Options Skew Risk Appetite Variant 137 | `1.93` | `2.21` |
| [[076 - C076-EPS-Revision-Shock-FY1-EPS-Skew-Value-Analyst-EP-FCFE-Growth-Growth-Signal-4Y-Credit-PD|C076 - EPS Revision Shock - FY1 EPS Skew + Value Analyst EP + FCFE Growth + Growth Signal + 4Y Credit PD]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 149 | `2.07` | `1.85` |
| [[077 - C077-Price-Volume-Momentum-Price-Liquidity-News-Signal-AA-Rating-Credit-Curve|C077 - Price Volume Momentum - Price Liquidity + News Signal + AA+ Rating + Credit Curve]] | 2 | exact-expression duplicate | Price Volume Momentum Variant 12 | `2` | `1.94` |
| [[078 - C078-Price-Volume-Reversal-Price-Liquidity-10Y-Credit-PD-A-Rating|C078 - Price Volume Reversal - Price Liquidity + 10Y Credit PD + A Rating]] | 2 | exact-expression duplicate | Price Volume Reversal Variant 9 | `1.9` | `2` |
| [[079 - C079-EPS-Revision-Shock-Value-Analyst-EP-FCFE-Growth-Receivables-Change-10Y-Credit-PD-A-Rating|C079 - EPS Revision Shock - Value Analyst EP + FCFE Growth + Receivables Change + 10Y Credit PD + A Rating]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 172 | `1.9` | `1.97` |
| [[080 - C080-Price-Volume-Momentum-Price-Liquidity-6M-Credit-PD-A-Rating-Tax-Working-Spread-60D-Idio-Risk|C080 - Price Volume Momentum - Price Liquidity + 6M Credit PD + A- Rating + Tax Working Spread + 60D Idio Risk]] | 2 | same-field same-operator variant | Price Volume Momentum Variant 15 | `1.8` | `2.08` |
| [[081 - C081-EPS-Revision-Shock-Earnings-Quality-Analyst-Margin-Sales-Tax-Working-Spread-BB-Rating-3Y-Credit-PD|C081 - EPS Revision Shock - Earnings Quality + Analyst Margin Sales + Tax Working Spread + BB+ Rating + 3Y Credit PD]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 76 | `2.34` | `2.59` |
| [[082 - C082-EPS-Revision-Shock-Earnings-Quality-Analyst-Margin-Sales-OCF-Growth-BB-Rating-3Y-Credit-PD|C082 - EPS Revision Shock - Earnings Quality + Analyst Margin Sales + OCF Growth + BB+ Rating + 3Y Credit PD]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 98 | `2.32` | `2.46` |
| [[083 - C083-Options-Skew-Risk-Appetite-Put-Call-OI-270D-IV-Skew-Tax-Working-Spread-BB-Rating-3Y-Credit-PD|C083 - Options Skew Risk Appetite - Put-Call OI + 270D IV Skew + Tax Working Spread + BB+ Rating + 3Y Credit PD]] | 2 | exact-expression duplicate | Options Skew Risk Appetite Variant 131 | `2.26` | `2.49` |
| [[084 - C084-Cross-Sectional-Signal-Momentum-F-Score-Growth|C084 - Cross Sectional Signal Momentum - F-Score Growth]] | 2 | same-field same-operator variant | Cross Sectional Signal Momentum Variant 3 | `4.97` | `1.46` |

## Singletons

- [[99 - Alpha Proposal Singletons|Alpha Proposal Singletons]]
