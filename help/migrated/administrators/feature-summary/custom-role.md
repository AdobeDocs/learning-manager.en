---
jcr-language: en_us
title: Custom roles
contentowner: dvenkate
---


# Custom roles {#custom-roles}

Captivate Prime&nbsp;Learning Programs&nbsp;are renamed to&nbsp;Learning Paths.&nbsp;This change happens immediately&nbsp;after the October 2021 release and&nbsp;the terminology of&nbsp;Learning Path&nbsp;is&nbsp;reflected for all roles.

This feature helps you define custom roles and assign specific responsibilities to set of users. This feature enables you to assign responsibilities outside the purview of the individual’s existing role.

You can create a custom role to provide authoring capabilities limited to a particular catalog. You can also create a role dedicated to manage reporting. Such roles can then be assigned to individuals who are supposed to take up these specific responsibilities.

## Create a custom role {#create-role}

1. Log in as an Administrator. Open&nbsp;**Users > Custom Role**.
1. Select Create Role. The Create New Role tab opens.

   ![](assets/create-new-role.png)

1. Enter the **Name of the Role**.
1. **Account privileges:** These privileges give the role owners access to specific system configuration aspects and which act on the entire account. Choose the access permissions. The user gets full control over assigned permissions.

   Note: Scope is not applicable on these privileges.

   ![](assets/account-privileges.png)

1. **Feature privileges- Core features**: Used to grant access to specific features for managing learning activities. Permissions to the following features can be given using this option.

   * Catalogs
   * Reports
   * Tags

   ![](assets/core-features.png)

1. **Feature privileges- Learning Objects:**&nbsp; Use this option to provide access to LOs related features. You can provide access to the following LOs.

   * Certifications
   * Courses
   * Job Aids
   * Learning Programs

   You can also grant specific operation control for the LOs. The permission can be one of the following:

   * Full Control
   * Edit and delete
   * Enrollment
   * Report

   ![](assets/learning-objects.png)

