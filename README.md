# A/B Testing Subscription Conversion Case Study

This project analyzes an A/B test for a subscription screen.

The business question was simple:

**Will an updated subscription screen increase subscription purchases compared with the current screen?**

The test compared two variants:

- **Control A:** current subscription screen
- **Variant B:** updated subscription screen where the same $4.99 offer was presented as a 50% discount

The goal was not only to check whether conversion increased, but also to understand whether the result is strong enough to support a business decision.

## Dataset

The dataset contains user-level A/B test data with the following fields:

- `user_id` — unique user identifier
- `timestamp` — event timestamp
- `test_group` — test group, either `a` or `b`
- `conversion` — conversion result, where `1` means converted and `0` means not converted

The timestamps in the dataset refer to historical dates from July 2023.  
They are used as part of a structured A/B testing case study focused on conversion analysis, statistical validation and business decision-making.

## Tools Used

- Python
- Pandas
- NumPy
- SciPy
- Matplotlib
- Seaborn
- Google Colab
- Google Slides
- GitHub

## Analysis Steps

The analysis included:

1. Loading and checking the dataset structure
2. Checking missing values and duplicates
3. Calculating users, conversions and conversion rate by test group
4. Calculating the test period
5. Testing statistical significance with a two-sample t-test
6. Running an additional permutation test
7. Visualizing conversion rate by variant with 95% confidence intervals
8. Visualizing daily conversion trend by group
9. Preparing a business recommendation based on the result

## Key Results

| Metric | Control A | Variant B |
|---|---:|---:|
| Users | 10,013 | 9,985 |
| Conversions | 611 | 889 |
| Conversion rate | 6.10% | 8.90% |

Variant B increased subscription conversion from **6.10% to 8.90%**.

Main uplift results:

- **Absolute uplift:** +2.80 percentage points
- **Relative uplift:** +45.9%
- **Statistical result:** p-value < 0.05

Both the t-test and the permutation test showed that the difference between the groups was statistically significant.

## Hypotheses

- **H0:** There is no statistically significant difference in conversion rates between Control A and Variant B.
- **H1:** There is a statistically significant difference in conversion rates between Control A and Variant B.

Since the p-value was below 0.05, the null hypothesis was rejected.

This means that the conversion difference is unlikely to be explained by random variation alone.

## Business Interpretation

Variant B performed better in terms of subscription conversion.

However, a higher conversion rate alone is not enough for an immediate full launch.  
The updated screen presents the same $4.99 price as a discount offer, so the business should also check whether the new presentation attracts lower-quality purchases.

Before a full rollout, the company should monitor:

- revenue
- cancellations
- refunds
- retention
- repeat payments

These metrics help confirm whether the conversion uplift creates real business value.

## Recommendation

The recommended decision is to roll out Variant B gradually to **20–30% of users** instead of launching it to everyone immediately.

The rollout should continue only if the uplift remains stable and downstream business metrics do not get worse.

## Key Risks

Main risks:

- Discount-based messaging may attract more price-sensitive users.
- Short-term conversion growth may not turn into stronger long-term value.
- Presenting the same $4.99 price as a discount may affect user trust if the original price is unclear.

## Suggested Follow-up Test

A follow-up A/B test is recommended to compare two different ways of presenting the subscription offer:

- **Option A:** discount-based presentation  
  Focus: “50% discount”

- **Option B:** value-based messaging  
  Focus: unlimited content, no ads, cancel anytime

This would help understand whether users respond better to a discount message or to a clear product value message.

## Project Files

- `AB_testing_Viktoria_Serdiuk.ipynb` — notebook with analysis and visualizations
- `ab_test_data.csv` — dataset used for the analysis
- `AB_Testing_Subscription_Conversion_Case_Study.pdf` — final presentation
- `conversion_rate_by_variant.png` — conversion rate chart
- `daily_conversion_trend_clean.png` — daily conversion trend chart

## Links

- [Google Colab notebook](https://colab.research.google.com/drive/1nLnNXbh0yZyFjzi8iSMxbCP0NxNoKn-r?usp=sharing)
- [Google Slides presentation](https://docs.google.com/presentation/d/1QECFDT38jRxoTbV0xpmO49KEcEHZmph5L0ybh4WRMvs/edit?usp=sharing)

## Final Conclusion

Variant B showed a statistically significant improvement in subscription conversion.

The result is strong enough to support a controlled rollout, but not enough for an immediate full launch without additional business checks.

The final decision should depend on both conversion uplift and downstream user quality metrics.
    
