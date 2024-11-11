---
title: What's new in this release
description: Learn about the new features and enhancements in the November 2023 release of Adobe Learning Manager.
exl-id: d670dc47-d57f-464a-bee8-064cc16e59f9
---
# What's new in this release

## Revamped User Interface

The Adobe Learning Manager User Interface has undergone a few updates to offer a cleaner and more modern experience. The landing pages for Admin and Author roles have been revamped, and UI theme updates have been made for all roles. However, no changes have been made to the location of menus, buttons, or links and you'll be able to find these exactly where they were located before. 

The theme updates will apply automatically to accounts that use the default theme. The UI theme updates will not impact accounts that have made modifications to use a custom theme. Such accounts need to switch back to the default theme to get the new theme updates.

![UI image](assets/refreshed-ui.png)

### About this change

**What changes in this release?**

There is a new template in the header, which auto-resizes the logo to a fixed size and position while maintaining the logo's aspect ratio. The change intends to enhance the visual appeal of the learner experience.

The organization's name in the header also auto resizes to 336 (minimum) x 680 (maximum) px for learners.

**What is the recommended size of the logo?**

The maximum width of the logo is 210px. Logos with a width of more than 210px or a height of more than 42px are resized to 42x210px.

If the logo size is less than the recommended size, the logo is uploaded without any change, and is center-aligned.

**What is the impact?**

Company names that are longer will be trimmed, and an ellipsis will fill the space.

**What do we recommend?**

* Resize the image keeping the aspect ratio intact. Recommended max logo size is 42 px (vertical) x 210 px (horizontal).
* For many accounts, this would automatically apply; no change is required.

## Native extensibility

Set up custom experiences within the native version of Adobe Learning Manager, allowing you not to use headless for less complicated cases. You can also create custom apps and place them at various points in the native version of the learner, manager, admin, author, or instructor workflows.

A Learner can use a custom-built app or an extension, which an Admin had created.

View [Native extensibility](/help/migrated/administrators/feature-summary/native-extensibility.md) to learn more.

## Quiz creation tool

You'll now be able to create assessments within Learning Manager with the new quiz creation tool on the Content Library page. The assessments created become part of the Content Library and can be added to a "public" folder for course reusability. 

View [Create a quiz](/help/migrated/authors/feature-summary/content-library.md) to learn more.

## Reporting changes in this release

### Changes in job aid enrollment report

In earlier versions of Adobe Learning Manager, the Job Aid enrollment report had no filters. Adobe Learning Manager downloaded all the data of an account.

In this release, we've added a dropdown in the Job Aids Report dialog.

### Changes in notifications announcement report

In earlier releases of Adobe Learning Manager, the Notification Announcement report didn't have any filters. Adobe Learning Manager downloaded all notifications in the account.

In this release, we've added a date filter, using which you can download the notifications within a specified period.  You can, however, download the report for the last six months only.

### Changes in course revisit data in enrollment report

In this release, you can download the course revisit information in an Enrollment report by specifying a time. The download period will be limited to six months for accounts with more than five million enrollments. For all other accounts, the period will be 15 months.

You can download the report from **[!UICONTROL Reports]** > **[!UICONTROL Custom Reports]** > **[!UICONTROL Historic Reports]** > **[!UICONTROL Course Access Report]**.

### Changes in learner transcript

In earlier releases of Adobe Learning Manager, if a Custom Admin had User scope, the Learning Transcript contained the deleted users. In this release, the Learning Transcript will contain the deleted users if the Custom Admin has either the User scope or access to all user groups.

### Changes in attendance report

The Attendance report on the attendance page of Courses in the Admin app and on the Session Learners page of the Instructor app used to get downloaded synchronously. In this release, this report will be downloaded asynchronously via a notification.

For more information on reports, see [Reports](/help/migrated/administrators/feature-summary/reports.md) in Adobe Learning Manager.

## Decommissioning of Content Marketplace

The courses that have expired in the imported content marketplace catalog (Enterprise training) will be auto-deleted once they expire. The courses will be set to retire when the content is marked for decommissioning. Existing enrolled learners can consume them within a limited timeframe after which they will be deleted. This will keep the catalog clean and not show users any expired courses.

## Skill-based new recommendations

Adobe Learning Manager improves the recommendations for Customer and Partner-enabled accounts. This improvement in the recommendation algorithm with the change in the ranking algorithm for course, learning path, and certification provides a better user experience in content discovery.

The algorithm will no longer allow peer-based recommendations. The change will not affect the existing users, but the Industry Aligned option will continue to exist. For the Custom option, Adobe Learning Manager will no longer allow custom peer-based selection.