1. **Scope for feature privileges: **The scope of Feature privileges allocated to this role can be restricted to a specific User Group or one or more Catalogs.

   Catalogs: Use the radio button to provide control over **All catalogs** or use the **Set access per Catalog** option to provide access to specific catalogs. You can also select multiple catalogs.

   User Groups: Provide access to **All User Groups** or use the **Set access per user group** option to provide access to specific user groups. Only a single user group can be specified.

   **Note: **If you have selected Announcement, Gamification, Email Templates, Skills, and Users under Account Privileges, the User Group access is provided to all user groups by default and this option is disabled.

   If you have selected Learning Plans under Account Privileges, access to all Catalogs and User Groups is provided by default and these options under Scope is disabled.&nbsp;

   ![](assets/define-scope-of-privileges.png)

   In Captivate Prime 27.6, you can create a custom role to be scoped over multiple catalogs with each catalog being granted different set of permissions.

   To grant various permissions to the catalogs, follow the steps below:

   1. 
   1. 
   1. 
   1.

   Click the option **Set access per Catalog**.

   Choose the catalogs and you can see the level of permission for each catalog. The permissions are as follows:

   <table>
    <tbody>
     <tr>
      <td>
       <p>Permission</p></td>
      <td>
       <p>Description</p></td>
     </tr>
     <tr>
      <td>
       <p>Full Control</p></td>
      <td>
       <p>Grants Full Control on all Learning Objects. Permissions include Add, Edit, Delete, Read, Enroll, and Report.<br></p></td>
     </tr>
     <tr>
      <td>
       <p>Report</p></td>
      <td>
       <p>Grants access to the Reports tab only of the Learning Object.</p></td>
     </tr>
     <tr>
      <td>
       <p>Enroll</p></td>
      <td>
       <p>Grants permission to only enroll for the Learning Object.</p></td>
     </tr>
     <tr>
      <td>
       <p>Read Only</p></td>
      <td>
       <p>Grants permission to only view the Learning Objects in the Catalog.</p></td>
     </tr>
    </tbody>
   </table>

   Enable or disable the permissions according to your requirements.

   To save the changes, click **OK**. Then, to save the changes for the Custom Role, click **Save**.

   For example, consider the following scenario.

   The resultant permission, a custom user would have on a Learning Object, is an intersection of the Learning Object Permission and Catalog Permission.

   A custom user has Full Permission on Courses and only Read Only access on Catalog A but Full Permission on Catalog B. The results are a Read Only access on the courses of Catalog A and Full Control over the courses of Catalog B.

   A user with a Custom Role can:

   * Only view content from the catalogs he/she has access to.
   * Access any Learning Object based on the permissions of the Catalog the Learning Object is a part of.

   As an Administrator, you can:

   * Choose more than one catalog for a Custom Role.
   * Modify the permissions of a catalog any time.
   * Remove the catalogs from a scope to which you no longer want to grant permissions.
   * Implicitly grant Read Only permission to a catalog, when you grant permissions to the catalog.

   The table below illustrates how permissions are granted.

   <table width="100%" cellspacing="0" cellpadding="1" border="1">
    <tbody>
     <tr>
      <td width="177" valign="top">
       <p><strong>&nbsp;</strong></p></td>
      <td width="446" colspan="4" valign="top">
       <p><strong>Catalog Level Permission</strong></p></td>
     </tr>
     <tr>
      <td width="177" valign="top">
       <p><strong>Learning Object- Level Permission</strong></p>
       <p><strong>(Ex: Courses)</strong></p></td>
      <td width="106" valign="top">
       <p>Full Control</p></td>
      <td width="104" valign="top">
       <p>Enrol</p></td>
      <td width="104" valign="top">
       <p>Report</p></td>
      <td width="132" valign="top">
       <p>Read Only</p></td>
     </tr>
     <tr>
      <td width="177" valign="top">
       <p>Full Control</p></td>
      <td width="106" valign="top">
       <p>Full Control</p></td>
      <td width="104" valign="top">
       <p>Enrol</p></td>
      <td width="104" valign="top">
       <p>Report</p></td>
      <td width="132" valign="top">
       <p>Read Only</p></td>
     </tr>
     <tr>
      <td width="177" valign="top">
       <p>Enrol</p></td>
      <td width="106" valign="top">
       <p>Enrol</p></td>
      <td width="104" valign="top">
       <p>Enrol</p></td>
      <td width="104" valign="top">
       <p>Read Only</p></td>
      <td width="132" valign="top">
       <p>Read Only</p></td>
     </tr>
     <tr>
      <td width="177" valign="top">
       <p>Edit &amp; Delete</p></td>
      <td width="106" valign="top">
       <p>Edit &amp; Delete</p></td>
      <td width="104" valign="top">
       <p>Read Only</p></td>
      <td width="104" valign="top">
       <p>Read Only</p></td>
      <td width="132" valign="top">
       <p>Read Only</p></td>
     </tr>
     <tr>
      <td width="177" valign="top">
       <p>Report</p></td>
      <td width="106" valign="top">
       <p>Report</p></td>
      <td width="104" valign="top">
       <p>Read Only</p></td>
      <td width="104" valign="top">
       <p>Report</p></td>
      <td width="132" valign="top">
       <p>Read Only</p></td>
     </tr>
    </tbody>
   </table>

1. 
1. 
1. 
1. 
1. **Users:** Use this option to determine which users are assigned this role. You can choose&nbsp;one or more users using the search box.

   **Add users to custom role CSV upload: **To add users via CSV updalod, add a CustomRole column to the .csv file that the Administrator used to import users. Enter the role of the user under the CustomRole coloumn for the users to whom you wish to assign a cusrom role. To upload the CSV file, click  **[!UICONTROL Add > Upload a CSV]**.

   CustomRole columnNote:

   * You cannot search User Groups.
   * You cannot search users who already have Admin role assigned to them.
   * Assigning a new custom role to a user overrides&nbsp;user's previous custom role.

   ![](assets/users.png)

* A custom admin having permission to&nbsp;&nbsp;Settings will be able to configure the schedule for sync or sync users from Data-source even if they don't have permission to the Users entity.
* If a custom admin has permission on the Users entity, they can assign Admin role to themselves and become a standard Admin.

## Restrict folder access for custom authors {#folder-custom-author}

Captivate Prime already supports an ability to give access to content Library using&nbsp;custom roles. All custom&nbsp;authors who already have access to&nbsp;the&nbsp;content library, will continue to have access to all content files even after content folders are configured. This is to maintain the legacy behavior. Administrators need not make any changes&nbsp;in case&nbsp;they wish to continue to current behavior.&nbsp;&nbsp;

