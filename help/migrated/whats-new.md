---
description: Learn about the new features and enhancements in the May 2025 release of Adobe Learning Manager
jcr-language: en_us
title: New features summary
exl-id: 812d33c8-b2e4-43eb-adda-67dc356ca1ca
---
# New features summary May 2025

The upcoming release of Adobe Learning Manager introduces a variety of new features and enhancements aimed at streamlining the platform and enhancing its capabilities.

## Group Success Dashboard

The Group Success Dashboard (GSD) in Adobe Learning Manager allows administrators and managers to monitor learner progress in near real time (60-minute delay from enrollment, progress, or completion to reflecting on the dashboard) across departments or user groups. It supports proactive tracking of course completion, enrollment, and pending actions, making it easier to manage learning for teams. Group Success Dashboard simplifies progress tracking by replacing Excel-based transcripts with an easy-to-use interface, making it easier to review learner activity for scenarios like performance appraisals or compliance checks. It's especially helpful for managers overseeing small teams (under 50 people), such as store managers or internal teams, allowing them to quickly monitor course completion and keep learning on track.

View this [article](/help/migrated/administrators/feature-summary/group-success-dashboard.md) for more information about the Group Success Dashboard.

## Enhancements to custom roles

Adobe Learning Manager now allows users to have multiple custom roles, addressing the need for custom administrators to manage various responsibilities. Each role can have up to 500 users, and each user can have up to 50 roles, providing flexibility in delegating tasks. Users can easily switch between their assigned roles through a new option in their profile, ensuring seamless management of different responsibilities. Administrators can assign or modify roles for users via a new link in the user page, allowing them to add or remove roles as needed. These enhancements simplify the management of multiple responsibilities, particularly for small teams with limited resources.

