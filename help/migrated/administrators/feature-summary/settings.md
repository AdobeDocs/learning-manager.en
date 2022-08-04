---
description: Learn about the Learning Manager account settings that you can configure as an administrator. 
jcr-language: en_us
title: Settings
contentowner: manochan
---


# Settings {#settings}

Learn about the Learning Manager account settings that you can configure as an administrator.

You can change your Administrator profile settings and update your Account settings. View your profile information, add/change profile photo, and modify&nbsp;**About me**&nbsp;content. Update your company info, set up log in methods for users, and set up connect integration through account settings.

# Account settings {#accountsettings}

To update your organization's account settings, click **Settings **on the left pane.&nbsp;

**Basic info (Company info)  
**Click **Change **on the page and edit country, timezone, locale, and financial year settings.&nbsp;

**Configure contact admin**

If you want to add or change the support administrators email addresses for your organization , you can configure by clicking **General** on the left pane. Click **Change**&nbsp;adjacent to **Support Email ID** and add the email ids. Email is sent to these administrators when learner clicks **Contact Admin**&nbsp;at the footer of the page.&nbsp;

Add additional email-ids with semi-colon as a separator. &nbsp;

**Login methods  
**Administrators can choose the mode using which your internal or external users can access the account.&nbsp;

* **Internal users:&nbsp;**For internal users, you can set&nbsp;Adobe ID or Single Sign-on as a log in mode.&nbsp;

* **External users:&nbsp;**For external users, you can set Adobe ID or Single Sign-On or Learning Manager ID.**&nbsp;**If you choose, Learning Manager ID, external users can log into this account after creating their Learning Manager username and password.

**Note:&nbsp;**If there are multiple external profiles set, all profiles can have any one type of login. For example, if login type is Adobe ID, all profiles have to login using Adobe ID only. Each profile cannot have its individual login type.

You can access Learning Manager application using Adobe ID or by using Single Sign-On. Single sign‑on is a mechanism that allows a user to authenticate once and gain access to multiple applications many number of times. This configuration is not mandatory for the organization. If your organization has SAML 2.0 based SSO provider, you can use it to configure Learning Manager application. The configuration is required at your organization level and at Learning Manager application. If you choose to use SSO, contact Adobe support to receive configuration instructions

**Feedback**

Click **Feedback** on the left pane to set up the questionnaire to get feedback from learners after completing a course. Refer to [courses feature help content](courses.md)on creating L1 and L3 feedback.&nbsp;

**Multi attempts**

Select **Settings** > **General** > **Multiple Attempts.&nbsp;**

If you enable the ‘Multi Attempts’ check box, then the Authors can set ‘Multiple attempts’ for interactive e-learning courses or modules .On selecting the second checkbox, administrators can set ‘Infinite attempts’ by default for any newly created interactive e-learning courses.

![](assets/admin-config.png)

**Course Moderation**