In case&nbsp;they wish to restrict access to these custom&nbsp;authors, Administrators need to edit the existing custom role and configure them by providing access to only specific content folders.&nbsp;

![](assets/folder-access-forcustomauthors.png)

While creating a custom author, you can now assign content folders to the author. Choose the option&nbsp;**Selected Folders**.

After you click the option, a new dialog opens, where you can assign the folders to the custom author.

![](assets/choose-folder.png)

Choose the folders and click&nbsp;**OK**.&nbsp;

## Learning Summary Dashboard for Custom Admin {#custom-admin-dashboard}

Custom&nbsp;admins can see the same view as what an Admin&nbsp;sees.&nbsp;A&nbsp;custom admin&nbsp;may&nbsp;data outside his scope.&nbsp;This is only&nbsp;applicable if&nbsp;the&nbsp;custom admin has full scope. To grant full scope, while creating a custom admin,&nbsp;enable the option&nbsp;**Full&nbsp;Control**&nbsp;in Account Summary Report.

![](assets/create-custom-role.png)

As a result,&nbsp;the options,&nbsp;**All Catalogs**&nbsp;and&nbsp;**All User&nbsp;Groups**&nbsp;will&nbsp;get selected and the rest disabled.

![](assets/scope-of-featureprivileges.png)

## Implicit permissions {#implicitpermissions}

When a user is given a role with a specific entity, there might be cases where they need&nbsp;access to other entities as well to be able to perform tasks on the granted entity. For Instance, if a user is given Create access on Course entity, they need access to Skill and Tag entities so that they can associate them with the course being created. This tables gives you information of such implicit permissions.

<table width="100%" cellspacing="0" cellpadding="1" border="1">
 <tbody>
  <tr>
   <th>Access Type</th>
   <th>Entity Permission granted by admin</th>
   <th>Implicit Entity Permission</th>
   <th>Implicit Access</th>
  </tr>
  <tr>
   <td>Manage</td>
   <td>User</td>
   <td>Group</td>
   <td>Crud</td>
  </tr>
  <tr>
   <td>Enroll</td>
   <td>All los (course, job aid, learning program, certification)</td>
   <td>User<br>
     Learning plan</td>
   <td>Read</td>
  </tr>
  <tr>
   <td>Create</td>
   <td>
    <p>Content group<br>
      Job aid<br></p></td>
   <td>Tag</td>
   <td>Read</td>
  </tr>
  <tr>
   <td>Create</td>
   <td>Course</td>
   <td>Content group<br>
     Tag<br>
     Skill<br>
     Badge<br>
     Job aid</td>
   <td>Read on all</td>
  </tr>
  <tr>
   <td>Create</td>
   <td>Learning program<br>
     Certification<br></td>
   <td>Course<br>
     Tag<br>
     Skill<br>
     Badge</td>
   <td>Read</td>
  </tr>
  <tr>
   <td>Create</td>
   <td>Learning plan</td>
   <td>Catalog<br>
     Group<br>
     Skill<br>
     All los (course, job aid, learning program, certification)</td>
   <td>Read</td>
  </tr>
  <tr>
   <td>Create</td>
   <td>Announcement</td>
   <td>User<br>
     Group<br>
     All los (course, job aid, learning program, certification)</td>
   <td>Read</td>
  </tr>
  <tr>
   <td>Create</td>
   <td>Gamification</td>
   <td>Branding</td>
   <td>Write</td>
  </tr>
  <tr>
   <td>*</td>
   <td>User</td>
   <td>Billing</td>
   <td>Read</td>
  </tr>
  <tr>
   <td>*</td>
   <td>Catalog</td>
   <td>Group<br>
     All los (course, job aid, learning program, certification)</td>
   <td>Read</td>
  </tr>
  <tr>
   <td>*</td>
   <td>Setting</td>
   <td>Branding<br>
     User</td>
   <td>Read</td>
  </tr>
  <tr>
   <td>*</td>
   <td>Branding</td>
   <td>Setting</td>
   <td>Read</td>
  </tr>
  <tr>
   <td>*</td>
   <td>Billing<br>
     Gamification</td>
   <td>User</td>
   <td>Read</td>
  </tr>
 </tbody>
