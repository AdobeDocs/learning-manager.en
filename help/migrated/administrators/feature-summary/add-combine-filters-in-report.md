---
jcr-language: en_us
title: Add and combine filters in a report
description: Restrict report data in Adobe Learning Manager Report Builder using single filters, AND / OR logic, and nested filter groups. 
contentowner: mmanuel
---

# Add and combine filters in a report

## Overview

Filters let you scope your report to exactly the records you need. You can apply a single filter, combine multiple filters with AND or OR logic, and create nested groups for complex conditions.

## Add a filter

Use filters to limit your report to a specific subset of data instead of viewing everything.

For example, you may want to understand how many learners enrolled in courses in the last 365 days. In this case, you apply a date filter on enrollment date to include only recent activity.

1. Launch Report Builder and select **Create Report**.
2. Type the name and description of the report.
3. Select the following columns: <dataset>:<column name>

    * Enrollment - Enrolled Date
    * User - Name

    ![](assets/report-builder-0024.png)

4. In the Reports section, select **Add filter**.
5. Search for or browse to the field you want to filter on. In this example, select **Enrollment - Enrolled Date**.

    ![](assets/report-builder-0025.png)

6. Select **Add**.
7. Select an operator. Available operators depend on the field's data type:

    * String fields - contains, equals, starts with
    * Numeric fields - greater than, less than, equals, between
    * Date fields - equals, before, after, between, last N days
    * List (enum) fields - is in, is not in

8. In this case, select **is within last year**.

    ![](assets/report-builder-0026.png)

9. Select **Save Report** and select **Actions** > **Download** to download the report.

The downloaded report lists all users who've enrolled in a Learning Object in the past 365 days.

## Add multiple filters with AND / OR logic

When you add a second filter, the default relationship between filters is AND; both conditions must be true for a row to appear.

For example, you may want to identify learners who enrolled in courses in the last 365 days AND report to a specific manager. In this case, both conditions must be true, so filters are combined using AND logic.

1. Launch Report Builder and select **Create Report**.
2. Type the name and description of the report.
3. Select the following columns: <dataset>:<column name>

    * User - Name
    * User - Manager Name
    * <span class="mark">Enrollment - Enrolled Date</span>

4. Group by the column **User-Manager Name**.
5. In the Filter section, select the following filters:

    * Enrollment - Enrolled Date i**s within last year**
    * User - Manager Name **starts with** N
    * User - Manager Name **is not empty**
    
        ![](assets/report-builder-0027.png)

6. Select **Save Report** and select **Actions** > **Download** to download the report.

The downloaded report lists all users who have enrolled in a Learning Object in the past 365 days **and** report to a manager whose name starts with N.

## Create nested filter groups

Nested groups let you build conditions with multiple logical levels, equivalent to brackets in a formula. For example: (Catalog = Safety OR Catalog = Hygiene) AND Completion Date is in the last 90 days.

Use nested filter groups when your logic includes a mix of AND and OR conditions that must be evaluated together.

For example, use nested filter logic to identify incomplete enrollments where learners have progress below 50% or overdue training, demonstrating how AND and OR conditions work together.

1. Launch Report Builder and select **Create Report**.
2. Type the name and description of the report.
3. Select the following columns: <dataset>:<column name>

    * Enrollment - Status
    * Enrollment - Progress Percent
    * Enrollment - Overdue

        ![](assets/report-builder-0028.png)

4. In the **Filter** section, select the following filters:

    * Enrollment -Status **does not equal any of** Completed.
    * Select +.
    * Search for Enrollment-Progress Percent.
    * Select the filter.
    * Select **Add as group**.

        ![](assets/report-builder-0029.png)

5. Add Enrollment - Progress Percent **less than** 50.

    ![](assets/report-builder-0030.png)

6. Select +.
7. Search for **Enrollment-Overdue**.
8. Select the filter.
9. Select **Add as group**.

    ![](assets/report-builder-0031.png)

10. Add Enrollment-Overdue equals TRUE.
11. Change the nested AND to OR.

    ![](assets/report-builder-0032.png)

12. Select **Save Report** and select **Actions** > **Download** to download the report.

The downloaded report lists all enrollments that are in progress or not started, whose progress percent is less than 50%, or are overdue.
