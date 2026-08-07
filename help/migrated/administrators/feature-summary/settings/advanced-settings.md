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

Content folders in Adobe Learning Manager control which authors can see and access content in the Content Library. With hierarchical content folders, administrators can organize large content libraries into up to three levels of nested private folders, making content easier to find, manage, and reuse across your organization.

### What is a content folder

A content folder is a container that groups related content and determines who can access it. Every content file in Adobe Learning Manager belongs to at least one folder at all times.

There are two types of content folders:

**Public folder**- present in every account by default. The public folder has these properties:

* All authors in the account can access content in the public folder.
* Content in the public folder cannot be in any private folder. The reverse is also true. Content in a private folder cannot be in the public folder.
* The public folder is not part of role-based access configuration. Restricting a custom role to specific private folders does not restrict access to the public folder.

**Private folders**- created by administrators. Private folders support a three-level hierarchy, and their access is controlled through role configuration.

**Understand folder hierarchy levels**

Private content folders support up to three levels of nesting:

* **Level 1 folders**- top-level folders at the root of your content library

* **Level 2 folders**- subfolders nested inside a Level 1 folder

* **Level 3 folders**- subfolders nested inside a Level 2 folder

This structure gives organizations the flexibility to mirror real-world content organization, by topic area, delivery type, audience, or team, rather than managing thousands of files in a flat list.

>[!NOTE]
>
>Only administrators can create, edit, or delete folders at any level. Custom administrators with access to any root level folder can creat, edit, or delete folders under that root folder.


### Folder naming rules

Folder names must be unique within the same level under the same parent folder. Specifically:

| **Scenario**                                                                                 | **Allowed?**             |
|----------------------------------------------------------------------------------------------|--------------------------|
| Two Level 1 folders with the same name                                                       | No                       |
| Two Level 2 folders under the same Level 1 folder with the same name                         | No                       |
| Two Level 2 folders under different Level 1 folders with the same name                       | Yes                      |
| A Level 2 folder and a Level 3 folder with the same name                                     | Yes. Levels are distinct |
| A Level 3 folder and another Level 3 folder under the same Level 2 folder with the same name | No                       |


### How folder paths appear

The Content Library displays each content file's full folder path. For example, **Training Programs** / **Onboarding** / **SCORM Assets**. This path shows the complete location of the content.

If a file exists in more than one folder, all paths appear separated by commas. If a path is long, it is truncated from the beginning with an ellipsis (…), and the deepest folder name is always shown.

### Role-based access to folders

Access to private folders is assigned at **Level 1 only**. When a custom role is granted access to a Level 1 folder, that access automatically cascades to all Level 2 and Level 3 subfolders within it. There is no option to grant access at the subfolder level independently.

The following table describes what each role can do with the folder hierarchy.

| **Role**        | **What they can do**                                                                                                                                      |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Administrator   | Create, rename, and delete Level 1, Level 2, and Level 3 private folders; configure Level 1 folder access for custom roles                                |
| Custom admin    | Manage folders within accessible Level 1 branches, subject to their assigned privileges                                                                   |
| Author          | Browse folders, filter content by folder, add content to folders, copy and move content between folders, select content when adding modules to a course   |
| Custom author   | Same as the author, but limited to folders accessible through their assigned Level 1 privileges                                                           |

### Folder structure limits

| **Limit**                             | **Value** |
|---------------------------------------|-----------|
| Level 1 folders per account           | No limit  |
| Level 2 subfolders per Level 1 folder | 25        |
| Level 3 subfolders per Level 2 folder | 25        |
| Maximum folder depth                  | 3 levels  |


<!--
### Folder selection behavior

When you select a folder, for example, when filtering or deleting, the selection cascades through the hierarchy as follows:

* Selecting a **Level 1 folder** automatically selects all Level 2 and Level 3 folders under it.

* Selecting a **Level 2 folder** automatically selects all Level 3 folders under it. Other Level 2 folders under the same Level 1 folder are not selected.

* Selecting a **Level 3 folder** selects only that folder. No other folders are selected.

>[!NOTE]
>
>When you select a subfolder without selecting its parent, the parent folder does not display a partial or mixed selection indicator. This is intentional. Because a parent folder can itself contain content, not just subfolders. Selecting a parent folder means "include all content in this folder and everything beneath it." A partial indicator would suggest the parent folder's own content is partially included, which would be misleading. If you want to filter by a specific subfolder only, select that subfolder directly. If you want all content in a parent folder and its subfolders, select the parent folder.
-->