Click&nbsp;**General**&nbsp;from the left pane, and select the Course Moderation option to enable the Course Moderation functionality. To know more about this feature, see&nbsp; [Course Moderation](courses.md#main-pars_header_1879001177).

**Discussion Board**

If you enable the Discussion Board check box, then the learners and instructors can post comments for courses using the Discussion tab from the Courses page in the Learners App. However, if course level settings indicate that this feature is not selected, then the course level settings take precedence over administrator settings.

**Learner Dashboard**

From the left pane, click Learner Dashboard. This page allows you to choose the widgets that you want to display on the Learners page. Select the widgets that you want to enable in the Learners Page. The widgets that are not selected will not appear on the Learners page.

**Adobe Connect**

Click&nbsp;**Adobe Connect**&nbsp;on the left pane to configure Adobe Connect account to host virtual classroom sessions. For more information, refer to&nbsp; [Adobe Connect](adobeconnect-integration.md)&nbsp;feature help.&nbsp;

# General settings {#general}

Enable or disable the following settings:

<table width="100%" cellspacing="0" cellpadding="1" border="1"> 
 <tbody> 
  <tr> 
   <th><p>Name</p> </th> 
   <th>Description</th> 
  </tr> 
  <tr> 
   <td>Show Course Effectiveness</td> 
   <td>If enabled, Learners can see current Course Effectiveness on the Course tile.&nbsp;This feature is only for available for courses. Star rating is not supported for Learning Programs or Certificates. It is available for courses and learning program but not certifications.</td> 
  </tr> 
  <tr> 
   <td>Course Moderation</td> 
   <td>If enabled, all changes to Courses must need Admin approval before the courses visible to the learners.</td> 
  </tr> 
  <tr> 
   <td>Discussion Board</td> 
   <td>If you enable the Discussion Board check box, then the learners and instructors can post comments for courses using the Discussion tab from the Courses page in the Learners App. However, if course level settings indicate that this feature is not selected, then the course level settings take precedence over administrator settings.</td> 
  </tr> 
  <tr> 
   <td>Multiple Attempts</td> 
   <td>If enabled, Author can configure multiple attempts for course modules.</td> 
  </tr> 
  <tr> 
   <td>Explore Skills Option</td> 
   <td>If enabled, Learners can explore Peer and Leadership Skills, and subscribe to the Skills of their choice.</td> 
  </tr> 
  <tr> 
   <td>Skills/Tags Visibility</td> 
   <td>Display all Skills and tags to Learners. You can either show all skills and tags or show skills and tags that are assigned, or those that are part of the Catalogs visible to the Learner.</td> 
  </tr> 
  <tr> 
   <td>Unique Learning Object Ids</td> 
   <td>If enabled, an Admin or an Author can add a unique id for each Learning Object.</td> 
  </tr> 
  <tr> 
   <td>Show Filter Panels</td> 
   <td><p><a id="filter-panels"></a>Control which filter panels are available to users in the Learner application for refining their search results. The options are as follows:</p> 
    <ul> 
     <li>Catalogs</li> 
     <li>Type</li> 
     <li>Format</li> 
     <li>Duration</li> 
     <li>Skills</li> 
     <li>Skill Levels</li> 
     <li>Tags</li> 
    </ul> <p>When the learner launches the learner app, in the My Learning and Catalog sections, the learner can see the filters in their respective panels.</p> <p><b>Note: </b>The filters <b>Format </b>and <b>Duration </b>are switched off by default and do not appear to the learners immediately after the release. The Administrator should enable them.&nbsp;<br> </p> </td> 
  </tr> 
  <tr> 
   <td>Show Catalog Listing</td> 
   <td>If enabled, Learners can see a list of all Catalogs available to them. Learners can use this to refine how the Learning Objects are displayed.</td> 
  </tr> 
  <tr> 
   <td>Product Terminology</td> 
   <td>Learning Manager has a standard terminology that is used across the product. Modify the terminology to match your organization's needs.</td> 
  </tr> 
  <tr> 
   <td>Module Version Update</td> 
   <td>Configure the default setting to update content. The settings can be modified for each content from the course page.</td> 
  </tr> 
  <tr> 
   <td>Auto-register Users</td> 
   <td>If enabled, newly imported Users are auto-registered. By default, users must be registered manually before they can start using Learning Manager.</td> 
  </tr> 
  <tr> 
   <td><a id="autodelete"></a>Auto-delete Internal Users</td> 
   <td>If enabled, Internal users get deleted automatically if they do not access the system for specified number of days. This feature is applicable to users who only have the role <b>Learner</b>. To restore the access, users must contact the Administrator.<br> </td> 
  </tr> 
  <tr> 
   <td>Show Catalog Labels</td> 
   <td>If enabled, Administrators and Authors can set Catalog Labels and values and link them to Learning Objects.</td> 
  </tr> 
  <tr> 
   <td>Learners can view their scores</td> 
   <td>If enabled, the learners can view their scores in the learner transcript.</td> 
  </tr> 
  <tr> 
   <td><a id="digest-email-admin-settings"></a>Digest Email<br> </td> 
   <td><p>An Administrator can enable or disable sending an email to learners. The Admin will also be able to control the frequency of the emails sent.</p> 
    <ul> 
     <li>For <b>active accounts</b>, digest emails will be disabled by default, which the Admin can enable it manually.</li> 
     <li>For <b>trial accounts</b>, the option for digest emails will remain disabled and the Admin cannot enable the option.</li> 
    </ul> <p>If the feature is disabled, then:</p> 
    <ul> 
     <li>The option <b>Digest Email</b> will be disabled.</li> 
     <li>A learner cannot see the user setting for digest email subscription.</li> 
    </ul> <p>&nbsp;If the feature is enabled, then:</p> 
    <ul> 
     <li>The Admin can enable and modify the Digest Email option.</li> 
     <li>From the <b>Profile Settings </b>on the learber app, a learner (not in the DND list) can opt to subscribe/unsubscribe to the digest email.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Enable Training Card Icons<br> </td> 
   <td>If enabled, icons will be seen on Training Cards on the Learner app.<br> </td> 
  </tr> 
  <tr> 
   <td><a id="footer"></a>Footer Links</td> 
   <td><p>Add links or email ids that appear as footers. You can add a maximum of three footer links.</p> <p>To customize the links on the footer, perform the following steps:</p> 
    <ol> 
     <li>Click <b>Add More</b>, enter the name, and the URL or email id in the fields specified. Prefix the URL with http:// or https://.</li> 
     <li>To cascade the change across all locales, click <b>Replicate</b>. This ensures that all languages get the name and the url.</li> 
     <li>To save the changes, click <b>Save</b>. You can see a pop-up message confirming the change. After you click OK, the footer gets populated with the newly added links.</li> 
    </ol> <p>Additionally, you can:</p> 
    <ul> 
     <li>Click the&nbsp;<b>Reset</b>&nbsp;icon to reset the default values in the <b>Help</b> and <b>Contact Admin</b> fields.</li> 
     <li>Customize the link on the footer for all languages. Click the <b>Language</b> drop-down list, select the language, and add the <b>Name</b> and <b>URL</b> in the specified fields. After you save the changes, the updated links appear on the footer.<br> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Report Timezone<br> </td> 
   <td><p><a id="report_timezone"></a>&nbsp;Set an account level preference to export the Learning Transcript in the following time zones:</p> 
    <ul> 
     <li>UTC (Default behavior)</li> 
     <li>Account-level time zone preference</li> 
    </ul> <p>The Learner Transcript downloaded using Jobs API also downloads the data in the selected&nbsp;timezone.</p> <p><b>Note:&nbsp;</b>There is no change expected in the Learner Transcript by default immediately after the release. Administrators can configure this setting from Admin &gt; Settings &gt; General &gt; Report&nbsp;Timezone.</p> </td> 
  </tr> 
 </tbody> 
</table>

<table border="0" cellpadding="0" cellspacing="0" width="1709"> 
 <tbody> 
  <tr> 
   <td height="20" width="147">Name</td> 
   <td width="1562">Description</td> 
  </tr> 
  <tr> 
   <td height="20">Show Course Effectiveness</td> 
   <td>If enabled, Learners can see current Course Effectiveness on the Course tile.</td> 
  </tr> 
  <tr> 
   <td height="20">Course Moderation</td> 
   <td>If enabled, all changes to Courses must need Admin approval before the courses visible to the learners.</td> 
  </tr> 
  <tr> 
   <td height="20">Discussion Board</td> 
   <td>If you enable the Discussion Board check box, then the learners and instructors can post comments for courses using the Discussion tab from the Courses page in the Learners App. However, if course level settings indicate that this feature is not selected, then the course level settings take precedence over administrator settings.</td> 
  </tr> 
  <tr> 
   <td height="20">Multiple Attempts</td> 
   <td>If enabled, Author can configure multiple attempts for course modules.</td> 
  </tr> 
  <tr> 
   <td height="20">Explore Skills Option</td> 
   <td>If enabled, Learners can explore Peer and Leadership Skills, and subscribe to the Skills of their choice.</td> 
  </tr> 
  <tr> 
   <td height="20">Skills/Tags Visibility</td> 
   <td>Display all Skills and tags to Learners. You can either show all skills and tags or show skills and tags that are assigned, or those that are part of the Catalogs visible to the Learner.</td> 
  </tr> 
  <tr> 
   <td height="20">Unique Learning Object Ids</td> 
   <td>If enabled, an Admin or an Author can add a unique id for each Learning Object.</td> 
  </tr> 
  <tr> 
   <td rowspan="10" height="191">Show Filter Panels</td> 
   <td>Control which filter panels are available to users in the Learner application for refining their search results. The options are as follows:</td> 
  </tr> 
  <tr> 
   <td height="19">Catalogs</td> 
  </tr> 
  <tr> 
   <td height="19">Type</td> 
  </tr> 
  <tr> 
   <td height="19">Format</td> 
  </tr> 
  <tr> 
   <td height="19">Duration</td> 
  </tr> 
  <tr> 
   <td height="19">Skills</td> 
  </tr> 
  <tr> 
   <td height="19">Skill Levels</td> 
  </tr> 
  <tr> 
   <td height="19">Tags</td> 
  </tr> 
  <tr> 
   <td height="19">When the learner launches the learner app, in the My Learning and Catalog sections, the learner can see the filters in their respective panels.</td> 
  </tr> 
  <tr> 
   <td height="20">Note:&nbsp;The filters&nbsp;Format&nbsp;and&nbsp;Duration&nbsp;are switched off by default and do not appear to the learners immediately after the release. The Administrator should enable them.&nbsp;</td> 
  </tr> 
  <tr> 
   <td height="20">Show Catalog Listing</td> 
   <td>If enabled, Learners can see a list of all Catalogs available to them. Learners can use this to refine how the Learning Objects are displayed.</td> 
  </tr> 
  <tr> 
   <td height="20">Product Terminology</td> 
   <td>Learning Manager has a standard terminology that is used across the product. Modify the terminology to match your organization's needs.</td> 
  </tr> 
  <tr> 
   <td height="20">Module Version Update</td> 
   <td>Configure the default setting to update content. The settings can be modified for each content from the course page.</td> 
  </tr> 
  <tr> 
   <td height="20">Auto-register Users</td> 
   <td>If enabled, newly imported Users are auto-registered. By default, users must be registered manually before they can start using Learning Manager.</td> 
  </tr> 
  <tr> 
   <td height="20">Auto-delete Internal Users</td> 
   <td>If enabled, Internal users get deleted automatically if they do not access the system for specified number of days. This feature is applicable to users who only have the role&nbsp;Learner. To restore the access, users must contact the Administrator.</td> 
  </tr> 
  <tr> 
   <td height="20">Show Catalog Labels</td> 
   <td>If enabled, Administrators and Authors can set Catalog Labels and values and link them to Learning Objects.</td> 
  </tr> 
  <tr> 
   <td height="20">Learners can view their scores</td> 
   <td>If enabled, the learners can view their scores in the learner transcript.</td> 
  </tr> 
  <tr> 
   <td rowspan="9" height="172">Digest Email</td> 
   <td>An Administrator can enable or disable sending an email to learners. The Admin will also be able to control the frequency of the emails sent.</td> 
  </tr> 
  <tr> 
   <td height="19">For&nbsp;active accounts, digest emails will be disabled by default, which the Admin can enable it manually.</td> 
  </tr> 
  <tr> 
   <td height="19">For&nbsp;trial accounts, the option for digest emails will remain disabled and the Admin cannot enable the option.</td> 
  </tr> 
  <tr> 
   <td height="19">If the feature is disabled, then:</td> 
  </tr> 
  <tr> 
   <td height="19">The option&nbsp;Digest Email&nbsp;will be disabled.</td> 
  </tr> 
  <tr> 
   <td height="19">A learner cannot see the user setting for digest email subscription.</td> 
  </tr> 
  <tr> 
   <td height="19">&nbsp;If the feature is enabled, then:</td> 
  </tr> 
  <tr> 
   <td height="19">The Admin can enable and modify the Digest Email option.</td> 
  </tr> 
  <tr> 
   <td height="20">From the&nbsp;Profile Settings&nbsp;on the learber app, a learner (not in the DND list) can opt to subscribe/unsubscribe to the digest email.</td> 
  </tr> 
  <tr> 
   <td height="20">Enable Training Card Icons</td> 
   <td>If enabled, icons will be seen on Training Cards on the Learner app.</td> 
  </tr> 
  <tr> 
   <td rowspan="8" height="153">Footer Links</td> 
   <td>Add links or email ids that appear as footers. You can add a maximum of three footer links.</td> 
  </tr> 
  <tr> 
   <td height="19">To customize the links on the footer, perform the following steps:</td> 
  </tr> 
  <tr> 
   <td height="19">1. Click&nbsp;Add More, enter the name, and the URL or email id in the fields specified. Prefix the URL with http:// or https://.</td> 
  </tr> 
  <tr> 
   <td height="19">2. To cascade the change across all locales, click&nbsp;Replicate. This ensures that all languages get the name and the url.</td> 
  </tr> 
  <tr> 
   <td height="19">3. To save the changes, click&nbsp;Save. You can see a pop-up message confirming the change. After you click OK, the footer gets populated with the newly added links.</td> 
  </tr> 
  <tr> 
   <td height="19">Additionally, you can:</td> 
  </tr> 
  <tr> 
   <td height="19">Click the&nbsp;Reset&nbsp;icon to reset the default values in the&nbsp;Help&nbsp;and&nbsp;Contact Admin&nbsp;fields.</td> 
  </tr> 
  <tr> 
   <td height="20">Customize the link on the footer for all languages. Click the&nbsp;Language&nbsp;drop-down list, select the language, and add the&nbsp;Name&nbsp;and&nbsp;URL&nbsp;in the specified fields. After you save the changes, the updated links appear on the footer.</td> 
  </tr> 
  <tr> 
   <td rowspan="5" height="96">Report Timezone</td> 
   <td>&nbsp;Set an account level preference to export the Learning Transcript in the following time zones:</td> 
  </tr> 
  <tr> 
   <td height="19">UTC (Default behavior)</td> 
  </tr> 
  <tr> 
   <td height="19">Account-level time zone preference</td> 
  </tr> 
  <tr> 
   <td height="19">The Learner Transcript downloaded using Jobs API also downloads the data in the selected&nbsp;timezone.</td> 
  </tr> 
  <tr> 
   <td height="20">Note:&nbsp;There is no change expected in the Learner Transcript by default immediately after the release. Administrators can configure this setting from Admin &gt; Settings &gt; General &gt; Report&nbsp;Timezone.</td> 
  </tr> 
  <tr> 
   <td height="19">Badgr Integration</td> 
   <td>If enabled, the learners will be able to upload their badges to the Badgr website. In customer education scenarios, organizations want to be able to "certify" their customers and give them an opportunity to display those credentials over social media. This motivates the learner to take a training and share his/her achievements with others.&nbsp;</td> 
  </tr> 
  <tr> 
   <td height="135"><p>Show rating</p> </td> 
   <td width="1562"> 
    <ul> 
     <li>If the option <b>Course Effectiveness</b> is enabled, learners will be able to see only the value of the course effectiveness.</li> 
     <li>If the option <b>Star rating</b> is enabled, learners will be able to view only the average star rating and the number of learners who have rated the course.<br> </li> 
    </ul> <p>This feature is only for available for courses. Star rating is not supported for Learning Programs or Certificates.<br> <br> <b>Note: </b>This change affects the learner app only.&nbsp;</p> <p>In all other apps (admin, author, manager, custom admin, custom author), changes in the settings (star rating/course effectiveness/disabling show rating) will not have any affect.&nbsp;</p> <p>For new accounts, the&nbsp;<b>Show Ratings</b>&nbsp;section will have the option&nbsp;<b>Star rating</b>&nbsp;enabled by default.</p> <p>For existing accounts,&nbsp;if the account previously had the option&nbsp;<b>Course effectiveness</b>&nbsp;enabled, then the&nbsp;<b>Show Ratings</b>&nbsp;section will be enabled with the option&nbsp;Course effectiveness&nbsp;selected.&nbsp;If the option&nbsp;<b>Course effectivenes</b>s&nbsp;is disabled, then the&nbsp;<b>Show Ratings</b>&nbsp;section will also be disabled. When the&nbsp;<b>Show Ratings</b>&nbsp;section is enabled, the option&nbsp;<b>Star rating</b>&nbsp;will be enabled by default.</p> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody>
  <tr> 
   <td><p>Learning Paths</p> </td> 
   <td><p><span style="color: rgb(50, 50, 50);">If the option <b>Enable Extended features of Learning Path</b> is enabled, Admins will be able to include Learning Paths inside Learning Paths, and combine those Learning Paths with Courses. The option is irreversible.</span><br> </p> </td> 
  </tr> 
  <tr> 
   <td><p>Instructor Management<br> </p> </td> 
   <td><p>Enable this setting to restrict the list of instructors which can be selected while creating classroom/virtual classroom sessions. All users having the instructor privileged can only be assigned as an instructor to any session. This restriction does not apply to migration workflows.<br> </p> </td> 
  </tr> 
  <tr> 
   <td><p>Enable Price at trainings</p> </td> 
   <td><p>If enabled, an author can specify a price for a course. The learner can then see the price on their course card and choose to buy the course.&nbsp;When you add an Adobe Commerce connection, this checkbox is automatically selected and enforced.<br> </p> </td> 
  </tr> 
  <tr> 
   <td><p>Module Preview<br> </p> </td> 
   <td><p>If enabled, an Administrator or Author will be able to select the modules that are available for learners to preview without enrollment.<br> </p> </td> 
  </tr> 
 </tbody>
</table>

## AI-based recommendation

Learning Manager includes a brand-new learner homepage, which is modern, more content-driven, and personalized according to a learner’s preferences. AI-based learning recommendations aim to enhance learner engagement and identify and address gaps in learning.

The recommendation algorithm is designed to take in multiple sources of input including Industry data on Job roles, titles and descriptions that Adobe has sourced from its partners. This data is then used to train Adobe’s AI algorithms so that Learning Manager can come up with a map that connects industry aligned skills to job titles and/or designations. This then becomes one input to the recommendation algorithm

Learning Manager then uses topic modeling algorithms to analyze the training content within an account and map them to the skills.

Learning Manager uses peer activity data as another signal to drive the recommendation algorithm in a personalized manner. Activities like enrollment, completion and any explicit feedback provided by learners is used here.

Additionally, Learning Manager uses explicit and implicit information gathered from individual learners to further personalize recommendations. A learner will be able to indicate their areas of interest explicitly through enrollments and Learning Manager will receive this information implicitly based on how the Learner ends up taking up the trainings.

Finally, the Admin will also be able to influence the recommendation algorithm using learner attributes that Learning Manager should look at when defining peer groups, and also by actually highlighting Trainings for specific user groups.&nbsp;&nbsp;

# Renaming Learning objects {#renaminglearningobjects}

This feature is only available in  English  language.

Administrators can now rename Learning Objects in Learning Manager. The following are the terminologies that can be renamed.

Module  
Course  
Learning Program  
Certification  
Learning Plan  
Job Aid  
Catalog  
Skill  
Badge  
Announcement  
My Learning  
Leaderboard  
Effectiveness  
Prerequisite  
Prework  
Core Content  
Testout  
Self Paced  
Blended  
Classroom  
Virtual Classroom  
Activity

To rename the terminologies, follow these steps.

1. As an Administrator, click **[!UICONTROL Settings]** > **[!UICONTROL General]** > **[!UICONTROL Product Terminology]**.&nbsp;The product terminology option opens.&nbsp;

   ![](assets/product-terminology.png)

1. Changes can be made by uploading a modified product terminology template by downloading the sample CSV file. To download the sample CSV file, click on the **[!UICONTROL Download here]**option.
1. The downloaded CSV file contains the name of the objects in  coloum &nbsp;A. In  coloumn &nbsp;B, choose the name you want to assign to the respective object. Note that you need to update the singular and plural form of the name separated by a (|).
1. You can choose to modify&nbsp;one or more rows. You can either retain the non-modified rows or remove them from the CSV file before uploading them.
1. Upload the modified CSV file and click **[!UICONTROL Save]**. Learning Manager refreshes reflecting your changes.
1. To reset to default terminologies, click **[!UICONTROL Reset Product Terminology.]**

   ![](assets/with-reset-option.png)

# Profile settings {#profilesettings}

1. Click the drop-down arrow at the upper-right corner, adjacent to your photo/account and choose&nbsp;**Profile Settings**.
1. From the pop-up dialog,&nbsp;you can add/change a photo by hovering the mouse and by clicking&nbsp;**Edit**&nbsp;in the profile photo area.
1. Add/modify&nbsp;**About** content by clicking **Edit** adjacent to it.&nbsp;
1. Click **Save.**

# Content Folder {#content-folder}

Learning Manager supports private content folders.&nbsp;An Administrator can configure private content folders and provide its access to specific custom-authors using Custom Roles. Note that Standard Authors (also called as Full Authors) continue to have access to all the content in the account. Hence Full Authors have&nbsp;access to all folders and all the content.&nbsp;

Content Folders can be configured by Administrators. Only once configured, content folders become visible to authors and they get an ability to place the content in one or multiple folders.&nbsp;

To add a content folder, in the Administrator app,&nbsp;click&nbsp;**Settings > Content Folder**.

![](assets/manage-content-folders.png) 

### **Folder**

A folder is a repository of content, which is a subset of the entire content library available in an account with the following properties:

* Only an Admin can create, edit, or delete a folder.
* An Admin can control access to folders&nbsp;as part of defining roles only for custom admins.  
* Content **must at all times, be associated with at least one folder**. To start with, all content will be associated with the Public folder, which can later be changed.
* Content can be associated with multiple folders at the time of creation, which will also be possible by a copy operation
* All folder names must be unique within the account, otherwise there will be an error in naming a folder.

Folders only control visibility of content and don't create copies of content. Therefore, editing content will reflect in all the associated folders.

### Public folder

A public folder is always present in an account and initially, all content will be part of this folder. Later, authors can move content out of this folder into other folders. A public folder has the following properties:

* All content associated with this folder will be accessible to all types of authors, by default.
* Any content that is a part of a public folder, cannot be part of any other folder. The converse also holds true.

This folder cannot be part of configurable role definition. Consequently, not having a public folder in configurable role definition doesn't restrict access to a public folder.

### Private folder

* Any folder created by an Admin is a private folder.

### Folder operations

**Add a folder**

To add a folder, click&nbsp;**Add&nbsp;**on the upper-right corner of the window.

**Delete a folder**

You can also delete a folder.&nbsp;Select the folder to delete, click the&nbsp;Actions&nbsp;menu, and click&nbsp;**Delete Folder**.

**NOTE: **Folders can be deleted&nbsp;when&nbsp;all of&nbsp;its associated content is also associated with other folders.&nbsp;If there is content that is linked&nbsp;with only the folder being deleted, first move the content to another folder, and then delete the folder.

# Frequently Asked Questions {#frequentlyaskedquestions}

**1. How to create different folders for content library?**

Click **Settings > Content Folder**. To add a folder, click **Add **on the upper-right corner,&nbsp; and in the dialog, enter the name and description of the folder.

Content Folders can be configured by Administrators. Only once configured, content folders become visible to authors and they get an ability to place the content in one or multiple folders.&nbsp;

For more information, see the section on [Content Folder](settings.md#content-folder).

**2.&nbsp;How to add financial year for the account?**

In **Settings > Basic Info**, click **Change**. From the&nbsp;**Financial year starts from** drop-down list, select the month.