The peer group now becomes an account, and learners will see a string that shows the trending topics in the group. All recommendations are explainable. For example, if you are viewing something on a subject, the card on the strip will display the reason for the course.

## Custom Admin workflow enhancements

Custom Admins will now have more parity with Admin roles regarding access to reports. Admins will be able to configure reporting access with better control.

In Adobe Learning Manager, only Learning Transcript and Gamification Transcript are available to a Custom Admin. In this release, a Custom Admin can access all custom reports except for xAPI and email reports, which are still available only to the admin. Access to all the reports is subject to the catalog and user scope which the custom admin has. There are few reports which are available only with full scope. They are:

<table>
    <tbody>
        <tr>
            <td>
    <p style="text-align: left;"><b>Report</b></p></td>
   <td>
    <p style="text-align: left;"><b>Available</b></p></td>
   <td>
    <p style="text-align: left;"><b>Scope</b></p></td>
        </tr>
    <tr>
   <td>
    <p>Content Audit Trail</p></td>
   <td>
    <p>Yes</p></td>
   <td>
    <p>Full Catalog</p></td>
  </tr>
  <tr>
   <td>
    <p>User Audit Trail</p></td>
   <td>
    <p>Yes</p></td>
   <td>
    <p>Full User</p></td>
  </tr>
  <tr>
   <td>
    <p>Login Access</p></td>
   <td>
    <p>Yes</p></td>
   <td>
    <p>Full User</p></td>
  </tr>
    </tbody>
</table>

**New Read-Only controls**

In the Custom Roles page, we've added the following Read Only options to enable admins to provide more flexible options to the Custom Admin: Custom admin will now have additional Read Only permission for Users, Email templates, and Learning Plans.

**Users**:

If you select Read Only, the Custom Admin will be able to view all users but will not be able to edit user data, and create a self-registration portal for users.

**Learning Plans**: 

If you select Read Only, a Custom Admin cannot add or edit a Learning Plan. They can download a Learning Plan report and view its details. But they cannot change the course details.

>[!NOTE]
>
>Learning Plans will be additional read-only along with full control.

**Email Templates**

If you select Read Only, a Custom Admin can view the email templates. They cannot enable or disable email template settings but can download email access reports.

### Learner transcripts

If User permission or All user group is selected, and custom admin tries to download Learner Transcripts, the Include deleted learner option will return all deleted learners in the report.

### Reports

A Custom Admin can access the following reports according to the defined scope:

<table>
    <tbody>
        <tr>
            <td>
    <p style="text-align: left;"><b>Report</b></p></td>
   <td>
    <p style="text-align: left;"><b>Available</b></p></td>
   <td>
    <p style="text-align: left;"><b>Scope</b></p></td>
        </tr>
    <tr>
   <td>
    <p>Content Audit Trail</p></td>
   <td>
    <p>Yes</p></td>
   <td>
    <p>Full Catalog</p></td>
  </tr>
  <tr>
   <td>
    <p>User Audit Trail</p></td>
   <td>
    <p>Yes</p></td>
   <td>
    <p>Full User</p></td>
  </tr>
  <tr>
   <td>
    <p>Login Access</p></td>
   <td>
    <p>Yes</p></td>
   <td>
    <p>Full User</p></td>
  </tr>
    </tbody>
</table>

<!--| Report | Available | Scope |
|--- |--- |
| Content Audit Trail | Yes | Full Catalog |
| User Audit Trail | Yes | Full User |
|Login Access | Yes | Full User |-->

## Enhanced Connect Integration

Instructors can personalize their session experience by selecting instructor-specific rooms. In this release, we've made the following enhancements:

### Import transcripts

You'll be able to import session transcripts from Connect and analyze the transcripts. Learners will receive the transcript after the recording, which they can download later.

### Edit videos

Instructors can edit the video and enhance the learners' viewing experience. Instructors will see a link on the Session overview page to take them to Adobe Connect login page. After logging in, the instructor will see the recording link. Clicking the link will redirect them to the video, which they can trim.

## Restricting dashboard reports to users with manager role

Admins can search only managers in Dashboard reports.

## Limit legacy dashboard report processing

When an Administrator attempts to plot a dashboard report, and the report takes too long to plot (more than 2.5 min), Adobe Learning Manager displays the following message:

![legacy report image](assets/error-message.png)
*Error message when report takes too long*

Reports of such magnitude cannot be displayed on the User Interface, but the Administrator can download them.

## Migration Support for Catalog Labels

The migration workflow now supports catalog labels. Migration CSVs can be used to import catalog label keys and catalog label values and attach them to courses, learning paths, certifications, and job-aids. The workflow can also be used to delete incorrect values and keys if required.

## API Enhancements for Complex Course Filtering

Advanced filtering of courses by Tags and Catalog-labels (using a combination of "AND" and "OR" conditions) will now be possible via Learning Manager APIs.

