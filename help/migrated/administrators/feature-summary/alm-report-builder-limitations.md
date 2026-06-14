---
jcr-language: en_us
title: Limitations of Report Builder in Adobe Learning Manager  
description: Understand what Report Builder doesn't support in this release so you can plan your reporting approach accordingly.
contentowner: mmanuel
---

# Limitations of Report Builder in Adobe Learning Manager

Report Builder covers a wide range of custom reporting needs, but some report types, data sets, and configurations are not supported in this release. This section lists known limitations and suggests workarounds where available.

## Recurring certifications

Certain queries involving recurring certifications don't work correctly in Report Builder in this release. If your report involves recurring certification cycles, such as tracking re-enrollment or re-completion across multiple certification periods, use the existing certification reports in Adobe Learning Manager instead.

## Unsupported data sets and report types

The following are not available in Report Builder in this release:

* **Business outcome data**: Report Builder doesn't support Bring Your Own Data (BYOD) integrations. Reports that combine external business data with LMS data aren't supported.
* **Audit reports**: System audit trails and admin activity logs can't be built in Report Builder. Use the existing audit reports in the admin view for this data.
* **Incremental reports**: Report Builder generates full snapshot reports each time. Incremental reports that return only records changed since the last download aren't supported. For incremental data, use the Job API.

## Trend report limitations

### Only one date column per trend report

A single trend report can only group by one date-based column. You can't combine two different date-based trends in the same report.

For example, you can build:

* A report showing **enrollments by month** (grouped by Enrolled Date)
* A separate report showing **completions by month** (grouped by Completion Date)

You can't build a single report that shows both enrollment month and completion month as separate trend columns. To get both, create two separate reports and analyze them side by side.

### Trends reflect current data, not historical snapshots

Trend reports in Report Builder are based on current point-in-time data, not historical snapshots. The report reflects the state of records as they exist today, distributed across their date fields.

This means:

* A learner who enrolled in January but later unenrolled may not appear in the January enrollment trend
* A user group that was reorganized won't reflect its historical membership in the past months
* Deleted records may not appear in the trend for the period they were active

Use trend reports for directional analysis. For precise historical records or audit purposes, use the existing fixed reports or Job API exports.
