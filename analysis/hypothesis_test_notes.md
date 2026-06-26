# Hypothesis Test Notes

## Objective

The purpose of this hypothesis test is to determine whether the new onboarding and activation campaign (Treatment group) performs better than the existing onboarding experience (Control group) in increasing the paid conversion rate.

## Metric Being Tested

**Paid Conversion Rate**

Paid Conversion Rate = Number of users who converted to paid ÷ Total number of users

## Why This Metric?

Paid conversion rate is the primary success metric because it directly measures how effectively the onboarding experience converts users into paying subscribers. Since the company follows a subscription-based business model, improving this metric contributes directly to business growth and revenue.

## Null Hypothesis (H₀)

There is **no significant difference** in the paid conversion rate between the Control group and the Treatment group.

[
H_0 : p_{Treatment} = p_{Control}
]

## Alternative Hypothesis (H₁)

There **is a significant difference** in the paid conversion rate between the Control group and the Treatment group.

[
H_1 : p_{Treatment} \neq p_{Control}
]

## Type of Test

**Two-tailed hypothesis test**

A two-tailed test is used because we want to determine whether the new onboarding campaign performs differently from the existing experience, whether the result is better or worse.

## Significance Level

**α = 0.05 (5%)**

A 5% significance level is used, which is the standard threshold for business experiments. If the p-value is less than 0.05, the result will be considered statistically significant.

## Interpretation Logic

* If **p-value < 0.05**, reject the null hypothesis and conclude that the new onboarding campaign has a statistically significant impact on the paid conversion rate.
* If **p-value ≥ 0.05**, fail to reject the null hypothesis and conclude that there is not enough evidence to say the Treatment group performs differently from the Control group.

## Business Decision

The new onboarding campaign should be recommended for rollout only if:

* The Treatment group shows a statistically significant improvement in paid conversion rate.
* Guardrail metrics (such as refund rate and support ticket rate) do not show a meaningful decline in user experience.
* The expected business benefits outweigh the cost of implementing the new onboarding experience.
