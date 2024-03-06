---
description: Learn about the new features and enhancements in tne March 2024 release of Adobe Learning Manager
jcr-language: en_us
title: New features summary
contentowner: jayakarr
---


# New features summary {#new-features-summary}

Learn about the new features and enhancements in Adobe Learning Manager

## What's new in this release {#whatsnewandchanged}

### Import skills from external sources

Import Skills from content providers, such as LinkedIn and Go1, by using the respective connectors. This enhancement is a part of the goal towards Learning Manager's ability to integrate with external Skills Clouds and Talent Management Systems. The imported skills will be added to the admin defined skills in Learning Manager and will be available to Authors during the course creation workflow. Enhancements have also been made to the skill search functionality across the platform to provide a better search experience when the account has an extensive number of skills.

View [Import skills](administrators/feature-summary/import-skills-external-sources.md) to know more.

### Custom branding

You will now be able to customize certain UI elements—the organization name, logo, and UI theme based on the user-groups available in the account. For example, an organization with multiple divisions can set up a custom logo and UI theme to be displayed for each division.

>[!NOTE]
>
>This multiple branding feature does not apply to Admin's view. They will always see org-level branding in their account. This is because this is a learner facing feature, and admin's may not want it in their account.

View [Multiple custom branding](administrators/feature-summary/themes.md#multiple-branding) for more information.


## Changes for accounts with large user base

### Admin- Course or Learning Path pages

If a large number of learners are enrolled to the course, for example, more than 50,000, the list of learners wil not be displayed. You can either search for a learner in the *Search Learners* search bar or select the **Download** link at the top of the search bar to download the list of learners.

### Admin- Learners page

When searching for any user, the **Download learner** and **Export** options download the same report. Meanwhile, while searching for a User Group, you can now download filtered users from that user group. When searching a User Group,
the **Download learner list** changes to **Download leaner list for user group** The **Export** option again downloads the entire list.

### Admin- Users page

#### Internal users

If the number of users exceed, for example, 50,000, there'll be a message to download the data for a more detailed analysis later. The search bar is now prominent and displays a user in the format *Name, email | UUID*.

>[!NOTE]
>
>The UUID displays only if UUID is enabled for the account.

#### External users

For external users, the same behavior applies. If the number of users is large, you can download the users, and also retrieve the details of a user after a search in the format *Name, email | UUID*.

#### User Cleanup page

On the User Cleanup page, for deleted users, we've removed the sort capability on **Date deleted**. You can only sort on the UUIDs.

### Admin- Instance pages

#### Course or Learning Path

If the number of enrollments is large, Adobe Learning Manager will not display the number of learners. Instead, there will be an icon, which you can select, and view the number of learners and navigate to the Learners page.

The number of learners will be displayed as an approximate value. For example, if the number of learners is more than 50,000, the value will be displayed as 50K+.

### Admin- L1/L3 pages

On the L1 Feedback page, if the number of course enrollments is large, the list of learners is not displayed. Instead, you can export the list of users for a more detailed analysis later. 

The search supports type-ahead and the results are restricted to the selected instance.

#### Attendance and Scoring page

On the page, when you search a user, the search executes across all available instances. However, the result is for the selected instance.

On the Attendance page, if you search for a User Group and the number of users exceeds 10,000 in the User Group irrespective of enrollment, you can only perform bulk-level actions. You'll be unable to view the list of users.

If the number of users in the User Group is fewer than 10,000, then you can perform individual user-level actions along with bulk-level actions. In this case, the listing of users is not disabled.

### Admin- Certifications page

In current versions of Adobe Learning Manager, if there is a large number of users enrolled to a certification, you're unable to view the unenrolled learners since the **Status** dropdown is disabled.

In this release of Adobe Learning Manager, if the number of enrolled users is large, the **Status** dropdown only displays two options- **Enrolled** and **Unenrolled**. The option **Enrolled** is selected by default. If you select **Unenrolled**, the list of unenrolled learners displays.

#### User Group changes

In case of a User Group, if the number of users in the User Group is fewer than, for example, 50,000, the **Status** dropdown displays all options- Certified, Assigned, and Expiring.

If the number of users in a User Group is large, the **Status** dropdown only displays two options- **Enrolled** and **Unenrolled**, according to the new design.

### Comparison table

<table>
    <tbody>
        <tr>
            <td><b>Page</b></td>
            <td><b>Before threshold change</b></td>
            <td><b>After threshold change</b></td>
        </tr>
        <tr>
            <td>Admin- Course Instance</td>
            <td>Instances display as designed with the following:
            <ul>
                <li>Modules</li>
                <li>Learners Enrolled</li>
                <li>Sessions</li>
                <li>Badge</li>
                <li>L1 feedback enabled</li>
                <li>Notification alerts</li>
                <li>Gamification points</li>
                <li>QR Code</li>
                <li>Learning Path extension</li>
            </ul>
            <td>
                <ul>
                    <li>If the number of enrolments exceed the pre-defined threshold, ALM will not display the count; it will replace the count with an icon, which when clicked, displays the actual number of learners and a link to take you to the Learners page.</li>
                    <li>The number of enrolments will be displayed in an approximate format. For example, if the number is more than 50,000, the count will be displayed as 50K+ at the course level.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Admin- Learners page</td>
            <td>
                    <ul>
                        <li>The list of learners displays for each instance.</li>
                        <li>You can search a user or User Group enrolled in a course.</li>
                        <li>The exported report does not consist of any filter for User Group.</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>Selection of instance is disabled.</li>
                    <li>Download learner list also downloads the same data except for one case. If you search for a user-group and then select the Download Learner List, it will download that user-group data.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Admin- L1/L3 feedback page</td>
            <td>
                <p>No change in existing behavior</p>
            </td>
            <td>
                <ul>
                    <li>Selection of instance is disabled.</li>
                    <li>If enrolment to a course is above 50K, ALM does not list learners and displays only the Search bar. If enrolment is fewer than 50K, ALM displays both learner list and search bar.</li>
                    <li>Listing is disabled by default.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Admin- Attendance and Scoring page</td>
            <td>
                <p>No change in existing behavior</p>
            </td>
            <td>
                <ul>
                    <li>Selection of instance is disabled when searching a user.</li>
                    <li>If the number of users exceed, for example, 50,000, there'll be an additional message to download the data for a more detailed analysis later. The search bar is now prominent and displays a user in the format Name, email | UUID.</li>
                    <li>If the number of users in the User Group is fewer than 10,000 irrespective of enrollment, then you can perform individual user-level actions along with bulk-level actions. In this case, the listing of users is not disabled.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Admin- L2 Quiz Score page</td>
            <td>
                    <ul>
                        <li>User search is implemented as well.</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>User search is implemented as well. While typeahead searches at LO level, listing is filtered to the currently selected instance.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Admin- Users page (Internal, External)</td>
            <td>
                    <ul>
                        <li>The email id is displayed upon searching a user.</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>If the number of users exceed, for example, 50,000, there'll be a additional message to download the data for a more detailed analysis later. The search bar is now prominent and displays a user in the format Name, email | UUID.</li>
                    <li>On the User Cleanup page, for deleted users, we've removed the sort capability on **Date deleted**. You can only sort on the UUIDs.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Instructors- Submission</td>
            <td>
                    <ul>
                        <li>Pagination of modules to be submitted.</li>
                        <li>As an instructor, you can now filter file submissions from learners based on status, ending Review, Pending Submission, Passed, and Failed. </li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>You can only search users, not User Groups in that instance.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Count on preview as learner page</td>
            <td>
                    <ul>
                        <li>Count includes the data from higher order enrollment.</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>Count excludes data from higher order enrollments.</li>
                </ul>
            </td>
        </tr>
    </tbody>
</table>

## Advanced searching capabilities

In this release, we've enhanced the search experience. The search results are fetched based not only on the metadata, but also semantic, and in-content search to derive results based on precision, recency and relevant content. 

This change reflects on the following:
* Catalog and My Learning page: The hover action on course, learning path, and certification has been removed.
* The appearance of the search bar.
* Added filter tags in the learning app.

To enable the search capabilities, contact the CSAM team of Adobe Learning Manager.

## Changes to reports

* Tag(s) and Skill(s) columns in Trainings Report are changed to Tag and Skills.
* Added the report [Gamification Audit Trail](administrators/feature-summary/reports.md#gamification-audit-trail).
* If an account contains more than 280000 learners assigned to a skill, then the skill-learner report gets downloaded as a zipped csv.
If the account has fewer than 250000 learners, the same report gets downloaded as a CSV.
On the Admin page, select **Admin** > **Skills** > **Skill** > **Learners**. The report gets downloaded as CSV.
* The [Session Summary report](administrators/feature-summary/reports.md#session-summary-report) has two new columns- Location Information and Location region.

## Changes to classroom creation

Based on [Administrator settings](administrators/feature-summary/classroom.md#classroom-settings), you, as an Author, can [create,modify, and delete locations](administrators/feature-summary/classroom.md#add-classroom-location).
>[!NOTE]
>
>While adding location and Catalog labels, authors (in course creation page) and admins (at instance page) will see an auto populated list of locations and catalog labels respectively.

As as Administrator, you can enforce restrictions on a Author to modify or delete a classroom location. View [Classroom settings](administrators/feature-summary/classroom.md#classroom-settings) for more information.

## Changes to Flexible Learning Path

All accounts (old and new) in will start including Enrollment Deadline, Unenrollment Deadline, and Seat limit in the Learner app for a Flexible Learning Path.
Learners now will be able to enroll to Flexible Learning Path without selecting any instance of the course.

## New trigger for Learning Plans 

A new trigger has been added to the Learning Plan setup page. Authors and Admins will now be able to trigger actions when a learner fails a module of a course.

View [Learning Plans](administrators/feature-summary/learning-plans.md) for more information.

## New submission status 

As an instructor, you can now filter file submissions from learners based on status, ending Review, Pending Submission, Passed, and Failed.

View [Submission status](instructors/feature-summary/learners.md#filter-file-submissions) for more information.

## Checklist enhancements

### Mandatory checklist

In current versions of Adobe Learning Manager, for a checklist, the progress of a module was allowed even if a reviewer has marked the modules as Failed. In this release, an Author can configure to prevent the progress of a learner of they fail the checklist.

### Checklist re-evaluation

In the same workflow, you, as an Author, can re-evaluate  a Learner who has failed a checklist. Select the **Enable** checkbox in the Re-evaluation section, while creating a checklist.

View [Create a checklist](authors/feature-summary/courses.md#checklist-fail) for more information.

## Other enhancements

### Session-related email notifications

In earlier releases of Adobe Learning Manager, a Learner did not session-related emails, Session Details Updated, Session Invite, and Session Reminder, when:

* Learners have completed a course,
* New sessions are added to a course, or
* There are changes to existing sessions.

In the March 2024 release of Adobe Learning Manager, the following are the new changes:

* Session Details Updated and Session Invite (For Learner and Instructor)
    * For future sessions, emails for **Session Details updated**, **Session Invite** for enrolled Learners  and current Instructors will be deprecated. For past sessions, emails for **Session Details updated** and **Session Invite** for enrolled Learners and current Instructors will stay as is.
* Reminder Emails (For Admin and Learner)
    * For future sessions, only **Session Reminder** emails will be sent.

>[!NOTE]
>
>The mails do not depend on session and course completion.


### AEM Reference site changes

In an AEM Reference site, we've added support for adding Admin Refresh Token to Learner Access Token.

### Hide submissions from instructors

After learners upload their files using the file submission workflow, if an instructor does not take any action (approve or reject) on the submission, the submission URL is hidden from the view after a pre-defined number of days. Contact the CSAM teams of Adobe Learning Manager to set or change the number of days.

### Product terminology changes

We've added the columns *Instance* and *Learner* to the product terminology vocabulary.

### Mobile app changes

In this mobile app release, learners can schedule and manage overdue course reminders. Clicking on an overdue reminder notification allows you to access the following options:

* Cancel
* Go to course
* Remind me again in 3 days
* Remind me again in a week

On Android: Clicking the push notification will direct you to the **Course Overview** page.
On iOS: Clicking the push notification will direct you to the Home page of the app. This is a known limitation in iOS.

### Checklist changes in Learner app on Salesforce

If a learner fails a checklist, they cannot proceed to the next module or course. When the Mandatory Checklist checkbox is selected, the learner is unable to move ahead in a course if they fail the checklist.

As with the web app, if a learner fails a checklist on the Salesforce app, they will see a message, and will not move ahead.

### Changes in Connect VC

In current releases of Adobe Learning Manager, a learner is marked **Not Attended** when they are enrolled for a Connect VC session, but didn't meet the completion criteria.

In this release, the status changes to **Yet to mark**.

### White labeling in Adobe Learning Manager

Adobe Learning Manager mobile app now supports white labeling – which means that you can now release the app under your own branding.

View White labeling in [Adobe Learning Manager mobile app](white-label.md) for more information.

### App rating

A learner can provide their feedback on the Adobe Learning Manager app to further enhance the app experience. If the learner rates four star or more, a pop-up displays that requests the learner to rate the app on Play Store or App Store.

### Bluejeans has reached its end of life (EOL) in February 2024

We wanted to inform you that Bluejeans has reached its end of life (EOL) on February 2024. After February 2024, Bluejeans will no longer receive updates or support. Our CSAM and support teams will assist you with any questions or concerns you may have during this transition period.

View [Connectors in Adobe Learning Manager](integration-admin/feature-summary/connectors.md) for more information on configuring connectors.

## API changes in this release

### Learner APIs

In this release, we've added API support for learners to view the branding logo and personalized themes in the User Group level.

The APIs /account and /user?include=account returns four fields, which are overridden specific to the active field of the user belongs to logoUrl, logoStyling, and themeData.

### New attributes

A new attribute, isExpiredSubmission, in learningObjectResource, which shows whether the submission in the resource is expired or not.

* GET /account API: Returns new attribute **expireSubmissionDuration** X, where X is the number of days set. If not set, 0 will be returned
* GET /LO API with resource includes new attribute **isExpiredSubmission**" True or False.
    * True, if the submission is expired and  "submissionUrl" is not displayed. 
    * If False, the submission is not expired and "submissionUrl" is fetched.

### API changes in Checklist

A course can consist of several modules of which Checklist is a type of module. This checklist module is evaluated by the instructor and can be marked as Failed  or Success based on evaluation.

But in both cases the checklist status is marked as Completed and this way, the course is marked as Completed.

In this release, the LO API includes the parameter *isChecklistMandatory*. If the value is True, the checklist is mandatory.

### Support for multiple locales

An Administrator can now download L1 feedback report in the language of their choice. However, you cannot download L1 feedback reports for Power BI yet. In the API request, use the parameter preferredLocale to specify the locale of your choice.

### Changes in the count of Instance summary

This is applicable to accounts where the enrollments for a Classroom/VC course is more than 1000.

If the number is fewer than 1000, the enrollments invalidate the cache and returns the updated values in a GET Summary API call, such as, number of enrollment, completion, and seatLimit.

If the account is enabled for this feature and the number of enrollments is more than 1000, the values are retrieved from the cache.

### Deprecated paths

At present, Learning Manager APIs follow a graph data structure, which allows you to fetch data by traversing the API model through includes. Even though you could traverse an API up to seven levels, fetching the data using a single API call is computationally expensive. 

We recommend that all existing and new customers make small calls multiple times instead of one large call. This approach will prevent unwanted data from being loaded in the call.

#### What paths are deprecated 

The following paths are deprecated: 

* /learningObjects 
    * Deprecated paths:  
        * enrollment.loInstance.loResources.resources 
        * instances.loResources.resources 
    * Existing paths: 
        * enrollment.loInstance 
        * instances.loResources 
* /learningObjects/{id} 
    * Deprecated path: 
        * enrollment.instances.subLoInstances.learningObject 
    * Existing path: 
        * enrollment.instances.subLoInstances 
* /enrollments 
    * Deprecated path:  
        * loInstance.learningObject.enrollment 
    * New path: 
        * loInstance.learningObject 
* /learningObjects/{id} 
    * Deprecated path: 
        * instance.subLoInstances.learningObject.enrollment.loResourceGrades 
    * New path: 
        * instance.subLoInstances

### Login access and User audit report archival changes for Job API

With this release, the Job API will retain Login Access Report up to five quarters and User Audit Report for six months. If you want to download the data older than this time period, you must pass the archive parameter, specifying quarter and year. Refer the sample payload.

```
{
    "data": {
        "type": "job",
        "attributes": {
            "description": "description of your choice",
            "jobType": "generateLoginAccessReport",
            "payload": {
                "fromDate": "2023-04-01T18:30:00.000Z",
                "toDate": "2023-04-30T18:30:00.000Z",
                "archive": {
                    "quarter": "4",
                    "year": "2021"
                }
            }
        }
    }
}
```

If you try to download the **Login Access** report that goes beyond five quarters, an error message displays. A similar error message displays if you try to download the **User Audit** report that goes beyond six months.

### Deprecated APIs

View [API deprecations in Adobe Learning Manager](api-deprecations-list.md) for a cumulative list of all deprecated APIs in the product.

## Bugs fixed in this update {#bug-fixes}

* When a learner is enrolled in a course and then tries to enroll to another course, a warning message displays.
* A User Group, even after being deleted, is visible in Search.
* When users trigger a lot of Learner Transcripts with a large amount of data, the Learner Transcripts queue gets blocked, and prevents a new request.
* If a child account requests its parent account to share a report, the parent account is unable to do so.
* The URLs from a Course and a Learning Path redirect to incorrect locations.
* A learner intermittently views the course instance of a different course on clicking the course link on the catalog page.
* The **Unenroll** button does not display as expected after the first enrollment, but the button displays after a refresh.
* You're unable to save Content or a Quiz that has a blank space in its name.
* In manager-approved courses, you're able to re-enroll learners in a User Group.
* In some cases, if you try to add an additional active field, the error message, "Active fields could not be saved.", displays.
* The text overflows in the name of a course inside a course card in the Related Courses section.
* After switching an instance and enrolling a learner to the instance, the old instances still exist in the Outlook calendar.
* When a learner from a peer account tries to select the thumbnail of a course, an error message displays.
* When learners enroll to a course, they receive multiple notifications for the enrollment.
* If a user manually changes the name of the catalogs created in a connector, then new catalogs get created, and the courses are published to the incorrect catalogs.
* Users belonging to inactive accounts still receive subscription emails.

### API-related bug fixes

* The API GET/users does not retrieve the details of a Manager.
* In an account, users got created through a scheduled FTP user import during a scheduled downtime.
* In the mobile app or immersive mode, after deleting or retiring a course instance, and selecting the next active instance, the **Register Interest** button displays instead of **Enroll**.
* When a learner from a peer account tries to select the thumbnail of a course using the Learning Object API, the error 403 Forbidden displays.

## System requirements

View [Adobe Learning Manager system requirements](system-requirements.md).

## Previous releases of Adobe Learning Manager

* [November 2023 release](whats-new-november-2023.md)
* [July 2023 release](whats-new-2023-july.md)
