---
jcr-language: en_us
title: Report Builder - concepts and terminology  
description: Understand the key concepts of Report Builder, including datasets, columns, grouping, filters, and aggregates, before building your first report.
contentowner: mmanuel
---

# Report Builder: Concepts and terminology

## Templates and reports

**Templates** are pre-built report configurations provided by Adobe Learning Manager. They're designed for common use cases, enrollment and completion tracking, compliance reporting, instructor performance, and are ready to download immediately. Templates are read-only; you cannot edit or overwrite them.
![](assets/report-builder-002.png)  

**Reports** are your own saved configurations. You can create a report from scratch or by duplicating a template and editing the copy. When you duplicate a template, the copy becomes a report in your Reports tab.  

Templates and reports both appear in Report Builder, but under separate tabs.

## Datasets

A dataset is a named group of related columns in Report Builder. When you add columns to a report, you pick from these datasets. Think of each data set as a table of information about one aspect of your learning data.

The following is a sample of datasets available in Report Builder:

* **User:** learner profile data, including active fields  
* **Transcript:** enrollment and completion records  
* **Learning Object:** course, learning path, and certification data  
* **Learning Object Instance:** instance-level details  
* **Catalog:** catalog and catalog label data  
* **User Group:** user group membership and hierarchy  
* **Module Session:** classroom and virtual session data, including e-learning module details  

>[!NOTE]
>
>Data sets are selectively joinable. Not all combinations are available in a single report.

## Columns and the Add button

Each column you add appears as a row in the report canvas and becomes a column in the downloaded file. You can add the same column more than once. This is useful when you want to measure two different values from the same field. For example, you can add the Status column twice: once to count enrollments and once to count in-progress learners using the count if aggregate.
![](assets/report-builder-003.png)

You can also rename any column by entering an alias. The alias appears as the column header in the downloaded report.

## Group by and aggregation

Group by summarizes your data by a chosen field instead of showing individual rows. For example, grouping by instructor name gives you one row per instructor rather than one row per enrollment.  

Group by follows standard database behavior: once you apply group by on one column, every other column in the report must have an aggregate function applied. You can't mix individual row data with grouped data. Available aggregate **functions** are:

* **Count:** Total number of rows  
* **Count if:** Number of rows where the field matches a value you specify  
* **Sum:** total of a numeric **field**  
* **Min:** lowest value in a numeric field  
* **Max:** the highest value in a numeric field  
* **Average:** mean value of a numeric field  

If you've used pivot tables in Excel, group by works the same way at the column level.

## Filters

Filters restrict which rows appear in your report. You can apply multiple filters and combine them with AND or OR logic.

Filter operators depend on the column's data type:

* **String fields:** Contains, equals, starts with (type-ahead search available for recognized values)  
* **Numeric fields:** Greater than, less than, equals, between  
* **Date fields:** Equals, before, after, between, and relative ranges (for example, last 90 days)  
* **Enum (list) fields:** Is in, is not in (multi-select value picker)  

## AND / OR logic and nested filter groups

Multiple filters default to AND logic. All conditions must be true for a row to appear. You can switch the operator between any two filters to OR. You can also group filters using Add as group, which creates a bracket. Filters within the group are evaluated together before being combined with filters outside it.

This lets you build conditions like:

(catalog = Safety OR catalog = Hygiene) AND completion date is in the last 90 days.  

You can nest groups within other groups to support complex multi-level logic.

## Sorting

You can sort on one or more columns. The first column you sort on is the primary sort. Additional sorts apply within ties in the primary column.  

Always apply at least one sort when you need consistent output. Because report generation runs across a distributed system, row order is not guaranteed between two downloads of the same report unless sorting is applied.

## Trend data vs. snapshot data

Any report that uses a trend aggregator, such as month-on-month or week-on-week, reflects current snapshot data grouped by date. It does not reflect the historical state of the data at each past date.  

For example, an enrollment trend grouped by month shows how many enrollments exist today, distributed across the months they were created. It doesn't account for learners who later unenrolled or changed user groups. Those changes aren't retroactively applied to past months.

## Deleted learners and active fields

Report Builder supports including deleted learners in reports and retrieving their active field values. Use the **Deletion Date** column in the **User** dataset to create the report.

## Best practices

* Read the available data sets reference before building a report from scratch. Knowing which data set contains the fields you need saves significant configuration time.  
* Apply sorting before subscribing to a scheduled report. This ensures consistent row order across every delivery.  
* If you see unexpected duplicate rows, check whether your report includes a field that can have multiple values per row, such as an instructor's name for a session with multiple instructors.
