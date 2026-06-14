---
jcr-language: en_us
title: Build a trend report in Report Builder
description: Track month-on-month or week-on-week learning trends in Adobe Learning Manager Report Builder using trend aggregators on date fields.
contentowner: mmanuel
---

# Build a trend report in Report Builder

Trend reports show how metrics, such as course count, enrollment count, or completions, change over time. You choose a date column and a trend granularity (day, week, or month), and Report Builder groups the data by that time period.

## What trend data mean

Trend reports in Report Builder reflect **a current snapshot of data, grouped by date**. They don't show the historical state of the data at each past date.

For example, a monthly enrollment trend shows the number of enrollments that exist today, distributed across the months in which they were created. If a learner enrolled in January and later unenrolled, that enrollment record may no longer appear. The report reflects the current state of records, not what was true in January.

This is an important distinction for audit purposes. If you need point-in-time historical data, use this report for directional trend analysis rather than precise historical records.

## Build a course count trend report

This report shows how many courses were added to the account month-on-month.

1. Select **Reports** > **Report Builder**, then select the **Reports** tab.
2. Select **Create report**. Type a name such as Course count MoM.
3. Add **Learning Object ID** from the **Learning Object** dataset.
4. Add **Created Date** from the **Learning Object** data set.
    ![](assets/image039.png)
5. Apply **Group by** on **Created Date**. Set the trend granularity to **Month**.
    ![](assets/image40.png)
6. Apply **Count** to **Learning Object ID**. Enter the alias Course count.
    ![](assets/image041.png)
7. Sort by **Created Date** ascending to show the trend chronologically.
    ![](assets/image042.png)
8. Select **Save Report** and select **Actions** > **Download** to download the report.

The downloaded file consists of a monthly trend of course creation activity, showing the number of courses created over time. It helps track course production patterns, peaks, declines, and overall content growth.

## Build a catalog-wise completions trend report

This report shows monthly completion totals per catalog over a defined period.

1. Select **Reports** > **Report Builder**, then select the **Reports** tab.
2. Select **Create report**. Type a name such as Catalog completions MoM.
3. Add **Catalog Name** from the **Catalog** dataset.
4. Add **Completed Date** from the **Module Transcript** dataset.
5. Add **Learning Object ID** from the **Learning Object** data set to count completions.
6. Apply **Group by** on **Catalog Name**. Also apply **Group by** on **Completed Date** with **Month** granularity.
    ![](assets/image_043.png)
7. Apply **Count** to **Learning Object ID**. Enter the alias Total completions.
8. Add a filter: **Catalog** is in Safety, POS, Delivery (or the catalogs relevant to your account).
9. Add a filter: **Completion Date** is within last year.
    ![](assets/image044.png)
10. Sort by **Completed Date** ascending.
    ![](assets/image_045.png)
11. Select **Save Report** and select **Actions** > **Download** to download the report.

## Best practices

* Use **Completion Date** for completion trends and **Enrollment Date** for enrollment trends. Using the wrong date field produces misleading results.
* Add a date filter to limit the trend to a meaningful window, for example, the last 12 months for a monthly trend, or the last 8 weeks for a weekly trend.
* Label your trend report with the granularity and date range in the name, for example, "Catalog completions MoM – last 3 months", so it's clear when you view it later.
