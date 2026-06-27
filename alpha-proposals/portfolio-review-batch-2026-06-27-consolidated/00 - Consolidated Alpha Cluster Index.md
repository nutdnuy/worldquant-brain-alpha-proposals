---
title: Consolidated Alpha Cluster Index - Portfolio Review 2026-06-27
type: alpha-cluster-index
project: worldquant-brain
proposal_batch: portfolio-review-2026-06-27-consolidated
source_count: 517
cluster_count: 95
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
| Consolidated multi-member clusters | 95 |
| Rows inside consolidated clusters | 437 |
| Singleton rows kept separate | 80 |
| Total consolidated review units | 175 |

## Merge Criteria

Rows were merged only when at least one conservative rule was true:

- exact expression duplicate;
- same expression after replacing numeric parameters with placeholders;
- same reader-facing base family plus high field, operator, token, and factor-family similarity;
- same base family and same field set with highly similar operator structure.

## Cluster Basis Coverage

| Basis | Count |
| --- | ---: |
| same-field same-operator variant | 47 |
| exact-expression duplicate | 28 |
| high-similarity field/operator/family cluster | 14 |
| numeric-parameter variant | 6 |

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
| [[001 - Standardized-Cross-Sectional-Signal-Cluster-001-weight-raw-probability-rating-ccc-plus|Standardized Cross Sectional Signal Cluster 001 - weight_raw probability_rating_ccc_plus]] | 43 | same-field same-operator variant | Standardized Cross Sectional Signal | `2.31` | `3.16` |
| [[002 - Capital-Productivity-Momentum-Cluster-002-cogs-c|Capital Productivity Momentum Cluster 002 - cogs c]] | 27 | high-similarity field/operator/family cluster | Capital Productivity Momentum | `2.03` | `2.89` |
| [[003 - EPS-Revision-Shock-Cluster-003-tx-conf-vector-neut|EPS Revision Shock Cluster 003 - tx_conf vector_neut]] | 20 | high-similarity field/operator/family cluster | EPS Revision Shock | `2.76` | `3.53` |
| [[004 - EPS-Revision-Shock-Cluster-004-mdl177-2-earningmomentumfactor400-fy1epssk|EPS Revision Shock Cluster 004 - mdl177_2_earningmomentumfactor400_fy1epssk]] | 14 | same-field same-operator variant | EPS Revision Shock Variant 111 | `2.13` | `2.01` |
| [[005 - Fundamental-Score-Momentum-Cluster-005-multi-factor-static-score-derivative|Fundamental Score Momentum Cluster 005 - multi_factor_static_score_derivative]] | 14 | same-field same-operator variant | Fundamental Score Momentum | `2.33` | `4.9` |
| [[006 - Options-Skew-Risk-Appetite-Cluster-006-implied-volatility-call-270-pcr-oi-270|Options Skew Risk Appetite Cluster 006 - implied_volatility_call_270 pcr_oi_270]] | 13 | same-field same-operator variant | Options Skew Risk Appetite Variant 24 | `2.59` | `2.59` |
| [[007 - Options-Skew-Risk-Appetite-Cluster-007-implied-volatility-call-270-pcr-oi-270|Options Skew Risk Appetite Cluster 007 - implied_volatility_call_270 pcr_oi_270]] | 12 | same-field same-operator variant | Options Skew Risk Appetite Variant 113 | `2.16` | `2.33` |
| [[008 - EPS-Revision-Shock-Cluster-008-implied-volatility-call-270-pcr-oi-270|EPS Revision Shock Cluster 008 - implied_volatility_call_270 pcr_oi_270]] | 11 | same-field same-operator variant | EPS Revision Shock Variant 28 | `2.48` | `2.25` |
| [[009 - Options-Skew-Risk-Appetite-Cluster-009-turn|Options Skew Risk Appetite Cluster 009 - turn]] | 10 | same-field same-operator variant | Options Skew Risk Appetite Variant 39 | `2.84` | `2.83` |
| [[010 - Options-Skew-Risk-Appetite-Cluster-010-implied-volatility-put-60-pcr-oi-270|Options Skew Risk Appetite Cluster 010 - implied_volatility_put_60 pcr_oi_270]] | 8 | same-field same-operator variant | Options Skew Risk Appetite | `2.69` | `3.49` |
| [[011 - EPS-Revision-Shock-Cluster-011-returns|EPS Revision Shock Cluster 011 - returns]] | 8 | same-field same-operator variant | EPS Revision Shock Variant 89 | `1.98` | `2.3` |
| [[012 - Options-Skew-Risk-Appetite-Cluster-012-weight-raw-pcr-oi-270|Options Skew Risk Appetite Cluster 012 - weight_raw pcr_oi_270]] | 7 | same-field same-operator variant | Options Skew Risk Appetite Variant 9 | `2.56` | `2.98` |
| [[013 - Options-Skew-Risk-Appetite-Cluster-013-implied-volatility-call-270-pcr-oi-270|Options Skew Risk Appetite Cluster 013 - implied_volatility_call_270 pcr_oi_270]] | 7 | same-field same-operator variant | Options Skew Risk Appetite Variant 78 | `2.3` | `2.15` |
| [[014 - EPS-Revision-Shock-Cluster-014-annualized-pd-4-year-jc7|EPS Revision Shock Cluster 014 - annualized_pd_4_year_jc7]] | 6 | same-field same-operator variant | EPS Revision Shock Variant 15 | `2.34` | `2.9` |
| [[015 - Options-Skew-Risk-Appetite-Cluster-015-implied-volatility-call-270|Options Skew Risk Appetite Cluster 015 - implied_volatility_call_270]] | 6 | high-similarity field/operator/family cluster | Options Skew Risk Appetite Variant 41 | `2.19` | `2.91` |
| [[016 - EPS-Revision-Shock-Cluster-016-eps-previous-estimate-value|EPS Revision Shock Cluster 016 - eps_previous_estimate_value]] | 6 | high-similarity field/operator/family cluster | EPS Revision Shock Variant 62 | `2.16` | `2.25` |
| [[017 - EPS-Revision-Shock-Cluster-017-eps-previous-estimate-value|EPS Revision Shock Cluster 017 - eps_previous_estimate_value]] | 6 | high-similarity field/operator/family cluster | EPS Revision Shock Variant 129 | `2.06` | `2` |
| [[018 - EPS-Revision-Shock-Cluster-018-mdl177-2-earningmomentumfactor400-fy1epssk|EPS Revision Shock Cluster 018 - mdl177_2_earningmomentumfactor400_fy1epssk]] | 6 | same-field same-operator variant | EPS Revision Shock Variant 138 | `2.02` | `1.98` |
| [[019 - EPS-Revision-Shock-Cluster-019-annualized-pd-7-year-jc7|EPS Revision Shock Cluster 019 - annualized_pd_7_year_jc7]] | 6 | high-similarity field/operator/family cluster | EPS Revision Shock Variant 142 | `1.96` | `2.05` |
| [[020 - EPS-Revision-Shock-Cluster-020-annualized-pd-7-year-jc7|EPS Revision Shock Cluster 020 - annualized_pd_7_year_jc7]] | 6 | high-similarity field/operator/family cluster | EPS Revision Shock Variant 156 | `1.89` | `2.08` |
| [[021 - Options-Skew-Risk-Appetite-Cluster-021-weight-raw-implied-volatility-call-270|Options Skew Risk Appetite Cluster 021 - weight_raw implied_volatility_call_270]] | 5 | same-field same-operator variant | Options Skew Risk Appetite Variant 6 | `2.59` | `3.07` |
| [[022 - Options-Skew-Risk-Appetite-Cluster-022-weight-raw-pcr-oi-270|Options Skew Risk Appetite Cluster 022 - weight_raw pcr_oi_270]] | 5 | same-field same-operator variant | Options Skew Risk Appetite Variant 15 | `2.52` | `2.91` |
| [[023 - EPS-Revision-Shock-Cluster-023-probability-rating-ccc-plus|EPS Revision Shock Cluster 023 - probability_rating_ccc_plus]] | 5 | same-field same-operator variant | EPS Revision Shock Variant 103 | `1.69` | `2.61` |
| [[024 - Options-Skew-Risk-Appetite-Cluster-024-pcr-oi-270|Options Skew Risk Appetite Cluster 024 - pcr_oi_270]] | 4 | same-field same-operator variant | Options Skew Risk Appetite Variant 2 | `2.8` | `3.24` |
| [[025 - EPS-Revision-Shock-Cluster-025-limit|EPS Revision Shock Cluster 025 - limit]] | 4 | same-field same-operator variant | EPS Revision Shock Variant 6 | `2.72` | `2.94` |
| [[026 - Price-Volume-Momentum-Cluster-026-annualized-pd-7-year-jc7|Price Volume Momentum Cluster 026 - annualized_pd_7_year_jc7]] | 4 | high-similarity field/operator/family cluster | Price Volume Momentum | `2.21` | `2.82` |
| [[027 - EPS-Revision-Shock-Cluster-027-eps-previous-estimate-value|EPS Revision Shock Cluster 027 - eps_previous_estimate_value]] | 4 | same-field same-operator variant | EPS Revision Shock Variant 26 | `2.35` | `2.52` |
| [[028 - EPS-Revision-Shock-Cluster-028-limit|EPS Revision Shock Cluster 028 - limit]] | 4 | same-field same-operator variant | EPS Revision Shock Variant 31 | `2.35` | `2.49` |
| [[029 - Options-Skew-Risk-Appetite-Cluster-029-implied-volatility-call-30-implied-volatil|Options Skew Risk Appetite Cluster 029 - implied_volatility_call_30 implied_volatil]] | 4 | numeric-parameter variant | Options Skew Risk Appetite Variant 71 | `2.2` | `2.39` |
| [[030 - Options-Skew-Risk-Appetite-Cluster-030-pcr-oi-270|Options Skew Risk Appetite Cluster 030 - pcr_oi_270]] | 4 | same-field same-operator variant | Options Skew Risk Appetite Variant 81 | `2.37` | `2.16` |
| [[031 - EPS-Revision-Shock-Cluster-031-probability-dist-a-minus-limit|EPS Revision Shock Cluster 031 - probability_dist_a_minus limit]] | 4 | same-field same-operator variant | EPS Revision Shock Variant 49 | `2.06` | `2.42` |
| [[032 - EPS-Revision-Shock-Cluster-032-annualized-pd-4-year-jc7|EPS Revision Shock Cluster 032 - annualized_pd_4_year_jc7]] | 4 | same-field same-operator variant | EPS Revision Shock Variant 53 | `2.16` | `2.27` |
| [[033 - Options-Skew-Risk-Appetite-Cluster-033-probability-dist-a-minus|Options Skew Risk Appetite Cluster 033 - probability_dist_a_minus]] | 4 | same-field same-operator variant | Options Skew Risk Appetite Variant 99 | `2.05` | `2.4` |
| [[034 - EPS-Revision-Shock-Cluster-034-limit|EPS Revision Shock Cluster 034 - limit]] | 4 | same-field same-operator variant | EPS Revision Shock Variant 65 | `2.13` | `2.29` |
| [[035 - EPS-Revision-Shock-Cluster-035-est-epsr-close|EPS Revision Shock Cluster 035 - est_epsr close]] | 4 | numeric-parameter variant | EPS Revision Shock Variant 135 | `2.36` | `1.59` |
| [[036 - EPS-Revision-Shock-Cluster-036-limit|EPS Revision Shock Cluster 036 - limit]] | 4 | high-similarity field/operator/family cluster | EPS Revision Shock Variant 171 | `1.84` | `2.08` |
| [[037 - Price-Volume-Reversal-Cluster-037-turn-volume|Price Volume Reversal Cluster 037 - turn volume]] | 4 | high-similarity field/operator/family cluster | Price Volume Reversal Variant 12 | `1.75` | `1.29` |
| [[038 - Options-Skew-Risk-Appetite-Cluster-038-implied-volatility-call-270|Options Skew Risk Appetite Cluster 038 - implied_volatility_call_270]] | 3 | same-field same-operator variant | Options Skew Risk Appetite Variant 48 | `2.14` | `2.82` |
| [[039 - Options-Skew-Risk-Appetite-Cluster-039-sign-implied-volatility-call-270|Options Skew Risk Appetite Cluster 039 - sign implied_volatility_call_270]] | 3 | same-field same-operator variant | Options Skew Risk Appetite Variant 67 | `2.43` | `2.26` |
| [[040 - Price-Volume-Momentum-Cluster-040-returns|Price Volume Momentum Cluster 040 - returns]] | 3 | high-similarity field/operator/family cluster | Price Volume Momentum Variant 3 | `2.18` | `2.6` |
| [[041 - Cross-Sectional-Signal-Momentum-Cluster-041-fnd6-txws|Cross Sectional Signal Momentum Cluster 041 - fnd6_txws]] | 3 | exact-expression duplicate | Cross Sectional Signal Momentum Variant 5 | `2.11` | `2.84` |
| [[042 - EPS-Revision-Shock-Cluster-042-ern4-erneffct1-mdl53-jc5-10year|EPS Revision Shock Cluster 042 - ern4_erneffct1 mdl53_jc5_10year]] | 3 | high-similarity field/operator/family cluster | EPS Revision Shock Variant 55 | `2.27` | `2.16` |
| [[043 - EPS-Revision-Shock-Cluster-043-probability-dist-a-minus|EPS Revision Shock Cluster 043 - probability_dist_a_minus]] | 3 | same-field same-operator variant | EPS Revision Shock Variant 69 | `1.99` | `2.45` |
| [[044 - Options-Skew-Risk-Appetite-Cluster-044-probability-dist-a-minus|Options Skew Risk Appetite Cluster 044 - probability_dist_a_minus]] | 3 | same-field same-operator variant | Options Skew Risk Appetite Variant 108 | `1.94` | `2.43` |
| [[045 - Options-Skew-Risk-Appetite-Cluster-045-probability-rating-ccc-plus|Options Skew Risk Appetite Cluster 045 - probability_rating_ccc_plus]] | 3 | same-field same-operator variant | Options Skew Risk Appetite Variant 150 | `1.64` | `2.46` |
| [[046 - Capital-Productivity-Momentum-Cluster-046-cogs-c|Capital Productivity Momentum Cluster 046 - cogs c]] | 3 | numeric-parameter variant | Capital Productivity Momentum Variant 5 | `2` | `2.41` |
| [[047 - EPS-Revision-Shock-Cluster-047-probability-rating-ccc-plus|EPS Revision Shock Cluster 047 - probability_rating_ccc_plus]] | 3 | same-field same-operator variant | EPS Revision Shock Variant 167 | `1.61` | `2.39` |
| [[048 - Options-Skew-Risk-Appetite-Cluster-048-probability-rating-ccc-plus|Options Skew Risk Appetite Cluster 048 - probability_rating_ccc_plus]] | 3 | same-field same-operator variant | Options Skew Risk Appetite Variant 157 | `1.6` | `2.4` |
| [[049 - Price-Volume-Momentum-Cluster-049-probability-dist-a-minus|Price Volume Momentum Cluster 049 - probability_dist_a_minus]] | 3 | high-similarity field/operator/family cluster | Price Volume Momentum Variant 17 | `1.8` | `2.06` |
| [[050 - EPS-Revision-Shock-Cluster-050-probability-rating-ccc-plus|EPS Revision Shock Cluster 050 - probability_rating_ccc_plus]] | 3 | same-field same-operator variant | EPS Revision Shock Variant 178 | `1.58` | `2.34` |
| [[051 - Tax-Cash-Flow-Capital-Momentum-Cluster-051-fnd6-txbcof-cap|Tax Cash Flow Capital Momentum Cluster 051 - fnd6_txbcof cap]] | 3 | numeric-parameter variant | Tax Cash Flow Capital Momentum Variant 2 | `2.78` | `4.44` |
| [[052 - Price-Volume-Reversal-Cluster-052-change-day-close|Price Volume Reversal Cluster 052 - change_day close]] | 2 | exact-expression duplicate | Price Volume Reversal Variant 7 | `1.4` | `2.86` |
| [[053 - Options-Skew-Risk-Appetite-Cluster-053-weight-raw-pcr-oi-270|Options Skew Risk Appetite Cluster 053 - weight_raw pcr_oi_270]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 5 | `2.6` | `3.07` |
| [[054 - Options-Skew-Risk-Appetite-Cluster-054-weight-raw-pcr-oi-270|Options Skew Risk Appetite Cluster 054 - weight_raw pcr_oi_270]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 7 | `2.58` | `3.05` |
| [[055 - Options-Skew-Risk-Appetite-Cluster-055-weight-raw-pcr-oi-270|Options Skew Risk Appetite Cluster 055 - weight_raw pcr_oi_270]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 11 | `2.55` | `2.94` |
| [[056 - Cross-Sectional-Signal-Momentum-Cluster-056-weight-raw-fnd6-txws|Cross Sectional Signal Momentum Cluster 056 - weight_raw fnd6_txws]] | 2 | same-field same-operator variant | Cross Sectional Signal Momentum Variant 4 | `2.36` | `3.11` |
| [[057 - Options-Skew-Risk-Appetite-Cluster-057-weight-raw-probability-rating-ccc-plus|Options Skew Risk Appetite Cluster 057 - weight_raw probability_rating_ccc_plus]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 18 | `2.5` | `2.82` |
| [[058 - Options-Skew-Risk-Appetite-Cluster-058-weight-raw-pcr-oi-270|Options Skew Risk Appetite Cluster 058 - weight_raw pcr_oi_270]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 22 | `2.48` | `2.79` |
| [[059 - Price-Volume-Reversal-Cluster-059-probability-dist-a-minus|Price Volume Reversal Cluster 059 - probability_dist_a_minus]] | 2 | exact-expression duplicate | Price Volume Reversal Variant 2 | `2.14` | `2.88` |
| [[060 - EPS-Revision-Shock-Cluster-060-annualized-pd-4-year-jc7-limit|EPS Revision Shock Cluster 060 - annualized_pd_4_year_jc7 limit]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 34 | `2.27` | `2.58` |
| [[061 - Cross-Sectional-Signal-Momentum-Cluster-061-weight-raw-fnd6-txws|Cross Sectional Signal Momentum Cluster 061 - weight_raw fnd6_txws]] | 2 | exact-expression duplicate | Cross Sectional Signal Momentum Variant 9 | `2.09` | `2.8` |
| [[062 - EPS-Revision-Shock-Cluster-062-weight-raw-implied-volatility-call-270|EPS Revision Shock Cluster 062 - weight_raw implied_volatility_call_270]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 39 | `2.26` | `2.56` |
| [[063 - Options-Skew-Risk-Appetite-Cluster-063-implied-volatility-put-30-s3-cogs-s|Options Skew Risk Appetite Cluster 063 - implied_volatility_put_30 _s3_cogs_s]] | 2 | exact-expression duplicate | Options Skew Risk Appetite Variant 62 | `2.26` | `2.61` |
| [[064 - Options-Skew-Risk-Appetite-Cluster-064-sign|Options Skew Risk Appetite Cluster 064 - sign]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 64 | `2.65` | `1.87` |
| [[065 - Price-Volume-Reversal-Cluster-065-anl4-detailrecv4-est-probability-dist-b|Price Volume Reversal Cluster 065 - anl4_detailrecv4_est probability_dist_b]] | 2 | same-field same-operator variant | Price Volume Reversal Variant 4 | `2.35` | `2.2` |
| [[066 - Options-Skew-Risk-Appetite-Cluster-066-cogs|Options Skew Risk Appetite Cluster 066 - cogs]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 82 | `2.09` | `2.41` |
| [[067 - Options-Skew-Risk-Appetite-Cluster-067-annualized-pd-4-year-jc7-weight-raw|Options Skew Risk Appetite Cluster 067 - annualized_pd_4_year_jc7 weight_raw]] | 2 | exact-expression duplicate | Options Skew Risk Appetite Variant 83 | `2.14` | `2.34` |
| [[068 - EPS-Revision-Shock-Cluster-068-ern4-erneffct1-mdl53-jc5-10year|EPS Revision Shock Cluster 068 - ern4_erneffct1 mdl53_jc5_10year]] | 2 | numeric-parameter variant | EPS Revision Shock Variant 52 | `2.26` | `2.16` |
| [[069 - EPS-Revision-Shock-Cluster-069-probability-rating-bb|EPS Revision Shock Cluster 069 - probability_rating_bb]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 68 | `2.05` | `2.37` |
| [[070 - EPS-Revision-Shock-Cluster-070-limit|EPS Revision Shock Cluster 070 - limit]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 73 | `2.11` | `2.26` |
| [[071 - EPS-Revision-Shock-Cluster-071-est-epsr-cogs|EPS Revision Shock Cluster 071 - est_epsr cogs]] | 2 | same-field same-operator variant | EPS Revision Shock Variant 75 | `2` | `2.39` |
| [[072 - Price-Volume-Momentum-Cluster-072-returns|Price Volume Momentum Cluster 072 - returns]] | 2 | exact-expression duplicate | Price Volume Momentum Variant 9 | `1.91` | `2.51` |
| [[073 - EPS-Revision-Shock-Cluster-073-limit|EPS Revision Shock Cluster 073 - limit]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 78 | `2.18` | `2.11` |
| [[074 - EPS-Revision-Shock-Cluster-074-limit|EPS Revision Shock Cluster 074 - limit]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 87 | `2.07` | `2.19` |
| [[075 - Options-Skew-Risk-Appetite-Cluster-075-implied-volatility-put-30-weight-raw|Options Skew Risk Appetite Cluster 075 - implied_volatility_put_30 weight_raw]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 119 | `2.18` | `2.37` |
| [[076 - Options-Skew-Risk-Appetite-Cluster-076-annualized-pd-4-year-jc7|Options Skew Risk Appetite Cluster 076 - annualized_pd_4_year_jc7]] | 2 | exact-expression duplicate | Options Skew Risk Appetite Variant 122 | `2.07` | `2.13` |
| [[077 - EPS-Revision-Shock-Cluster-077-probability-dist-a-minus|EPS Revision Shock Cluster 077 - probability_dist_a_minus]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 100 | `2.03` | `2.18` |
| [[078 - Options-Skew-Risk-Appetite-Cluster-078-implied-volatility-call-270|Options Skew Risk Appetite Cluster 078 - implied_volatility_call_270]] | 2 | same-field same-operator variant | Options Skew Risk Appetite Variant 126 | `1.9` | `2.35` |
| [[079 - Price-Volume-Momentum-Cluster-079-annualized-pd-4-year-jc7|Price Volume Momentum Cluster 079 - annualized_pd_4_year_jc7]] | 2 | high-similarity field/operator/family cluster | Price Volume Momentum Variant 10 | `2.08` | `2.1` |
| [[080 - EPS-Revision-Shock-Cluster-080-mdl53-jc6-4year|EPS Revision Shock Cluster 080 - mdl53_jc6_4year]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 121 | `2.09` | `2.02` |
| [[081 - EPS-Revision-Shock-Cluster-081-probability-dist-a-minus-limit|EPS Revision Shock Cluster 081 - probability_dist_a_minus limit]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 123 | `2.02` | `2.11` |
| [[082 - Options-Skew-Risk-Appetite-Cluster-082-implied-volatility-call-270|Options Skew Risk Appetite Cluster 082 - implied_volatility_call_270]] | 2 | exact-expression duplicate | Options Skew Risk Appetite Variant 137 | `1.93` | `2.21` |
| [[083 - EPS-Revision-Shock-Cluster-083-annualized-pd-4-year-jc7|EPS Revision Shock Cluster 083 - annualized_pd_4_year_jc7]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 149 | `2.07` | `1.85` |
| [[084 - Price-Volume-Momentum-Cluster-084-returns|Price Volume Momentum Cluster 084 - returns]] | 2 | exact-expression duplicate | Price Volume Momentum Variant 12 | `2` | `1.94` |
| [[085 - EPS-Revision-Shock-Cluster-085-eps-previous-estimate-value|EPS Revision Shock Cluster 085 - eps_previous_estimate_value]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 152 | `1.88` | `2.1` |
| [[086 - EPS-Revision-Shock-Cluster-086-eps-previous-estimate-value|EPS Revision Shock Cluster 086 - eps_previous_estimate_value]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 151 | `1.88` | `2.1` |
| [[087 - Price-Volume-Reversal-Cluster-087-weight-raw-returns|Price Volume Reversal Cluster 087 - weight_raw returns]] | 2 | exact-expression duplicate | Price Volume Reversal Variant 9 | `1.9` | `2` |
| [[088 - EPS-Revision-Shock-Cluster-088-anl4-detailrecv4-est|EPS Revision Shock Cluster 088 - anl4_detailrecv4_est]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 172 | `1.9` | `1.97` |
| [[089 - Price-Volume-Momentum-Cluster-089-probability-dist-a-minus|Price Volume Momentum Cluster 089 - probability_dist_a_minus]] | 2 | same-field same-operator variant | Price Volume Momentum Variant 15 | `1.8` | `2.08` |
| [[090 - Price-Volume-Reversal-Cluster-090-turn-returns|Price Volume Reversal Cluster 090 - turn returns]] | 2 | numeric-parameter variant | Price Volume Reversal Variant 16 | `1.51` | `1.18` |
| [[091 - EPS-Revision-Shock-Cluster-091-limit|EPS Revision Shock Cluster 091 - limit]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 76 | `2.34` | `2.59` |
| [[092 - EPS-Revision-Shock-Cluster-092-limit|EPS Revision Shock Cluster 092 - limit]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 85 | `2.35` | `2.5` |
| [[093 - EPS-Revision-Shock-Cluster-093-alpha1-raw|EPS Revision Shock Cluster 093 - alpha1_raw]] | 2 | exact-expression duplicate | EPS Revision Shock Variant 98 | `2.32` | `2.46` |
| [[094 - Options-Skew-Risk-Appetite-Cluster-094-implied-volatility-call-270|Options Skew Risk Appetite Cluster 094 - implied_volatility_call_270]] | 2 | exact-expression duplicate | Options Skew Risk Appetite Variant 131 | `2.26` | `2.49` |
| [[095 - Cross-Sectional-Signal-Momentum-Cluster-095-fscore-growth|Cross Sectional Signal Momentum Cluster 095 - fscore_growth]] | 2 | same-field same-operator variant | Cross Sectional Signal Momentum Variant 3 | `4.97` | `1.46` |

## Singletons

- [[99 - Alpha Proposal Singletons|Alpha Proposal Singletons]]
