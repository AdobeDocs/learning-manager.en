---
jcr-language: en_us
title: Monitor Virtual Coach usage 
description: Monitor how Virtual Coach is used by your account.
contentowner: mmanuel
---

# Monitor Virtual Coach usage

View Virtual Coach usage data, track Monthly Active User (MAU) credit consumption, and access learner performance reports in Adobe Learning Manager.

## Activate Virtual Coach for your account

Virtual Coach is available as an add-on to Adobe Learning Manager. After purchase, provisioning generates an activation key that is emailed to the account administrator.

1. Sign in to Adobe Learning Manager as an administrator.  
2. Navigate to the **Billing** page from the left navigation pane.  
3. In the **Virtual Coach** section, enter the activation key you received by email.  
4. Select **Apply**. Virtual Coach is enabled for your account.
    ![](assets/virtual-coach-037.png)  

Once activated, you will receive an in-app notification confirming the feature is live. Four sample roleplay scenarios are added automatically to the Content Library so authors can begin immediately.  

>[!NOTE]
>
>The activation key is auto-generated during provisioning and shared via email. If you do not have the activation key, please contact your Adobe Learning Manager Customer Success Manager (CSM).

## View your MAU credit balance

Monthly Active User (MAU) credits count the number of unique learners who use Virtual Coach each month.

1. Navigate to the **Billing** page.  
2. In the **Virtual Coach** section, select **View Usage Details**.  
3. Use the **Select period** drop-down to choose the date range you want to review.
    ![](assets/virtual-coach-038.png)   

    The **Overall Usage** table shows:

    a. **Available:** Total MAU credits purchased  
    b. **Used:** Credits consumed to date  
    c. **Remaining:** Credits available for the rest of the contract period  

    The **Monthly Usage** table shows the number of unique active learners by calendar month.

4. Select **Download Detailed Report** to export the full usage data.

## How MAU credits are consumed

An MAU credit is consumed when a learner completes a Virtual Coach session in a calendar month. Additional sessions by the same learner in the same month do not consume additional credits.

| Scenario | MAUs consumed |
|----------|--------------|
| One learner completes 5 sessions in January | 1 |
| Same learner uses Virtual Coach in both January and February | 2 (1 per month) |
| 100 learners each complete 1 session in January | 100 |

_MAU credits are counted per unique learner per calendar month, regardless of how many sessions each learner completes._  

Unused credits at the end of the contract period lapse and do not carry over.

### Example 1: Single learner, multiple sessions

Scenario: Sarah completes five Virtual Coach sessions in January.

* Sessions in January: 5  
* MAUs consumed: 1  
* Why: Sarah is counted as a single unique user for the month of January, regardless of how many times she practices.  

### Example 2: Same learner, multiple months

Scenario: Sarah uses Virtual Coach both January and February.

* Sessions in January: 3  
* Sessions in February: 2  
* MAUs consumed: 2 (1 for January + 1 for February)  
* Why: Each calendar month counts separately.  

### Example 3: Multiple learners, same month

Scenario: 100 sales reps each complete one Virtual Coach session in January.

* Total sessions: 100  
* MAUs consumed: 100  
* Why: Each unique learner counts as one MAU for that month.  

### Example 4: Team practice over time

Scenario: Your team of 50 people uses Virtual Coach throughout the year.

| Month | Active Learners | MAUs Consumed This Month | Cumulative MAUs |
|------|----------------|--------------------------|-----------------|
| anuary | 0 | 0 | 0 |
| ebruary | 5 (5 people didn't ractice) | 5 | 5 |
| March | 0 (all 50 practiced gain) | 0 | 45 |
| April | 0 | 0 | 75 |

## View Virtual Coach reports

The **Manage** section > **Reports** section > **AI Reports** page provides usage and performance data for all Virtual Coach activity across your organization. Two reports are available under the **Virtual Coach** heading.  

All reports are exported in CSV format. Report generation may take several minutes, depending on the data size.

### Learner Usage Summary

Contains monthly usage data for all learners. Use this report to track how many learners are using Virtual Coach each month, monitor MAU credit consumption, and identify engagement trends over time.

### Session Details

Contains session-level data for all learners over the last 90 days. Use this report to review individual session scores, topic coverage, and style metrics across your learner population, and to identify skill gaps that may require additional training or content.

## Access and download a report

1. Sign in to Adobe Learning Manager as an administrator.  
2. Select **Reports** in the left navigation pane.  
3. Select **AI Reports**.  
4. Under the **Virtual Coach** section, select the report you want to download, **Learner Usage Summary** or **Session Details**.
    ![](assets/virtual-coach-039.png)   
5. Select the date range when prompted, then select **Proceed**.  
6. The report downloads automatically as a CSV file.