</table>

## Access a custom role {#accessacustomrole}

When an Administrator assigns a custom role, you receive an email notification.&nbsp;

Note: If you are already logged in to Prime under a custom role, you would require to relogin to Prime to access the new role.

To switch between roles, click your profile icon on the upper-right corner of Prime and select the role.

## Learning plans scoped by configurable roles {#scopeconfigure}

In earlier versions of Captivate Prime, any Custom Role with permission to create learning plans could scope the learning plan for all types of user groups and Learning Objects.

The&nbsp;scope setting used to be disabled when learning plan access was granted, which gave the user access to All Catalogs and All User Groups by default.

All learning plans created by an Admin, by default, are applicable to all users. Users can also be assigned any Learning Object. On the other hand, users with Custom Roles have access to full scopes, for example, all catalogs, Learning Objects, or User Groups. This meant that admins were unable to create Custom Roles as expected that allowed access to Learning Plans for users with limited scope.

In this update of Captivate Prime, you can create Custom Roles for Learning Plans that allow scoping of users and Learning Objects. In other words, Learning Plans can be created with a limited scope that is derived from a custom admin's role scope.

Now, an Admin can define or restrict the scope while granting learning plan management access.

Custom admins can create learning plans with a limited scope, determined by the scope of the custom admin's configurable role. Such learning plans are only accessible to custom admins with the same role, besides being accessible to regular admins. In addition, the custom admins cannot see any other Learning Plans in the account.

Existing custom admins, having access to Learning Plans, will always have full scope (by definition). They will have access to all learning plans in the account just like a regular admins do. New custom roles created with full scope and new custom admins added to such roles, will continue to have access to all learning plans.

Learning plans created by Admins and full scope custom admins will be created as usual and will not be limited by scope.

In the section **Scope for Feature Privileges**, grant access to User Groups and/or Catalog for the Custom Role.

![](assets/scope-for-featureprivileges.png)

Assign a user to the Custom Role.

![](assets/assign-users-to-customrole.png)

The user now logs in to Captivate Prime as Custom Admin and now adds a Learning Plan.

When a new learner is added, the Custom Admin can select a training from the configurable role's scoped catalogs only.

This learning plan is now applicable to the learner only if the user is also added to the group within the learning plan’s scoped user group. All other learners get exempted from this learning plan.

## Learner gets added to the group {#learnergetsaddedtothegroup}

![](assets/add-learner-to-thegroup.png)

The custom admin can select any user group that has users from within the role's scoped user group.

When a user is added to the specified group, only users that are already part of the learning plan's scoped user group and got added to the specified user group will be assigned the Learning Object.

## Change in scope {#changeinscope}

When the Admin changes the scope of the custom role, the change also cascades to the Custom Admin. When the Custom Admin chooses a Learning Plan that was already scoped by a previous custom role, a message is displayed, as shown below:

![](assets/change-scope.png)

The Custom Admin now must update or refresh the earlier scope to the new scope.

Clicking **Refresh Scope** updates the scope. There is a warning message that displays.

![](assets/refresh-scope-message.png)

Clicking **Yes** updates the scope.

## Add gamification report to a custom role {#gamification-custom}

An administrator can enable gamification reports for a custom user.

1. In the **Custom Roles** page, enter the name of the custom role.
1. In the&nbsp;**Feature Privileges: Core Features** section,&nbsp; enable the option **Full Control** for the category **Reports**.  

1. In the section **Users**, select the user that will be assigned the newly created custom role.
1. Click **Save**.

When a user logs in as Custom Admin and clicks **Reports** on the left pane, the transcripts appear, as shown below:

![](assets/download-gamificationtranscripts.png)

Click **Gamification Transcripts**, choose a user, and generate the report.

If an Administrator changes the level points, the reports show levels according to the current points.

Resetting gamification does not reset the level achieved date.

## Frequently Asked Questions {#frequentlyaskedquestions}

**1.&nbsp;How to create a Custom Role?**

A Custom Role is like a subset of an Author or Administrator role. Allow one or multiple privileges, define the scope, and assign the role to a user.

Click **Users > Custom Roles**. In the Custom Roles page, click **Create Role**. Enter the name of the custom role and set the privileges for the role. For more information, see [Create a custom role](custom-role.md#create-role).
