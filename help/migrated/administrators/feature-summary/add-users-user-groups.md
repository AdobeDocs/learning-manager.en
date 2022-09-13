---
description: Learn how to add users or user groups in Learning Manager application.
jcr-language: en_us
title: Add users and create user groups
contentowner: manochan
---


# Add users and create user groups {#add-users-and-create-user-groups}

Learn how to add users or user groups in Learning Manager application.

![](assets/user-mgmt-new.png) 

## Overview {#overview}

In Adobe Learning Manager, you can assume the following roles:

* **Administrator:** An Administrator defines the training strategy for the organization. An Administrator can add learners, search required skills for learners, manage and assign courses, create learning plans, certifications, and learning programs, and manage reports for the entire organization.
* **Author:** Authors are Instructional Designers and content creators. An Author can add modules and courses to Learning Manager.
* **Manager:** A Manager manages the learning activities of a team. A Manager can nominate team members to take a course, approve requests from team members, and provide feedback on performance of their team members post-completion of training. Managers can also view reports for their team to track their performance.
* **Learner:** Learners can access courses, learning programs, and certifications assigned to them. Learners can also browse through all the available courses by using a catalog and enroll themselves for either courses, learning programs, or certifications.

As an Administrator, you can add users in three ways:

* Internal
* External
* User groups

## Add a single user {#addasingleuser}

To add users,

1. Log into Adobe Learning Manager as an Administrator. 
1. On the home page, click **Add Users**. On this page, you can add a single user or multiple users at a time using a CSV. You can also create a self-registration link for internal employees or create an external learner profile.
1. To add a single user, click **Add** on the upper-right corner and choose the option **Single User**.

   ![](assets/single-user.png)

1. On the **Add User** dialog, enter the details of the learner. For the field **Manager's Name**, pick the name of an existing user in the system.

   ![](assets/manager.png)

1. To add the new user in Prime, click **Add**. After the user is added, the user receives a verification mail. The Learner then activates the account and starts using Learning Manager. This workflow is helpful if you need to add limited number of learners to your Prime Account. But if you're planning to enroll all the employees of a large organization, you can add them in a singe attempt. For more information, see the next section.

## Add users in bulk {#addusersinbulk}

Typically, most organizations work with an HR Management System (HRMS), which maintains all employee records, such as, designation, location, date of joining, or employee hierarchy. You can export this data in a CSV format. To import a CSV, follow the steps below:

1. Click **Add** on the upper-right corner, and choose the option **Upload a CSV**.

   ![](assets/upload-a-csv.png)

