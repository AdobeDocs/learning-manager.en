---
jcr-language: en_us
title: Apply group by and aggregations in Report Builder  
description: Summarize Adobe Learning Manager report data by a chosen field and calculate counts, totals, and percentages across grouped rows.
contentowner: mmanuel
---

# Apply group by and aggregations in Report Builder

Group by and aggregation let you produce summary reports, such as total completions per instructor, enrollment count per catalog, or compliance percentage by region.

## When to use group by

Use group by when you want one row per category rather than one row per record. For example:

* One row per instructor, showing how many sessions they taught
* One row per catalog, showing total enrollments
* One row per user group, showing compliance percentage

If you want to see individual learner records or individual enrollment rows, don't apply group by.

When you apply group by to one column, every other column in the report must have an aggregate function applied. You can't show a raw field value alongside a grouped column - only a calculated value (count, sum, average, and so on).

For example, if you group by **Instructor Name**, you can't show individual **Session Name** values alongside it. Instead, you'd apply **Count** to the **Session ID** field to show how many sessions each instructor taught.

## Apply group by and aggregations

In this example, you'll compare enrollment progress across learners. Use this report to understand how different managers are performing in terms of enrollment progress and completion.

### Select columns

1. Launch **Report Builder** and select **Create Report**.
2. Type the name and description of the report:
    a. **Name:** Compare enrollment progress across users
    b. **Description:** This report groups learners by manager and calculates summary metrics such as total learners, average progress, and completion counts for enrollment status=COMPLETED
3. Select the following columns: `<dataset>:<column name>`
    a. User\Manager Name
    b. User\Name
    c. Enrollment\Status
    d. Enrollment\Progress Percent
    e. Learning Object\Completion Count

### Select Group by columns

1. Select the following columns in the **Group by** section:
    a. Enrollment\Status
    b. User\Manager Name
    ![](assets/image020.jpg)
2. Select **Apply**.

### Select columns to aggregate

The aggregate functions summarize learner enrollment performance by manager and enrollment status, showing distinct learner counts, average training progress percentages, and average learning object completion counts across grouped training records.

1. Select **Count Distinct** for User\Name.
2. Select **Average** for Enrollment\Progress Percent.
3. Select **Average** for Learning Object\Completion Count.
    ![](assets/image021.png)

### Apply filters

Apply filters to include only completed enrollments and exclude records with missing manager names, ensuring the report analyzes valid learner data for accurate manager-wise training progress and completion insights.

1. Apply a filter where _Enrollment-Status_ equals _Completed_.
2. Apply a second filter where _User-Manager Name_ is not empty.
3. Combine both filters using the AND condition to include only valid completed learner records.

### Save and download the report

Select **Save Report** and select **Actions** > **Download** to download the report. You'll receive a notification to download the report in .csv format once it's ready.

The CSV contains a manager-wise summary of completed learner enrollments and training progress. Each row represents a manager and includes learner counts, enrollment status, average progress percentage, and average completion counts.

Overall, the report compares training completion and learning activity across managers, highlighting differences in learner engagement and the number of completed learning objects.