## API changes in this release

### Validation in job API

In this release, if the Job aid report exceeds 10 million generated using the Job API, the response will have the message, "Requested report has too much data to generate, consider applying job aid filters!".

### Notification for a deleted post

In previous releases of Adobe Learning Manager, if any Course, Certification, or Learning Plan is deleted and its notification is present, then you could still access the Course, Certification, or Learning Plan by visiting its notification.

In this release, we'll ensure that a deleted post is no longer accessible. If you specify the id in the /posts/{id} API, and the id for the post is no longer available, the API displays the message, "Post not found for the specified resource".

### Learner API completion deadline

In previous releases, Adobe Learning Manager fetched the deadline from the enrollment table. In this release, Adobe Learning Manager will calculate the deadline from the course instance table. If the deadline is unavailable, it will fall back to the enrollment table.

### Override flag

In the November 2023 release of Adobe Learning Manager, we are discontinuing the override flag from the APIs. The override flag is not a part of the public API specification and is intended for backend testing. The flag is now discontinued for Learner APIs. However, the flag is still valid for Admin APIs.

The reason we're deprecating the flag for the Learner APIs is because the override flag was fetching a large amount of data via the Learner APIs.

Going forward, the following Learner API will stop working because it has the override flag.

`https://captivateprime.adobe.com/primeapi/v2/users?page[offset]=0&page[limit]=10&sort=id&override=TRUE`

### Highlight results

In the upcoming release of Adobe Learning Manager, for example, in /search API, we're changing the default for highlightResults to false.

Additionally, we'll change the default of snippetTypes to courseName. Doing so will only highlight the course names in the search if highlightResults is True.

### New resource type for quiz

The `instances.loResources.resources` endpoint will return `ResourceContentType` with Quiz.

## Deprecation notice

On November 30, 2023, LinkedIn Learning will deprecate the usage of the HTTP GET method for obtaining an OAuth token. After the deprecation, you'll only be able to generate an OAuth token using the HTTP POST method.
Adobe Learning Manager will discontinue BlueJeans in February 2024. All new accounts after February 2024 will not include the BlueJeans connector.

## Release Notes

For information regarding current and previous releases of Learning Manager web app and device app, see the [Release notes](release-note/release-notes.md).

## Bugs fixed in this release

* A thumbnail for a course, which is a pre-requisite for a Learning Path or another course does not display when a learner opens the preview page of the Learning Path or the course.
* If Calendar, Gamification, and Social Learning options are not selected, the learner dashboard setting does not retain the next setting. The options like Recommended in your areas of interest and Browse by Catalog do not appear as selected but show in the preview.
* Even after a learner completes a VC course, they receive a reminder mail to complete the course.
* For peer accounts, you are unable to download dashboard reports.
* Deleting and adding a checklist module in a course produces an internal error.
* In the case of Session Invite templates, the sender's email ID has the text captivatePrime instead of AdobeLearningManager.
* When you use Course effectiveness as secondary Y-axis, the report download fails with a Null Pointer Exception.
* If a learner is assigned a Custom Admin role, they navigate to the Custom Admin profile by default. However, when a Learner redirect URL is set on the account, the custom admin is taken to a different destination, not the Custom Admin Role profile.
* The gamification scope does not work as expected if disabled_sub_groups are set to a large number.
* In some cases, deleted users trigger a migration.
* A learner cannot play LinkedIn courses on the MS Teams app.
* The Enrollment API doesn't return the enrollments in a Flex Learning Plan or Embedded Learning Plan as expected.
* In the mobile app, the names of a Course, Certification, or Learning Plan appear in lowercase.
* In previous releases of Adobe Learning Manager, if any Course, Certification, or Learning Plan is deleted and its notification is present, then you could still access the Course, Certification, or Learning Plan by visiting its notification. In this release, we'll ensure that a deleted post is no longer accessible. If you specify the id in the /posts/{id} API, and the id for the post is no longer available, the API displays the message, "Post not found for the specified resource".
* In the Learner API, the completion deadline field isn't displayed in the response of the Enrollment API.
* In the Get Enrollment API for learners, the enrollment details appear even after you specify an incorrect Instance ID.

## Known issues in this release

* A new enrollment or updating an enrollment fails when a Flex Learning Plan is inside another Flex Learning Plan.
* The transcript URL does not display the session recordings in Adobe Connect sessions.
* A learner can take an offline quiz in the mobile app even if they fail it.

## System Requirements

[Learning Manager system requirements](system-requirements.md)

## Previous releases of Adobe Learning Manager

* [July 2023 release](whats-new-2023-july.md)
* [April 2023 release](whats-new-2023-april.md)
