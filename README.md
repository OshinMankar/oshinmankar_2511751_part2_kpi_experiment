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