View this [article](/help/migrated/administrators/feature-summary/custom-role.md#assign-multiple-custom-roles-to-a-user) for more information about the custom roles. 

## Learner bulk enrollment, attendance, and completion {#bulk-enrollment}

Using Adobe Learning Manager's bulk enrollment feature, administrators can efficiently enroll large groups of learners into courses, certifications, or learning programs by uploading a CSV file. This process saves time, ensures consistency, and supports organizational scalability. Additionally, administrators and instructors can update learner information, attendance, and completions in bulk through CSV uploads, minimizing manual work and ensuring data accuracy.

View this [article](/help/migrated/administrators/feature-summary/courses.md#learner-bulk-enrollment-attendance-and-completion) for more information about the bulk enrollment, attendance, and completion. 

## Track content using Content unique ID and Expiry Dates

The Content unique ID is a unique code given to each content item in Adobe Learning Manager. It helps administrators and authors find and manage content easily, especially when updating or moving it between systems. This Content unique ID is also useful for connecting content with other tools like HR or compliance systems. The same Content unique ID is used across all language versions, so everything stays consistent for learners.

The Expiry Date marks content that may be outdated or no longer needed. Even after the expiry date, the content stays available, but it reminds authors and administrators to check and update it if needed. Based on settings, expired content can be removed from new enrollments or archived. Like the Content unique ID, the Expiry Date works the same way for all language versions, helping keep content clean and up to date for everyone.

Additionally, the Content unique ID supports integration with content migration processes, allowing easy content transfer and management across different systems.

* The Content unique ID makes it easier to link content between external systems and Adobe Learning Manager.
* The Expiry Date helps authors keep track of outdated content that may need review or updates.

View this [article](/help/migrated/authors/feature-summary/content-library.md#add-content-unique-id-and-expiry-date) for more information about content unique ID and expiry date.

## Admin AI Assistant (Beta)

In complex learning setups, Administrators may struggle to find content or complete tasks because of complicated menus and disconnected workflows. For instance, tasks like running reports or accessing specific information may require navigating multiple screens. The Admin AI Assistant (Beta) helps you find the right information to understand and complete tasks efficiently.

The Admin AI Assistant (Beta) in Adobe Learning Manager helps administrators quickly find answers to common questions, explore system features, and understand how to complete key task, just by asking in plain language. Whether you're new to Adobe Learning Manager or looking for faster ways to troubleshoot, the Admin AI Assistant (Beta) simplifies your workflow by providing context-aware help directly in the platform.

It uses Adobe's AI capabilities to enable natural language queries across learning content and system workflows.  Administrators can ask questions like **How to add users to Adobe Learning Manager** or **How to add Learning Paths**. The Adobe Learning Manager Admin AI Assistant (Beta) is trained exclusively on publicly available, Adobe-owned documentation such as, resources hosted on **[!UICONTROL Experience League]**. It does not learn from or access customer content, internal training material, or user-generated data.

View this [article](/help/migrated/administrators/feature-summary/alm-ai-assistant.md) for more information about the AI Assistant (Beta).

## New content languages

Adobe Learning Manager is known for supporting many languages for both content and interface, which makes it stand out from other learning platforms. With every milestone, Adobe Learning Manager expands its language offerings to better support a global and diverse user base. In this release, we're introducing new content languages, further enhancing our commitment to delivering inclusive and accessible learning experiences for all.

* Chinese-traditional Hong Kong (cn-HK)
* Norwegian Bokmal (nb-NO)
* Tamil (ta-IN)
* Telugu (te-IN)
* Kannada (kn-IN)
* Malayalam (ml-IN)

View this [article](/help/migrated/languages-supported.md) for a list of supported languages in Adobe Learning Manager.

## Enhancements to Content Marketplace

Adobe Learning Manager introduces new purchasing models for acquiring content, providing more flexibility and options for acquiring content: Premium Essentials and Premium Essential Plus. Essentials offers cost-effective solutions for boosting employee engagement and includes content providers like Skillshub, Thomson Reuters, and Emtrain. Premium Essential Plus offers additional content from premium providers such as Blinkist, Pluralsight, Skillsoft, Traliant, and Coursera.

View this [article](/help/migrated/administrators/feature-summary/content-marketplace.md) for more information about the new purchase plans. 

## Login access report in FTP, custom FTP, and Box {#log-in-access-report}

The login access reports are now available for Box, FTP, and Custom FTP connectors, in addition to the existing Job APIs. This report provides detailed information on user login activities, including execution status, compression settings, and scheduling options. The report can be generated on-demand or scheduled, and the data is stored in the specified connector for easy access and analysis. This enhancement improves the ability to monitor and audit user login activities, ensuring better security and compliance tracking.

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

Purging users means permanently deleting their data from the system. Sort users by the date they were deleted, making it easier to locate and manage specific records. Additionally, a new filter allows administrators to select users based on the year and month of deletion, narrowing down the list to a specific timeframe. These changes streamline the user cleanup process, enabling administrators to efficiently purge users by selecting multiple records within a defined period.

Refer to this [article](/help/migrated/administrators/feature-summary/purge-users.md#filter-deleted-users-before-purging) for more information.

## Adobe Connect connector enhancements

### Support for seminars with large audiences

Adobe Learning Manager now also supports selecting Seminar rooms from Adobe Connect while setting up a VC session in Connect. Previously, administrator could only select the Meeting room type. This enhancement enables administrator with a valid seminar license to schedule and manage one-time or large-scale events (up to 1,500 attendees) within Adobe Learning Manager.

View this [article](https://helpx.adobe.com/adobe-connect/using/creating-seminars.html) for more information about the Seminar room.

### Support for access to session analytics

Adobe Learning Manager allows users to access Session Analytics via a URL, which redirects to the Connect session analytics dashboard. This dashboard provides detailed information on session duration, attendee count, and recording details, available approximately 20 minutes after the session ends.

![](assets/adobe-connect-session-url.png)
_Select session URL_

![](assets/session-dashboard.png)
_Session dashboard_

View this [article](https://helpx.adobe.com/in/adobe-connect/using/session-dashboard.html) for more information about the Connect session analytics. 

## Migration changes

### Success criteria for the content using migration 

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

### Add Content unique ID and Expiry Date for content using migration

Content unique ID and Expiry Date are now supported during migration. Two additional columns: expiryDate and uniqueContentId have been added to the module_version.csv file to enable this functionality. Refer this [sample CSV](assets/module_version_content.csv) and [CSV specification file](assets/4-module_version_content.xlsx) for more information. 

View this [article](/help/migrated/integration-admin/feature-summary/migration-manual.md) for more information about the migration process. 

## Enhancements to webhooks

Webhooks now support events for courses within Learning Paths (LPs) and certifications when enrollment, unenrollment, or completion occurs.
This includes supporting events for each course within the LP or certification, in addition to the parent LO event.

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

* Corrected inaccurate timestamps in the GET learningObject API response for Job Aids where dateCompleted, dateEnrolled, and dateStarted were incorrectly matching dateModified.
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

[Adobe Learning Manager system requirements](/help/migrated/system-requirements.md)

## Previous releases of Adobe Learning Manager

* [November 2024 release](/help/migrated/whats-new-nov-24.md)
* [July 2024 release](/help/migrated/whats-new-july-2024.md)
