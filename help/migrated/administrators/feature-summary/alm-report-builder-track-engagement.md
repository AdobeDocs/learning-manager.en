---
jcr-language: en_us
title: Track engagement by user group in Report Builder  
description: Build a report in Adobe Learning Manager Report Builder that shows total time spent and enrollments per user group, grouped by month.
contentowner: mmanuel
---

# Track engagement by user group in Report Builder

This report helps training managers and L&D administrators identify which user groups are most active and how engagement trends month on month. It uses the **Active Field User Group** and **Enrollment** data sets with group by and aggregate functions to produce one summary row per user group per month.

## Build the engagement by user group report

1. Launch **Report Builder** and select **Create Report**.
2. Type a name, for example, _Engagement by user group MoM_.
3. In the **Select columns** panel, expand **Active Field User Group** and select **+** next to **User Group Name**. The column appears in the **Selected Columns** panel.
4. Expand **Enrollment** and select **+** next to **Enrolled Date**.
5. Select **+** next to **Time Spent**. Select the **edit** (pencil) icon and enter the alias _Total time spent_.
6. Expand **Learning Object** and select **+** next to **Enrollment User Count**. Select the edit icon and enter the alias _Total enrollments_.
7. Select **Group by: Select** at the top of the **Selected Columns** panel.
8. Choose **Enrollment - Enrolled Date** and set the granularity to **Month**. Choose **Active Field User Group - User Group Name**. Both appear as tags: **Enrollment - Enrolled Date (Month)** and **Active Field User Group - User Group Name**.
9. On the **Enrollment - Time Spent** row, select **Aggregate by** and choose **Sum**.
10. On the **Learning Object - Enrollment User Count** row, select **Aggregate by** and choose **Count**.
    ![](assets/image038.jpg)
11. Select **Add filter**. Choose **Enrollment - Enrolled Date**, and select a relative range such as **Last 3 months**, or enter a specific date range.
12. Select **+ Add sorting**. Sort by **Enrollment - Enrolled Date** ascending, then add a secondary sort on **Total time spent** descending.
13. Select **Save Report** and select **Actions** > **Download** to download the report.

The report will have one row per user group per month, showing total time spent and total enrollments for that period. 

