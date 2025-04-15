---
jcr-language: en_us
title: Add users in bulk
description: Learn to add multiple users at a time.
contentowner: saghosh
exl-id: c3309ce5-8764-452e-82d5-5637c23c661b
---
# Add users in bulk

In this training, you will learn how to add users in bulk through a CSV. 

[![button](feature-summary/assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/7555555)

If you're unable to launch the training, write to <almacademy@adobe.com>.

## How to add multiple users

You can add multiple users at a time by following the below steps:

1. Click **[!UICONTROL Users]** on the left pane in Administrator login, and then click **[!UICONTROL Add]** > **[!UICONTROL Upload a csv]**. A pop-up dialog appears.   

1. You can add multiple users using a .CSV file. Click **[!UICONTROL Import]** and select/open the .csv file from your computer.   

1. After importing the file, map the contents of .csv file with the application labels when you upload .csv file first time.

   For all the subsequent uploads, previous settings for labels are considered. Click **[!UICONTROL Save]** after completing the mapping of data and click **[!UICONTROL Add]** to upload the mapped .csv file.

1. Click **[!UICONTROL Save]** after completing the mapping of data and click **[!UICONTROL Add]** to upload the mapped .csv file.

## CSV upload with mandatory fields {#csvuploadwithmandatoryfields}

It is not mandatory to add user's profile and Manager's email-id in the CSV. User name and the user's email-id are the only mandatory fields.

In this case, by default your company's Administrator is treated as the Manager for users. By default, employee is considered as user's profile.

>[!NOTE]
>
>To add new users, create a new CSV file with their details and upload it. Updating and re-uploading an existing CSV file is not supported.

**Sample CSV**

Learning Manager sample CSV is available below with mandatory fields.
[Sample-CSV-name-email.zip](assets/sample-csv-name-email.zip)

## CSV upload with all the fields {#csvuploadwithallthefields}

Before including Manager's email-id for any employee, ensure that the Manager is first added as an employee in CSV. For example, refer to the employee name, Howard Walters in the snapshot below:

![](assets/csv-example.png)

*CSV template for upload*

Also, Administrators of an organization can add **themselves** as employees and mention their Manager's email-id as root.

**Sample CSV**

Learning Manager sample CSV is available below with all the fields.
[learning-manager-sample-csv.zip](assets/learning-manager-sample-csv.zip).

Refer to  [Using CSV upload](/help/migrated/administrators/feature-summary/add-users-user-groups.md) feature help content for more information.
