---
description: Learn about the new features and enhancements in the May 2025 release of Adobe Learning Manager
jcr-language: en_us
title: New features summary
---

# New features summary

The upcoming release of Adobe Learning Manager introduces a variety of new features and enhancements aimed at streamlining the platform and enhancing its capabilities.

## Group Success Dashboard

The Group Success Dashboard (GSD) allows administrators and managers to track learner progress in real time. The dashboard provides a clear view of enrollment status, pending actions, and course. Group Success Dashboard simplifies progress tracking by replacing Excel-based transcripts with an easy-to-use interface, making it easier to review learner activity for scenarios like performance appraisals or compliance checks. It's especially helpful for managers overseeing small teams (under 50 people), such as store managers or internal teams, allowing them to quickly monitor course completion and keep learning on track.

View this [article](/help/migrated/administrators/feature-summary/group-success-dashboard.md) for more information about the Group Success Dashboard.

## Enhancements to custom roles

Adobe Learning Manager now allows assigning multiple custom roles to a single user. This update, along with CSV role assignments and automatic scope refresh prompts, gives admins more flexibility in defining responsibilities. These improvements enhance scalability, streamline access management, and ensure users only see relevant content, boosting efficiency and compliance. 

The multiple assignment of custom roles is useful when custom admins transfer to other teams, change responsibilities, or leave the organization. It allows existing users to be reassigned without disruption. Custom roles are now labeled in the user interface for easier identification. Assigned custom admins can view all their available roles in the profile section (top right corner) and switch between roles as needed. 

