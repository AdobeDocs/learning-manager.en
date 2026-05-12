---
description: getAbstract connector in Adobe Learning Manager
jcr-language: en_us
title: getAbstract connector
contentowner: mmanuel
---

# getAbstract connector for Adobe Learning Manager

## Introduction

The **getAbstract connector** is designed for enterprise customers of [getAbstract.com](https://www.getabstract.com/). It enables learners to discover and consume getAbstract content directly through Adobe Learning Manager. The connector also allows administrators to import user engagement data and track learner completion records automatically.

Adobe Learning Manager wants to oﬀer learners ongoing, self-directed learning opportunities focused on leadership and soft skills. Rather than developing all content internally, the administrator connects the organization's getAbstract account to Adobe Learning Manager using the getAbstract connector.

- Automatically imports getAbstract content into Adobe Learning Manager.
- Tracks learner consumption of courses and learning paths.

This article outlines the steps to configure and manage the getAbstract connector in Adobe Learning Manager.

## Prerequisites

- Ensure the **Migration** feature is enabled for your account before configuring the connector.
- Obtain the **Client ID** and **Client Secret** from your getAbstract account representative. These credentials are required to retrieve course metadata and user consumption data.

## Configure the getAbstract connector

The getAbstract connector enables Adobe Learning Manager administrators to enhance the learning experience by integrating high-quality, curated content from getAbstract.

To configure the getAbstract connector:

1. Log in as an integration admin.
2. Select **getAbstract** on the home page.
3. Select from the following options on the **Connector** tile:

   - **Getting Started**: Overview of the connector.
   - **Connect**: Create a new connection.
   - **Manage Connections**: View or modify existing connections.

   ![](assets/getabstract-connector1.png)
   _getAbstract tile shows three options for configuration_

## Create a new connection

To create a new connection:

1. Select **Connect**.

   ![](assets/getabstract-connector2.png)
      _Select Connect on getAbstract tile to create a new connection_

2. Type a **Connection Name**.
3. Type the **Client ID** and **Client Secret**.

   ![](assets/getabstract-connector3.png)
   _Type the connection, client ID, and client secret on the getAbstract connection page_

4. Select **Save** to create the connection.

## Manage getAbstract connector

Before importing data, you must configure the connector and set up a synchronization schedule. Once configured, the connector automatically pulls usage data, enabling you to monitor learner progress and include getAbstract content in learning plans and reports.

### Enable the connection

To enable the connection:

1. Select **Manage Connections** on the **getAbstract** tile.

   ![](assets/getabstract-connector4.png)
      _Manage connections to configure and schedule the data import_

2. Select the connection.
3. Select **Configure** on the left navigation pane.
4. Select **Enable Connection** and then select **Save**.

   ![](assets/getabstract-connector5.png)
      _Enable the connection to import the data from getAbstract to Adobe Learning Manager_

### Edit the connection

To edit the connection:

1. Select **Manage Connections** on the **getAbstract** tile.
2. Select the connection.
3. Select **Configure** on the left navigation pane.
4. Select **Edit** to update the **Client Id** and **Client Secret**.

   ![](assets/getabstract-connector6.png)
      _Edit the credentials including client ID and client secret_

5. Select **Save**.

### Schedule synchronization

To schedule synchronization:

1. Select **Manage Connections** on the **getAbstract** tile.
2. Select the connection.
3. Select **Configure** on the left navigation pane.
4. Select **Enable schedule** under the **Schedule synchronization** section.

   ![](assets/getabstract-connector7.png)
      _Schedule the data import from getAbstract to Adobe Learning Manager_

5. Select the start date and time in UTC.
6. Type the number of days after which the synchronization should repeat.
7. Select **Save**.

The synchronization settings are saved. The connector will run on the schedule and import data from getAbstract into Adobe Learning Manager.

## Run on-demand synchronization

The **On-Demand Synchronization** option lets you manually import data from getAbstract into Adobe Learning Manager. This is useful when you want to update learner activity data immediately, without waiting for the next scheduled sync.

To run on-demand data import:

1. Select **Manage Connections** on the **getAbstract** tile.
2. Select the connection.
3. Select **On Demand Execution** from the left pane.
4. Select **Start Date**.

   ![](assets/getabstract-connector8.png)
      _Run the on-demand request for immediate data import from getAbstract to Adobe Learning Manager_

5. Select one of the following options:

   - **Disable access to Adobe Learning Manager during execution**: Recommended if synchronization may cause downtime.
   - **Enable access to Adobe Learning Manager during execution**: Recommended to avoid service disruption.
6. Select **Execute** to import all data from the start date to the present.

### View execution history

The **Execution Status** page lists all sync runs in order. If a run has errors, a warning icon appears. You can check the error log, fix the CSV file, and rerun the latest sync if needed.

To view the execution history:

1. Select **Execution Status** in the left pane.
2. You can see the following columns:
   - **Run**
   - **Start Date**
   - **Duration**
   - **Type** (Scheduled or On-Demand)
   - **Status** (In Progress or Complete)

   ![](assets/getabstract-connector9.png)
      _View the execution status of the on-demand and scheduled imports_

>[!NOTE]
>
>If you delete and re-create a connection, execution history for the previous runs will still be visible. You can only re-run the latest synchronization.

### Requirements for successful synchronization

To ensure synchronization works correctly:

- A valid user feed file must be in the getAbstract FTP folder for the specified synchronization dates.
- The file should follow the naming format:
  - report_export_yyyy_MM_dd_HHmmss.xlsx or,
  - report_export_yyyy_MM_dd.xlsx

Download a [sample getAbstract user feed file](https://experienceleague.adobe.com/docs/learning-manager/assets/report-export-20170401175342.xlsx?lang=en) to understand the format.
