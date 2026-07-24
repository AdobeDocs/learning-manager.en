---
jcr-language: en_us
title: Sort report columns in Report Builder
description: Apply single or multi-column sorting in Adobe Learning Manager Report Builder to control the row order of your downloaded reports. 
contentowner: mmanuel
---

# Sort report columns in Report Builder

## Overview

Sorting determines the order of rows in the downloaded report file. Apply sorting whenever consistent output matters.

## Add a sort

In this example, you'll find out the courses that have the highest completions.

1. Launch Report Builder and select **Create Report**.
2. Type the name and description of the report.
3. Select the following columns: <dataset>:<column name>

    * Learning Object - Learning Object Name
    * Learning Object - Learning Object Status
    * Learning Object - Completion Count

4. In the Sorting section, select **Add sorting**.
5. Select **Learning Object - Completion Count**.
6. Select a sort order- **Ascending** or **Descending**

    ![](assets/report-builder-0034.png)

7. Select **Add**.
8. Select **Save Report** and select **Actions** > **Download** to download the report.

The downloaded report lists all records, sorted by the number of course completions.

## Add multi-column sorting

In this example, you'll generate a report to measure performance across managers.

To sort by more than one column:

1. Launch Report Builder and select **Create Report**.
2. Type the name and description of the report.
3. Select the following columns: <dataset>:<column name>

    * User - Name
    * User - Manager Name
    * Module Transcript - Status
    * Module Transcript - Progress Percent

4. Add the following aggregates:

    * Group by User-Manager Name
    * Count Distinct User-Name
    * Count If=COMPLETED Module Transcript - Status
    * Average Module Transcript - Progress Percent

    ![](assets/report-builder-0035.png)

5. In the Sort section, add the following multi-column sorting:

    * <span class="mark">Module Transcript - Status: Descending</span>
    * User - Manager Name: Ascending

    ![](assets/report-builder-0036.png)

6. Select **Save Report** and select **Actions** > **Download** to download the report.

The downloaded report provides a manager-wise performance summary, showing distinct learner counts, status-based enrollment counts, and average progress percentages. It highlights participation levels and training progress across different manager groups.
