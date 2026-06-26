# Business Problem Statement

The company has launched a new onboarding and activation campaign to help new users get started more effectively and encourage them to become paying customers. To test whether the new campaign works better than the current onboarding process, users were divided into two groups:

### * Control Group: Existing onboarding experience
### * Treatment Group: New onboarding campaign

The main decision is whether the company should launch the new onboarding campaign for all users.

This decision will affect new users, the Product and Growth teams, and company leadership because it can influence user experience, customer engagement, and revenue.

## The goal of the new campaign is to increase:

 1. The number of users who convert to paid subscribers
 2. The number of users who complete important onboarding steps
 3. Early user engagement with the product

## At the same time, the company must ensure that the new campaign does not create any negative effects. Therefore, we need to monitor metrics such as:

 1. User churn or cancellations
 2. Refund requests
 3. Customer complaints or support tickets
 4. Any drop in user satisfaction

## Before making a recommendation, we need clear evidence that:

 1. The treatment group performs better than the control group on key success metrics.
 2. The improvement is statistically significant and not due to chance.
 3. Guardrail metrics do not get worse.
 4. The expected business benefits outweigh the cost and effort of rolling out the new campaign.

Based on this analysis, we will recommend whether the new onboarding experience should be launched to all users or not.

## Data Preparation and Quality Checks

Before analyzing the experiment results, the dataset was reviewed for data quality and consistency.

### Checks Performed

| Check                 | Result                                                                                                                             |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Missing Values        | Found mainly in `days_to_convert` (1,336 records), with a small number in `device_type`, `traffic_source`, and `engagement_score`. |
| Group Counts          | Control: 693 users, Treatment: 715 users. Groups were reasonably balanced.                                                         |
| Duplicate User IDs    | Duplicate user IDs were identified and flagged using a helper column.                                                              |
| Invalid Binary Values | No invalid values found. All binary fields contained only 0 or 1.                                                                  |
| Revenue Outliers      | 72 records were flagged using the IQR method and retained as they may represent legitimate high-value customers.                   |
| Segment Distribution  | Device type, region, and traffic source distributions were similar across Control and Treatment groups.                            |

### Data Preparation Actions

* Created a `Duplicate_Flag` column to identify duplicate user IDs.
* Created a `Revenue_Outlier_Flag` column to identify potential revenue outliers.
* Retained missing values and revenue outliers where they represented valid business scenarios.
* Verified that experiment groups were balanced and suitable for comparison.

### Conclusion

The dataset passed the required quality checks and was considered suitable for experiment analysis.

# A/B Testing Analysis for Onboarding & Activation Campaign

## Business Context

A subscription-based digital product company launched a new onboarding and activation campaign to improve user conversion and early engagement. Users were randomly assigned to either a **Control** group (existing onboarding experience) or a **Treatment** group (new onboarding experience).

The objective of this project was to evaluate whether the new onboarding campaign should be rolled out to all users based on experiment results and supporting business metrics.

---

## Dataset Description

The dataset contains user-level experiment data, including:

* User ID
* Experiment group (Control/Treatment)
* Landing page visit
* Trial start
* Onboarding completion
* Paid conversion
* Revenue (30 days)
* Support tickets
* Refund requests
* Days to convert
* Engagement score
* User segments (Device Type, Region, Traffic Source, Plan Type)

A total of **1,408 users** participated in the experiment.

---

## North Star Metric

**Paid Conversion Rate**

Paid Conversion Rate was selected as the North Star Metric because it directly measures how successfully the onboarding experience converts users into paying subscribers. Improving this metric supports subscription growth and increases business revenue.

---

## KPI Tree Summary

The KPI Tree was designed around the Paid Conversion Rate and included the following drivers:

* Landing Page Visits
* Trial Starts
* Onboarding Completion
* Paid Conversion
* Revenue & Engagement

Guardrail metrics monitored during the experiment included:

* Refund Rate
* Support Ticket Rate
* Average Days to Convert
* Engagement Score

---

## Experiment Analysis Approach

The analysis followed these steps:

* Performed data quality checks (missing values, duplicates, invalid binary values, outliers, and segment distribution).
* Calculated key experiment metrics for the Control and Treatment groups.
* Compared business KPIs using Pivot Tables and summary tables.
* Conducted a Two-Proportion Z-Test to determine whether the difference in paid conversion rate was statistically significant.
* Evaluated guardrail metrics to ensure the improvement did not negatively affect user experience.
* Reviewed segment-level performance across Device Type, Region, and Traffic Source.

---

## Hypothesis Test Summary

A Two-Proportion Z-Test was performed using the Paid Conversion Rate as the primary metric.

### Results

* Control Conversion Rate: **3.17%**
* Treatment Conversion Rate: **6.99%**
* Z-score: **3.25**
* P-value: **0.00115**

Since the p-value was less than **0.05**, the null hypothesis was rejected. The Treatment group showed a statistically significant improvement in paid conversion rate.

---

## Guardrail Metrics Considered

The following guardrail metrics were evaluated:

| Metric                   | Observation                         |
| ------------------------ | ----------------------------------- |
| Refund Rate              | Slight increase from 0.00% to 0.42% |
| Support Ticket Rate      | Increased from 14.72% to 24.76%     |
| Average Days to Convert  | Improved from 8.86 to 6.40 days     |
| Average Engagement Score | Increased from 57.03 to 62.93       |
| Average Revenue per User | Increased from 51.70 to 53.90       |

While the Treatment group improved conversion and engagement, the higher support ticket rate indicates a potential usability concern.

---

## Final Recommendation

**Recommendation: Continue Testing**

The new onboarding campaign significantly improved paid conversion rate and user engagement. However, the increase in support ticket rate suggests that the onboarding experience may be creating additional user issues.

Before a full rollout, the company should investigate the reasons for the increase in support requests, improve the onboarding flow where necessary, and run a follow-up experiment to confirm the results.

---

## Assumptions and Limitations

### Assumptions

* Users were randomly assigned to Control and Treatment groups.
* Revenue values accurately represent 30-day revenue.
* Missing values in `days_to_convert` correspond to users who did not convert.
* Revenue outliers represent genuine high-value customers and were retained.

### Limitations

* Results are based on a single experiment period.
* The increase in support ticket rate requires further investigation.
* Additional testing with a larger user base may provide stronger validation.

---

## Screenshots Included

The repository includes the following screenshots:

* KPI Tree Preview
* Data Quality Checks
* Experiment Summary
* Hypothesis Test Output
* Guardrail Metrics Summary
* Segment-Level Analysis