1. The CSV that you upload consists of the fields, as shown below:

   ![](assets/csv.png)

   You must maintain a master CSV and perform perform all additions and deletions on the master CSV. The master CSV contains the following fields:

   * name &#42;
   * email &#42;
   * profile
   * manager

   (&#42;) Required field.

1. After you click the option **Upload a CSV**, the following dialog displays.

   ![](assets/upload-a-csv-dialog.png)

1. Choose the CSV or drag-and-drop the file. After you've chosen the file, map the data fields with the ones in the CSV file. Click the required drop-down and choose the right field.

   ![](assets/map-data-fields.png)

1. To start importing the users, click **Save**. You can see a confirmation message.

   ![](assets/save-csv.png)

1. The new users are now added to your Adobe Learning Manager account. To select the new users, select the check-box next to the names so that everybody is selected. 

   ![](assets/select-new-users.png)

For more information, see the FAQ, [***Add users in bulk***](../add-users-in-bulk.md).

After you have selected the users, you can perform the following:

## Register a user {#registerauser}

With the user selected, click **Actions** on the upper-right corner and click **Register**.

The selected users receive a Welcome email. If the learners have an existing Adobe ID, they can click this link. If they don't have an existing Adobe ID, they can go ahead and click the Welcome link to create an Adobe ID and link it to their Prime account.

## Assign a role {#assignarole}

After adding learners to the Adobe Learning Manager account, if you want to change their roles, click Actions on the upper-right corner of the page. Choose the option **Assign Role**. Here you can decide whether you want to give Author access or Admin access to the learner. After you have assigned a role, this learner has Author access to the account and can add modules and create courses. 

![](assets/assign-a-role.png) 

## Remove a role {#removearole}

You can also remove Author or Admin access for the users. Select one or more learners, click **Actions**, and select **Remove Role**. Choose an option, for example, **Remove Author**, and the author access gets revoked for this learner. 

You cannot manually assign a Manager role to someone in the system. They automatically get access to the Manager dashboard when one or more employees are added under them.

## Delete a user {#deleteauser}

To delete a user, click **Actions**, and choose **Delete User**. On the confirmation dialog, click **Yes**, and the learner gets deleted.

![](assets/delete-a-role.png) 

## Edit a user {#editauser}

On the list of users, choose a user, and click the user. On the user details, click the **Edit** ( ![](assets/edit-pen.png)) button. On the **Edit User** dialog, make the necessary edits and to save the changes, click **Save**.

![](assets/edit-user.png) 

## Workflows for active fields and active field values preserving case sensitivity

In this release, Learning Manager preserves the case sensitivity of the user attribute and its value. **For example**, the case sensitivity of a user attribute is 'location' and its value as 'PARIS' will be preserved and displayed in the same manner. In case of any issues, the Administrator can now edit the attribute name and values to correct any case sensitivity errors. 

The Administrator can do this by visiting **Admin app** > **Users** > **User groups** and clicking on the group name.  

Admin can add and update allowed attribute values for a learner through UI.

Types of active fields:

* Groupable: Learners would get grouped on the basis of the Values
* Reportable: Reporting user groups would be created based on the active fields
* Exportable: The fields will be seen in exported in user group report.

## Create a self-registration link {#createaselfregistrationlink}

You can also enable employees in your organization to register themselves as Learners to Adobe Learning Manager Account, without taking help from you as an administrator. The administrator can create a Self-Registration link and share with the employees, who can further register to Prime using their Adobe credentials.

On the upper-right corner of the page, click **Add**, and choose **Self-Registration**.

![](assets/self-registration.png)

The **Add Self-Registration Profile** dialog appears. Give this profile a name. Then add the manager's name. It's important to know that the manager must already be registered Learner in Prime.

![](assets/add-self-registrationprofile.png)

After you click **Save**, a URL gets generated, which you can share with the learners, so that they can click the URL and self-register themselves.

## Enroll external learners {#enrollexternallearners}

In Adobe Learning Manager, you can also create Registration links for external partners or agencies with limited access to your account and provide them learning material.

There are a few differences between internal and external registrations.

| Internal users | External users |
|---|---|
| Log in using Adobe ID or SSO credentials. | Log in using any email ID. |
| Gamification is available. | Gamification is not available. |
| Learner hierarchies are available. | Learner hierarchies are not available. |

To enroll external users, follow the steps below:

1. In the left navigation pane, click **External**.

   ![](assets/click-external.png)

1. On the upper-right corner of the page, click **Add**.
1. On the **Add External Registration Profile** dialog, add the following details:

   * The profile name of the partner organization.
   * The email address of the manager of the partner organization.
   * Seat limit for external enrollment for this partner.
   * Expiry date to set a deadline to stop allowing new registrations to this group. After the Expiry date, only the existing registered users can access this training.

   ![](assets/map-data-fields-2.png)

   * In the Advanced Settings section, enter the following:

     * **Login Requirement:** Specify a value in days. Learners get deleted if they do not login for the above duration.
     * **Allowed Domains:** A comma-separated list of whitelisted email domain names.
     * **Email Verification Required:** Select this option to make email verification mandatory for a learner.

   ![](assets/email-verificationrequired.png)

1. After you click **Save**, you can see the following confirmation message. You must share the URL with your external partner.

   ![](assets/save-and-share-urlwithexternalusers.png)

## Enable an external profile {#enableanexternalprofile}

After an external profile has been created, you must enable its status. From the list of external profiles, choose the required profile, and toggle the status button.

![](assets/choose-required-profiles.png)

This enables the External Enrollment link. A welcome email is automatically be sent to the partner. You can also copy the link and share with them by clicking the Copy URL icon (), or you can resend the welcome email to the partner organization by clicking the Mail icon ().

The partner manager can share the link with the employees who must take the training in Prime. When they click the link, they can self-enroll themselves after filling out some details to create their profile on Prime. These users will not appear on the Learners tab along with the internal employees. You can see their names under the **External Learners** tab.

## Pause an external profile {#pause}

After adding an external user group to Learning Manager, you can also pause the external users' registration process. When you pause, the external users' registration process is blocked. However, this process works only when the users haven't registered yet by accepting the invitation.

To pause the external user groups, choose a group or groups, click **Actions** from the upper-right corner of the page, and click **Pause**.

## Resume an external profile {#resumeanexternalprofile}

At any time, you can always revoke the paused state of an external partner and resume normal services. Click **Actions** at the upper-right corner of the page and choose **Resume**.

The following states are applicable for external users:

* **Inactive state** - In this state, the external users' registration is expired. Administrators set the expiry date for the external users while adding them through the add user workflow.
* **Active state** - In this state, the external users can register to the Learning Manager application, and log in to the application.
* **Pause** - In this state, the registration process for external users is blocked. However, the existing users can continue to log in.

## Check used seats {#checkusedseats}

On the list of external profiles, click **Seats Used**. You can view the number of learners in the partner organization who have been added.

![](assets/seats-used.png) 

## Delete a user {#Deleteauser-1}

Choose a user, and from the upper-right corner, click **Actions > Delete User**.

## Change profile {#changeprofile}

To move a user to another external profile, choose a user, from the upper-right corner, click **Actions > Change Profile**. From the list of profiles, choose a profile, and click **Change**.

## Assign a role {#Assignarole-1}

Choose a user, and from the upper-right corner, click **Actions > Assign Role** > **Make `<role>`**. The user gets a new role.

## Remove a role {#Removearole-1}

Choose a user, and from the upper-right corner, click **Actions > Remove Role** > **Remove `<role>`**. The selected role gets removed from the list of roles that were assigned to the user.

## Search for external users

In the list of external users, search for a user by typing the name of the user in the search bar. The top five matching names will be listed and you can choose any.

## Create user groups {#createusergroups}

A User Group is a set of users who are related to a category. User Groups help administrators to select learners in their organization based on their attributes, and then assign learning content to them. Also, these User Groups enable administrators to assign customized logos and catalogs to learners and show customized reports on their progress.

To access User Groups, on the left navigation pane, click **User Groups**.

![](assets/user-groups.png)

There are two types of groups in Adobe Learning Manager, Custom and Auto-generated. When you add learners to your account, some groups are automatically created based on their common properties.

To see the automatically created groups, click the tab **Auto-generated**.

![](assets/auto-generated.png)

You can see that there are different groups, like All Internal Users, All Managers, groups based on the Cost Center, based on the department, and based on the teams of the managers.

In addition to Auto-generated groups, you can create Custom groups. To add a new Custom Group, on the upper-right corner, click **Add**. 

1. Enter the name, and description for the group.
1. Enter user name or profile in search-as-you-type field and select from the drop-down list, to add users.
1. To add more learners, click **Add More Users.**
1. To create the user group, click **Save**.

This Custom Group is now created and added to the profile. The User Groups that you create are dynamic in nature. If new users are added with similar attributes, they're automatically added to the User Group.

## Exclusion of user groups

At times you would want to exclude a small set of users from a large user group. This is required to enroll this specific set of users into training via Learning Plans or to setup the correct visibility of catalogs. In this release of Learning Manager, you can exclude learners or User Groups when you create a custom user group. In the Add User Group dialog, the Exclude Learners section enables you to achieve so.

![](assets/exclude-user-groups.png)

For example, if you want to set up a Learning Plan so that all users belonging to location = California except Store-5 (located in California) get enrolled. 

## Advanced settings {#advancedsettings}

## Data Sources {#datasources}

You can use this feature when you want to import/sync the users or learning data from your organization's database in to the Learning Manager application. You can also set up the frequency of this sync. 

Click **Data Sources** on the left pane under **Advanced** section. 

![](assets/data-sources-add-users.png)

Choose the data source type from the **Source** drop-down, select the update frequency, and click **Sync now** if you need to sync immediately or click **Save.** Data source types are SFDC, FTP, and so on for internal users. 

You can add multiple data sources. 

## Active Fields {#activefields}

This feature enables administrators to add more active fields in addition to what has been provided during user registration. 

Click **Active Fields** available inside users page. Learners can only choose from the values given in custom values.

![](assets/active-fields.png) 

### Configure Fields {#configurefields}

**Internal users**

You can add custom value for user fields for internal users.

To add  custom values, follow these steps:

1. Click  **[!UICONTROL Modify Values]** for an Internal user. 

   ![](assets/modify-values.png)

1. The **Values in Custom field** dialog box appears.

   ![](assets/values-in-customfields.png)

1. Select the value to add from the **[!UICONTROL Select Field]** drop-down menu.
1. Enter new values in the **[!UICONTROL New Value]** field.
1. Click **[!UICONTROL Done]**. 
1. Click Save on the top right corner to **[!UICONTROL Save]** changes.

**External users**

Add custom values similar to that for internal users.

![](assets/modify-values-forexternalusers.png) 

### Settings {#settings}

**User Display**

If the option **Show only unfilled fields on Learner login** is enabled, a user only sees the blank fields upon login.

![](assets/settings-tab.png)

Using this option, an Administrator can decide whether he/she wants to show the fields or hide them once these have been populated.

### Restrict Active Fields in reports {#restrictactivefields}

Learning Manager 27.7 introduces two new options- **Reportable** and **Exportable,** for Active Fields.

![](assets/options-in-activefields.png)

For CSV fields and manually added fields, if an Active Field is marked as **Reportable**, the Active Field becomes searchable in a filter inside a dashboard report.

![](assets/filters-in-a-dashboardreport.png)

If an Active Field is marked as **Exportable**, then the Active Field appears in the Excel file upon downloading any Excel report.

These options appear for both internal and external Active Fields.

You can only delete a custom Active Field.

## User Display

You can hide the entire 'Complete your profile' page from the learners. The page will not pop up once the learner logs in.

Note that the existing default behavior does not change. This is an optional capability now available to Administrators. 

Enable the options below:

![](assets/user-display.png) 

## Support for manual csv fields by FTP and Box connectors {#import-connector}

Often, users want Active fields to be manually provided when a learner logs in to Prime. This is possible in Learning Manager at present, when the user imports a CSV manually.

The CSV may not contain all the Active fields. For all the Active fields that are not updated in the uploaded CSV, the user needs to enter the data for such Active fields.

Presently, all Active fields must be mapped to some field from the source CSV.

It so happens that sometimes a user does not want to map an Active field to a field specified in the CSV. In such cases, the user can map the Active field to the value **DontImportFromSource**. Select this value from the drop-down list, when importing users from FTP and Box connectors.

## Custom Roles {#customroles}

Add any field of your choice as part of your user information and click **Save**. After adding the fields, you can also cross check the availabilities of the fields in the **Edit users** dialog. 

After adding the fields, you can notice that the fields marked with tick mark are sourced from data source or CSV as mentioned in the below snapshot. Administrator can edit these sourced fields by enabling or disabling the fields. 

**Values for active fields in Learning Manager**

The values for active fields are fetched in the following ways: 

1. Learning Manager application imports metadata from data sources associated with your account. 
1. Metadata captured from the manually imported CSV file. 
1. Learners fill up metadata when they log in
1. Administrator enters data for the users. 

Learning Manager application creates user groups automatically, from these metadata. 

**Add custom value**

You can add custom value for user fields in the Internal and External user fields.

To add  custom values, follow these steps:

Custom fields can be added and deleted, they are applicable to all users. CSV fields can be enabled or disabled, they come into effect only when you upload CSV after making the modifications in Active fields. All internal active fields are applicable to all types of Internal users. External fields are applicable only to external users. If a custom field is present in CSV, on next upload it gets converted to a CSV field automatically and it is enabled. 

## Values for CSV fields {#valuesforcsvfields}

Users can only choose from predefined fields for CSV fields if the **[!UICONTROL Restrict Selection]** check-box is enabled.

![](assets/value-field-for-csv.png) 

## Import Logs {#importlogs}

In this space, you can view the CSV import history for the users the administrator has added using bulk import feature. You can also click **Add **at the upper-right corner of the page to add users using CSV upload feature. 

## Multi-valued Active Fields

With this feature, you can have more than one field for an active field. In an account, there can be at most three multi-valued active fields. The multi-valued active fields are available for both external and internal users.

Once you mark an active field as multi-valued, you cannot convert it back to single valued. This is irreversible.

An existing single valued field cannot be marked as multi-valued field.

To create a multi-valued active field, follow the steps below:

1. Add an active field.

   ![](assets/add-active-field.png)

1. Click **Add**.
1. In the **Settings** tab, mark the new field as multi-valued.

   ![](assets/mark-multi-valued.png)

   There is another checkbox, **Learner Configurable,** which when disabled, the learner will not be able to see the field on the Profile page.

1. Add the values using a CSV or by clicking **Modify Values**.

   ![](assets/add-values.png)

1. Click **Done**.

**Note:** Once is the user group is created and the field is populated, multi values cannot be converted to single values, and vice versa.

## Add multi-valued active field via CSV

Follow the steps below:

1. Create a CSV with the new active fields as columns (comma-separated or single values).
1. Import the CSV.
1. Mark the fields as multi-valued in the **Values in Custom Fields** dialog.
1. Import the CSV again.

The CSV must have a column with the same name as that of an active field that was marked as multi-valued.

The CSV contains the fields:

* **User:** User groups created as roles.
* **Roles:** Multi-valued active field with values.

If the CSV is re-uploaded with new values or deleted values, the active fields and groups also get updated accordingly.

## Reports

All reports include the multi-valued active fields and their values.

The Administrator can add auto-generated active fields, and configure user activity and training reports.

The Learner Transcript report contains all the active fields and comma-separated values. The Administrator can then filter the data accordingly.

## Frequently Asked Questions {#faq}

+++How to register users in Learning Manager?

After adding a user and assigning a role to the user, you can register the user by performing the steps below:

1. With the user or users selected, click **Actions** on the upper-right corner, and click **Register**.

1. On the pop-up window, click **Yes**.

The selected user(s) receive a Welcome email. If the learners have an existing Adobe ID, they can click this link. If they don't have an existing Adobe ID, they can go ahead and click the Welcome link to create an Adobe ID and link it to their Prime account.

Clicking one of these links in the email is mandatory for the learners as it helps Prime to verify the learner's account.

+++

+++How to edit user data?

To edit a user, follow the steps below:

1. In the list of users, click the user for who you want to edit the data.
1. Click the pencil icon, as shown below.

![](assets/edit-user-data.png)

In the **Edit User** dialog, update the fields accordingly. To save the changes, click **Save**.

+++

+++How to pause and resume an external user in Learning Manager?

In the list of External Users, choose the user that you want to delete. On the upper-right corner, click **Actions > Pause**.

For more information, see [Pause an external profile](add-users-user-groups.md#pause).

After you pause a profile, the external profile displays the status as ***Paused***.

+++

+++How to send welcome email to newly created external profile?

When adding an external user, in the **Add External Registration Profile** dialog, enter the email of the external manager. When you click Save, a welcome email also gets sent to the email address that you had specified. If you want to send the welcome mail again, click the envelope icon, as shown below:

![](assets/send-welcome-mail.png)

+++

+++How to create Custom User Groups?

Click **Users > User Groups** and on the User Groups page, click **Add**. In the Add User Group dialog, add the users both indivdually and as a team.

![](assets/custom-user-group.png)

+++

+++How to disable already filled active fields?

If you want learners to only see the active fields that are not filled by them, then follow the steps below:

1. Click **Users > Active Fields**.  

1. Click **Settings** and enable the option **Show only unfilled fields on Learner login**.

1. Click **Save**.

+++

+++How to prevent learners from entering random values in the active fields.?

You can restrict the selection for learners so that they can only select the values that are pre-defined and not enter any random values. Follow the steps below:

1. Click **Users > Active Fields**.
1. In the section **Configure fields**, click **Modify Values**.

1. Enable the option **Restrict Selection**.
1. Click **Done**.

+++

+++How do I differentiate CSV active fields and Custom Active fields?

You can only enable or disable CSV active fields, but cannot delete them. On the other hand, you cannot enable or disable custom active fields.

+++