### When to use a hierarchical folder structure

Hierarchical content folders are particularly valuable when your organization manages many content files and needs a structured way to navigate, reuse, and control access to them.

Common scenarios include:

* **Large content libraries**: When you have thousands of content files, a three-level hierarchy lets authors navigate directly to what they need, rather than scrolling through a flat list.

* **Multiple teams or projects**: Level 1 folders can separate team or project areas; Level 2 folders can be organized by delivery type; Level 3 folders can hold individual assets.

* **Role-based content separation**: When different author teams should access only the content relevant to their work, the Level 1 folder access assignment keeps each team's content private.

### Real-world use cases of hierarchical content folders

**Use case 1- Compliance training with jurisdiction-specific content**

A global organization runs mandatory compliance training across multiple regions. Each region has core modules that apply to everyone plus jurisdiction-specific legal addendums, like data privacy regulations, local labor law, financial disclosure requirements, that vary by country or region.

Without hierarchical folders, all compliance assets sit in a flat list, making it hard for regional content teams to know which files belong to which program or jurisdiction.

With a three-level structure:

* Level 1: Compliance Training

* Level 2: EMEA / APAC / Americas (one subfolder per region)

* Level 3: Specific modules or assets per region (Privacy Regulation PDFs, Local Policy Decks, Assessment files)

In cases of regional authors, being a custom role, only level 1 folder can be selected during custom role creation. Level 2 folder selection is not an option. They can find, update, and reuse only the assets relevant to their jurisdiction without seeing or accidentally modifying another region's content.

**Use case 2- Large-scale onboarding program with many roles**

An organization onboards thousands of employees per year across several distinct roles: individual contributors, managers, contractors, and technical specialists. Each role has its own onboarding track with shared foundational content and role-specific modules.

With a three-level structure:

* Level 1: Onboarding

* Level 2: Role (Individual Contributor / Manager / Contractor / Technical Specialist)

* Level 3: Module type (SCORM packages / ILT decks / Activity guides / Assessments)

Authors building courses for each role navigate directly to Level 2 and find the exact files for that track. When a module is reused across roles, such as a company values video, it can be copied or linked into multiple folders without creating duplicates. The content stays single-source but appears in all the relevant branches.

**Use case 3- High-volume technical skills library with multiple content teams**

A technology company maintains an internal skills training library with thousands of content files across product lines, cloud infrastructure, developer tools, security, and data engineering. Multiple author teams contribute, each responsible for one product area. Course modules can run 40–60 files per course.

Without hierarchy, all thousands of files sit in a handful of top-level folders, and authors from different teams frequently pick the wrong file version or accidentally overwrite shared assets.

With a three-level structure:

* Level 1: Product Area (Cloud / Dev Tools / Security / Data Engineering)

* Level 2: Course Name

* Level 3: Asset Type (Videos / PDFs / SCORM / Quizzes)

Each product team is granted access only to their Level 1 folder. Finding a specific quiz for a specific course means navigating to exactly the right Level 3 folder rather than searching across thousands of files. When the security team updates a SCORM package, they know it lives in Security > [Course Name] > SCORM and can't accidentally land in another team's branch.

### Manage content folders as an administrator

As an administrator in Adobe Learning Manager, you create and maintain the content folder hierarchy, control which custom roles have access to specific folders, and manage folder names and deletions. Authors can add content to folders and organize content within the hierarchy, but only administrators can create, rename, or delete folders.

#### Create a content folder

>[!NOTE]
>
>Two folders at the same level under the same parent cannot share a name. The same name is allowed in different branches or at different levels.

1. Sign in to Adobe Learning Manager as an administrator.
2. In the left navigation, select **Configure** > **Settings**.
3. Under the **Advanced** section, select **Content Folder**.
4. Select **Add** in the upper-right corner of the page. The **Add New Folder** dialog opens.
5. Enter a name and an optional description for the folder.
6. Select **Save**. The folder is created and appears in the folder list.


#### Create a sub-folder

1. On the **Content Folder** page, locate the parent folder.
2. Select the **Create subfolder** option next to the folder name.
3. Enter a name and an optional description for the subfolder.
4. Select **Save**. The subfolder appears indented below its parent in the folder list.

>[!NOTE]
>
>Each folder can contain up to 25 direct subfolders. Level 3 is the maximum depth. You cannot create a subfolder inside a Level 3 folder.

