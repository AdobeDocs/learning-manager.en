---
description: Learn how to add internal and external users to Adobe Learning Manager using step-by-step instructions. Explore different methods such as manual entry, bulk import, and automated user synchronization to simplify user management and enhance your learning platform.
jcr-language: en_us
title: Add Users in Adobe Learning Manager
contentowner: manochan
exl-id: 7df98f2b-c422-4733-8ce4-5489506d4fdf
---

# Add Users in Adobe Learning Manager

In Adobe Learning Manager, users are people who use the platform for learning or training. There are two types of users: internal users and external users.

Internal users are employees or team members from your organization.

External users are people outside your company, such as customers, partners, vendors, or clients, who can access your learning content.

Adobe Learning Manager (ALM) allows administrators to onboard and manage both internal and external users using various methods, including manual entry, CSV upload, self-registration, and system integrations.

## Internal users

Internal users in Adobe Learning Manager refer to employees or team members within your organization. You can add them manually, upload them in bulk, or import them through system integrations. After adding these users, you can organize them into groups, assign courses, and monitor their learning progress.

Users in Adobe Learning Manager can take on different responsibilities and manage various tasks based on their assigned roles. Each role, including Administrator, Author, Instructor, and Integration Admin, offers a set of specific capabilities tailored to support the user's responsibilities within the platform.

Adobe Learning Manager supports the following user roles:

* **Administrator**: Manages users and user groups, assign roles, and configure system-wide preferences such as data sources, allowed domains, and display options. Administrators are also responsible for creating and organizing learning content, tracking learner progress, generating reports, and setting up integrations with external systems. 
* **Author**: Creates and manages content, including modules and courses.
* **Manager**: Oversees team learning activities, nominates team members for courses, approves requests, and provides feedback.
* **Integration Admin**: Manages system integrations and data connections between ALM and external platforms. 
* **Custom roles**: Admins can create custom roles to give users tailored access based on their responsibilities. Refer to this article for more information about the custom roles.

### Methods to add internal users

Administrators can add internal users using the following methods:

* **Add a single user**: Manually add one user at a time.
* **Self-Registration profile**: Allow learners to self-register as learners in Adobe Learning Manager using a registration link created by the administrator.
* **Bulk upload via CSV**: Upload a CSV file to add multiple users at once.

### Manually add an internal user

Administrators can manually add individual users by entering their name, email ID, unique identifier, and manager's name. The Unique Identifier in Adobe Learning Manager is a required identifier that administrators assign when creating a user. It must be unique for each user and serve as a consistent reference throughout the system.

