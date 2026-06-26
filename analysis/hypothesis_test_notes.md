# Hypothesis Test Notes

## Objective

The objective of this hypothesis test was to determine whether the new onboarding and activation campaign (Treatment group) resulted in a higher paid conversion rate than the existing onboarding experience (Control group).

## Metric Tested

**Paid Conversion Rate**

Paid Conversion Rate = Number of users converted to paid ÷ Total number of users

This metric was selected because it is the primary success metric and directly measures the effectiveness of the onboarding campaign in converting users into paying subscribers.

## Test Used

Two-Proportion Z-Test

This test was chosen because the metric being analyzed is binary (users either converted to paid or did not).

## Test Inputs

| Group     | Total Users | Converted Users | Conversion Rate |
| --------- | ----------: | --------------: | --------------: |
| Control   |         693 |              22 |           3.17% |
| Treatment |         715 |              50 |           6.99% |

## Hypotheses

**Null Hypothesis (H₀):**
There is no significant difference in the paid conversion rate between the Control and Treatment groups.

**Alternative Hypothesis (H₁):**
There is a significant difference in the paid conversion rate between the Control and Treatment groups.

## Significance Level

The significance level used for the test is **α = 0.05**.

## Test Results

* Pooled Conversion Rate: **0.0511**
* Standard Error: **0.0117**
* Z-score: **3.25**
* P-value: **0.00115**

## Decision Rule

* If the p-value is less than 0.05, reject the null hypothesis.
* If the p-value is greater than or equal to 0.05, fail to reject the null hypothesis.

## Result

Since the **p-value (0.00115)** is less than **0.05**, the null hypothesis is rejected.

## Business Interpretation

The Treatment group achieved a paid conversion rate of **6.99%**, compared to **3.17%** for the Control group. The statistical test indicates that this improvement is unlikely to have occurred by chance.

Based on the primary success metric, the new onboarding campaign performed significantly better than the existing onboarding experience. Therefore, the Treatment can be considered for rollout, provided that the guardrail metrics (such as refund rate and support ticket rate) do not show any negative impact on the user experience.