#### Rename a folder

1. On the **Content Folder** page, select the folder you want to rename. The folder opens in edit mode.
2. Update the folder name and, if needed, the description.
3. Select **Save**. The folder is saved with the new name.

#### Delete a folder

Before deleting, be aware of the following rules:

* You can delete an empty folder at any level.
* Only empty folders can be deleted. Folders that contain content cannot be deleted, regardless of whether the content is linked to other folders or not.
* Deleting a parent folder deletes all its subfolders, provided the folder and all of its subfolders are empty. Selecting a parent folder automatically selects all its children.

#### Delete the parent folder

1. On the **Content Folder** page, select the checkbox next to each folder you want to delete.
2. Select **Actions** > **Delete Folder** in the upper-right corner of the page.
3. Confirm the deletion when prompted. All subfolders inside the parent folders are also deleted.

#### Delete a sub-folder

1. On the **Content Folder** page, select the checkbox next to the subfolder you want to delete.
2. Select **Actions** > **Delete Folder** in the upper-right corner of the page.
3. Confirm the deletion when prompted. The subfolder is deleted.

#### Configure folder access for custom roles

You can restrict custom roles to specific Level 1 folders so that custom administrators and authors with those roles see only the content relevant to them.

Access is set at the **Level 1 folder level only**. When you grant a custom role access to a Level 1 folder, that role automatically gains access to all Level 2 and Level 3 subfolders inside it. You cannot assign access at the subfolder level independently.

1. In the left navigation, select **Users** > **Custom Roles**.
2. Open the custom role you want to configure or create a new one.
3. Under **Account Privileges**, locate the **Content Folders** section.
4. Select **Selected Folders**.
5. Select the Level 1 folders this role should have access to.
6. Select **OK**.

Users with this role see only the content in the selected Level 1 folders and their subfolders. Content in other private folders and in the public folder remains inaccessible to them.

#### Best practices

The following practices help you build a folder structure that scales well and remains easy to navigate.

1. **Plan your structure before creating folders.** Once content is organized into a hierarchy, restructuring requires moving large volumes of content. Decide on your Level 1 categories, such as product lines, departments, or training programs, before you begin.

2. **Use three levels for meaningful groupings.** A common pattern is: Level 1 for a broad domain or program, Level 2 for delivery type or team, Level 3 for individual assets. For example:

    * Level 1: Sales Training

    * Level 2: Self-Paced Modules

    * Level 3: PDF Assets

3. **Keep names short, descriptive, and unique within their parent.** Avoid generic names like "Module 1" or "Content." Use identifiers that make sense to the authors browsing the library.

4. **Assign custom role access at Level 1 only.** Because access cascades automatically, assigning at Level 1 is sufficient and keeps access management simple. You do not need to update access when you add Level 2 or Level 3 subfolders.

<!--

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
-->

## Holidays

The **Holidays** setting in Adobe Learning Manager lets you define organization-wide holidays. Holidays appear on the Instructor calendar as non-working days, affecting instructor availability when scheduling Live
Hub sessions.

### Key points

Holidays are a set of non-working days maintained at the account level, with the following properties:

- Only the Administrator can add, edit, or delete holidays.

- Holidays apply organization-wide and appear on every instructor's calendar as non-working days.

- Because holidays mark instructors as unavailable, Live Hub sessions cannot be scheduled on those dates.

- Each holiday requires a date and a name; a description is optional.

- You can add holidays one at a time or import multiple holidays at once using a CSV file.

- Once added, holidays appear on the **Holidays** page, where you can view, search, and manage them.

View [Manage Holidays](../../../getting-started-with-live-hub/manage-holidays.md) for more information.

## Classroom Locations

Create and manage a library of physical or virtual classroom locations. These locations can be used by authors and administrators to set up instructor-led training (ILT) events. The feature ensures that classroom details, such as seat limits and location information, are pre-configured and easily accessible.

See [Add classroom locations in Adobe Learning Manager](/help/migrated/administrators/feature-summary/classroom.md) for more information.

## Reports

This section allows you to configure Compliance and Group Success dashboards. 

![alt text](assets/advanced-settings-picture2.png)
 
See the following for more information:

* [Compliance Dashboard](/help/migrated/administrators/feature-summary/reports.md#compliance-dashboard)
* [Group Success Dashboard](/help/migrated/administrators/feature-summary/group-success-dashboard.md)
