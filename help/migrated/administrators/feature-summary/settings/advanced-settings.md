---
description: Learn more about configuring Advanced settings in Adobe Learning Manager
jcr-language: en_us
title: Advanced settings in Adobe Learning Manager
exl-id: 7047c89f-5f1c-4e0a-a908-20ef0eb9667d
---
# Advanced settings in Adobe Learning Manager

## Catalog labels

Catalog Labels in Adobe Learning Manager are used to tag learning objects (courses, certifications, learning paths, etc.) with specific fields and values. These labels help you and authors categorize and organize content effectively, enabling better filtering, tracking, and reporting.

See [Catalog labels in Adobe Learning Manager](/help/migrated/administrators/feature-summary/catalog-labels.md) for more information.


>[!NOTE]
>
>* Mandatory labels: You can choose to make catalog labels mandatory for authors during course creation.
>* Author workflow: Authors must add compliance labels while creating or editing courses to ensure proper categorization.

## Content Folder

Content folders allow you to organize and manage content by creating private or public folders. This functionality ensures that content is accessible only to specific authors or groups, providing better control over content visibility and management.

**Key points:**

A folder is a repository of content, which is a subset of the entire content library available in an account with the following properties:

* Only you (administrator) can create, edit, or delete a folder.
* You can control access to folders as part of defining roles only for custom administrators.
* Content must at all times be associated with at least one folder. To start with, all content will be associated with the public folder, which can later be changed.
* Content can be associated with multiple folders at the time of creation, which will also be possible by a copy operation
* All folder names must be unique within the account, otherwise there will be an error in naming a folder.

Folders only control visibility of content and don't create copies of content. Therefore, editing content will reflect in all the associated folders.

**Public folder**

A public folder is always present in an account and initially, all content will be part of this folder. Later, authors can move content out of this folder into other folders. A public folder has the following properties:

* All content associated with this folder will be accessible to all types of authors, by default.
* Any content that is a part of a public folder, cannot be part of any other folder. The converse also holds true.

This folder cannot be part of configurable role definition. Consequently, not having a public folder in configurable role definition doesn't restrict access to a public folder.

**Private folder**

Any folder created by you is a private folder.

**Add a content folder**

To add a content folder, follow the steps:

1. Select **[!UICONTROL Settings]** > **[!UICONTROL Content Folder]**.
2. Select **[!UICONTROL Add]** to create a new folder.
3. Type the name and description of the folder to be created.
 
    ![alt text](assets/advanced-settings-picture1.png)

4. Select **[!UICONTROL Save]** to create the folder.

**Folder operations**

* **[!UICONTROL Add a folder]**: To add a folder, select the folder, and then select **[!UICONTROL Add]** on the upper-right corner of the screen.
* **[!UICONTROL Delete a folder]**: To delete a folder, select the folder to delete, select the **[!UICONTROL Actions]** menu, and then select **[!UICONTROL Delete Folder]**.

## Classroom Locations

Create and manage a library of physical or virtual classroom locations. These locations can be used by authors and administrators to set up instructor-led training (ILT) events. The feature ensures that classroom details, such as seat limits and location information, are pre-configured and easily accessible.

See [Add classroom locations in Adobe Learning Manager](/help/migrated/administrators/feature-summary/classroom.md) for more information.

## Reports

This section allows you to configure Compliance and Group Success dashboards. 

![alt text](assets/advanced-settings-picture2.png)
 
See the following for more information:

* [Compliance Dashboard](/help/migrated/administrators/feature-summary/reports.md#compliance-dashboard)
* [Group Success Dashboard](/help/migrated/administrators/feature-summary/group-success-dashboard.md)
