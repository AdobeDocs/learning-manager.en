---
jcr-language: en_us
title: Report Builder  
description: Introduction to Report Builder
contentowner: mmanuel
---

# Report Builder in Adobe Learning Manager

Build and download custom reports with the columns, filters, and data you choose, without post-processing using any tool.

Adobe Learning Manager's Report Builder gives administrators a self-serve reporting canvas to create exactly the reports they need. Instead of downloading a fixed report and reshaping it in a spreadsheet tool, you select the columns you want, apply filters, and download a clean output, all from one place.

## Why was Report Builder introduced

Existing reports in Adobe Learning Manager are fixed. Each report has a set list of columns you can't change, and filtering options are limited. Administrators who needed custom output had to download multiple reports, join them in Excel, manually apply filters, and repeat the process every week or month.

Report Builder removes that cycle. You configure a report once, save it, and download fresh data whenever you need it, no reshaping required.

Three specific problems Report Builder solves:

* **Fixed columns:** Existing reports include many columns you may not need and exclude ones you do. Report Builder lets you pick only the fields relevant to your use case.  
* **Limited filtering:** You can now filter on any supported field. For example, including enrollment date, completion date, active fields, and catalog labels, not just status.  
* **Inconsistent data sources:** Existing reports can be pulled from the UI, Job API, or connectors, which may return slightly different data depending on timing. Report Builder pulls from a single, consistent data source, so every download reflects the same underlying data.  

## How Report Builder fits with existing reports

Report Builder does not replace the existing fixed reports in Adobe Learning Manager. Both are available. Use existing reports for standard outputs you already rely on. Use Report Builder when you need custom columns, specific filters, or data that currently requires post-processing.

## Where to find Report Builder

Report Builder is available on the administrator homepage. Select **Reports**, then select **Report Builder**. You'll see two tabs: **Templates** and **Reports**.
![](assets/report-builder-001.png)

## Who can use Report Builder

Report Builder is available to administrators.

>[!NOTE]
>
>Report Builder needs to be enabled for accounts. Contact your Adobe account team or CSM if you don't see it in your admin view.

## Best practices

* Start with a template if you're new to Report Builder. Templates are pre-built for the most common use cases and work immediately.  
* Save every configured report before downloading. Saved reports can be downloaded again later without reconfiguration.
