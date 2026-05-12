---
description: Learn how to integrate Power BI connector with Adobe Learning Manager
jcr-language: en_us
title: Power BI connector
contentowner: mmanuel
---

# Power BI connector in Adobe Learning Manager

## Introduction

The Power BI connector allows you to integrate Adobe Learning Manager with Microsoft Power BI (commercial license) so you can analyze, visualize, and share your learning data.

With this integration, the integration administrator can automatically export live data sets such as learner transcripts, user skills, and xAPI activity reports directly to a selected Power BI workspace.

Once connected, you can use Power BI's full capabilities to create custom dashboards and reports. This helps your organization gain deeper insights into learner progress, skill achievements, and training effectiveness and make informed decisions based on real-time learning data.

>[!NOTE]
>
>Adobe Learning Manager supports integration only with the commercial version of Microsoft Power BI. Integration with the Government Cloud version is not supported.

## Prerequisites

- Only Microsoft Power BI with a **commercial license** is supported.
- Ensure you have permission to create Power BI apps and workspaces.
- Obtain your **Tenant Name**, **App Client ID**, **App Client Secret**, and **Workspace ID** (optional).

## Configure the Power BI connector

To connect ALM with Power BI:

1. Log in to Adobe Learning Manager as an integration administrator.
2. Hover over the **Power BI** connector tile and select **Connect**.

    ![](assets/power-bi-connector1.png)
    _Select Connect to configure Power BI connector_

3. Type the following details:

   - Client Id
   - Client Secret
   - Tenant name
   - Workspace Id (optional)

    ![](assets/power-bi-connector2.png)
    _Type the required details to configure Power BI_

4. Select **Connect**.

## Register the Power BI app

To register the Power BI app:

1. Go to [Register the Power BI app](https://app.powerbi.com/embedsetup).
2. Select **Embed for your organization** and log in to your Microsoft account.
3. Type a name for your app.
4. Select **Server-side Web app** under **App type**.
5. In the **Redirect URL** section, select **Use a custom URL** and type [this URL](https://learningmanager.adobe.com/ctr/app/azure/_callback): (Replace the domain if needed for your environment.)
6. In the **Home URL** field, type [this URL](https://learningmanager.adobe.com/).
7. In the **Permissions** section, select **Read All data sets** and **Read and Write all data sets**.
8. Contact your Power BI administrator to get the **Tenant Name**.
9. If you do not have a Workspace ID, create a workspace in Power BI (requires Power BI Pro) and copy the ID from the URL.
10. Select **Register app** and save the **Client Id** and **Client Secret** for later use.

>[!NOTE]
>
>If you need to reauthorize the connection later, create a new Power BI app and use the correct redirect URL for your environment.

## Export reports to Power BI

After configuring the connection, you can export these reports:

- **Learner Transcripts**
- **User Skills**
- **xAPI Activity Reports**
- **Unified Reports** (a combination of multiple reports)

### Learner transcript

#### Schedule exports

1. Select **Learner Transcripts** in the left panel.
2. Select **Enable Schedule** on the Export page.
3. Select the **start date** and **time**.
4. Define the **interval** for how often the export should repeat (daily, weekly, etc.).

    ![](assets/power-bi-connector3.png)
    _Enable the schedule export for learner transcript_

5. Select **Save**.

#### Export on demand

- You can generate reports manually by specifying the **start date** and running an on-demand export.
- The report will include data from the specified date to the present.

### User skills

#### Schedule exports

1. Select **User Skills** in the left panel.
2. Select **Enable Schedule** on the Export page.
3. Select the **start date** and **time**.
4. Define the **interval** for how often the export should repeat (daily, weekly, etc.).

    ![](assets/power-bi-connector4.png)
    _Enable the schedule export of user skills report_

5. Select **Save**.

#### Export on demand

- You can generate reports manually by specifying the **start date** and running an on-demand export.
- The report will include data from the specified date to the present.

### Manage xAPI activity reports

**xAPI statements** can also be exported to Power BI.

#### Configure xAPI exports

1. Select **Export xAPI Activity Report**.
2. Select **Configuration** in the left pane.

   - Fill in JSON path fields to match your CSV columns.
   - Select **Add** to include more paths.
   - Use **Edit** to update fields.
3. Select **Save**.

#### Schedule exports

1. Select **Configure Schedule**.
2. Select **Enable xAPI statements export using this connection**.
3. Set the **start date**, **time**, and **interval**.
4. Select **Save**.

#### On demand export

1. Select **On Demand**.
2. Specify the **start date**.
3. Select **Execute**.

>[!NOTE]
>
>If some xAPI statements in the Learning Record Store (LRS) lack configured JSON paths, their values will appear as N/A in Power BI.

#### View execution status

- Use **Execution Status** to view the history of exports, including start time, duration, and status.
- A warning icon indicates failed runs. Click the link to download error reports as .CSV.

### Unified reports

**Unified Reports** combine data from:

- Learner Transcript
- Gamification
- Feedback Report
- Login/Access
- User Skill
- User Report
- Training Report

This helps you create more powerful dashboards by merging data in Power BI.

#### Create unified report configuration

1. Select **Unified Reports** and then select **Configuration**.
2. Type a unique name in the **Data Set Name** field.
3. Select one or more reports you want to include in this dataset under **Select Reports for Data Export**.

   - Learner Transcript
   - Login/Access
   - Training Report
   - Gamification
   - User Skill
   - Feedback Report
   - User Report
4. Use the **Add user group filters** field to select which user groups' data you want to export. By default, **All Users** is selected.
5. Use the **Add Content Catalog Filters** field to filter reports by content catalog.
6. The filter table shows which reports support **User group**, **Catalog**, or **Time** filters.

    ![](assets/power-bi-connector5.png)
    _Create a configuration for unified reports_

7. After selecting reports and filters, select **Save** at the upper right.

#### Filter learner transcripts by status

- **All:** All records in the date range
- **Completed:** Only completed learning activities
- **In Progress:** Only ongoing activities
- **Not Started:** Excludes records not yet started
- **Unenrolled:** Includes unenrolled records

## Download Power BI Templates

Adobe provides ready-made Power BI templates to help you get started quickly.

- Download templates, import your reports, and customize as needed.
- Use templates to create compelling dashboards without starting from scratch.

## Learning Path related settings

How **Learning Paths** appear in your reports depends on your admin settings:

- **Existing Connections:**

  - If **Learning Path** is disabled, no related rows or columns are included.
  - If enabled, the report includes the Learning Path (Higher Level) for enrolled learners.

- **New Connections:**

  - If Learning Path is disabled, columns show:

    - **Embedded Path:** Learning Program name.
    - **Embedded Path ID:** ID for the Learning Program.
    - **Embedded Course ID:** IDs of courses within the Learning Path.
  - If enabled, the **Type** column uses Learning Path (Higher Level) where relevant.
  - For new connections, changes apply after 30 days.

### Where to See Your Data**

All exported data appears as datasets under your Power BI account. Use these to build custom dashboards and visualizations.