>[!INFO]
>
>Watch this ALM Academy training to learn more about adding single users in Adobe Learning Manager.<br>[![button](assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/7555534)</br>

To add a single user to Adobe Learning Manager:

1. Log in as an administrator.
2. Select **Users** and then select **Internal**.
3. Select **Add** and then select **Single User**. 
   
   ![](assets/add-single-user.png)
   _Administrator interface showing the option to manually add a single internal user_
4. On the **Add User** prompt, type the **Name**, **E-mail** and **Profile** (job title) of the user. 

   ![](assets/add-a-user-prompt.png)
   _Fields to enter name, email, unique identifier, and profile for a new user_
5. Search for the user's manager and select the name from the list of managers.
6. Select **Add**. 
   The user receives a welcome email containing a login URL for access. 


### Allow self-registration for internal users

Self-registration is a self-service onboarding process where users can visit a registration URL, input their details, and automatically enroll in the platform. This method minimizes administrative effort by allowing users to register themselves through the provided URL.

To create a self-registration URL for a user:

1. Log in as an administrator.
2. Select **Users** and then select **Internal**. 
3. Select **Add** in the upper-right corner and then select **Self-Registration.**


   ![](assets/add-self-register-link.png)
   _Dropdown menu for selecting the self-registration option_
4. On the **Add Self-Registration Profile** prompt, type the profile in the **Profile Name** (Job title of the user) field.
5. Select the user's manager by searching for the manager in the **Manager's Name** field. The manager assigned to the self-registration profile should be a registered user in Adobe Learning Manager.


   ![](assets/add-a-user-prompt.png)
   _Input fields for setting the job title and assigning a manager to a self-registration profile_
6. Select an image using **Add Image** option. This image will be visible to the learners in the profile section.
7. Select **Save**.

   Adobe Learning Manager creates a user profile and generates a self-registration URL, which can be shared with the users to complete their registration.


   ![](assets/self-register-url.png)
   _Confirmation message indicating successful creation of a self-registration URL_
8. Share the URL with the users who want to self-register.

   
   The URL can be shared with multiple users for registration. For example, you can generate a URL for the **Sales Associate** profile and share it with the Sales Associate team so they can register themselves.

![](assets/self-register-screem.png)
_Self-registration link opens a sign-up page_

### View the list of self-registration URLs

To view the list of self-registration URLs:

1. Select **Users** and then select **Internal**. 
2. Select **Self-Registration**.

   Administrators can see the list of self-registration URLs.

![](assets/self-registration-profile.png)
_List view showing existing self-registration URLs available for internal users_

### Bulk upload internal users

Adobe Learning Manager allows administrators to add multiple users at once by uploading a CSV containing the user's information, including name, email ID, and manager's name. This bulk upload feature saves time and effort compared to adding users individually.

>[!INFO]
>
>Watch this ALM Academy training to learn how to add users in bulk through a CSV. <br>[![button](assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/7555555)</br>

To add multiple users:

1. Log in as an administrator.
2. Select **Users** and then select **Internal**.
3. Select **Add** in the upper-right corner and select **Upload a CSV**.

   ![](assets/select-upload-acsv.png)
   _Option to upload a CSV file for bulk user import_

4. Prepare a CSV file with the following fields:

   * Employee's Name*
   * Employee's Email*
   * Employee's Profile/Designation
   * Manager's ID/Email  
   (*) Required fields.

5. Before adding a manager's email ID for any employee, make sure the manager is already included as an employee in the CSV file. For example, see the employee named Howard Walters in the snapshot below.

   ![](assets/csv-image.png)
   _Image of sample CSV with all the fields_

6. Upload the CSV file and map the data fields accordingly.
   
   ![](assets/map-the-column.png)
   _CSV mapping interface to align spreadsheet columns with system fields_
7. Select **Save** to import the users.

   A confirmation message appears after the upload is successful.
   
   ![](assets/csv-save-success.png)
   _Image shows the status of the CSV upload as successful_

>[!NOTE]
>
>Maintain a master CSV for all additions and deletions. Updating and re-uploading an existing CSV file is not supported.

When uploading a CSV file to add users, it's important to include all related information in the correct order. If you assign a manager's email ID to an employee, the manager's details must appear earlier in the CSV file. This ensures the system recognizes the manager as an existing user before linking them to their team members. For example, if Howard Walters is a manager, include his full user details in the CSV before listing employees who report to him.

### Manage user registration

After adding users individually or in bulk, you need to register them to activate their accounts. This allows users to access Adobe Learning Manager and start using the platform.

To register the users:

1. Select **Users** on the administrator home page.
2. Select the checkboxes next to the names of the users you want to register.
3. Select **Actions** and then select **Register**.
   
   ![](assets/register-user.png)
   _Register button to activate selected users in Adobe Learning Manager_

4. Select **Yes** to activate the user.

A verification email is sent to the user. The user must select the link in the email to activate their account and start using Adobe Learning Manager.

## External users

Adobe Learning Manager allows you to add users outside your company, such as customers, partners, vendors, or clients, to access the learning content. After they are added, you can group them, assign courses, and track their learning progress.

Adding external users in Adobe Learning Manager involves the following steps:

* Create an external registration profile
* Enable the registration profile
* Share the registration link with external users
* Pause or resume the profile when needed

Adobe Learning Manager supports enrollment of such users through external registration profiles.

To create an external user, follow these steps:

1. Log in as an administrator.
2. Select **Users** and then select **External**.
3. In the upper-right corner, select **Add** to create a registration for an external user.
4. In the **Add External Registration Profile** dialog, provide the following:

   * **Profile Name:** Type the name of the partner organization that wants to access Adobe Learning Manager
   * **Manager Email:** Type the manager's email address of the user.
   * **Seat Limit:** Set the maximum number of enrollments allowed.
   * **Expiry:** Define the last date for new registrations. After it expires, the link will not work for new user registration.

   ![](assets/add-external-user-prompt.png)
   _Dialog box for entering profile name, manager email, seat limit, and expiration_

5. Select an image using the **Add Image** option. This image will be visible to the learners in the profile section.
6. Select the **Advanced Settings** section to expand it and type the required details:
   * **Login Requirement:** Type the number of days. If learners remain inactive for the entire period, they will be automatically removed.
   * **Allowed Domains:** Type the comma-separated list of allowed email domains. Only users with email addresses from approved domains can sign up.
   * **Email Verification Required:** Select this to enforce email verification during registration.
   
   ![](assets/advanced-settings-add-external.png)
   _Advanced Settings panel to set login requirements, allowed domains, and email verification_

7. Select **Save**.

A registration URL is generated.

### Enable the external profile

To enable the external profile:

1. Locate the newly created profile in the list of external profiles.

2. Select the **Status** toggle button to enable it.

The administrator can share this URL with the external partner so they can sign up and log in to Adobe Learning Manager using it.

![](assets/enable-the-external-user.png)
_Select the toggle to enable the external profile_

### Copy and share registration URL of external profile

The registration URL for an external profile can be copied from the **External Users** section. 

![](assets/copy.png)
_Copy the registration URL of an external profile_

### Key differences between internal and external user registrations

There are a few differences between internal and external registrations:

|Internal users|External users|
|---|---|
|Can log in using Adobe ID or SSO credentials.|Can log in using any email ID.|
|Gamification is available. |Gamification is available. The administrator must enable gamification for external learners in the [Gamification settings](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/gamification).|

### Pause external registration profile

In Adobe Learning Manager, administrators can manage external user registration by pausing their profiles. This is helpful when you want to temporarily pause new users from joining using a specific external user profile. Pausing a profile prevents users who have received invitations but have not registered yet from completing the sign-up process. This action does not affect users who have already completed their registration.

To pause an external profile:

1. Select **Actions** in the upper-right corner of the **External Users** page.
2. Select **Pause** to pause the external user profile.

This blocks the registration process for users who have yet to accept their invitations. Note that this action only affects users who have yet to complete their registration.

![](assets/pause-external-user.png)
_Option to pause an existing external user profile from the Actions menu_

### Resume external registration profile

If an external profile was previously paused, administrators can resume it to allow new users to complete their registration. This reactivates the registration process for users who were invited but did not complete their sign up.

To resume an external user:

1. Select **Actions** in the upper-right corner of the page.
2. Select **Resume** to resume a paused partner's access.

![](assets/resume-an-external-user.png)
_Option to resume a previously paused external user profile_

### Monitor external seat usage

Administrators can track the number of users added to each external profile in Adobe Learning.

To check the used seats:

1. Select **Seats Used** in the list of external profiles.

You can view the number of learners added to the partner organization and whether the learners are active.

## Manage users

Admins can edit user details, delete users, assign roles, and remove roles. This helps make sure each user has the right access and tasks.

>[!INFO]
>
>Watch this ALM Academy training to learn how to assign and remove roles, send a welcome email, and delete and purge users.<br>[![button](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/7555586)</br>

### Edit a user

Use the **Edit User** option in Adobe Learning Manager to update a user's profile information, such as name, email address, unique identifier, profile and manager's name. Administrators can make these changes to ensure user data remains accurate and up to date.

To edit a user:

1. Select **Users** on the administrator home page.
2. Select the user you want to edit from the **Users** list.
3. Select **Edit Profile**.

   ![](assets/edit-a-profile.png)
   _Delete User option under Actions menu to remove a user from the platform_ 

4. Select **Yes** to delete the user.

A confirmation message appears when the user is successfully deleted.

## Assign a role to a user

User roles in Adobe Learning Manager define what actions each person can perform in the system. Each role comes with specific permissions based on the user's responsibilities.

To assign roles to users:

1. Select **Users** on the administrator home page.
2. Select the user you want to assign a role.
3. Select **Actions** in the upper-right corner.
4. Select **Assign Role**.
5. Select the required role.

   ![](assets/assign-roles-users.png)
   _Assign Role menu options display available roles for the selected user_

6. Select **Yes** on the confirmation dialog.

## Remove a role

Removing a user role revokes the permissions granted by that role.

To remove roles from users:

1. Select **Users** on the administrator homepage.
2. Select the user(s) whose roles you want to remove.
3. Select **Actions** and then select **Remove Role**.

   ![](assets/remove-a-role.png)
   _Option to remove assigned roles from a user under the Actions menu_

4. Select **Yes** on the confirmation dialog.
<!--# Add users and create user groups


Learn how to add users or user groups in Learning Manager application.

<!--![](assets/user-mgmt-new.png)-->

<!--## Overview {#overview}

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

Add internal learners to the Adobe Learning Manager using a single user option.

>[!INFO]
>
>In this training, you will learn how to add internal learners to the Adobe Learning Manager.<br><br>[![button](assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/7555534)</br></br>


If you're unable to launch the training, write to <almacademy@adobe.com>.

To add users,

1. Log into Adobe Learning Manager as an Administrator. 
1. On the home page, click **[!UICONTROL Add Users]**. On this page, you can add a single user or multiple users at a time using a CSV. You can also create a self-registration link for internal employees or create an external learner profile.
1. To add a single user, click **[!UICONTROL Add]** on the upper-right corner and choose the option **[!UICONTROL Single User]**.

1. To add a single user, click **[!UICONTROL Add]** on the upper-right corner and choose the option **Single User**.


   ![](assets/single-user.png)
   *Add a single internal user*

1. On the **[!UICONTROL Add User]** dialog, enter the details of the learner. For the field **[!UICONTROL Manager's Name]**, pick the name of an existing user in the system.

   ![](assets/manager.png)
   *Add user dialog box*

1. To add the new user in Learning Manager, click **[!UICONTROL Add]**. After the user is added, the user receives a verification mail. The Learner then activates the account and starts using Learning Manager. This workflow is helpful if you need to add limited number of learners to your Learning Manager Account. But if you're planning to enroll all the employees of a large organization, you can add them in a singe attempt. For more information, see the next section.

## Add users in bulk {#addusersinbulk}

Typically, most organizations work with an HR Management System (HRMS), which maintains all employee records, such as, designation, location, date of joining, or employee hierarchy. You can export this data in a CSV format. To import a CSV, follow the steps below:


1. Click **[!UICONTROL Add]** on the upper-right corner, and choose the option **[!UICONTROL Upload a CSV]**.

   ![](assets/upload-a-csv.png)
   *Upload a CSV to add users in bulk*

1. The CSV that you upload consists of the fields, as shown below:

   ![](assets/csv.png)
   *Structure of the CSV*

   You must maintain a master CSV and perform perform all additions and deletions on the master CSV. The master CSV contains the following fields:

   * name &#42;
   * email &#42;
   * profile
   * manager

   (&#42;) Required field.

1. After you click the option **[!UICONTROL Upload a CSV]**, the following dialog displays.

   ![](assets/upload-a-csv-dialog.png)
   *Upload a CSV dialog*

1. Choose the CSV or drag-and-drop the file. After you've chosen the file, map the data fields with the ones in the CSV file. Click the required drop-down and choose the right field.

   ![](assets/map-data-fields.png)
   *Map fields in CSV*

1. To start importing the users, click **[!UICONTROL Save]**. You can see a confirmation message.

   ![](assets/save-csv.png)
   *Confirmation message for successful upload of the CSV*

1. The new users are now added to your Adobe Learning Manager account. To select the new users, select the check-box next to the names so that everybody is selected. 

   ![](assets/select-new-users.png)
   *New users added*

>[!NOTE]
>
>For more information, see the FAQ, [Add users in bulk](../add-users-in-bulk.md).

>[!INFO]
>
>In this training, you will learn how to add users in bulk through a CSV.<br><br>[![button](assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/7555555)</br></br>

If you're unable to launch the training, write to <almacademy@adobe.com>.

## Register a user {#registerauser}

With the user selected, click **[!UICONTROL Actions]** on the upper-right corner and click **[!UICONTROL Register]**.

The selected users receive a Welcome email. If the learners have an existing Adobe ID, they can click this link. If they don't have an existing Adobe ID, they can go ahead and click the Welcome link to create an Adobe ID and link it to their Learning Manager account.

### Manage users

In this training, you will learn how to assign and remove roles, send a welcome email, and delete and purge users. 

[![button](assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/7555586)

If you're unable to launch the training, write to <almacademy@adobe.com>.

## Assign a role {#assignarole}

After adding learners to the Adobe Learning Manager account, if you want to change their roles, click Actions on the upper-right corner of the page. Choose the option **[!UICONTROL Assign Role]**. Here you can decide whether you want to give Author access or Admin access to the learner. After you have assigned a role, this learner has Author access to the account and can add modules and create courses. 

![](assets/assign-a-role.png)
*Assign a role to a user*

## Remove a role {#removearole}

You can also remove Author or Admin access for the users. Select one or more learners, click **[!UICONTROL Actions]**, and select **[!UICONTROL Remove Role]**. Choose an option, for example, **[!UICONTROL Remove Author]**, and the author access gets revoked for this learner. 

>[!NOTE]
>
>You cannot manually assign a Manager role to someone in the system. They automatically get access to the Manager dashboard when one or more employees are added under them.

## Delete a user {#deleteauser}

To delete a user, click **[!UICONTROL Actions]**, and choose **[!UICONTROL Delete User]**. On the confirmation dialog, click **[!UICONTROL Yes]**, and the learner gets deleted.

![](assets/delete-a-role.png)
*Confirmation message to delete a user*

## Edit a user {#editauser}

On the list of users, choose a user, and click the user. On the user details, click the **[!UICONTROL Edit]** ( ![](assets/edit-pen.png)) button. On the **[!UICONTROL Edit User]** dialog, make the necessary edits and to save the changes, click **[!UICONTROL Save]**.

![](assets/edit-user.png)
*Edit User dialog*

## Active fields

Active Fields in Adobe Learning Manager are customizable metadata fields used to store and manage user-specific information. These fields help define key attributes or characteristics associated with each user in the system.

### Manage user attributes

>[!INFO]
>
>In this training, you will learn how to add, customize, and configure Active Fields.<br><br>[![button](assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/7555741)</br></br>

If you're unable to launch the training, write to <almacademy@adobe.com>.

Adobe Learning Manager preserves the case sensitivity of the user attribute and its value. **For example**, the case sensitivity of a user attribute is 'location' and its value as 'PARIS' will be preserved and displayed in the same manner. In case of any issues, the Administrator can now edit the attribute name and values to correct any case sensitivity errors. 

The Administrator can do this by visiting **[!UICONTROL Admin app]** > **[!UICONTROL Users]** > **[!UICONTROL User groups]** and clicking on the group name.  

An Admin can add and update allowed attribute values for a learner through UI.

Types of active fields:

* Groupable: Learners would get grouped on the basis of the Values
* Reportable: Reporting user groups would be created based on the active fields
* Exportable: The fields will be seen in exported in user group report.

## Create a self-registration link {#createaselfregistrationlink}

You can also enable employees in your organization to register themselves as Learners to Adobe Learning Manager Account, without taking help from you as an administrator. The administrator can create a Self-Registration link and share with the employees, who can further register to Learning Manager using their Adobe credentials.

On the upper-right corner of the page, click **[!UICONTROL Add]**, and select **[!UICONTROL Self-Registration]**.


![](assets/self-registration.png)
*Create link to self-register as learner*

The **[!UICONTROL Add Self-Registration Profile]** dialog appears. Give this profile a name. Then add the manager's name. It's important to know that the manager must already be registered learner in Learning Manager.

![](assets/add-self-registrationprofile.png)
*Add profile for self-registration*

After you click **[!UICONTROL Save]**, a URL gets generated, which you can share with the learners, so that they can click the URL and self-register themselves.

## Enroll external learners {#enrollexternallearners}

In Adobe Learning Manager, you can also create Registration links for external partners or agencies with limited access to your account and provide them learning material.

There are a few differences between internal and external registrations.

<table>
 <tbody>
  <tr>
   <td>
    <p><b>Internal users</b></p></td>
   <td>
    <p><b>External users</b></p></td>
  </tr>
  <tr>
   <td>
    <p>Log in using Adobe ID or SSO credentials.</p></td>
   <td>
    <p>Log in using any email ID.</p></td>
  </tr>
  <tr>
   <td>
    <p>Gamification is available.</p></td>
   <td>
    <p>Gamification is available. The admin must enable gamification for external learners in the Gamification settings.</p></td>
  </tr>
  <tr>
   <td>
    <p>Learner hierarchies are available.</p></td>
   <td>
    <p>Learner hierarchies are not available.</p></td>
  </tr>
 </tbody>
</table>

To enroll external users, follow the steps below:

1. In the left navigation pane, click **[!UICONTROL External]**.

   ![](assets/click-external.png)
   
   *Enroll external users*

1. On the upper-right corner of the page, click **[!UICONTROL Add]**.

1. On the **Add External Registration Profile** dialog, add the following details:


   * The profile name of the partner organization.
   * The email address of the manager of the partner organization.
   * Seat limit for external enrollment for this partner.
   * Expiry date to set a deadline to stop allowing new registrations to this group. After the Expiry date, only the existing registered users can access this training.

   ![](assets/map-data-fields-2.png)

   *Add External Registration Profile dialog*

   * In the **[!UICONTROL Advanced Settings]** section, enter the following:

     * **[!UICONTROL Login Requirement]:** Specify a value in days. Learners get deleted if they do not login for the above duration.
     * **[!UICONTROL Allowed Domains]:** A comma-separated list of whitelisted email domain names.
     * **[!UICONTROL Email Verification Required]:** Select this option to make email verification mandatory for a learner.

   ![](assets/email-verificationrequired.png)

   *Enter the details in the Advanced Settings section* 

1. After you click **[!UICONTROL Save]**, you can see the following confirmation message. You must share the URL with your external partner.

   ![](assets/save-and-share-urlwithexternalusers.png)

## Enable an external profile {#enableanexternalprofile}

After an external profile has been created, you must enable its status. From the list of external profiles, choose the required profile, and toggle the status button.

![](assets/choose-required-profiles.png)
*Enable an external profile*

This enables the External Enrollment link. A welcome email is automatically be sent to the partner. You can also copy the link and share with them by clicking the Copy URL icon (), or you can resend the welcome email to the partner organization by clicking the Mail icon ().

The partner manager can share the link with the employees who must take the training in PrLearning Managerime. When they click the link, they can self-enroll themselves after filling out some details to create their profile on Learning Manager. These users will not appear on the Learners tab along with the internal employees. You can see their names under the **[!UICONTROL External Learners]** tab.

## Pause an external profile {#pause}

After adding an external user group to Learning Manager, you can also pause the external users' registration process. When you pause, the external users' registration process is blocked. However, this process works only when the users haven't registered yet by accepting the invitation.

To pause the external user groups, choose a group or groups, click **[!UICONTROL Actions]** from the upper-right corner of the page, and click **[!UICONTROL Pause]**.

## Resume an external profile {#resumeanexternalprofile}

At any time, you can always revoke the paused state of an external partner and resume normal services. Click **[!UICONTROL Actions]** at the upper-right corner of the page and select **[!UICONTROL Resume]**.

The following states are applicable for external users:

* **Inactive state** - In this state, the external users' registration is expired. Administrators set the expiry date for the external users while adding them through the add user workflow.
* **Active state** - In this state, the external users can register to the Learning Manager application, and log in to the application.
* **Pause** - In this state, the registration process for external users is blocked. However, the existing users can continue to log in.

## Check used seats {#checkusedseats}

On the list of external profiles, click **[!UICONTROL Seats Used]**. You can view the number of learners in the partner organization who have been added.

![](assets/seats-used.png)
*Check used seats*

## Delete a user {#Deleteauser-1}

Choose a user, and from the upper-right corner, click **[!UICONTROL Actions]** > **[!UICONTROL Delete User]**.

## Change profile {#changeprofile}

To move a user to another external profile, choose a user, from the upper-right corner, click **[!UICONTROL Actions]** > **[!UICONTROL Change Profile]**. From the list of profiles, choose a profile, and click **[!UICONTROL Change]**.

## Assign a role {#Assignarole-1}

Choose a user, and from the upper-right corner, click **[!UICONTROL Actions]** > **[!UICONTROL Assign Role]** > **Make `<role>`**. The user gets a new role.

## Remove a role {#Removearole-1}

Choose a user, and from the upper-right corner, click **[!UICONTROL Actions]** > **[!UICONTROL Remove Role]** > **Remove `<role>`**. The selected role gets removed from the list of roles that were assigned to the user.

>[!NOTE]
>
>Assigning a new role will not affect custom user groups. However, it will impact auto-generated user groups such as All Admins, All Authors, and similar role-based groups.

## Create user groups {#createusergroups}

A User Group is a set of users who are related to a category. User Groups help administrators to select learners in their organization based on their attributes, and then assign learning content to them. Also, these User Groups enable administrators to assign customized logos and catalogs to learners and show customized reports on their progress.

To access User Groups, on the left navigation pane, click **[!UICONTROL User Groups]**.

![](assets/user-groups.png)
*Create user groups*

### Manage user groups

>[!INFO]
>
>In this training, you will learn how to create a user group by names, email IDs, and combining multiple auto-generated user groups.<br><br>[![button](assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/7555694)</br></br>

If you're unable to launch the training, write to <almacademy@adobe.com>.

There are two types of groups in Adobe Learning Manager, Custom and Auto-generated. When you add learners to your account, some groups are automatically created based on their common properties.

To see the automatically created groups, click the tab **[!UICONTROL Auto-generated]**.

![](assets/auto-generated.png)
*View Auto-generated groups*

You can see that there are different groups, like All Internal Users, All Managers, groups based on the Cost Center, based on the department, and based on the teams of the managers.

In addition to Auto-generated groups, you can create Custom groups. To add a new Custom Group, on the upper-right corner, click **[!UICONTROL Add]**. 

1. Enter the name, and description for the group.
1. Enter user name or profile in search-as-you-type field and select from the drop-down list, to add users.

1. To add more learners, click **[!UICONTROL Add More Users]**.

1. To create the user group, click **[!UICONTROL Save]**.

This Custom Group is now created and added to the profile. The User Groups that you create are dynamic in nature. If new users are added with similar attributes, they're automatically added to the User Group.

To view the list of groups a user belongs to, navigate to **[!UICONTROL User]** > **[!UICONTROL User Groups]**, search for the user's name, and select it. This will display all the groups the user is part of.

![](assets/list-of-group.png)

### Download the list of users in a user group

To download the list of users in a specific user group, navigate to **[!UICONTROL User]** > **[!UICONTROL User Groups]**, select the **[!UICONTROL Download icon]** next to the group. This will generate a CSV file containing the list of users in that group.

![](assets/download-list-of-user.png) 

## Exclusion of user groups

At times you would want to exclude a small set of users from a large user group. This is required to enroll this specific set of users into training via Learning Plans or to setup the correct visibility of catalogs. In this release of Learning Manager, you can exclude learners or User Groups when you create a custom user group. In the Add User Group dialog, the Exclude Learners section enables you to achieve so.

![](assets/exclude-user-groups.png)
*Exclude user groups*

For example, if you want to set up a Learning Plan so that all users belonging to location = California except Store-5 (located in California) get enrolled. 

## Advanced settings {#advancedsettings}

### Data Sources {#datasources}

You can use this feature when you want to import/sync the users or learning data from your organization's database in to the Learning Manager application. You can also set up the frequency of this sync. 


Click **[!UICONTROL Data Sources]** on the left pane under **[!UICONTROL Advanced]** section. 


![](assets/data-sources-add-users.png)

*Data sources to iport or sync users*

Choose the data source type from the **[!UICONTROL Source]** drop-down, select the update frequency, and click **[!UICONTROL Sync now]** if you need to sync immediately or click **[!UICONTROL Save].** Data source types are SFDC, FTP, and so on for internal users. 

You can add multiple data sources. 

### Active Fields {#activefields}

This feature enables administrators to add more active fields in addition to what has been provided during user registration. 

Click **[!UICONTROL Active Fields]** available inside users page. Learners can only choose from the values given in custom values.

![](assets/active-fields.png)
*Active fields*

### Configure Fields {#configurefields}

**Internal users**

You can add custom value for user fields for internal users.

To add  custom values, follow these steps:

1. Click  **[!UICONTROL Modify Values]** for an Internal user. 

   ![](assets/modify-values.png)
   *Modify values for internal users*

1. The **Values in Custom field** dialog box appears.

   ![](assets/values-in-customfields.png)
   *Values in Custom Fields dialog box*

1. Select the value to add from the **[!UICONTROL Select Field]** drop-down menu.
1. Enter new values in the **[!UICONTROL New Value]** field.
1. Click **[!UICONTROL Done]**. 
1. Click Save on the top right corner to **[!UICONTROL Save]** changes.

**External users**

Add custom values similar to that for internal users.

![](assets/modify-values-forexternalusers.png)
*Modify values for external users*

### Settings {#settings}

**User Display**

If the option **Show only unfilled fields on Learner login** is enabled, a user only sees the blank fields upon login.

![](assets/settings-tab.png)
*Show unfilled fields*

Using this option, an Administrator can decide whether he/she wants to show the fields or hide them once these have been populated.

## Restrict Active Fields in reports {#restrictactivefields}

Learning Manager 27.7 introduces two new options- **[!UICONTROL Reportable]** and **[!UICONTROL Exportable]**, for Active Fields.

![](assets/options-in-activefields.png)
*Options in Active Fields*

For CSV fields and manually added fields, if an Active Field is marked as **[!UICONTROL Reportable]**, the Active Field becomes searchable in a filter inside a dashboard report.

![](assets/filters-in-a-dashboardreport.png)
*Filters in a dashboard report*

If an Active Field is marked as **[!UICONTROL Exportable]**, then the Active Field appears in the Excel file upon downloading any Excel report.

These options appear for both internal and external Active Fields.

You can only delete a custom Active Field.

## User Display

You can hide the entire 'Complete your profile' page from the learners. The page will not pop up once the learner logs in.

Note that the existing default behavior does not change. This is an optional capability now available to Administrators. 

Enable the options below:

![](assets/user-display.png)
*User Display section*

## Support for manual CSV fields by FTP and Box connectors {#import-connector}

Often, users want Active fields to be manually provided when a learner logs in to Learning Manager. This is possible in Learning Manager at present, when the user imports a CSV manually.

The CSV may not contain all the Active fields. For all the Active fields that are not updated in the uploaded CSV, the user needs to enter the data for such Active fields.

Presently, all Active fields must be mapped to some field from the source CSV.

It so happens that sometimes a user does not want to map an Active field to a field specified in the CSV. In such cases, the user can map the Active field to the value **[!UICONTROL DontImportFromSource]**. Select this value from the drop-down list, when importing users from FTP and Box connectors.

## Custom Roles {#customroles}

Add any field of your choice as part of your user information and click **[!UICONTROL Save]**. After adding the fields, you can also cross check the availabilities of the fields in the **[!UICONTROL Edit users]** dialog. 


After adding the fields, you can notice that the fields marked with tick mark are sourced from data source or CSV as mentioned in the below snapshot. Administrator can edit these sourced fields by enabling or disabling the fields. 

**Values for active fields in Learning Manager**

The values for active fields are fetched in the following ways: 

1. Learning Manager application imports metadata from data sources associated with your account. 
1. Metadata captured from the manually imported CSV file. 
1. Learners fill up metadata when they log in
1. Administrator enters data for the users. 

>[!NOTE]
>
>Learning Manager application creates user groups automatically, from these metadata. 

**Add custom value**

You can add custom value for user fields in the Internal and External user fields.

To add  custom values, follow these steps:

Custom fields can be added and deleted, they are applicable to all users. CSV fields can be enabled or disabled, they come into effect only when you upload CSV after making the modifications in Active fields. All internal active fields are applicable to all types of Internal users. External fields are applicable only to external users. If a custom field is present in CSV, on next upload it gets converted to a CSV field automatically and it is enabled. 

## Values for CSV fields {#valuesforcsvfields}

Users can only choose from predefined fields for CSV fields if the **[!UICONTROL Restrict Selection]** check-box is enabled.

![](assets/value-field-for-csv.png)
*Restrict selection check-box*

## Import Logs {#importlogs}

In this space, you can view the CSV import history for the users the administrator has added using bulk import feature. You can also click **[!UICONTROL Add]** at the upper-right corner of the page to add users using CSV upload feature. 

## Multi-valued Active Fields

With this feature, you can have more than one field for an active field. In an account, there can be at most three multi-valued active fields. The multi-valued active fields are available for both external and internal users.

Once you mark an active field as multi-valued, you cannot convert it back to single valued. This is irreversible.

An existing single valued field cannot be marked as multi-valued field.

To create a multi-valued active field, follow the steps below:

1. Add an active field.

   ![Add an active field](assets/add-active-field.png)
   *Add an active field*

1. Click Add.
1. In the Settings tab, mark the new field as multi-valued.

   ![Mark as multi-valued](assets/mark-multi-valued.png)
   *Mark as multi-valued*

   There is another checkbox, **[!UICONTROL Learner Configurable]**, which when disabled, the learner will not be able to see the field on the Profile page.

1. Add the values using a CSV or by clicking Modify Values.

   ![Add values](assets/add-values.png)
   *Add values*

1. Click [!UICONTROL **Done**].

>[!NOTE]
>
>Once is the user group is created and the field is populated, multi values cannot be converted to single values, and vice versa.

### Add multi-valued active field via CSV

Follow the steps below:

1. Create a CSV with the new active fields as columns (comma-separated or single values).
1. Import the CSV.
1. Mark the fields as multi-valued in the Values in Custom Fields dialog.
1. Import the CSV again.

The CSV must have a column with the same name as that of an active field that was marked as multi-valued.

The CSV contains the fields:

* **[!UICONTROL User]**: User groups created as roles.
* **[!UICONTROL Roles]**: Multi-valued active field with values.

If the CSV is re-uploaded with new values or deleted values, the active fields and groups also get updated accordingly.

### Reports

All reports include the multi-valued active fields and their values.

The Administrator can add auto-generated active fields, and configure user activity and training reports.

The Learner Transcript report contains all the active fields and comma-separated values. The Administrator can then filter the data accordingly.

## User group report

Adobe Learning Manager's new User Group Report helps manage user groups by providing visibility into groups left unmanaged when admins left. Admins can access the reports under the **[!UICONTROL Users]** > **[!UICONTROL User Group]** section. It provides detailed information about each group, including:

* User group type
* Group name
* Description
* Created by (Name)
* Created by (Email)
* Created on (UTC Timezone)
* Number of Users

To download the report, follow these steps:

1. Log in as an **[!UICONTROL Admin]**.
2. Select **[!UICONTROL Users]** > **[!UICONTROL User Group]**.
3. Select **[!UICONTROL Actions]** > **[!UICONTROL Download User Group Report]**.

![](assets/download-user-group-report.png) 
_Download the User Group report_

## Frequently Asked Questions {#faq}

+++How to register users in Learning Manager?

After adding a user and assigning a role to the user, you can register the user by performing the steps below:

1. With the user or users selected, click **[!UICONTROL Actions]** on the upper-right corner, and click **[!UICONTROL Register]**.

1. On the pop-up window, click **[!UICONTROL Yes]**.

The selected user(s) receive a Welcome email. If the learners have an existing Adobe ID, they can click this link. If they don't have an existing Adobe ID, they can go ahead and click the Welcome link to create an Adobe ID and link it to their Learning Manager account.

Clicking one of these links in the email is mandatory for the learners as it helps Learning Manager to verify the learner's account.

+++

+++How to edit user data?

To edit a user, follow the steps below:

1. In the list of users, click the user for who you want to edit the data.
1. Click the pencil icon, as shown below.

![](assets/edit-user-data.png)

In the **Edit User** dialog, update the fields accordingly. To save the changes, click **[!UICONTROL Save]**.

+++

+++How to pause and resume an external user in Learning Manager?

In the list of External Users, choose the user that you want to delete. On the upper-right corner, click **[!UICONTROL Actions]** > **[!UICONTROL Pause]**.

For more information, see [Pause an external profile](add-users-user-groups.md#pause).

After you pause a profile, the external profile displays the status as ***Paused***.

+++

+++How to send welcome email to newly created external profile?

When adding an external user, in the **[!UICONTROL Add External Registration Profile]** dialog, enter the email of the external manager. When you click Save, a welcome email also gets sent to the email address that you had specified. If you want to send the welcome mail again, click the envelope icon, as shown below:

![](assets/send-welcome-mail.png)

+++

+++How to create Custom User Groups?

Click **[!UICONTROL Users]** > **[!UICONTROL User Groups]** and on the User Groups page, click **[!UICONTROL Add]**. In the Add User Group dialog, add the users both individually and as a team.

![](assets/custom-user-group.png)

+++

+++How to disable already filled active fields?

If you want learners to only see the active fields that are not filled by them, then follow the steps below:

1. Click **[!UICONTROL Users]** > **[!UICONTROL Active Fields]**.  

1. Click **[!UICONTROL Settings]** and enable the option **[!UICONTROL Show only unfilled fields on Learner login]**.

1. Click **[!UICONTROL Save]**.

+++

+++How to prevent learners from entering random values in the active fields.?

You can restrict the selection for learners so that they can only select the values that are pre-defined and not enter any random values. Follow the steps below:

1. Click **[!UICONTROL Users]** > **[!UICONTROL Active Fields]**.
1. Enable the option **[!UICONTROL Restrict Selection]**.
1. Click **[!UICONTROL Done]**.

+++

+++How do I differentiate CSV active fields and Custom Active fields?

You can only enable or disable CSV active fields, but cannot delete them. On the other hand, you cannot enable or disable custom active fields.

+++-->