View this [article](/help/migrated/administrators/feature-summary/custom-role.md#assign-multiple-custom-roles-to-a-user) for more information about the custom roles. 

## Learner bulk enrollment, attendance, and completion {#bulk-enrollment}

Administrators and instructors manually mark completions and attendance when they get attendance rosters after session completions. This requires a lot of redundant work to update names and mark completions for them. Now, this enhancement allows administrators and instructors to update a CSV with email IDS of learners and directly upload it to the Adobe Learning Manager to mark enrollment, completions, and even mark attendance.

View this [article](/help/migrated/administrators/feature-summary/courses.md#learner-bulk-enrollment-attendance-and-completion) for more information about the bulk enrollment, attendance, and completion. 

## Manage content lifecycle with IDs and expiry dates

The Content ID is a unique, trackable identifier for external referencing, reporting, or integration with third-party systems like compliance tools or HRIS platforms. The Expiry Date flags or retires outdated or time-sensitive content, reducing compliance risk and improving content hygiene. Once the expiry date is reached, content can be excluded from new enrollments or archived based on organizational rules.

The content remains accessible after the expiry date; however, the date prompts authors and admins to review or update the material. Both the expiry date and unique content ID apply across all language versions of the content group, ensuring a consistent learner experience regardless of language. Authors can use the unique ID to quickly locate and manage specific content, streamlining updates and version control.

Additionally, the unique ID supports integration with content migration processes, allowing easy content transfer and management across different systems.

* The expiry date helps authors keep track of outdated content that may need review or updates.
* The unique code makes it easier to link content between external systems and Adobe Learning Manager.

>[!NOTE]
>
>Content expiry and unique content IDs are now supported during migration. Two additional columns: expiryDate and uniqueContentId have been added to the module_version.csv file to enable this functionality.

View this [article](/help/migrated/authors/feature-summary/content-library.md#add-content-unique-id-and-expiry-date) for more information about content unique ID and expiry date.

## ALM AI Assistant (Beta)

The new AI Assistant (Beta) in Adobe Learning Manager simplifies complex administrative tasks. It offers an intelligent conversational interface that enhances content discovery and reporting. Administrators can find relevant content quickly and access specific information easily.

This tool streamlines key administrative workflows, improving speed and accuracy while reducing the need to navigate multiple screens.

View this [article](/help/migrated/administrators/feature-summary/alm-ai-assistant.md) for more information about the AI Assistant (Beta).

## New content languages

Adobe Learning Manager is known for supporting many languages, which makes it stand out from other learning platforms. With every milestone, Adobe Learning Manager expands its language offerings to better support a global and diverse user base. In this release, we're introducing new content languages, further enhancing our commitment to delivering inclusive and accessible learning experiences for all.

* Chinese-traditional Hong Kong (cn-HK)
* Norwegian Bokmal (nb-NO)
* Tamil (ta-IN)
* Telugu (te-IN)
* Kannada (kn-IN)
* Malayalam (ml-IN)

View this [article](/help/migrated/languages-supported.md) for a list of supported languages in Adobe Learning Manager.

## Go1 content enhancements

Adobe Learning Manager introduces new purchasing models for Go1 content, providing more flexibility and options for acquiring content: Premium Essentials and Premium Essential Plus. Essentials offers cost-effective solutions for boosting employee engagement and includes content providers like Skillshub, Thomson Reuters, and Emtrain. Premium Essential Plus offers additional content from premium providers such as Blinkist, Pluralsight, Skillsoft, Traliant, and Coursera.

View this [article](/help/migrated/administrators/feature-summary/content-marketplace.md) for more information about the new purchase plans. 

## Login access report in FTP, custom FTP, and Box {#log-in-access-report}

The login access reports are now available for Box, FTP, and Custom FTP connectors, providing visibility into connector login activities. This report, along with other reports, helps administrators build their reporting suite outside the platform by providing detailed information about user login and access times. This report can be used to create more informative dashboards and track user activity effectively.

The report is now available in the custom FTP, FTP and Box along with existing reports, such as learner progress and course completion. This integration allows administrators to access all necessary reports from a single source, facilitating better data management and analysis.

The report helps in automation by enabling the export of login and access data to the FTP, where it can be joined with other reports to create comprehensive dashboards. This feature is particularly useful for organizations that rely on automated processes for data analysis and reporting.

View this [article](/help/migrated/integration-admin/feature-summary/connectors.md) for more information about the FTP, Custom FTP, and Box connectors.

## User language preference update on login through SAML

Adobe Learning Manager is a multi-lingual platform where learners' language preferences are taken care of through various ways, like interface language, content language, and courses, along with its modules and instances, are also multi-lingual.

For users of the Adobe Learning Manager native platform, this enhancement addresses the need for just-in-time user provisioning. When users are creating accounts and logging in for the first time, this feature ensures that their language preferences are accurately captured and applied.

This feature ensures that users' language preferences are updated automatically when they log in through SAML. This helps in providing a personalized experience by displaying the interface in the user's preferred language.
When users log in through SAML, their language preference (Interface and Content language) is checked and updated based on the information provided during the login process. 

The feature integrates with the SAML login process to capture and update the user's language preference seamlessly.

View this [article](/help/migrated/administrators/feature-summary/set-up-interface-language-through-saml.md) for more information.

## Filter deleted users before purging

Purging users means permanently deleting their data from the system. This includes removing all records and information linked to the user, so nothing is left behind. Purging helps keep the system clean, saves storage space, and follows data retention rules.

The feature is designed to help administrators manage and purge users who have been deleted for a certain period. This is particularly useful for maintaining data hygiene and ensuring that old, unused user data is removed from the system. 
Administrator can filter users by the month they were deleted, making it easier to identify and purge users who were deleted in a specific timeframe.

Refer to this [article](/help/migrated/administrators/feature-summary/purge-users.md#filter-deleted-users-before-purging) for more information.

## Adobe Connect connector enhancements

### Support for seminars with large audiences

Adobe Learning Manager now also supports selecting Seminar rooms from Adobe Connect while setting up a VC session in Connect. Previously, administrator could only select the Meeting room type. This enhancement enables administrator with a valid seminar license to schedule and manage one-time or large-scale events (up to 1,500 attendees) within Adobe Learning Manager.

View this [article](https://helpx.adobe.com/adobe-connect/using/creating-seminars.html) for more information about the Seminar room.

### Support for access to session analytics

Instructors can now access Session Analytics for their completed Adobe Connect sessions via a new link provided in their session dashboard.

![](assets/adobe-connect-session-url.png)
_Select session URL_

This link opens the session analytics dashboard in Connect, which provides detailed insights into session engagement.
This feature is available only for sessions conducted through Adobe Connect. The session analytics include: 

* Engagement: Overview of the live session's overall performance
* Interactions: Detailed breakdown of participant activity across different pods 
* Attendee Activity: Summary of participant engagement 
* Download Reports: Option to download reports for pod-specific engagement data

![](assets/session-dashboard.png)
_Session dashboard_

View this [article](https://helpx.adobe.com/in/adobe-connect/using/session-dashboard.html) for more information about the Connect session analytics. 

## Migration changes

Migration process in Adobe Learning Manager for importing modules now supports the ability to add parameters for defining success criteria. 
This is supported now by adding three new optional columns in the module_version.csv. Three new optional columns are: `successCriteria`, `successQuizData`, and `successViewPercent`.

These fields accept only specific values, and the connector will fail to process the file if invalid values are entered.
A quiz module can use three types of success criteria. Either it can mark pass if the learner launches the content, depending on a percentage value scored (defined by `successViewPercent`: below), or it can be based on the quiz module's outcome (defined by `successQuizData`: below). This value is to be filled in as per the instructions below. The successCriteria parameter is used to determine this. 

`successCriteria`: Accepts `LAUNCH_CONTENT`, `VIEW_PERCENT`, `QUIZ`, or `VIEWPERCENT_OR_QUIZ`.

* If `LAUNCH_CONTENT`: Leave `successQuizData` and `successViewPercent` blank. This will mark the learner as passed if the learner launches the content.
* If `VIEW_PERCENT`: Enter a value for `successViewPercent`, leave `successQuizData` blank. This will mark the learner pass depending on the percentage value scored in the quiz.
* If `QUIZ`: Enter a value for `successQuizData`, leave `successViewPercent` blank. This will mark the learner as passed depending on the outcome of the quiz module.
* If `VIEWPERCENT_OR_QUIZ`: Enter values for both `successQuizData` and `successViewPercent`. This will mark the learner as passed depending on either the outcome of the quiz module or the percentage scored.

This field is only valid if `hasQuiz` is true. Also, if only `completionCriteria` is passed, then `successCriteria` will be considered the same as `completionCriteria` for interactive content.

`successQuizData`: Accepts `QUIZ_ATTEMPTED`, `QUIZ_PASSED`, or `QUIZPASSED_OR_LIMITREACHED`.

* `QUIZ_ATTEMPTED` will mean that the learner will be marked as passing for the quiz if the learner has attempted the quiz.
* `QUIZ_PASSED` will mean that the learner will be marked as passed for the quiz, if the learner passes the quiz as per the criteria defined inside the quiz content. For e.g. Scorm module defines the criteria and reports it to Adobe Learning Manager.
* `QUIZPASSED_OR_LIMITREACHED` will mean that the learner will be marked as passed for the quiz if the learner has either passed the quiz or has exhausted the number of limits.

`successViewPercent`: Accepts integer values from 0 to 100.

* This criterion accepts a percentage value that the learner is required to score to successfully pass the quiz
Webhook changes.

View this [article](/help/migrated/integration-admin/feature-summary/migration-manual.md) for more information about the migration process. 

## Webhooks changes

* Using a webhook, you can now send payloads for both parent and child learning objects during key learner actions such as enrollment, completion, and unenrollment. For example, when a learner enrolls in a Learning Path that includes three courses, the system will generate one payload for the Learning Path and separate payloads for each course.
<!--* Adobe Learning Manager now captures learner activity from LinkedIn Learning (LIL) in Adobe Learning Manager Learning Record Store (LRS). For example, if a learner enrolls in and completes a course on LIL, that progress will automatically sync to Adobe Learning Manager using xAPI statements.-->

View this [article](/help/migrated/integration-admin/feature-summary/webhooks-usage-guide.md) for more information about Webhooks. 

## API changes

All the public APIs now support improved error handling by returning clear and specific error messages when invalid or incomplete data is passed in `POST` and `PATCH` requests. This enhancement applies particularly to relationship fields within the request payloads.

When a request includes incorrect data types or is missing required information in the relationship section, the API responds with descriptive messages that indicates the exact issue. This enables faster identification and resolution of errors during integration or testing.

The following sample responses illustrate various error scenarios:

```
{
  "status": "BAD_REQUEST",
  "title": "Field Type incorrect",
  "source": {
    "info": "incorrect relation type - Andrew"
  }
}
```

```
{
  "status": "BAD_REQUEST",
  "title": "Missing Param",
  "source": {
    "info": "skills"
  }
}
```

## Bugs fixed in this update

* Corrected inaccurate timestamps in the Get Learning Object API response for Job Aids where dateCompleted, dateEnrolled, and dateStarted were incorrectly matching dateModified.
* The User API endpoint now displays specific field-level error messages instead of generic ones.
* The /learningObjects endpoint returned a blank response when invoked for the default catalog.
* Updated public API responses to display Job Aids that were previously excluded due to outdated versioning.
* Improved recommendation accuracy by removing unrelated skills from appearing in the learner's course recommendation section.
* Synced folder names with search results so that renamed content folders reflect the updated name across all searches in the platform.
* The text on the Course Overview page does not overflow. The experience is much cleaner now.
* Restored self-registration links for accounts using custom domains to support smoother user sign-up.
* The subscription report prevents unintended course enrollments in flexible Learning Paths.
* In multi-SSO configurations, all configured profiles are now visible, beyond the previous 20-profile limit.
* Excluded Content Marketplace courses from recurring certification enrollments when not explicitly required.
* Enabled course duplication for users with edit permissions across both the My Courses and Courses tabs.
* Auto-enrollment triggers as expected for subsequent courses in enhanced Learning Paths shared via catalogs.
* Unexpected player launches are prevented by correctly handling system date changes with appropriate error prompts.
* Stabilized an author's session after modules are removed from a course, avoiding abrupt session terminations.
* The organization logo displays at full size on the logout screen.
* Restored Delete button functionality during Learning Path creation even after multiple drag actions.
* Store managers receive email notifications when learners lack an assigned manager.
* Standardized terminology by updating UI references from "virtual session" to "Virtual Classroom".
* Deleted badges are no longer visible, so learners no longer see or unlock obsolete achievements.
* Course descriptions are populated correctly in email communications by resolving issues with the CourseDescription field.
* Account-level discussion board configurations are not overridden by course-level settings.
* URL length limitations that blocked instructor assignments in the checklist modules have been resolved.
* Clearer error messages when duplicate columns are detected in the user upload file.
* Rendered complete data in enhanced Learning Path APIs, ensuring child Learning Paths are correctly displayed.
* Added rich text formatting for course descriptions in the mobile app for better user experience.

## System Requirements

[Learning Manager system requirements](/help/migrated/system-requirements.md)

## Previous releases of Adobe Learning Manager

* [November 2024 release](/help/migrated/whats-new-nov-24.md)
* [July 2024 release](/help/migrated/whats-new-july-2024.md)
