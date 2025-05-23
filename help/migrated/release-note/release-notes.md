---
description: Adobe Learning Manager release notes
jcr-language: en_us
title: Adobe Learning Manager release notes
contentowner: jayakarr
exl-id: ae9251b6-5326-42c2-881e-2ab3393d9e17
---
# Adobe Learning Manager release notes

<!--<table>
 <tbody>
  <tr>
   <td><img src="assets/cp-prime-appicon-88x84.png"></td>
   <td>
    <p><a href="https://business.adobe.com/products/learning-manager/adobe-learning-manager.html">Adobe Learning Manager</a> was launched in August 2015. As part of our continuous improvement efforts to enhance the product, we have been rolling out regular updates. Read on to know the features enhanced/issues fixed in update releases.<br></p></td>
  </tr>
 </tbody>
</table>-->

+++Update 100: The November 2024 release of Adobe Learning Manager

**Release date**: May 10, 2025

## What's new in this release

View [What's new in Adobe Learning Manager](/help/migrated/whats-new.md) for more information.
+++

+++Update 99: The February 2025 release of Adobe Learning Manager

## Set up interface language through SAML

Adobe Learning Manager (ALM) now accepts a SAML attribute for language. This attribute is then mapped to the user's interface and content language settings, ensuring smooth interaction with the LMS in their preferred language. The configuration of these language settings is managed through the Identity and Access Management (IAM) platform, utilizing SAML for Single-Sign-On (SSO). This supports both Service Provider (SP) initiated and Identity Provider (IdP) initiated logins, allowing users to see the interface and content in their chosen language. 

Refer this [article](/help/migrated/administrators/feature-summary/set-up-interface-language-through-saml.md) for more information.

## Enhancement in Migration APIs

Previously, activity modules with external links migrated using APIs (`GET /bulkimport/cansync` and `POST /bulkimport/startrun`) did not display the **[!UICONTROL Mark as Complete]** option for learners after accessing the link. This issue has been resolved. Now, activity modules with external links migrated through APIs will correctly display the **[!UICONTROL Mark as Complete]** option for learners.

## Sorting functionality in the Learner app

The sort feature in the learner app provides personalized course recommendations based on the content and interface language. ​ This enhancement simplifies the process for learners to find courses in their preferred language and utilize more intelligent sorting options.

Refer this [article](/help/migrated/learners/feature-summary/catalogs.md#sorting-functionality-in-the-learner-app) for more information. 

+++

+++Update 98: The November 2024 release of Adobe Learning Manager

**Release date**: 16 November, 2024

## What's new in this release

View [What's new in Adobe Learning Manager](/help/migrated/whats-new-nov-24.md) for more information.
+++

+++Update 97: The July 2024 release of Adobe Learning Manager

**Release date:** 13 July, 2024

## What's new in this release

View [What's new in Adobe Learning Manager](/help/migrated/whats-new-july-2024.md) for more information.
+++

+++Update 96: The March 2024 release of Adobe Learning Manager

**Release date:** 16 March, 2024

## What's new in this release

View [What's new in Adobe Learning Manager](/help/migrated/whats-new-march-2024.md) for more information.
+++

+++Update 95: The November 2023 release of Adobe Learning Manager

**Release date:** 18 November, 2023

## What's new in this release

View [What's new in Adobe Learning Manager](/help/migrated/whats-new-november-2023.md) for more information.
+++

+++Update 94

**Release date:** 23 August, 2023

## What's new in this update

* Select the player's gear icon to change the video's quality.
* Change the quality and speed of a video on social.
+++

+++Update 93: The July 2023 release of Adobe Learning Manager

**Release date:** 10 Jul, 2023

What's new in this release

### Improved Recommendations

Adobe Learning Manager has introduced a new and revamped recommendation system for courses. This recommendations feature uses AI algorithms and users' interests like Products, Roles, and Levels to provide personalized content recommendations.

### Multi-Enrollment

In this release of Adobe Learning Manager, we are introducing multi-enrollment for learners that allow learners to enroll in more than one instance of a course at one or different time periods. 

### Deprecation Of Exavault Connector

This release of Adobe Learning Manager will include a new connector, which will use AWS Transfer family's SFTP protocol. 

For more information, see [What's new in the July 2023 release of Adobe Learning Manager](/help/migrated/whats-new-2023-july.md).
+++

+++Update: 92

**Release date:** 23 June, 2023

**Bugs fixed in this update**

* After completing a module, the Grade API isn't triggered automatically, which results in the green tick mark not being displayed as expected on the User Interface.
* After completing a few modules in a Learning Path or a Certification, the green tick mark, which indicates successful completion, does not display as expected.
* Adobe Learning Manager does not launch as expected after uploading a user CSV with incorrect fields.
* The warning popup on how to contact Admin also displays other email addresses.
* All badges earned by a learner don't display in the response.
* During user registration, a user name with " " must be accepted.

#### Player

* Add a menu to select screen resolution when playing a video.
+++

+++Update 91

**Release date:** 01 June, 2023

### Connectors

* The Adobe Connect connector requires APIs to send CSRF tokens. For more information, see Enhance Adobe Connect account security.

### String change

* We have renamed the string Rate this training to Rate this Course, Rate this Learning Path, or Rate this Certification, based on the training a learner takes. Depending on the type of training, a learner sees the string accordingly.

### Bugs fixed in this update

* The Play Store's Adobe Learning Manager mobile app description incorrectly says that a learner can take a course offline.
* There were issues when migrating content (module_version.csv and course_module.csv) from LinkedIn to Adobe Learning Manager.
* If an account is in an inactive state and created more than three years ago, then all the users of the account are GDPR-deleted irrespective of the status of the users.
* In the Instructor app, when you set the waitlist limit to zero in a session, and save the session, the User Interface incorrectly displays "Not applicable" instead of zero.
* When generating Learner Transcripts for the Power BI connector, the Training or Module duration (mins) column displays null values for certain classroom or VC modules.
* After you mark a course as complete for learners in an instance or multiple instances, all learners in the course get marked as complete, not just the learners in the current instance or instances.
+++

+++Update 90

**Release date:** 04 April, 2023

### Bugs Fixed In This Update

SAML login fails if the SSO login URL contains the entity_id.
+++

+++Update 89: The March 2023 release of Adobe Learning Manager

**Release date:** 01 April, 2023

### What's new in this update

**Enhancements to the Instructor Led Training (ILT) Experience**

Several enhancements have been made to the Instructor-Led Training (ILT) experience. Key enhancements include—ability to filter classroom sessions based on location, ability to switch instances (VILT) without losing progress, a new "Scheduling Assistant" for managing conflicts in booking instructors and classrooms, ability to attach "Skills" to Instructors and choose Instructors based on skills.

**Improvements to the Observation Checklist**: 

Authors now can select "Manager" and "Store Manager" as the Observer for checklists. Managers can view and complete the checklists within the Manager interface without having to switch role to an instructor. Notification is sent to a manager when a checklist is assigned to him/her.

**Use Any App/Smartphone Camera to Scan Learning Manager QR Codes** 

Learners will now be able to use any QR Code scanning app or their smartphone camera to scan the Learning Manager generated QR codes for course enrolment, completion and more.

**Reporting Enhancements**

A new Instructor Utilization report, Trainings Revisit report, Job-Aids report, and other reporting enhancements.

**Support for 'Hybrid' Sessions** 

Adobe Learning Manager now supports the ability to create "hybrid" Instructor Led Training (ILT) sessions. Virtual ILT sessions can be created with optional location information so that learners can attend the session in-person as well if they are available at the location.

**Better Progress Tracking for Classroom and Virtual ILT** 

Classroom and virtual ILT modules now provide the ability to report a learner's quiz status (pass or fail) along with the attendance status. Hence, both attendance and quiz success can be considered to decide learner progress.

**Adobe Learning Manager App for Microsoft Teams**

The new Adobe Learning Manager app on Microsoft Teams is designed to foster learning in the flow of work and boost social learning. Learners will be able to access learning content within the Microsoft Teams platform without the need to switch over to a browser. Please contact your CSAM for the beta release of Adobe Learning Manager app on MS Teams.

### Bugs fixed in this update

**Course**

* A Custom author cannot preview a module when the course is in "UNDER_CONSTRUCTION" state. The response shows Error 404.
* The Course title on the course/add page of an author app overflows when course title cross certain character limit.

**Author**

* In the Author app, the title of the course (if its lengthy) exceeds the page boundaries while creating a course.
* Sometimes, a course gets added, even though no author is selected.

**Dashboard reports**

* Tooltips display fine when the interface language is English, but throws a console error when the interface language is different.
* Rename "Mandatory" to "Required" in Learner Dashboard.

**Instructor app**

* The time format in the instructor app is not consistent with the other apps.

**Social**

* For certain types of posts, after posting, the social board does not open as expected.

**Admin**

* A user with a custom role is unable to download resources when previewing a course.

**Email templates**

* When a learner unenrolls from a Learning Program that contains a Classroom/VC course, he/she does not receive any cancellation email.

**Job Aids**

* You are unable to see the name of the course on the Job Aid widget.

**Publishing**

* The module description added in Adobe Captivate is not visible in Learning Manager when the module is published in ALM.

**Active fields**

* When a CSV with a large number of records is under process, it takes a significant amount of time, during which, if a user logs in and enters a value for one of the attributes, it might create a new user group that might result in CSV errors. To fix that, when the CSV import is in progress, Active Fields attribute pop-up message is disabled and its re-enabled once the CSV upload is complete.
* If the column in the Users csv file has the same name as the external users active field, the csv upload fails.

**API-related fixes**

* In the learningObjects reponse, the bookmark attribute is missing.
* An access entry gets created while generating an oauth refresh tokens for deleted users.
* The LO API returns incorrect loFormat, as pre-work modules were considered for calculating the course type along with the core content.

**Known issues in this update**

* The Share button on the Learner catalog does not work as expected on safari browser, Mobile & iPad MS Teams app.
* Notifications do not display in the Activity tab once the app is removed in other machines.
Nothing happens when you click the notifications in the Activity tab of the app on iPhone 14.
* On MS Teams app, the Learning Manager notifications (completed, enrolled, deadline, and overdue) do not display the status and the name of the course in the Activity tab.
* A pop-up with XML content displays when the Integration Admin does not approve the MS Teams app.
* The User Interface language on the Adobe Learning Manager app on MS Teams don't sometimes change as expected when the language is changed.
* You're unable to interact with the first notification when the focus is within the Iframe (Home & Catalog tabs).

**Limitations of the Adobe Learning Manager mobile app**

* Viewing of offline content.
* Grid/List view on the Catalog/My Learning page.
* Multiple attempts of taking a course.
* Enrolment deadline on a course card.
* On iOS devices, push notifications don't appear when the app is in the foreground.
* Deep links in push notifications don't redirect to the intended landing page.
* Clicking on the Register Interest button will redirect to the web.
* While replying or commenting in Social Learning, you will not be able to attach a file.
* You'll be unable to log in to LinkedIn Learning.
+++

+++Update 88

**Release date:** 7 March, 2023

### Performance Improvements In This Release

When a bulk enrollment of learners is performed, there will not be any log file generated for each learner.
We have optimized the processing of Learning Plans for large accounts. Doing so avoids any search issues or lags.
+++

+++Update 87

**Release date:** 1 March, 2023

## Bugs Fixed In This Update

* A learner does not receive the session cancellation email if the CR/VC module is removed from the enrolled course.
* Change GetNotificationData from GET to POST. The original implementation produced the error, **IllegalArgumentException: Request header is too large**, that led to failed notifications.
+++

+++Update: 86

**Release date:** 17 February, 2023

### Bug Fixed In This Release

In the learner app, searching for users and user groups are failing due to some issues with locale settings.
+++

+++Update 85

**Release date:** 13 February, 2023

### What's Changed In This Update

Added support for four letter language code while filtering languages in GET learningmanagerapi/v2/learningObjects.

### Bugs Fixed In This Update

For some locales, the search returns incorrect results.
The course metadata gets overwritten when the course has more than one variant of the same locale.
+++

+++Update 84

**Release date:** February 2, 2023

### What's Changed In This Update

**Job Aid report**

This update features a new Job Aid report that lists all job aids in the account. 

**Version control**

We've added version control for resources when adding the resources while creating a course.

**Report for attempts**

You can view a report of all reattempts and revisits by a learner for every training.

**Module reset API**

An administrator can now reset a module by using the Module reset API. For more information, see [Adobe Learning Manager API reference](https://captivateprime.adobe.com/docs/primeapi/v2/).

**Email template**

For a few email templates, you can now add a pre-requisite to the template.

**Other changes**

* You can add a manager-approved course as a pre-requisite.
* Performance improvement when refreshing the learning summary dashboard.
* Email ids and Account ids are verified before sending a bounce report.

### BUGS FIXED IN THIS UPDATE

* Duplicate author names appear on the Course overview page.
* A hyperlink on the account creation page led to Error 404.
* The Czech locale did not reflect as expected in player settings.
* In some cases, skills are displayed as undefined for in-progress and not started learners.
* Time spent across multiple days shows different time spent in Learner Transcript and Enrollment reports.
* The Back button is unresponsive for Administrator and Manager profiles in Course > L2 Quiz Score > By Question tab and Attendance & Scoring respectively.
* For a few locales, in an email template, some content in the email body is missing, and the language translation in the template isn't consistent.
+++

+++Update 83

**Release date:** 18 January, 2023

### What's Changed In This Update

**New column**

A new column, **unenrollmentAllowed**, is added to course.xlsx. Download the file from this manual.

**Linkedin Learning connector**

For Linked in learning connector, there is a new checkbox introduced Learner can Unenroll on the Filters page. For more information, see [LinkedIn Learning connector](/help/migrated/integration-admin/feature-summary/connectors.md).

### Bugs Fixed In This Update

* When hovering on the bar charts, the dashboard report tooltip appears as expected.
* In Reports under User activity, the Learning Time Spent report displays incorrect data for daily/monthly data.
* In some cases, the quiz score graph displays incorrect values.
* In a course with SCORM content with multiple attempts set, when a learner attempts the course, the Revisit button is disabled.
* In some cases, after enrolling a learner in a course and downloading an email audit log, the email is delivered, but it does not appear in the log.
* The calendar invite for an instructor must include the text instructor in the subject.
* The Training card icon does not reflect on related courses recommendation and Learning Path cards present on the course overview page.
* On the Learner homepage settings, add a Saved by Me section.
* For certain accounts, a user is prompted for SSO login for an account where Adobe id is required.
* In timezones with Daylight Savings, the 'start_time' field is calculated based on the time difference currently, not based on the time difference in the actual start date and time. This caused invites with incorrect times.
* Whenever a certification recurs, a copy of the underlying courses gets created internally in the database. These courses then appear in search, contrary to the expected behavior.
* When uploading a CSV fails, you do not receive any email notification.
* If the names of the Active fields are lengthy, the names disappear when dragged and dropped. Following that, the Save button also does not work as expected.
* A session report does not get exported via a course's attendance and scoring page if the first user in the report has a record in the activity grade table with the comment as null.
* When you use the admin account to retrieve the badges, you can get the list sorted as expected. But when you perform the same for a learner, the results are not sorted.
* If you choose a course from your search results and then try to go back to the search results using the back button, the search results disappear.
* Not all users are added to a user group as instructors in a session.
* Templates that have multiple user templates inside, their subject is overridden with some values.
+++

+++Update 82

**Release date:** 15 December 2022

* The GET LO API now includes pricing information, if available.
* A new column, Completed by, is added to LT reports. This helps admin identify the completion source of an LO. 
* We've added a new ILT module that can record learner pass / fail status along with attendance. Instructors can now mark a learner as attended with pass or attended with fail option.
* An Admin can now require learners to complete and pass before consuming next module / course. This is applicable for pre-requisites, ordered courses & LPs. 

**Bug fixes**

* Bahasa language issues of immersive mobile experience on the sidebar and footer.
* Immersive view fixes related to module previewing.
* A course search in admin & author returns results in a different locale than the typed one.
* Changes to welcome email templates were not saving after editing.
* Users having different email IDs and adobe IDs were not able to log in to the mobile app. 
* Users were incorrectly identified while joining Zoom / BJ VC sessions.
+++

+++Update 81 - November 2022 release of Adobe Learning Manager

**Release date:** 05 November 2022

**Note:** With this release of Adobe Learning Manager, users with inactive accounts can no longer access their accounts using subdomains. The accounts can be accessed using the account id or by using the acapindex.html page and entering the email id.

### What's new in this release

The November 2022 release of Adobe Learning Manager consists of the following:

* Multiple SSO Configuration
* Non-logged-in feature support
* Training Overview Page Enhancements
* Player customization
* Impersonation of Learner and Manager

**Note:** With the November 2022 release of Adobe Learning Manager, Zoom will deprecate [JWT authentication by June 2023](https://marketplace.zoom.us/docs/guides/auth/jwt/). Accordingly, the Zoom connector with JWT will continue to work until mentioned date, but we recommend users to create Server-to-Server OAuth app to replace the functionality in their account. Any new connection will have Zoom OAuth authentication by default.

### Bugs fixed in this update

* As a learner, when you attempt to access a Learning Program with more than 10 courses on mobile, an error message appears.
* If a course has set a reminder to be sent n days after missing the deadline, the email is being sent after n days as expected but the number of days the deadline is missed is n-1 instead of n.
* A video does not load in the player if L1 feedback is enabled for the course in the learner app and the user has only a learner role.
* A completion reminder email does not display the time in the user's timezone as expected.
* Learner Transcripts which are generated via dashboard reports do not honor the filters and display more information than required.
* You are unable to select content where the interface language is not added as the content language.
* When self-registering for a course for a second time, the URL that appeared was incorrect.
* When an instructor gets removed from a VC session, they do not receive any mail notifying them of the cancellation of the session.
* The text "minute" on a tile on the learner training page does not get translated to Bahasa Indonesian as expected.
* The Compliance dashboard displays incorrect data for non-compliant learners.
* While adding a report, you are unable to select courses or catalogs where the interface language wasn't added the content language.
* We've added the following content languages in this release:
   * Bulgarian
   * Flemish
   * Portuguese (Brazil)

### Known issues in this update

* In some cases, the quiz score graph does not display as expected. When you resize the graph, a blank space appears at the beginning. In addition, not all questions appear, and incorrect data display intermittently.
+++

+++Update 80

**Release date:** 20 September 2022

* Login issues on the mobile app on iOS now have been fixed.
* Fixed an issue with bounced emails.
* Instructors were incorrectly notified even before submissions were made by learners.
* An instructor gets an email notification even though a learner has not submitted an activity.
* After creating a VC session on MS Teams or Adobe Connect, instructors don't receive the session invites.
* Incorrect status in a Learning Path.
* Enhanced the performance of the app.
+++

+++Update 79

**Release date:** 18 August, 2022

* Calendar invite confirmation for ILT / VILT sessions now works with Google calendar.
* A store manager now can see notifications for users under them even if they are removed as a people manager.
* In some cases, course enrollment fails, and displays Error 500.
* In some cases, you're unable to modify a virtual course instance for Teams.
* Admins and instructors can add comments for users who have not attended ILT / VILT sessions.
* Improvements in performance when downloading large-sized reports.
* When a user's email gets bounced, the Admin receives an email notification. The email contains a link, which when clicked, downloads a CSV with the list of users whose email got bounced. The Admin then can take necessary action.
   * The email triggers when an email bounces or drops.
   * The email triggers once a day to all the admins who are added to the list.
   * The link expires in seven days.
* An error message displays while trying to integrate an already integrated Adobe Connect account with another Learning Manager account.
+++

+++Update 78

**Release date:** 4 August, 2022

### Bugs fixed in this update

* If you've a course that contains a module with a preview and then use an API to retrieve the resources from the course,  then the response will not contain any data from location, contentZipUrl, and contentStructureInfoUrl.
* Incorrect response after sending a XAPI request from Swagger document, where the domain name is learningmanager. 
* In the /boards/{id}/posts API response, the "post.attributes.myPoll" property appears as an empty object.
* In some cases, for a non-logged-in user, the Add to cart button is disabled for some courses or Learning Paths.
* Incorrect sub-domain url on the branding page.
+++

+++Update 77

**Release Date:** 24 May, 2022

**Issues fixed in this update:**

* New courses do not honor the sequence in Salesforce app. If you alter the sequence, the course fails to display in the intended sequence.
* After you modify the settings in the Classic homepage and save them, the changes do not get saved as expected. This happens intermittently.
* HTML code displays when learners check their notifications, which adversely impacts the experience.
* On the dashboard, the learning spent time is incorrectly displayed as zero hours.

## UPDATE: Adobe Learning Manager will be rebranded to Adobe Learning Manager

This is an update about an upcoming change and help you prepare for it.

**Adobe Learning Manager as a product will be rebranded to Adobe Learning Manager in July 2022**. This is a strategic effort being done to more accurately reflect alignment of the product with certain business priorities.

The product team is taking all steps to ensure that there is no impact on your usage of the platform. You can continue to use the product as usual. The Administrators of the platform may notice the new brand name in certain screens in July.

As part of this change, the access URLs for Learning Manager are affected.

For example, if the access URL for your account is `https://learningmanager.adobe.com/XYZ`, then the new URL will be `https://learningmanager.adobe.com/XYZ`.

All exisiting URLs will continue to work.

To complete this action, work with your IT department of your organization. For more information, contact us at `learningmanagersupport@adobe.com`.
+++

+++Update 76

**Release date:** April 20, 2022

* Fixes to product terminologies on a few dashboard reports.
* A double slash ("//") in the URL of an endpoint resulted in validation errors.
* After refreshing a page, the percentage completion and the last visited fields displayed incorrect information.
* We've made some changes in how the value Certificate or a Learning Plan is calculated.
* A Custom Admin was able to add all users as instructors even though he/she was permitted to add only one user.  
* On a badge PDF, an incorrect completion date was displayed.
+++

+++Update 75

**Release date:** March 29, 2022

* In some accounts, after copying the raw csv in the FTP location, the user import does not take place as expected, and there are multiple notifications of errors.
* In previous releases of Learning Manager, to configure a Zoom connector, you had to configure Exavault FTP first for copying the csv file. In this release, the FTP connector will no longer be used for the csv file, and hence, you need not configure the FTP first.
+++

+++Update 74: Learning Manager AWS India instance

**Release date:** 15 February, 2022

### Overview

An [instance](https://learningmanagerapac.adobe.com/acapindex.html) of Learning Manager will now be hosted on AWS in Mumbai (ap-south-1). For customers using this India instance, will have their user's personally identified information (PII) and user's learning records stored in India region only. 

### What is supported

Adobe Learning Manager India instance is at par with other instances like EU and US regions in terms of feature capabilities. There are a few features which are not supported in India instance. These are:

* Credit card payment for purchase of seats  
* Creative Cloud content catalog  
* Slack App
* **&#42;** Awaiting certification for SOC2 compliance

### Frequently Asked Questions

**How is this instance in Mumbai different from other AWS-only environments?**

There is no difference. The instance in Mumbai is the same as [AWS US](http://learningmanager.adobe.com/) or [AWS EU](http://learningmanagereu.adobe.com/) instances. This instance is hosted in India, and all the learning records and user data stay in India. The following features are unsupported in the India instance:

* Credit card payment for purchase of seats  
* Creative Cloud content catalog  
* Slack App
* **&#42;** Awaiting certification for SOC2 compliance

**Will this environment be Common Controls Framework (CCF)-compliant?**

Yes. The new instance is Common Control Framework (CCF)-compliant.
+++

+++Update 73

Release date: February 05, 2022

* Email template support is now available for content languages, including Hungarian and Finnish.
+++

+++Update 72 - January 2022 release of Learning Manager

Release date: 15 January, 2022

### What's new and changed

* Add classroom locations
* Gamification changes
* Microsoft Teams connector
* API changes
* Mobile immersive web changes

<!--
For more information, see What's new in the [**January 2022 release of Adobe Learning Manager**](../whats-new.md).
-->

### Bugs fixed in this release

**Content Library**

* Searching of content files in private content folders was not working for users having custom role privileges. This is now fixed.

**Courses**

* Deletion of a course or learning path was not possible if they had a historic association with a learning plan. This is now fixed. Users can now delete a course or a learning path if they are not presently associated with a learning plan.  
* When previewing a course or learning path, if the resource file has a long name without spaces, the file name does not wrap as expected and overflows into the next line. This issue is fixed.  
* In the case of virtual classroom, earlier you were able to create a module without selecting any VC conferencing system there by in a new instance VC URL did not have the required info. This is now avoided by an error message at module creation stage asking you to specify the VC conferencing system before you can save module.  
* The waitlist page was displaying a misleading banner message on registered users, which is removed now.  
* In the case of bulk unenrollment for courses, the pop up to enter email ids was not showing up, which is now fixed.  
* The option to send email to learners from attendance & scoring tab in admin and instructor app was not excluding unchecked learners after performing select all operation. Hence Learning Manager was sending email to all learners. This issue is now fixed.  
* The enrollment report shows as "Not Started", even though a learner has already completed the course.

**SSO**

* In SSO setup, if entity id had any leading or training spaces then login configuration was not working, this is now being handled as part of the fix.

**Announcements**

* As an admin, the start and end dates for an announcement were not getting saved if interface & content language was set to Deutsch/Espanol. This issue is now fixed.

**Email template**

* Session invites spanning across multiple days where the invites did not reflect the correct information on days are blocked in some email clients. This is now fixed.  
* "Venue Name" variable was missing in "Reminder of upcoming session" email template for learners in German locale. This is now added.  
* The link to create account as part of the welcome email to user was not considering the user locale which is now fixed.

**Email reminders**

* If learners were enrolled to training through a Learning Plan, then the completion reminder emails were sent multiple times based on number of edits made to completion dates of the same learning plan. This issue is now fixed.

**User**

* The message shown to user when his/her account is inactive/suspended has been improved indicating to reach out to their admin to have their accounts enabled again.

**Activity**

* An instructor was unable to view the learner submissions if the submission filename had special character in it. This is now fixed.

**Report**

* An admin was unable to download the course enrolment report if it contains a learner who is indirectly enrolled into this course through a flexible learning path but is yet to choose an instance for this course in learning path. This issue is now fixed.  
* Rearranging reports in reports dashboard for admin and manager roles, was not preserving the state of the reports order. This issue is now fixed.

**Content**

* Audio in training content was not auto playing in preview as learner mode due to browser auto play policies. This is now fixed for supported browsers except for Safari.

**Gamification**

* If an external learner was converted as an internal learner in the same account, then he/she was unable to access the gamification leaderboard in learner app. This issue is now fixed.

**Player**

* The player was not showing warning message when user tried to jump modules in ordered course having AICC type of modules. This is now fixed.  
* For certain acquired courses having video modules in headless LMS case playback was not working for certain users. This issue is fixed now.

**Manager dashboard**

* A manager was unable to export report for his direct team from Manager Dashboard's team skills page. This issue is now fixed.

**Publish**

* In the European instance of Learning Manager content that was directly published to Adobe Learning Manager from Adobe Captivate was getting published in Deutsch locale by default. This is now fixed.

**API**

* The duration field is now added to the Job Aid model.  
* For the recommendation APIs, sometimes a GET request returns Error 500.  
* When you migrate trainings through Exavault and if the text contains non-English characters, then it used to get updated with garbage characters in the text. This issue is now fixed.

**Localization**

* `NormalTextRun  BCX0 SCXW38820519 For the`Admin, Author, and Learner apps, some content in German does not appear as expected.

## Known issues in this release

* On the Social Learning page, when creating a post, you are unable to record an audio or upload the audio after tapping the mic button. This is a limitation of the browser. 
* In iOS, H264 and WMA audio files are unsupported in the mobile browser.
* Learners who have a + in their email address do not have their progress marked. This is after they take a VC course in Microsoft Teams.
* In Safari Mobile browser, learners will not be able to upload more than 200 mb file in Social Learning. This is browser limitation.
+++

+++Update 71

Release date: November 17, 2021

### Share training with managers

Learning Manager offers compliance dashboard to all Administrators and Managers. Managers find it very useful to track compliance of their team members for a particular training. At the same time, Administrators would like all Managers to add compliance trainings to their dashboard and track it. 

In Learning Manager, the **Share with Managers** workflow allows Administrators to share training with Managers, so that they can get added to a manager's Compliance Dashboard. Thus, Managers do not need to take any action and can start tracking compliance immediately. 

For more information, see  [**Share training with managers**](../administrators/feature-summary/reports.md#share_training_managers).

### Bugs fixed in this update

* If there are two accounts and the enhanced Learning Path feature is disabled, and there is a shared catalog from the first account to the other, then the Learning Path in the second account has duplicate sections in the course page.
* A custom FTP now supports sftp:// in addition to http:// and https://
* Exavault connector now uses V2 APIs.
* In some cases, the quality of videos was suboptimal. The issue is fixed now.
* Even after a learner has completed a mandatory course and approved by the manager, the certification remains in Pending Approval state.
* If the names of authors contains accented characters, the migration of the course fails.
* If the Active Field has values in upper case, the Active Field does not get saved as expected.
* Unable to filter Learning Paths based on skills.
* When an Administrator creates an instance and adds a new session, an Instructor does not receive the session invite email. This issue occurs in Zoom VC courses.
+++

+++Update 70

Release date: October 28, 2021

### Bugs fixed in this update

* In some cases, information about a Learning Path does not reflect in a Learner Transcript.
* The text inside the **Mark Completion** dialog is updated to reflect that the operation is irreversible.
* The Learning Objects API, in some cases, returned metadata error.
+++

+++Update 69 - October 2021 release of Learning Manager

**Release date:** 09 October, 2021

### Learning Path

The **October 2021 release of Adobe Learning Manager** introduces the concept of Learning Paths. 

>[!NOTE]
>
>The **Settings > General** page has a new option to enable extended capabilities of Learning Paths. If this option is enabled, you can add Learning Paths in another Learning Path. You cannot change the option once it is enabled.

Learning Paths replace our existing feature of Learning Programs. Imagine Learning Programs getting powerful enhancements without dropping any existing capabilities. Also, the feature gets branded as a Learning Path. 

For more information, see [***Learning Paths***](../administrators/feature-summary/learning-paths.md).

### Other changes

* New Salesforce app
* Content Hub
* Reporting changes
* Session Summary report
* Player TOC changes
* API changes
* Connector-related changes

For more information, see [***What's New in the October 2021 release of Learning Manager***](../whats-new.md).

### Bugs fixed in this update

* Email templates, such as, Course Unenrollment, Learning Program Unenrollment, or Certification Unenrollment do not reflect the latest product terminologies as defined in the csv. Now the default text in email templates will support customized terminologies.
* The user language in Learning Manager is not supported in the Publish to Learning Manager workflow. If the user language is different, Publish to Learning Manager happens in English.
* If you add many catalogs to a custom role, an error occurs when you update the role. Now the limit of number of catalogs is increased upto 50 catalogs. 
* In some cases, trainings that are deleted are still visible in a catalog. This issue occurred in the Admin app only and is fixed now.
* When the manager role is changed from one user to another, the manager role from previous user was still reflected in the UI. This is now fixed. This issue was present only for external users and not for internal users.
* In some specific scenarios for a large set of users getting imported via user csv, the import failed. This issue is fixed now.  
* A Learning Transcript does not display the completion date for an external certificate if a mandatory course is added after external certificate is created, and a user is enrolled to it. This is now fixed.  
* A certificate does not display the localized name of the learner as expected. This is now fixed.  
* In case of Zoom VC sessions, an instructor does not always receive the invite for the session. This is now fixed. The instructor now receives the required communication.  
* A learner does not receive invites for a session if course level templates is enabled but account level templates are disabled. This is now fixed.  
* For specific time zones, email reminders were delivered a day later than expected. This is now fixed.  
* Learners do not receive session notification mails if certain email templates are disabled.  
* Incase a BlueJeans meeting is updated by Authors, Admins, BJ meeting URL was becoming unusable. This is now fixed.  
* Upon running the GET /LO API in some cases, the courses that are part of a Learning Program are not returned.  
* If learner attempts to upload content whose name has blank space, then the learner encounters an internal server error.  
* Badge PDFs generated for learners had formatting issues when they were generated in non-English locales. Such issues are now fixed.
+++

+++Update 68

Release date: September 28, 2021

### Bugs fixed in this update

* On the mobile browser, deep links have been enabled for the following:

   * All Board
   * Public Board and Post
   * Private Board and Post with Access
   * Private Board and Post without Access
   * Restricted Board and Post
   * Comment on Post
   * Reply on comment
   * Social User Profile

* For accounts using custom domain, the Learner app does not display the favicon.
* On AEM, the Learning Manager component deletes the configuration of other components.
* The help page for AEM component redirects to an incorrect location.
* Externalized getting and storing user emails/tokens so that users can implement their own storage backend instead of using AEM user nodes.  
* When editing plain text description in Courses, Learning Programs, Certificates, and Job Aids, a warning message displays.
* The reports from Manager Dashboard do not get downloaded when a user has both custom and manager roles.  
* An email digest displays incorrect value of training activity.
* In some cases, Learning Manager behaves unexpectedly when you move from the Content Marketplace to the Learner page.
* On the Social app, the filters do not work as expected in the list view.
* The welcome e-mail that internal users receive are also received by external users.  
* Add the Learning Manager widget in the page template in AEM.
* If you want to republish a certificate after removing a course, you are unable to do so.
* Learners do not receive mails that contain details of a session.
+++

+++Update 67 - Updates to Azure

This update introduces a new instance of Azure.

>[!NOTE]
>
>The following are not supported in the instance:
>
>* [Custom domain](../custom-domain.md)
>* [Credit card purchase](../administrators/feature-summary/billing-management.md)
>* [Content catalog](../administrators/feature-summary/content-catalogs.md)

+++

+++Update 66 - August 2021 release of Learning Manager

The **August 2021** **release of Adobe Learning Manager** focuses on improving Learner Experience, Reporting, and Administrative workflows. Some of the highlights include:

* **Content marketplace:** Learning Manager now offers more than 70000 courses from varied domains, such as, Technology, Management, Leadership, and so on.
* **Enhanced Accessibility support:** Accessibility support for the learner role strengthens via enhanced keyboard navigation, screen reader capability, and contrast ratio compliance. 
* **Rich Text Formatting:** Learning Manager now offers rich text editing for descriptions in courses, programs, certificates, and Job Aids. This allows authors to specify descriptions in rich text including hyperlinks, images and other text formatting options, as opposed to plain text.
* **Star Rating:** A learner can now rate a course on a 5-point scale. An Administrator can select between existing effectiveness rating or the 5-star rating. 
* **Badgr Integration:** Learners can now authorize Learning Manager to automatically push badges they have earned in Learning Manager to their Badgr account, from where they can share their badges in their social networks.
* **Export learning events to Salesforce:** Learning Manager now offers an ability to export some specific events in Learning Manager like new user addition, enrollment and completion to a Salesforce tenant, and provide an ability to link these with the appropriate User object or Contact object in Salesforce.

For more information, see [***What's new and changed in the August 2021 release of Learning Manager***](../whats-new.md).


**Release date:** 7 August, 2021

### Bugs fixed in this update

**Learner Experience**

* After a learner is added to two user groups and a Learning Plan is added, the learner is enrolled in a different instance of the same course.
* In some cases, after enrollment and starting the course, the course does not play as expected.
* The course description displays HTML tags, which is now fixed.
* If you comment on a post in a social board that spans multiple lines, the comment appears in a single line. This is now fixed.

**Authoring**

* In some cases with auto enrollments, learners receive multiple enrollment emails.

**Reporting**

* When the interface is set to a few non-English locales, Learner Transcripts do not generate as expected.
* Ability to reset the progress of a course inside a Learning Program and Certification. 
* If a CSV contains active fields with the same name, but with different case sensitivity, the CSV produces an exception.

**Others**

* The option to edit scores and comments must be disabled when no learner is selected or if the attendance of selected learner is not marked.
* Values in active fields displays in lower case in the Edit User dialog even though a user had previously added the values in upper case.
* Ability for Administrators and management to view pending approvals for courses. This allows management to ensure that managers track employee learning and training, and also allow Learning Manager administrators to approve course enrollment as needed.
* A user who has an author or custom admin/author permission cannot edit a Job Aid that is created by another user.
* From Admin role, when user navigates to Course > Instance and select the 'Learners enrolled' for any instance, earlier it used to show the learners from 'Default instance'. Admin needed to change the instance from the dropdown manually. Now Learning Manager correctly navigates user to the learners page with the correct instance selected.

**Device app**

* On Android and iPhone devices, a learner is unable to launch course modules at random. Doing so produces Error 401 unauthorized.
* A learner can scan two QR codes, but on scanning the third QR code, an error message displays.
* On some Android and iOS devices, a file does not open as expected for some downloaded courses.
* Trying to open a Job Aid displays an error message.
* The device app behaves unexpectedly when a Learning Program is consumed offline.
* When a learner goes back online and opens the app, the app gets stuck on the splash screen.  
* Sometimes, when a user is back online, the app switches to the classic view.
* At times, when a course is consumed offline, the progress is not saved.
* Sometimes, a course name is not displayed as expected from the beginning when the name is lengthy.  
* On the catalog page, the courses do not get sorted as expected.
+++

+++Update 65

Release date: July 2021

### Bugs fixed in this update

* Issues with logins for users.
* The course enrollment email template for Manager does not display the course completion deadline if the variable is added to the template.  
* TLS 1.0 and TLS 1.1 have been deprecated.
* Issues with GDPR data deletion for a user.
+++

+++Update 64

Release date: July 2021

### Bugs fixed in this update

* Notification for enrollment is sent to learners who are already enrolled in a course.
* When a custom certificate as a badge is generated, the date format is not supported in German language.
+++

+++Update 63

Release date: June 2021

### Bugs fixed in this update

* You can create a user with a blank name in a csv.
* If there is a '/' character in the active field, thae after creating a job for downloading user.csv, the state of the job doesn't change from "Submitted" to "Completed".  
* Ordered modules does not honor the sequence.
* When an external author is deleted, the course that the author has created, is no longer available.
* Searching a Learning Object with more than one skill produces unexpected results.
+++

+++Update 62

Release date: June 2021

### Bugs fixed in this update

* Unable to log in to the app when the account is SP-login initiated.
* Videos are not getting rendered from Brightcove as expected.
* The userGroupInfo API is not visible while visiting the learning program in any of the apps.  
* Unable to search a retired Learning Program and Certification while creating a Dashboard report.  
* An author is unable to edit or update a Job Aid, which is created by another author.
* The API for file submission does not work as expected in the EU cluster.
+++

+++Update 61

Release date: May 2021

### Bugs fixed in this update

* Performance improvement on userGroupInfo calls.  
* After enabling new Brightcove profiles, Learning Manager supports contents with video and audio modules.  
* Learning Transcripts fail to capture the data if a narrow date range is selected.
* A session invite is sent to the enrolled learners for all the sessions even when only one new session is added.  
* Audio modules are not getting uploaded as expected.
+++

+++Update 60

Release date: April 2021

### Bugs fixed in this update

**Report**

* After creating a report, if you search for a retired course, you are unable to do so.
* Errors in one report propagate to others. As a result, those reports led to errors.

**Job Aids**

* After downloading a Job Aid, you are unable to delete the Job Aid.

**Player**

* WebVTT captions do not appear as expected.

**Learner app**

* On the Certification Overview page, External Certification does not display the duration added by an author.  
* Add the option **All** in the Skill filter.
* Learners were receiving multiple digest emails.
* The number of rows selected do not reflect as exected on a page.

**AEM component**

* Widgets do not get updated as expected after a page refresh.

**Localization**

* A few German strings are not localized as expected.
* The translation of strings defaults to English if a learner did not select the interface and content language.

**Certification**

* Ordering of the module can be bypassed if the pre-requisites are not enforced.

**Browser**

* Author, manager, or learner apps do not display as expected in IE 11.

**Gamification**

* Gamification points are not getting redeemed as expected.

**Content Library**

* Content Trial App courses do not work as expected.

**Player**

* The player loads only in the space where the widget is present.
* Videos inside a Captivate module do not play as expected.

**Connector**

* In some cases, files are getting deleted from an FTP/Box connector.
* Files get deleted from ftp the if the files are updated with the same names.
* A BlueJeans event supports pagination where the number of events are greater than 100.

**Mobile app update 3.3 - March 2021**

Release date: March 26, 2021

### What's new and changed {#whatsnewandchanged}

Captivate  Learning Manager Mobile App update 3.3 introduces a brand new Home Page, which supports mastheads and AI-based training recommendations. This home page is available to all accounts that are configured for the new Immersive Layout option. The accounts configured with the Classic Layout continues to see the classic/legacy home page. They should not observe any changes in the home page. 

In addition, this update also allows learners to download their badge as PDF and an image. The update also introduces a feedback po-pup, which allows learners to provide feedback about the app anonymously. 

For more information, see  [Learning Manager device app](../learners/feature-summary/ipad-android-tablet-users.md).

Read on to know more.

#### New home page

For all accounts that have the option Immersive Layout enabled, there is a brand-new home page to support the Immersive Layout configuration. 

#### Feedback rating

In this release, Learning Manager prompts the user to provide feedback about their experience with the Mobile App. 

#### Download badge 

This update allows learners to download their badges in PDF and Image format.

<!--## Previous update releases {#previousupdatereleases}-->
+++

+++Update 60 - February 2021 release of Learning Manager

Release date: February 20, 2021

### What's new and changed {#Whatsnewandchanged-1}

* Board view in social.
* Customizing the social banner.
* Catalog filters in Learner app.
* Unenrollment from training.
* Import users from Salesforce contacts.
* ...and many more.

For more information, see What's new in the [February 2021 update of Learning Manager](../whats-new.md).

### Bugs fixed in this update {#bug-fixes}

**Certification**

* In some cases, a learner was unable to reattempt a course, which is part of a certification even though maximum attempts for the course is set to infinite. This issue is now fixed.
* In some cases, a learner is unable to enroll into a certification due to the **Enroll**button not being visible as expected.

**Content Library**

* Incorrect help url on the **Add New Content** page. The correct url has been updated.

**Course**

* An L2 Quiz Score report downloaded for an AICC content module shows incorrect score under the Total User Score / Quiz Score column. This issue has been fixed.  
* Downloading resources from a course was not working if it is duplicated from another course if learner did not have access to the original course which used to create a duplicate course.   
* Banner images where not getting deleted when author removes it while the course is in draft state. This issue has been fixed.

**AEM**

* After inserting the Learning Manager component in AEM, the page was taking a long time to load preventing access to the other components. This issue has been fixed.

**Admin**

* Courses that are retired do not appear in the search results as expected. This issue has been fixed.  
* Admin was unable to search for retired courses in **Admin app** -> **Custom reports** -> **Excel reports** -> **Course Reports**, which is now fixed.   

* Downloading a quiz report as excel does not work if the file contains learners who've consumed the trainings before and after content update. This issue has been fixed.  
* A CSV upload fails if the active fields contain special characters. This has been fixed.  
* In a few cases, when a learner takes a quiz, created in Captivate, the answers do not get captured the way they're expected to.  
* After creating a subscription and attempting to edit the subscription, the **Save** and **Cancel** buttons do not appear as expected. This has been fixed.

**Player**

* For a specific type of content of SCORM-2004 resume scenario was not working. Hence, learners had to navigate to the point where they left off. This is now fixed. Content should now resume from the point where used left it earlier.    
* After enrolling to a course, in some cases, content does not play as expected. This issue has been fixed.

**Unenrollment**

* An enrollment report only lists 20 unenrolled learners even when there are more learners unenrolled from the course/certification. This issue has been fixed.  
* There was an issue in exporting the list of unenrolled learners in Enrollment report in some cases. This is now fixed.

**Learning Program**

* For a flexible Learning Plan, if a learner is enrolled to only one of the course instance, then on clicking the course link of the other courses whose instances were not selected, a blank page opens.

**Learner**

* A few learners, whose user names have special characters, do not receive email notifications as expected.
* In the immersive view, in some cases, the Calendar widget does not display upcoming VC sessions as expected.  
* In the Learner App, the **Skill** filter did not work as expected. This issue has been fixed.

**Search**

* In a specific scenario, Manager was not able to search for a manager's group of users earlier. This issue is now fixed for the Manager role.

**User Group**

* When exporting user group report having more than 500 users, the data values & the column headers in the report were not matching which is now fixed.  
* When Administrator edits Email signature in Email templates and adds multiple lines, he used to see html tags only in the Admin interface. This issue is fixed now.   
* In **Admin App > Catalog > search for catalog**, you are unable to search.

**Users**

* A few active external users were getting deleted. We've made some changes and the issue is fixed now.

**Import**

* Importing a csv fails if the csv header contains trailing white spaces or the email of a user contains accents or diacritical characters.

**Activity Submission**

* In the Instructor app - activity submissions page, the submitted date value used to overlap with the file name if it was a long one this UI issue is now resolved. 

**Instructor**

* An instructor receives session invites for all his/her sessions even though only a new session is added. This issue has been fixed.

**SCORM**

* For certain SCORM content, there are few browser-related issues, player navigation issues, and inconsistencies in recording quiz score. These issues have been fixed.

**SAML and SSO**

* We've updated the error message that you see when the SSO credentials are expired.

**Learning Manager API**

* The getlearningObject API returned incorrect enrollment data due to issues in caching. This issue has been fixed.
* A VC session now displays the meeting URL in the Location field in a meeting invite.
* If you have setup multiple VC provider integrations and if any of them does not work as expected, VC selection dropdown used to show empty list. This is now fixed. Remaining VC integration get listed correctly now.  
* Connect VC templates do not load as expected when an instructor joins the session.
* An incorrect duration is shown in the UI after migrating modules with duration in module_version csv file.  
* For some accounts, updating a user does not work as expected. This has been fixed.

### Known issues in this update {#known-issues}

* When using the **Duration**filter in the Learner app, the content and filter may not be in sync if the learner uses some other content locale and is not a part of the default instance in terms of enrolment.

>[!NOTE]
>
>The training '**Duration**' and '**Format**' filters are identified based on the training content available for default instance and for account preferred locale.

+++

+++Update 59

## Update 59

Release date: December 18, 2020

### BlueJeans Event connector {#bluejeanseventconnector}

BlueJeans Events connector connects Learning Manager and BlueJeans systems to automate data synchronization. Using this connector, you can:

* **Set up virtual sessions using BlueJeans Events:** Configure a new event in BlueJeans and setup a VC session in Learning Manager by selecting the appropriate BlueJeans event. Date and time details are picked automatically from the BlueJeans events.
* **Automated User Completion Syncing:** An Automated user completion syncing process allows the Learning Manager Administrator to fetch completion records for BlueJeans events automatically.

This new connector requires a separate set of credentials to configure the connector. 

For more information, see [***BlueJeans Event connector***](../integration-admin/feature-summary/connectors.md#bj-events).

+++

+++Update 58- December 2020 release of Learning Manager

## Update 58- December 2020 release of Learning Manager

Release date: December 05, 2020

### What's new and changed {#Whatsnewandchanged-2}

This release focuses on the following:

* Brand new learner homepage experience  
* Mobile web responsive layout for learner role  
* AI-based recommendation for learners  
* Weekly digest emails  
* Checklist  
* Marketo engage integration  
* Custom Domain  
* Import of quiz scores from Adobe Connect  
* Deep link to catalog for learners  
* LinkedIn Learning Enhancements  
* ...and many more

For more information, see  [***What's new in the December 2020 release of Adobe Learning Manager***](../whats-new.md).

### Unsupported features in mobile immersive experience {#unsupportedfeaturesinmobileimmersiveexperience}

The following features are not supported:

* Social App: A learner is redirected to Classic experience if he/she clicks on Social widget on Home page
* Profile Settings/Edit Profile
* View Badge/Skills
* Leaderboard: A learner is redirected to Classic experience if he clicks on Leaderboard widget on Home page
* Downloading Job Aids.
* Filter options in Search.

### Bugs fixed in this update {#bug-fixes-1}

* You are unable to delete a content folder if the content folder contains deleted content. 
* Learning Plan allows Admins to setup a course with auto-instance. For a course with Activity submission module, Instructor information was not setting up correctly earlier. Now Learning Manager assigns the Instructor from default instance to this auto instance automatically. 
* A custom badge with a catalog label with a space does not allow the pdf to download as expected. 
* A report downloaded from the dashboard is different from the subscription email received for the dashboard report.  
* A Learner Transcript does not have updated data for a recurred certification.
* After starting a course, if you let the course time out, then the number of attempts do not display as expected. Also there is a blank screen sometimes when you attempt a course multiple times.
* There are Error 5xx after you upload a module.
* A private social board is not visible to all the learners.

### Known issues in this update {#known-issues-1}

After completing a course or a certification, you do not see the feedback pop-up immediately. This issue occurrs only when you take the course in the immersive UI. If you take the course in the classic UI, you can see the feedback pop-up appear as expected.

+++

+++Update 57

## Update 57

Release date: September 23, 2020

**Content library**

* In the content library, retiring a content does not remove the content in the **Published**tab. When you refresh the page,  the retired content no longer displays.
* When creating a content folder, the **Name**field is not marked as mandatory, which in fact is a mandatory field.

**Customer request**

* To identify all the courses that each learner is enrolled in and whether they have completed it, include the following fields in the dashboard, Subscription Report:

   * UUID
   * Email address

**Learner Transcript**

* Generating a Learner Transcript in the Indonesian locale was producing errors.

**Search**

* You are unable to search for a specific course. This has been fixed.

+++

+++Update 56 - Mobile app

Release date: August 25, 2020

### Take courses from LinkedIn Learning {#takecoursesfromlinkedinlearning}

Learning Manager already supports LinkedIn Learning courses within the learning platform. Now learners can take up such LinkedIn Learning courses within the Learning Manager mobile app. In the device app, search for a course, and then start the course.

For more information, see Take courses from [***LinkedIn Learning***](../learners/feature-summary/ipad-android-tablet-users.md#linkedin).

### Push notification for Admin enrollments {#pushnotificationforadminenrollments}

When the Administrator enrolls learners into trainings, the learners will get notifications regarding the enrollments.

Push notification is now also supported for Announcements.

### Mandatory L1 feedback {#mandatoryl1feedback}

In its latest August 2020 release, Learning Manager allows Administrators to configure L1 feedback such that all questions become mandatory. Same is now supported from learner's perspective in the mobile app.

### User Interface enhancements {#userinterfaceenhancements}

**Footer links**

The Administrator can set up multiple footer links in the Administrator view on web. Learners can now access these links by tapping the Hamburger icon and the Help icon .

By default, there will be two links and the administrator can add another three links (via Admin view on web) that will appear in the app.

**Card view for Learning Objects**

By default, on the My Learning and Catalog sections of the app, the trainings appear as cards instead of lists. This is a change for learners as earlier the default view was "List View".

Learners can however toggle the view between List view and Card view.

+++

+++Update 55- August 2020 release of Learning Manager

Release date: 23 August, 2020

### What's new and changed {#Whatsnewandchanged-3}

This release focuses on the following:

* Reporting enhancements
* Private content folders
* Custom FTP
* Caption support for videos
* Power BI enhancements
* Feedback enhancements
* New and changed APIs
* Data retention policy changes
* ...and many more

For more information, see  [***What's new in the August 2020 release of Adobe Learning Manager***](../whats-new.md).

### Notes about this release {#notes}

* Generating a Learner Transcript (~1 GB) takes less than 15 minutes.
* In earlier versions of Learning Manager, Learner Transcript columns Quiz score and Highest quiz score used to provide the score and maximum score in the format 25/100. To support better readability and analysis, quiz score is now also exported as separate columns - **Quiz_score, Quiz_score_max, Highest_Quiz_score, and Highest_Quiz_score_max**. These allow Admins to make quick calculations and analysis.

### Bugs fixed in this update {#bug-fixes-2}

**Connector**

* A learner is unable to participate in two different meetings at the same time, which are created by two different authors. 
* Clicking on the option Manage connections from the Adobe Connect card navigates to the FTP connection page. 
* A scheduled FTP sync exits with an exception. 
* There are password-related issues when connecting to Exavault. 

**Course**

* You can create a VC module without selecting any conferencing system. As a side effect, the process of creating a course throws Error 500. 
* A learner is unable to download resources even though the learner is enrolled to a course, which has been duplicated. 
* When previewing a course as a learner, an admin or author cannot download resources unless he/she is enrolled to the course.

**Device app**

* In specific enrollment cases, the Donut chart under My Pending Learning displays different values of Learner app from the browser to the Mobile app. 

**Certification**

* The report filter Status does not work as expected when trying to download a dashboard report for certification. 

**Search**

* On the Learner catalog page, when you attempt to search a course by its note, no search results appear. 

**SCORM**

* For some content, the SCORM player displays a blank screen. 
* A Storyline content is identified as a Captivate content, if the published Storyline project contains a web object pointing to the published Captivate output. 
* SCORM content is unable to launch due to incorrect url.

**Custom Role**

* For certain scenarios, a custom admin is unable to see the complete list of Learning Objects. 
* A custom admin is unable to search for a Learning Program or Certification in the dashboard reports. 
* A custom admin is unable to search for a manager in a dashboard.
* Learner Transcripts generated by a custom admin does not contain data of deleted users.
* A custom author or custom admin is unable to duplicate a Learning Program or a course or a certification. 

**Reports**

* The Type column in a Learner Transcript displays the value as course for the courses that are part of a certification, if the learner is un-enrolled from the certification. 

**Skills**

* While adding a skill for a course, there are a few issues when searching for a skill. 

**Gamification**

* If many users are made confidential, then on clicking the confidential learner tab on Edge and Internet Example, the browser behaves unexpectedly. 
* When the frequency of a criteria is changed, the points calculated with older frequency is added to the current calculation. 

**Administrator**

* Learners cannot be marked as attended if the course instance that is mapped to a Learning Program is changed. 

**Email templates**

* For Learning Programs and Certifications, the toggle button in email template is missing. 

**Content Library**

* SCORM content does not get launched as expected due to incorrect url. 

**Learner Transcripts**

* .When generating Learner Transcripts, if you add a deleted learner in the Select Learners input box and then enable the option "Include data of Deleted Learners" in Advanced, the page behaves unexpectedly.

**Search**

* You are unable to search for a course using its notes.

**Excel reports**

* If a user audit trail report takes more than one hour to download due to large data or slow processing, the connection times out, and the report never downloads.
* In a Learner Transcript, the Type column displays as 'Course' instead of 'Certification' for the courses that are part of certification, if the learner is un-enrolled from the certification. 

**Learner app**

* A learner can take an ordered course in an unordered way by accessing courses via an unenroll email or an unenroll notification.
* A learner does not receive session reminder emails as expected.
* A course does not launch as expected if a certain module is missing.

**Announcements**

* If an announcement contains the tag `<a>`, the announcement does not get created as expected.

**Account**

* In some cases, accounts get deactivated even though an account has a valid PO.

**API**

* If you click Manage Connections from the Adobe Connect card, you are redirected to the FTP Connection page.
* For some scenarios, the Connect admin receives incorrect alerts.
* LinkedIn Learning migration produces a few errors.

### Known issues in this update {#known-issues-2}

**Dashboard reports**

* When a Learning Program of certification is deleted, the Active Trainings report displays the courses present inside the Learning Program or certification, even though the Learning Program or certification did not have any enrollments.

+++

+++Update 54 - Mobile app

## Update 54 - Mobile app

Release date: April 16, 2020

To get the latest features, updates, and a better experience, we recommend that you update the device app to the latest version. The update is **mandatory**.

### New and enhanced features {#newandenhancedfeatures}

An Administrator can communicate important information to all users of the app. Announcements can be of type video or image or a simple text message. With this device app release, we now support announcements in the device app. A new announcement will pop up as soon as the app is launched, so that learners don't miss any important communication sent by the Administrators. Learners can read it instantly or read later by visiting the **Announcements** tab.

When there is any announcement or multiple announcements, you can see the announcements in the **Announcements** section.

To see an announcement, tap **Announcements**. The most recent announcement displays on the screen.

To see the next announcement, tap **Swipe Left for Next**.

### Announcements {#announcements}

![](assets/read-later.png)

If you do not want to read the announcement at that moment, you can always opt to read the announcement later. Tap **Read Later** on the announcement and the announcement goes back to the unread state.

### Bugs fixed in this update {#bugsfixedinthisupdate}

* On iOS, a podcast stops playing when the screen is locked. The issue has been fixed and the audio will play even when the screen is locked.
* If you take a course on the device app, the result slide may sometimes appear blank. This issue has been fixed in this update.

+++

+++Update 53 - April 2020 release of Learning Manager

Release date: April 04, 2020

The April 2020 release of Learning Manager focused on the following:

* [Performance enhancements](../whats-new.md#performance)
* [Classroom training](../whats-new.md#classroom)
* [Manager workflows](../whats-new.md#manager)
* [Social learning](../whats-new.md#social)
* [Reporting](../whats-new.md#reporting)
* [Learner experience](../whats-new.md#learner)
* [API-level changes](../whats-new.md#api)

For more information, see [***What's new in April 2020 release of Learning Manager***](../whats-new.md).

+++

+++Update 52 - Mobile app

## Update 52 - Mobile app

Release date: Dec 20, 2019

### New and enhanced features {#Newandenhancedfeatures-1}

#### Company branding logo {#companybrandinglogo}

The App now has the capability to display either the Brand name, Brand logo or both inside the device app depending on the settings set by the Administrator.

#### Deep links {#deeplinks}

Learning Manager now launches the the device app as soon as you click a Learning Manager supported link/URL. In case the app is not installed on the device, the URL opens in the browser.

Here are a few use cases, which will be supported in this update.

* Click a training URL received in an email.
* Default training URLs which appear in the email templates.
* Account URL which appear in the email templates.
* My Learning and Catalog go-URLs.

In addition, any URL with domain *learningmanager.adobe.com* opens in the device app.

#### Upload assets in external certificate as proof of completion {#uploadassetsinexternalcertificateasproofofcompletion}

In this update, a learner can upload assets as proof of completion for an external certificate.

A learner can open an external certificate and upload assets, such as, pdf, text, or image files.

For more information, see  [***Upload assets in external certificate***](../learners/feature-summary/ipad-android-tablet-users.md#externalcert).****

### Issues fixed in this release {#issuesfixedinthisrelease}

* A user is unable to log in to the device app if the email contains special characters.
* While scrolling, the Learning Object icon flickers, when you are in a list view.
* You can now view all push notifications without tapping the down arrow button and view messages one at a time.
* Upon clicking a notification for a post that has been accepted or rejected in curation, a blank page opens in the app. In this update, the board page opens.

+++

+++Update 51

In this update, you can also change the banner image for a Learning Object.

You can also customize the banner in a Social Learning page.

## Update 51

Release date: Dec 17, 2019

### New and enhanced features {#Newandenhancedfeatures-2}

### Learning plans scoped by configurable roles {#learningplansscopedbyconfigurableroles}

You can create Custom Roles for Learning Plans that allow scoping of users and Learning Objects. In other words, Learning Plans can be created with a limited scope that is derived from a custom admin's role scope.

Now, an Admin can define or restrict the scope while granting learning plan management access.

For more information, see [***Learning plans scoped by configurable roles***](../administrators/feature-summary/custom-role.md#scopeconfigure).

### Restrict Active Fields in reports {#restrictactivefieldsinreports}

For Active Fields, we've added two new options- **Reportable** and **Exportable**.

For CSV fields and manually added fields, if an Active Field is marked as **Reportable**, the Active Field becomes searchable in a filter inside a dashboard report.

For more information, see  [***Restrict Active Fields in reports***](../administrators/feature-summary/add-users-user-groups.md#restrictactivefields)***.***

### View description of content module {#viewdescriptionofcontentmodule}

As an author, you can see the description of the modules while adding the module to a course.

While creating a module, add its description. To know more about creating a course, see [***Create a course***](../authors/feature-summary/courses.md).

### Display Course and Session names {#displaycourseandsessionnames}

As an instructor, you can see session and course names in the Attendance view. You can keep track of the sessions that are being modified.

### Announcement for learners {#announcementforlearners}

Learners can now view an announcement in full view instead of a list view. This happens when the learner has one unread announcement. This enhances the learners experience in viewing the announcement.

Adobe Learning Manager now allows you to customize your account to provide a richer experience to your users. Here's a list of elements that can be customized. Contact [Learning Manager support](mailto:learningmanagersupport@adobe.com)to make these changes.

* Training card colors.
* Progress icon
* Mouse pointer image
* Font

For more information, see [***Customize your account***](../administrators/feature-summary/themes.md#customize).

### Upload banner images {#uploadbannerimages}

In this update, you can also change the banner image for a Learning Object.

You can also customize the banner in a Social Learning page.

### API support {#apisupport}

This update of Learning Manager includes API for the following operations:

**Download badge PDF**

This update includes learner API to allow downloading of PDF of a badge.

**Download learner transcript**

This update includes learner API to allow downloading of learner transcripts.

**Download quiz report**

This update includes Admin API to allow downloading of quiz reports.

**Paginated gamification**

Learner API now allows fetching of all learners and gamification points in the learner's scope. This helps in building a gamification leaderboard.

**API:** `GET /users`

**Request:** `GET\\ users?page[offset]=0&page[limit]=10&sort=id&filter=gamification`

**Response:** *The response will contain the users sorted in order of gamification points.*

**Do Not Disturb**

Currently only admins can add users to a Do Not Disturb list via the UI. After this release, a learner will be able to set these permissions for himself through API provided this API is enabled by Admin. Enabling this API for an account requires a backend setting. This API allows the learner to edit the permissions below related to emails.

* Direct emails to learner
* Escalation emails to Learners Managers
* About direct reports
* About skip level reports

### Issues fixed in this release {#Issuesfixedinthisrelease-1}

* Only users belonging to a specific user group must receive announcements that are meant for them. Other users must not receive the announcements.
* The player displays a loading spinner before the content gets displayed.
* User metadata in reports causes a Null Pointer Exception.
* Upon adding an instructor for a default instance for Connect VC course, the message, *"No session for this module"*, displays in the Course Instance page in the Admin app.  

* Exporting a learner transcript leads to unexpected behavior during an FTP transfer.
* The name of an author is incorrectly displayed on Courses in a Learning Program.
* The changes in product terminology of job aids does not reflect as expected.
* The name of a module gets truncated if the name is lengthy and is viewed in mobile portrait mode.
* Unable to create an instance for an older Connect course after updating the default instance with older Connect implementation.
* An instructor receives a calender invite even before the course is published.

+++

+++Update 50

## Update 50

Release date: Oct 24, 2019

### New and enhanced features {#Newandenhancedfeatures-3}

#### Create custom role with multiple catalog scopes {#createcustomrolewithmultiplecatalogscopes}

As an Administrator, you can restrict a custom role based on Catalogs and User Groups. All users belonging to such roles can only see Learning objects from the Catalog in their scope. These users can only perform actions that were defined in the scope of their User Groups.

So far in Learning Manager, a custom role could be scoped on multiple catalogs for a single User Group with full permissions.

In this update of Learning Manager, you can create a custom role to be scoped over multiple catalogs with each catalog being granted different set of permissions. For more information, see [***Custom role scoping over multiple catalogs***](../administrators/feature-summary/custom-role.md#multi-scope).

### Enhancements to search {#enhancementstosearch}

**Learning Plan**

On the Learning Plans page for Administrators and Authors, there is now a search bar, which you can use to search any Learning Plan.

![](assets/search-for-as-learningplan.png)

**Administrator and Author apps**

In this update of Learning Manager, as an Administrator or an Author, in addition to executing a type-ahead search, you can execute free search to search any Learning Object.

### Search filter is preserved {#searchfilterispreserved}

This only applies to a Learner profile.

On the **Catalog** and **My Learning** pages, a learner can apply a filter on the left panel, for example, **Courses** or **Learning Programs**, and then clicks a Course or Catalog item.

![](assets/choose-learning-objects.png)

When the learner comes back to the **Catalog** or **My Learning** pages using the browser back button, the filter remains preserved. The filter that a learner had applied earlier no longer gets reset.

### Control visibility of search filters {#controlvisibilityofsearchfilters}

In earlier versions of Learning Manager, Administrators do not have control over visibility options of a catalog filter, so that learners do not see the skills and tags. In this release of Learning Manager, and Admin can filter types, skills, and tags of a catalog.

In the **Settings** page, for the category Show Filter Panels, when you click **[!UICONTROL Edit]**, you can see the following options. The options determine the filter panels that are visible to learners, so that the learners can fine tune the search results.

For more information, see [***Show filter panels***](../administrators/feature-summary/settings.md#filter-panels).

### Download QR code from Administrator app {#downloadqrcodefromadministratorapp}

In previous updates of Learning Manager, a Custom Administrator faced issues while downloading a QR code. In this update, a Custom Administrator who had access to **All Learners** and permission for **Course Enrollment** can download the QR code.

QR code is still unavailable for custom role users in case they have permissions for limited scope of users.

### Add comments while enrolling learners {#addcommentswhileenrollinglearners}

As an Administrator or a Manager, you can add comments while enrolling learners in a course. You can mention additional information about the cohort of users who are getting enrolled. This data gets exported in course reports.

For more information, see [***Add comments while enrolling learners***](../administrators/feature-summary/courses.md#enroll-comments).

### Support for Adobe Connect persistent meeting room {#supportforadobeconnectpersistentmeetingroom}

In Adobe Connect, customers use existing meeting rooms that they have already created in Connect. All meeting rooms in Connect are persistent and the meeting room templates are carefully set up to provide a unified experience for each persistent room.

In this release of Learning Manager, integration with Adobe Connect is now enhanced to support persistent room as well. It means that you can now create a virtual classroom session using one of the already created room in Adobe Connect.

Learning Manager now also allows learners to enter the connect room for their virtual session using SSO authentication.

For more information, see [***Persistent room support in Adobe Connect***](../integration-admin/feature-summary/connectors.md#persistent).

### Warning before marking attendance if the session duration is zero {#warningbeforemarkingattendanceifthesessiondurationiszero}

An Author or an Administrator can create a session with duration as 0. It is possible when:

* start date and/or end date are empty.
* start time and/or end time are empty.

In this update, a **warning message, which states that the duration of a session is zero**, is shown to the Administrator or Manager or Instructor.

### Warning if a Classroom module is created without adding session data {#warningifaclassroommoduleiscreatedwithoutaddingsessiondata}

If an Author creates a course by adding a Classroom or VC module, the Author can opt to:

* Not add a start/end date and start/end time.
* Add a date, but not a start/end time.
* Add a date and a start time.

In all of the above, when an Administrator or a Manage or an Instructor marks attendance or completion, the values of the session start date and session end date become equal, which means that in a Learner Transcript, the value Learning Time Spent is displayed as zero.

In this update, a **warning message, which states that the session data is incomplete**, is shown to the Author.

### Issues fixed in this release {#Issuesfixedinthisrelease-2}

**Learner app**

* A learner is unable to view a course in a Learning Program, if the course has been created by an external author.
* If an Administrator adds a post to an external board, the curation request goes to an internal SME, who is assigned to that skill.
* A learner is unable to view the Start or Continue button after enrolling for LinkedIn courses.

**Email**

* When there were a large number of users in an email DND list, the **Settings** page would load very slowly. In this update, pagination is added to a list of Email DNDs.
* An instructor receives updates/mails for sessions that he/she is not a part of. In this update, this has been fixed.

**Skills**

* In a Learner Transcript, the type of value of a skill appears incorrectly as text.

**Mobile app**

* In the mobile app, a learner could view and enroll in a Learning Plan instance, which was not the intended behavior. In this update, this has been fixed.

**Custom Roles**

* As a Custom Admin, you are unable to search for a manager in a dashboard report.

**Multiple Attempts**

* In some scenarios, a few course modules are not displayed to learners.

**External Enrollment**

* You are unable to change a user's external profile if seats have been filled up for top profiles.

### Known issues in this release {#knownissuesinthisrelease}

* On the browsers mentioned below, when you mouse over on the left pane, the text appears after a slight delay.

   * Edge 42.17134.1.0
   * Edge 44.17763.1.0
   * Internet Explorer 11.1006
   * Internet Explorer 11.615

* A learner is allowed to enter a Connect meeting room before and after the session.

+++

+++Update 49

## Update 49

Release date: Aug 26, 2019

### New and enhanced features {#Newandenhancedfeatures-4}

**Performance enhancements**

* Importing users in the system is faster compared to previous releases. There is significant improvement when importing large user data.
* For Managers and Administrators, the options in the Report Configuration drop-down list have been modified to load the data on-demand.
* API performance has been improved. Many APIs should now have an improved response time.
* The time taken to generate learner transcript has been improved.
* There is no lag in the pages where Internal and External learners are listed, especially when there are a large number of users.

**Special User Privileges**

An Administrator can grant special privileges to a user group, using which members of the group can participate in all boards. Any restrictions that were set in the Scope Settings section is bypassed by the special user group. For more information, see [***Special User privileges***](../administrators/feature-summary/social-learning-configurations-as-an-admin.md#privilege).

**Changes in User Interface**

* In the **Add Report** dialog, the **Time Span** and **Filters** selectors appear as separate sections, which are in collapsed state, by default. For more information, see [***Create reports***](../administrators/feature-summary/reports.md#report).

* In the **Add Report** dialog, for a user group, you can use type-ahead search to choose a single or multiple user groups. For more information, see [***User group reports***](../administrators/feature-summary/reports.md#user-group-reporting).

**Changes in values in Time columns**

In the Learner Transcripts, in the time columns, the minutes are rounded to the nearest minute and the value of the second is 00. For more information, see [***Time columns***](../administrators/feature-summary/learner-transcripts.md#datetime).

### Issues fixed in this release {#Issuesfixedinthisrelease-3}

**Learner dashboard**

* A Learning Calendar displayed the status **Session Enrolled** even when a Manager was yet to approve the enrollment. Now the correct status **Pending** gets displayed to the learner till the Manager approves the enrollment.

* In a particular case, for a session, the Learning calendar displayed the status **Enrolled** even though the learner has completed a course.

**Manager dashboard**

* Managers were not able to track compliance trainings of their team if the team members are enrolled via Learning Plans.

**Search**

* In the Instructor view, you were unable to search for a learner.

**User Interface**

* For an account with taxonomy changes applied, the changes did not reflect as expected in notifications.

### Known issues in this release {#Knownissuesinthisrelease-1}

* Using the search bar, you cannot search for deleted users in the External Users list. As a work-around,  scroll down to view the list of all users and locate the required user manually.
* If a Special User posts in an external board, the curation request is received by by SMEs in his/her scope.

+++

+++Update 48

## Update 48

Release date: Aug 02, 2019

### New and enhanced features {#Newandenhancedfeatures-5}

**Separation of scope in Social learning for internal and external users**An Administrator can define separate scopes for internal and external learners. There are two new sections for internal and external users. In both sections, you can define the scopes for the learner groups. For internal users, you can define the values of the User Characteristic. For external users, you can define the external profile, within which learners can share the same social space. For more information, see [***Scope settings***](../administrators/feature-summary/social-learning-configurations-as-an-admin.md#scopesettings).  **Social-Restrict creation of social boards**To restrict the creation of boards by all learners and to moderate the boards effectively, an Administrator can grant permissions to create boards to a select group of users. The Administrator can restrict the creation of a board to only a selected group and not every learner who participates in social learning. For more information, see [***Board creation permissions***](../administrators/feature-summary/social-learning-configurations-as-an-admin.md#permission).  **Display only empty Active fields to learners**An Administrator can choose to display the Active fields or hide the fields after the values have been populated. For more information, see [***User display***](../administrators/feature-summary/add-users-user-groups.md#activefields).  **Internal users get deleted upon a specified duration of inactivity**An Administrator can set the duration (in days) within which an internal learner gets deleted if the learner stays inactive for the specified duration. For more information, see ***[Auto delete users](../administrators/feature-summary/settings.md#autodelete)***.  **Customize links on the footer**An Administrator can add and customize links on the footer. The links can also be customized for various locales. The existing method of adding the Contact Admin link on the footer is also available in the **Footer Links** section. For more information, see [***Customize footer links***](../administrators/feature-summary/settings.md#footer). 

### Known issues in this release {#Knownissuesinthisrelease-2}

* Custom Footer links do not appear for Integration Admin roles.

+++

+++Update 47- Mobile app

## Update 47- Mobile app

Release date: July 24, 2019

Android users:

This update also supports necessary changes to adhere to Google's revised recommendations to implement push-notifications. Hence you will no longer receive **notifications** if you are using version 2.7.4 or older.

To receive notifications, we recommend upgrading to version 2.8.

### New and enhanced features {#Newandenhancedfeatures-6}

**Social learning**

Share your expertise with peers in the form of user-generated content posted on topic-based discussion boards. Other learners interested in similar skills can follow these boards to learn and even contribute to the topic, akin to a social media platform. 

Share ideas and meaningful insights in an informal environment. Like, dislike a post, upload content, and comment on posts. For more information, see [***Social learning in the mobile app***](../learners/feature-summary/ipad-android-tablet-users.md#socialmobile).

**Share media in a board**

Share pictures, documents, or audio or videos files to any board, so that other board members can view your post and start an interaction.  For more information, see [***Share post***](../learners/feature-summary/ipad-android-tablet-users.md#socialmobile).

**Submit file for classroom and activity modules**

Submit files as proof of course completion to your instructor. The instructor can then approve or reject your submission, based on the contents of the file. For more information, see [***Submit file for approval***](../learners/feature-summary/ipad-android-tablet-users.md#submitfile).

**Updated platform support**

Learning Manager mobile app is now supported on devices with Android 7 and above, and iOS 10 and above. For more information,, see [***System requirements***](../system-requirements.md).

### Known issues in this release {#Knownissuesinthisrelease-3}

1. On Android, you cannot upload a GIF file in a post, comment, or while replying to a comment.
1. As a moderator of any board, you cannot delete a user's post, comment, or reply. You can however, perform the same from the web app.
1. In the app, you cannot mark a Question type.
1. After you enable Social Learning on the app, relaunch the app to view the tab **Social Learning**. If you do not see Social Learning, kill the app, and then restart the app. The tab Social Learning would be visible.

+++

+++Update 46

### New and enhanced features {#Newandenhancedfeatures-7}

## Update 46

Release date: June 20, 2019

**Auto curation of content**

Social Learning allows content posted by learners to be curated in two ways namely - **No Curation** and **Manual Curation**. In this release, Adobe Learning Manager enhances social learning by providing AI-enabled auto curation capabilities. Once content is posted, the content is analyzed to identify if the content belongs to the skill for which it is posted. Based on the confidence score, the content is either posted live or sent for manual curation. For more information, see *[**Auto-assisted curation**](../administrators/feature-summary/social-learning-configurations-as-an-admin.md#autocuration)**.***

**Map skill with skill domains**

Map skills in your account with the skill domains present in the Learning Manager LMS. This helps in linking your account skills with the skill domains which Learning Manager support for auto-assisted curation. For more information, see [***Map skill with domains***](../administrators/feature-summary/curation-skills.md).

**CSV specifications and sample CSVs**

Updated CSV specifications that you can use to map your existing LMS migration data. Use the latest downloadable csv-specifications and sample-csvs zip files to understand the prescribed format of data to be entered. For more information, see  [***Migration manual***.](../integration-admin/feature-summary/migration-manual.md)

### Issues fixed in this release {#Issuesfixedinthisrelease-4}

**Learning Manager API**

* When an external profile is added using the POST method of the API *externalProfile*, the welcome mail does not get displayed.

**Manager dashboard**

* When a manager selected the option **This quarter**, the enrollment, progression, and completion details of a Learning Object did not get displayed. In this release, these details now display as expected.

**Waitlisted learners**

* In earlier releases of Learning Manager, after a manager enrolled learners, when an instructor wanted to check for waitlisted learners, an error message displayed. In this release, an instructor can browse the list of waitlisted learners without encountering any error message.

**Certification overview**

* After an author created a course and a certification that contained a description and overview content, when a learner landed on the course page, the overview content did not display as expected. The content, however, was visible on the learner preview pages on the Admin and Author apps. In this release, the overview content appears as expected in the Learner app.

**Catalog**

* For each catalog, a learner can view all Learning Objects. In earlier releases, if any catalog did not contain a Learning Object, the catalog still showed up at the beginning of other catalogs. In this release, all catalogs that do not have any Learning Objects appear at the bottom of the catalogs.

+++

+++Update 45

Release date: May 30, 2019

**New and enhanced features**

* Consolidated search across all instances for enrolled learners on the Learning Object's learner section. Search for enrolled users on the Learning Object's Learner section using type-ahead search. For more information, see [***Search for enrolled users***](../administrators/feature-summary/courses.md#searchforusers).
* Complete editing capabilities of learning objects acquired via shared catalog. For more information, see [***Shared catalog control***](../administrators/feature-summary/shared-catalog-full-control.md). To enable the feature, contact Learning Manager support.
* Instructors can now identify the sessions and modules with pending reviews easily. For more information, see [***Pending reviews***](../instructors/feature-summary/learners.md#pending).  

* Skills now support awarding credit values in decimal format. This allows authors to award decimal level credit value to a certain course. For more information, see [***Decimal support***](../administrators/feature-summary/skills-levels.md#decimal).
* Automate the creation of custom roles. For more information, see [***Configure roles via csv files***](../integration-admin/feature-summary/configure-role-csv-files.md).
* Submissions required for external certifications and activity modules are now optional. This allows Managers and Instructors to evaluate without a submission. For more information, see [***Optional submission***](../managers/feature-summary/learning-objects.md#optional).
* Download Learner Transcripts for deleted users. For more information, see [***Learner Transcripts***](../administrators/feature-summary/learner-transcripts.md).
* Support for the following languages:

   * Korean    
   * Turkish
   * Dutch
   * Polish

**Known issues**

* Decimal support in skill credits is only supported for English.
* For Korean, Japanese, and Russian languages, the value of the session time meridian does not display as expected.

**Issues fixed in this release**

* The quiz scores do not get saved for a Learning Program or Certification on the Attendance and Scoring tabs.  
* An Administrator or a Manager is unable to mark an External Certification complete.  
* On the Learner Transcripts dialog box, an Administrator is unable to select a custom date range if the language is set to Portuguese or Spanish.
* An Administrator is unable to create an External Profile when the profile language is French.  
* Active Fields are not visible in the Edit User dialog box if the locale is in any other language except English.

+++

+++Update 44- Mobile app

Release date: April 26, 2019

* **User Interface changes:** On the app, the  ![](assets/hamburger.jpg) and the  ![](assets/search-magnifying-glass-icon.png) options now appear at the top.

![](assets/1.png)

* **Scan QR code to enroll:** QR code capabilities are enhanced. In addition to supporting attendance marking using QR code, now it also supports enrolling to a course, completing a course using QR code.   
  
 To enroll in a course as well as complete the course, you can scan a QR code that your administrator has provided. For more information on scanning QR codes in the web version of Learning Manager, see  [***Scan QR code***](<https://helpx.adobe.com/captivate-Learning>Manager/whats-new.html#QRcodetoenrollcompleteenrollcompleteacourse).

* **Multiple attempts at course:** The Learning Manager app allows the learner to consume courses with multi attempts enabled. For more information on setting up multiple attempts, see  [***Multiple attempts***](<https://helpx.adobe.com/captivate-Learning>Manager/authors/feature-summary/courses.html#Multiattempts).

+++

+++Update 43

## Update 43

Release date: January 28, 2019

* Learning time spent by a learner on a module may be counted multiple times on marking attendance more than once. This issue is fixed. 
* Marking attendance for a Learning Object within a multiday session may display the wrong session starting date for a learner in a Learning Transcript. This issue is fixed. 
* Users may be unable to view a course when the course is added to a completed Learning Program or Certification. This issue is fixed. 
* Enrollment of users may happen incorrectly when they are moved out of a user group. This issue is fixed. 
* Learner and Instructor may not receive an email when the session details are changed in the Instructor app. This issue is fixed. 
* Adobe Connect URL may not work properly when '/' is provided at the end of the url. This issue is fixed. 
* An error message may be displayed on selection of at least one mandatory module for an already published course. This issue is fixed. 
* When a learner has completed a course and latter it is marked mandatory by the author, then the completion of the course may not be marked as completed. This issue is fixed. 
* Checked value of a selected module for a duplicate course may not appear instantly. It is only displayed as a duplicate course when the page is refreshed. This issue is fixed. 
* All modules will be shown as unchecked in edit mode after publishing of a course. The page requires to be refreshed to see the changes. This issue is fixed. 
* Selection of a mandatory module may have been available for an ordered course when it should not have been. This issue is fixed. 
* A mandatory module continues to appear in the dropdown checkbox even after removing it while editing the course. This issue is fixed. 
* Prework and Test out modules might be marked mandatory by default. This issue is fixed.  
* On clicking the L3 feedback link in your email, the feedback modal may not open. This issue is fixed.
* Certification is missing in the dashboard report dropdown although it is visible in the manager app and in the data API list. This issue is fixed.
* Few learning objects could not be retired by the administrator due to lack of permissions although shared catalogs are independent of Learning Manager accounts. This issue is fixed.

+++

+++Update 42

Update 42

Release date: January 11, 2019.

* Insertion of user notifications may fail randomly, resulting in associated emails not getting delivered. This issue is fixed.
* `If a Learner is enrolled in Learning Program 1 and a Course in Learning Program 2, when the Learning Transcript is downloaded for a user group or more than one individual, the Learning Transcript may have missing data. This issue is fixed.`

+++

+++Update 41

Update 41Release date: December 1, 2018.

* Administrators can control the permission given to Learners to view Quiz Scores in Learner Transcripts. This can be enabled/disabled from the Settings page.
* Insertion of user notifications may fail randomly, resulting in associated emails not getting delivered. This issue is fixed.
* Learning Time Spent data may not appear in Learner Transcript and Dashboard Reports. This issue is fixed.
* Information about activities such as enrollment/completion may not be present in the Learner transcript downloaded by a Manager. This is fixed.
* Modules which are a part of a course still in progress may appear as completed in Learner Transcript. This issue is fixed.
* Learner Transcript may not display the downloaded data as per the selected date range. This issue is fixed.
* For users with only Author role assigned, Catalogs may not appear. This issue is fixed.
* When a Custom Role Administrator, downloads the Learner Transcript, the downloaded report will not have information about the LOs which were part of only default catalogs. This issue is fixed.
* There may occur mismatch in the total count of users and the list of users in the User Group page. This is fixed.
* The Learning Program pop-up may not appear even when enabled and users may get redirected to the LO page. This issue is fixed.
* When waitlist is cleared and Learners are enrolled into a Course, the Admin may receive an email notification with their name mentioned instead of the Learner's name being mentioned. This issue is fixed.
* Last Name may not appear on UI for a user added through POST user API. This issue is fixed.

+++

+++Update 40

Update 40

Release date: September 2018.

Performance enhancement

* Users might experience time out issues while downloading large sets of Learner transcript. This issue is fixed.
* Users might experience delay while downloading large set of enrollment report where the Learner's quiz score is recorded. This issue is fixed.
* Downloading large set of quiz score reports might take longer than usual. This is fixed.
* When the Learner completes a learning program, the L1 feedback form might not pop up automatically even when the auto pop up is enabled by the Administrator. This issue is fixed.
* In the downloaded reports of user audit trail and content audit trail, the columns modified by user name and modified by user email might be unrecorded. The report shows System in such instances. This has been updated to be marked Unknown.

+++

+++Update 39

Release date: May 19, 2018.

* This release of Adobe Learning Manager rolls out new features and enhancements. It brings to you the ability to create custom roles, add catalog labels, capacity to purge users, manage tags, rename Learning Objects, Slack integration, new connector integrations, support to xAPI, and much more. For more information about the new features and enhancements, see  [New feature's summary](../whats-new.md#main-pars_text).

* Learning Manager is compliant with GDPR. For more information, see [Learning Manager compliance to GDPR](/help/migrated/kb/prime-gdpr.md).

## Known Issue {#knownissue}

* The hyperlink to the number of courses and certifications inside tags modal includes shadow courses and recurred certifications. When you click on the hyperlink, these courses and certifications may not be listed causing a discrepancy in numbers.

+++

+++Update 38

* Learners in Pending state or in state of awaiting acceptance were being marked complete. This issue is fixed.
* When an instructor searches and selects all learners, the number of learners selected and the count shown have disparities. This issue is fixed.
* When you search and select any learner and mark attendance, Learning Manager could mark attendance for all learners. This is fixed.
* Learning Manager would display time in emails in 24 hours format. This has been fixed. Time is now displayed in 12 hours format.
* When a Manager nominates a Learner for a course using the nominate button available in the notifications page, the nominate modal would not load. This has been fixed.
* In exported excel reports, the deadline date, which should be enrollment date + days to complete value set in auto instance of the LOs, would be displayed wrong. This issue is fixed.

* User search results are displayed empty when no users are present in the group that is searched. This is now fixed.
* Managers could not be deleted even if there are no direct reports. This issue is fixed. Managers can now be deleted.
* Reset module progress functionality might stop working. This is now fixed.
* Deleted certification could shows up in the widget for Learners. This issue is fixed.
* Issue with calculation of course effectiveness has been resolved.

* Issue for integrating new connect account has been fixed.
* L1 Feedback auto pop might not appear if enabled at non-default instances. Issue has been fixed.
* Instructor might not be able to mark attendance for all the users at one go for sessions which are part of Learning Program/Certification. This is fixed.

+++

+++Update 37

Release date: March 25, 2018

The March 2018 version of Adobe Learning Manager rolls out exciting new features and enhancements. It brings to you, generation of user audit trail reports and login/access reports, gives Learners the capacity to choose course instances, enhancements to classrooms and virtual classrooms, and much more. This release also brings to you bug fixes and performance enhancements.

To read all that is new in this release, see  [What's New in Adobe Learning Manager](../whats-new.md).

### Known Issue {#KnownIssue-1}

**Issue:** Accessing a few specific Learning Objects using Internet Explorer v11.1478.10586.0 might lead Learning Manager to crash.

**Workaround:** Update your Internet Explorer 11 browser to the latest version by reaching out to the IT team in your organization.

+++

+++Update 36

Release date: January 22, 2018.

### Issues Fixed {#issuesfixed}

* Making any change in the Email template setting might lead to the disappearance of Email Banner. This issue is fixed.
* Learners might be unable to add/launch private job aids. This is fixed.
* Custom user groups present in an account might not be listed under the user group field in add/edit report modal. This issue is fixed.
* If a badge image has space in its name, it might not appear to the learner in the home page.
* When an enrolled user is deleted from a course, the course report and quiz report might not get generated for that particular course. This issue is fixed.
* If the admin changes the number of nominated seats for a manager, the count might appear wrong in the nomination request when opened from different places. This issue is fixed.
* When converting an external user to an internal user, the user might not get added to the All Internal Learners group. This issue is fixed.
* If you search for an individual learner, select them, and perform the unenroll action, it might result in unenrolling all the learners in that group instead of only the selected one. This issue is fixed.
* As an administrator, you might be unable to use the check-box to select a learner inside certifications. This issue is fixed.
* Creation and updating of user groups with more than 600 individual users might fail. This issue is fixed. You can now create user groups with more than 600 individual users.
* If you delete a custom user group which is part of another custom user group, intersection rule might roll over the user number to the higher group. This issue is fixed.
* When the default catalog is disabled, and a new catalog is created, and if the manager has access to this newly created catalog, he might not be able to search any course under that catalog. This issue is fixed.
* Mobile application users might not receive L1 feedback as push notifications. This has been fixed.

+++

+++Update 35

Release date: January 7, 2018.

This release of Learning Manager brings to you performance optimizations aimed to improve scalability, performance, and security.

### Enhancements {#enhancements}

* Experience elastic search while searching for courses, and users across all applications. This includes Courses, User, and User Group search.
* Support the use of Box connector to integrate Learning Manager with external systems to automate data synchronization. For more information, see [Box connector](../integration-admin/feature-summary/connectors.md#main-pars_header_302653946).
* Updated CSV specifications that you can use to map your existing LMS migration data. Use the latest downloadable csv-specifications and sample-csvs zip files to understand the prescribed format of data to be entered. For more information, see [Migration manual.](../integration-admin/feature-summary/migration-manual.md)

+++

+++Update 34

### Issues Fixed {#IssuesFixed-1}

* Announcements might fail when the number of users are high. This issue is resolved.
* Accessing Learning Manager account using the subdomain URL in EU could redirect users to a different page. This issue is resolved.
* When a LP is ordered, a learner should be able to consume the LP only in the specified order. Learners were able to consume courses which were not listed first using the course hyperlinks. This issue is fixed. Learners can no longer start a course until he finishes the previous one.  

* Unsupported browser version error message might not show up in unsupported versions of Internet Explorer ( IE 7, IE 8, IE 9, and IE 10) and Safari ( version 7, 8, and 9). This issue is fixed.

 

+++

+++Update 33

Release date: October 5, 2017.

### Issues Fixed {#IssuesFixed-2}

* Changes to a shared course might not get propagated to the shared account if the author in origin account auto saves the course. This issue is fixed.
* Sometimes, for specific Learning Manager projects, content used to freeze in fluidic player. This issue is fixed.  

* The calendar listing under the Learning Calendar widget in the Learner Dashboard might appear in a random order. This issue is fixed. The listing will now appear in an orderly manner.
* When marking attendance using select-all option, learners get marked as attended across the learning objects for the same session. This issue is fixed.
* In certain high-resolution screens, the email received from Learning Manager had alignment and truncation issues for the banner image and text. This has been fixed.   
* Certain emails from Learning Manager such as emails without any notification data were not getting triggered to the users. Example- Email received on creating and enabling external profile and Email received on configuring connect account. This issue has been fixed.
* When you create a LP, set a reminder, enroll users, and then change the deadline of the instance, the changed deadline might not be reflected for the reminders. This is fixed. The reminders would now carry the changed deadline.
* In certain cases, for content created using Adobe Presenter, the total and the elapsed time in fluidic player was not in sync with the content. This issue is fixed.
* In certain cases, after adding a learning program to a catalog, the option to add might still be enabled. This issue has been fixed.
* Opening Learning Manager in a device browser displays an option to experience Learning Manager on device app. Clicking yes should launch the Play Store (Android) if app is not installed, or launch the app if installed (in Android and iOS). This workflow had issues and have been fixed. 

+++

+++Update 32

Release date: August 17, 2017

### Issues Fixed {#IssuesFixed-3}

**Course with multiple module versions getting rolled back to the previous version on delete action.**

When a course has multiple module version entries for specific modules, on deleting the module, it would roll-back to the previous version and not get deleted completely. This issue has been fixed.

**Changes to a shared course would not get propagated if it is auto saved by moving across tabs.**

Changes to a shared course might not get propagated to tenant account if the author in parent account autosaves the course by moving to next tab. This issue has been fixed.

**Users were unable to change deadline of instances for an activity only course.**

Users were unable to change deadline of an instance in activity courses as it would revert to the previous deadline date. This issue has been fixed.

**Inability to use a unique id once removed from a learning object.**

When you assign a unique id to a course and remove it, you would be unable to use the id again. This issue has been fixed.

**A learning program which is already enrolled as part of one learning plan event might appear again as part of another event in learner app.**

If a learning program is already enrolled as part of one learning plan event, it might appear again as part of another event in learner app. This issue has been fixed.

**Learner getting reminder emails with deadline date/ session time specified incorrectly.**

Learners would often get emails with incorrect deadline reminders/ session time reminders due to timezone corrections. This issue has been fixed.

**Gamification leaderboard timeline shows external learners if he gets converted from an external learner to an internal one.**

An internal learner's gamification leaderboard timeline might show external learner when he is converted from external to an internal learner. This issue has been fixed.

**UUID field for a learner is shown in editable format while creating a single and CSV users in a UUID enabled account.**

UUID field was displayed to the learner while completing his profile even when the administrator has provided the UUID for single and CSV users. This issue is fixed.

**Learning time spent is not getting captured in reports in certain cases.**

Learning time spent data was not showing up in reports for a learner,

* If his/her attendance is auto-marked by the system for connect modules.
* When a QR code is scanned for CR and VC modules using Learning Manager device application.

**This release of Learning Manager also introduced enhancements and bug fixes related to device player.**

* Issues regarding completion of activity modules. This has been fixed.
* When the learner is playing a video in portrait mode, +10 and -10 buttons might not work. This has been fixed  
* Improved the playback experience of certain sample projects when played on an android device (mobile and tab) which would earlier flicker.  
* When you add a new note, the notes panel should close and the playback should resume in the player. This might not happen in certain cases. This has been fixed.
* When you open the notes added to a module, the close button might not be displayed. This issue has been fixed.
* When learner opens notes panel using Note marker, he might have to click the Notes icon twice to close the panel.  
* When clicked on the table of content, it might not collapse automatically and needs manual closure to view the content. This issue is fixed.
* A course which has a module with multiple languages might not display all the available languages as the scroll bar might not scale accordingly. This has been fixed.  
* When you open a third party activity course module in a player in landscape mode, the text orientation might not adjust making it difficult to scroll. This has been fixed.
* Increased the tap area for the close button of the player in both online and offline mode.
* The TOC does not automatically close when the orientation of the device is changed. This has been fixed.
* Some minor issues in relation to user interface such as alignment of play button, radio button and other settings in landscape and portrait mode have been fixed.

* The issue of seek bar being displayed even when the show playback control option is unchecked in content has been fixed.
* The close button of the player was not visible for certain projects when the device orientation is changed. This has been fixed.  
* The issue in regard to TOC section of module getting truncated in landscape mode on device player has been fixed. In certain cases, TOC was not visible for content in device player. This has also been corrected.

**This release of Learning Manager also introduced enhancements and fixes listed below for the Device application**.

* Push notification related to completion deadlines might not get delivered on certain devices. This issue has been resolved.
* We now support learning object lifecycle on device application as well. Learners can now access the latest content in learning objects if they have been edited by the author.  

* Application orientation issues (including default orientation- portrait mode) of the Learning Manager application has been fixed.
* There might not be an option to update the content when user transitions from offline to online mode.
* Module ordering is now supported for courses in device application in online mode.

* If a user has not downloaded any Job Aids, then clicking on My Job Aids tab in offline mode might crash the app in IOS and show a message saying error loading data in android. This has been resolved.
* Learning Manager application closes or throws an error if we access the course immediately after switching off the internet even when it is a downloaded course. This issue is now fixed.  
* Sometimes when you scan the QR code, it displays a captured image of the previous QR code scan. This has been corrected.
* Trying to remove a Job Aid which is already added from my Job Aids tab on certain occasions would show an error message. This issue has been fixed.

+++

+++Update 31

Release date: July 16, 2017

### Enhancements {#Enhancements-1}

**Gamification**

This release enhances the scope of gamification. External Users can now take part in Gamification. As an administrator, you can define the scope of gamification by changing the scope settings. You can selectively enable gamification among similar profile users, groups or location.

**External user enhancements**

With this enhancement, you can set a time-range after which users get automatically deleted after the period of inactivity. The enhancement also allows admin to re-add user as an external learner for both automatically deleted and manually deleted learners.

**Job Aid, announcements, and unenrollment report**

Job Aids are training content that a Learner can access without having to enroll for any specific learning object like a Course or Learning Program. With this enhancement, administrators can extract and download Job Aids report. As an administrator, you can also generate a report of all the announcements that have been sent by you. Administrators and managers can also extract a report of the learners who have been unenrolled.

**Learning Manager connectors**

You can now export user skills to an FTP location to integrate with any third party system using the Data Export option. You can specify the Connection Name for your integration and choose if you want to import internal users, or export user skills by configuring them or fetching it on demand.

**Copy course instances**

You can now copy the instance URL by clicking the drop-down arrow at the upper-right corner of an instance.

### Issues Fixed {#IssuesFixed-4}

**Users not getting calendar invite when being enrolled into learning program**

Users were sometimes not getting calendar invite (.ics) file invite when they enroll in Learning Programs, Certificates carrying Classroom, and Connect sessions. This issue has been fixed. Users will now get .ics files as attachments which mention the session details along with the enrollment email.

**Activity description even if provided in multiple languages, would still appear in English**

A user whose content language preference is set to non-English would still be able to see Activity module description in English. This issue has been fixed.

+++

+++Update 30

Release date: June 30, 2017

### Enhancements {#Enhancements-2}

**Multiple learning objects support in learning plan**

As an administrator or author, you can now assign multiple learning objects to a Learning Plan. If any of the learning object's instance retires or expires, the whole learning plan gets disabled automatically. With this enhancement, you can also search **[!UICONTROL Completed Learning]** and **[!UICONTROL Assign Learning]** fields using learning objects unique IDs.

**Accessibility**

With this update Learning Manager Learner Experience now supports section 508 Standard of accessibility. Learning Manager is also compatible with the latest version of **[!UICONTROL JAWS]**. This feature is only supported for the Learner application. Use Internet Explorer 11, Windows Chrome, or macOS Safari to access this feature.

### Issues Fixed {#IssuesFixed-5}

**Incorrect information in certain time zones**

Deadline reminders mentioned the number of remaining days incorrectly for learners in certain time zones. This issue has been fixed.

**Learning Program issues in the case of expired Program instance**

Launching of modules from Learning Program had issues if Program instance is expired. This led to the expansion of module not working and learners unable to launch the player and visit the content. This issue has been fixed.

**Translation issues in Learner application**

Learning Manager users experienced certain translation issues in Learner app. These issues have been fixed.

**Issues regarding subscription to a skill**

In certain cases, Learners were unable to subscribe to a new skill. This issue has been fixed.

+++

+++Update 29

Release date: April 9, 2017

### New features {#newfeatures}

For a list of new features and enhancements in Learning Manager April release, refer to [What's New.](../whats-new.md)

**Widget-based Learner App**

Use widgets on the home page to manage your courses, skills, and achievements. Use the search bar to perform a search in your entire LMS that spans all the learning objects, catalogs, skills, notes, and discussions

For detailed information on the new home page, see  [Learner home page in Learning Manager](../learners/feature-summary/getting-started-learner.md).

**Administrator settings for Learner Dashboard**

As an administrator, you can control the learner's home page by enabling and disabling different widgets.

**Learning Manager mobile app for learners**

The new Learning Manager mobile app lets learners use the app to enroll and undertake courses. The app can also be used to manage dashboards.

To know more about using Learning Manager in mobiles, see  [Learning Manager leaner app for mobiles](../learners/feature-summary/ipad-android-tablet-users.md#main-pars_header_1451175907).

**Marking attendance using QR code**

Use QR Scan Code to mark your attendance for classroom sessions using your mobile devices.

**Instructor role**

Learning Manager now introduces instructors for modules. Instructors can manage module sessions including the time, venue, and seat limit for the modules that are assigned to them.

To view detailed information on Instructors, see  [Instructors in Learning Manager](../instructors/feature-summary/getting-started.md#main-pars_header).

**Peer account**

If you are an administrator, you can create peer accounts with whom you can share your purchased seats.

To know how to create and manage peer accounts, see  [Peer accounts](../administrators/feature-summary/peer-account.md#main-pars_text).

**Course equivalency offerings**

Use **[!UICONTROL Add New Language]** option when you add a module or a course to make it available in multiple  language and format.

**Learner Transcript**

Learning Manager offers managers and administrators the ability to download transcript data to track the learning history of individuals as well as teams.

**Integration with other content providers**

Learning Manager has introduced three new connectors in this release, so that learners can access and consume courses from the following content providers: Lynda.com, getAbstract, and Harvard ManageMentor.

To know how to configure and use each of these connectors, see  [Connectors](../integration-admin/feature-summary/connectors.md#main-pars_header).

**Unique ID for Learning Objects**

While creating Learning Objects, now authors and administrators can specify unique IDs for the courses, learning programs, or certifications. If you want to enable unique ID when creating a learning object, click Settings > General. Select the Enable check box next to the Unique Learning Object Ids option.

**Discussion board for learners**

Use the Discussion board in courses to interact with your peers and instructors. As a learner you can view all the posts for courses. However, you can also delete only those posts that you entered. For more information about Discussion board, see  [Viewing and participating in discussions](../learners/feature-summary/courses.md#main-pars_header_1772461149).

### Enhancements {#Enhancements-3}

**X out of Y courses**

The completion criteria for learning objects such as courses, certifications, and learning plans can be set such that learners need to complete only X out of Y modules or courses. Authors can similarly set the completion criteria for certifications and learning plans as well. 

For more information of this feature, see  [Course completion criteria](../learners/feature-summary/courses.md#main-pars_image_1164377098).

**Course Moderation**

Administrators now receive notifications whenever an author edits or updates modules and republishes a course. 

**Administrator settings for resetting modules**

Now, administrators have the ability to configure the Reset Module option to allow learners to reset a failed or an incomplete course.

**Report Catalog**

When you create reports in Learning Manager, you can generate reports and graphs for catalogs now.

**Learning Plan enhancements**

Administrators can now create Learning Plans of the types On Date. With the On Date Learning Plan, an administrator can specify the event name, choose the date for the event, and select the user group for whom the event belongs to. 

**Course specific enrollment messages**

Administrators can now configure and send course specific enrollment messages via email, to learners.

**Sticky announcements**

As an administrator, you can now enable Sticky feature for announcements.

**Support for URL in announcements**

You can add URLs as announcements by adding the URL in HTML. 

**Add New Delivery Types (Courses)**

Adobe Learning Manager now lets you add delivery types for your courses.

**Author role enhancements**

Earlier authors could only create modules and courses. Now, authors also have the ability to create certifications and learning programs for learners.

**Author role to external users**

As an administrator, you can now assign author roles to external users.

**Multiple authors**

Learning Manager now lets multiple authors to simultaneously edit the same content group.

**Adobe Connect enhancements**

You can now configure a single Adobe Connect URL with multiple Learning Manager accounts.

**Support for new languages**

Support for Japanese, Brazilian Portuguese, Italian is available from this release.

 

+++

+++Update 28

Release date: January 30, 2017

### Issues Fixed {#IssuesFixed-6}

#### Account Settings {#accountsettings}

As an Administrator, when you click External Profile and chose Actions > Change Profile, all the profiles were not listed. This issue is now fixed.

#### Course life cycle {#courselifecycle}

* When you launch a course that was created using the Biz library e-learning tool, the "Resume" action did not work. This issue is fixed.
* Some users were unable to launch a course in iPad using the course link in Announcements. This is now fixed.
* When you click the Continue button in Learner's Program, you could not access the courses in order. This is now fixed.
* The Course Overview label for courses in Learner's Program was earlier misplaced. This issue is now fixed.

#### Learner app {#learnerapp}

* In your device, if you open an announcement image in full screen mode, you were not able to go back to the application. This is fixed now.
* Tincan content that was uploaded from Captivate did not play in online mode in Android and iOS operating systems. This issue is fixed.

#### Course reports {#coursereports}

Incorrect learner transcript reports are generated in Learning Manager when the course has multiple versions of modules. This is now fixed.

#### API layer {#apilayer}

You encounter an error whenever you tried to fetch the module version information using AP/courses/{coursesid}. This has now been fixed.

+++

+++Update 27

Release date: December 23, 2016.

### New features {#Newfeatures-1}

Adobe enables enterprises to migrate their organization's training data and training content from their existing Learning Management Systems (LMS) to the Learning Manager LMS application. 

Learning Manager provides the necessary tools and templates so that your organization's integration Administrator can set up and perform the migration tasks. 

For more information on Migration feature, refer to  [Migration manual Help](../integration-admin/feature-summary/migration-manual.md)

### Enhancements {#Enhancements-4}

**User registration**

As an administrator, you can now add specific domain names while adding external users. When learners register to the account, they can enter email addresses only from those domain names.

You can also send email verification links to users' email when users register to the account. For more information on this enhancement, see  [Add users/user groups](../administrators/feature-summary/add-users-user-groups.md#main-pars_header_1217981931).

**Fluidic Player**

Fluidic Player now allows you to modify the playback speed. You can choose from five speed variants that are available. Fluidic Player also allows you to control the volume settings when you take a course.

As a learner, you can also skip forward or backward by 10 seconds using the new icons on either side of the play button in the Fluidic Player. For more information on these enhancements, see  [Fluidic Player](../learners/feature-summary/fluidic-player.md).

The Fluidic Player enhancements are applicable for video only.

+++

+++Update 26

Release date: December 06, 2016.

### Enhancement {#enhancement}

As part of this update, Learning Manager provides an end point [PATCH/users/{id}](<https://learningmanager.adobe.com/docs/Learning>Managerapi/v1/#!/user/patch_users_id) to update users in an application. You can access this API end point in Admin role. Using****this end point you can update the following information of Learning Manager users:

* Name
* Email
* Profile
* Role
* Manager

### Issue fixed {#issuefixed}

**Fluidic player**

When you consume a course that was developed in Captivate using  `code cpQuizInfoStudentName` variable, the student name was not appearing as expected. This issue is fixed. 

+++

+++Update 25

Release date: November 17, 2016.

### Enhancements {#Enhancements-5}

**Shared Catalogs**

Shared Catalog feature enables Administrators across accounts to share or acquire Catalogs with learning objects. As an extension to this shared catalog feature we support propagation of the updates to learning objects such as Badges, Skills, Modules, Courses, Learning Programs, Certifications & Job Aids.

For more information on this feature, refer to  [Shared catalogs Help](../administrators/feature-summary/catalogs.md#propagation)

**L1 and L3 feedback**

* L1 feedback dialog appears as soon as a learner completes course consumption. Also, the learner receives a notification about L1 feedback completion. 
* An option to add descriptive questions has been provided in L1 and L3 feedback feature. Administrators can add these descriptive questions to learners. This provision is in addition to the default set of questions provided by Learning Manager. You can add two descriptive questions for L1 feedback and one descriptive question for L3 feedback.   
  For more information on this feature, refer to [L1 & L3 feedback descriptive questions Help](../administrators/feature-summary/courses.md#descriptive)

**Export users**

* Based on the request of some large enterprise users, a new option to download the list of all users in Learning Manager account is provided. In Administrator login, click **[!UICONTROL Users]** on the left pane and click **[!UICONTROL Export user data]** to download the list of users as an excel sheet. 

### Issues fixed {#Issuesfixed-1}

**Course enrollments**

* In some instances, when an Administrator tries to view course enrollments using learners tab, some of the enrolled learners names did not appear. This issue is fixed. 

**Add courses**

* While adding a skill to the course, if an author adds a skill which has a blank space at the end of the name then an error used to occur and the course was not saved. This issue is fixed. 

**Consume courses**

* In an ordered course, some learners were unable to move from one module to another while consuming a course as the modules were not being marked as completed. This issue is fixed. 
* In an ordered course, learners were unable to navigate among the modules within TOC during normal and revisit modes. This issue is fixed. 

**Fluidic player**

* In some instances, when a user uploads a module content with hidden frames/slides, the Table of Contents on the left pane used to display the hidden frames/slides. This issue is fixed. 

**Reports**

* The time taken to load reports is higher in the latest update of Learning Manager. This issue is fixed. 

+++

+++Update 24

Release date: October 12, 2016.

### Enhancements {#Enhancements-6}

**Course reports**

* For Universal Unique Identifier (UUID) enabled Learning Manager accounts, UUID appears in course enrollment report, learner transcripts, and Quiz score reports. 

### Issues fixed {#Issuesfixed-2}

**Job Aids**

* In some instances, when a learner tries to navigate from Learning>Job Aids to Learning>Courses tab, courses were not loaded as expected in Learning>Courses tab. This issue is fixed. 

**Add users**

* In some instances, when a single user is added to Learning Manager application, an email notification is not received by the user. This issue is fixed.
* Administrators were unable to download the CSV file if the CSV upload process fails. This issue is fixed, Administrators can download the latest CSV even if the CSV upload process fails. 
* If a CSV is imported after modifying self-registered user info with mixed case letters, then the self-registered user details were not displayed in Administrator user interface. This issue is fixed. 

**Course reports**

* In some instances, quiz scores did not appear for courses even though the scores appear in learner transcripts. This issue is fixed. 

**Enrollment reports**

* In some instances, the learner's enrollment Excel reports were not being downloaded for the learning objects. This issue used to occur whenever non-ASCII or special characters were used in learning objects name. This issue is fixed. 

**User login**

* While setting up a password during registration or during reset, the error message did not appear even though the entered password is not adhering to the password policy. This issue is fixed. 

**Course effectiveness**

* In learner role, course effectiveness was displayed as one of the **Sort By** filter options even when an Administrator disabled the course effectiveness for learners. This issue is fixed. 

**Certifications**

* When an Administrator removes learners from a recurring certification, an error used to occur and the Learning Manager application used to hang up. This issue is fixed. 

**Reports**

* When an Administrator tries to generate a certification report with **Till date**as an option, the inactive users were not displayed in the report. This issue is fixed. 
* When an Administrator clicks Course Reports link in Reports>MyReports tab, a pop-up dialog used to appear without a Close button. This issue is fixed. 

**Fluidic player**

* While previewing courses as an Administrator or an Author, when a user chooses the Full-Screen mode in Fluidic player, the screen appears blank. This issue is fixed. 

**Multi-language support**

* Question mark characters used to appear instead of Chinese characters in response to API calls by users. This issue is fixed. 

**API layer**

* An error used to occur whenever a user tries to fetch default catalog id using get/catalog/catalog Id API. A default catalog id can be similar to '970_default'. This issue is fixed. 

**User interface**

* Some minor typos are fixed in the Learning Manager application user interface for learner role.

+++

+++Update 23

Release date: September 19, 2016.

### Issues fixed {#Issuesfixed-3}

**Learner transcripts**

* In some instances, if there are more than twenty inactive/deleted learners in an account, the inactive learners above twenty were not displayed in the search drop-down list of learner transcript dialog. This issue is fixed. 
* If an external user account is expired, then its learners were not listed in the generated learner transcript. This issue is fixed. 

**Catalogs**

* Some of the customers were facing an issue with display of user groups in a Catalog. Even if there are more than twenty user groups in a catalog, only 20 user groups were displayed. We have fixed this issue by displaying 200 user groups in a page. 

+++

+++Update 22

Release date: September 13, 2016.

In this update release, we have fixed some of the product engineering backend issues to enhance customer experience. 

### Issues fixed {#Issuesfixed-4}

* There was an issue with module data export in learner transcripts resulting in improper export data. This issue is fixed.
* If a user uses an email id extension with more than four characters, it was not supported. For example, if an email id is <abcd@company.world> it was not supported as the extension world was more than four characters. We have fixed it to support the extension with more than four characters. 

+++

+++Update 21

Release date: September 01, 2016.

### Enhancements {#Enhancements-7}

**Course effectiveness**

Now, Administrators can customize the course or learning program effectiveness feature to hide the effectiveness score from learners view. 

**Add external users**

Learning Manager has enhanced the maximum limit of external self registrations to 5 digits. 

**Reports**

All the downloaded reports and learners lists for all learning objects display deleted users now with clear demarcation for deleted users. 

### Issues fixed {#Issuesfixed-5}

**Course life cycle**

In some instances, when an author edits a shared course to update a modified module information, a warning message used to appear that user cannot edit as previous changes are being processed. This issue is fixed. 

**Multi-language support**

In some of the features of Learning Manager user interface, the messages were not being translated and displayed to the user in appropriate locale sentences. This issue is fixed. 

**Add users**

* When a deleted user is added back as a single user, the user was not added to the 'all users' user group by default. This issue is fixed. 
* A limited number of profiles used to appear in external enrollment and self enrollment profile change dialogs. Pagination is implemented now. 

**Job aids**

Whenever a learner accesses Job Aids tab in the learner account, an error message used to appear as 'This job aid does not exist in your list anymore' before loading the content. This issue is fixed.  

**Catalogs**

During Catalog creation, while adding courses as content to the catalog, the Sort By filter was not working as expected. This issue is fixed. 

**Settings**

In account settings, when an Administrator uses a sub domain which was already used by some other account, an error message was not appearing to the Administrator. This issue is fixed. 

**API Layer**

* When include manager is used while fetching users, complete hierarchy of managers was fetched instead of the user's immediate manager. This issue is fixed. 
* When a user with learner scope authorization permission tries to add users, a generic error message used to appear. This issue is fixed and an Unauthorized access message appears to the learner now. 
* When a user tries to delete a last existing user in a user group, a 204 error message used to appear to the user. This issue is fixed now by displaying a relevant error message to the user stating that the group should have at least one user. 
* The space, if exists at the beginning of the name, was trimmed while displaying the user name in GET/users API. This is fixed now. 
* The draft courses were also returned in response when Administrator tries to fetch all courses.These draft courses are supposed to be private to the author. This issue is fixed, draft courses do not return now.

**Adobe Connect integration**

* In some instances of Adobe Connect based virtual classroom sessions, the attendance was not being marked automatically after the session. This issue used to occur only when a login id was used by instructor to login instead of email id. It is fixed now. 
* In some instances, instructor name used to appear multiple times in the Instructor drop-down list during Adobe Connect based Virtual classroom module creation. This issue is fixed. 

+++

+++Update 20

Release date: August 22, 2016. 

### Enhancements {#Enhancements-8}

**API Layer**

As part of this update, we have added the following new APIs to meet some of our customer requirements:

1. POST Users
1. DELETE Users
1. GET userGroups
1. GET userGroups /{id}
1. DELETE userGroups /{id}/Users
1. POST userGroups /{id}/Users
1. GET /users/userId/userGroups

We have also enhanced the existing User model with the following additions: 

1. Manager model is added as relationship to User model
1. userGroupId is added as a new parameter to GetUsers

**Learner Transcript**

When a user generates Learner Transcript for a learner, the pop-up dialog used to appear for a very short time and disappear without prompting for user action. We have enhanced the user experience by providing a pop-up that pauses and prompts the user to click OK. 

**Adobe Connect integration**

Login id is provided as a new optional field in Adobe Connect integration settings for the users who do not use their email id to log in. 

### Issues fixed {#Issuesfixed-6}

**Course reports**

* When a course module consists of open type questions or only survey questions, a blank quiz score report used to appear when it was exported. This issue is fixed. 
* In some instances, quiz score report was not getting downloaded when a user uses the Export quiz score link. This issue is fixed. 

**Create courses**

The course Settings page in Author role was not appearing whenever a skill associated with that course is retired by the Administrator. This issue is fixed. 

**Smart enroller**

The search field was not supporting special characters as input, and as a result, the search results were not displayed. This issue is fixed. 

+++

+++Update 19

Release date: August 11, 2016. 

### Enhancements {#Enhancements-9}

**Smart enroller**

The search engine performance has been enhanced to provide more accurate search results to users. 

**Adobe Connect integration**

The integration request verification/authentication process has been enhanced in Learning Manager application. 

### Issues fixed {#Issuesfixed-7}

**Add users**

* When there are large number of Learning Manager users, there was a delay in loading users and user groups page. This issue is fixed. 
* After Administrator completes uploading CSV file with new users, the list of users in the page was not updated with new users until the page was refreshed. This issue is fixed. 
* Sometimes, after importing users using CSV, the user id value in the page used to be replaced with email id. This issue is fixed. 

**Create user groups**

In some instances, user count was not displayed in default user groups page of Learning Manager. This issue is fixed.

**Learner transcript**

Attribute values of active fields were displayed incorrectly in learner transcripts for Certifications. This issue is fixed. 

**Multi-account sharing**

In a scenario where an account administrator shared a course catalog with the receiver and updated test out or pre-work module later, pre-work or test out module content used to play in content module for the receiver. This issue is fixed. 

**Themes and branding**

When an Administrator changes a theme to the application using Live preview widget and switches his/her role, the Live preview widget was not functioning as expected in a new role. This issue is fixed. 

**Multi-language support**

When an Administrator changes the Locale of the application to Chinese Simplified or Spanish, some of the menu content in the left pane, online instructions and pop-up messages were not displayed in meaningful words or sentences. This issue is fixed. 

**Fluidic player**

* When an author creates a course with AICC or Tin Can content and tries to preview the content, the content was not played. This issue is fixed. 
* Module preview was not functioning while creating a course or while editing the course by an author. This issue is fixed. 

**Catalogs**

When a learner tries to access catalogs/learning programs URL directly in the browser, it used to get redirected to courses. This issue is fixed. 

**Salesforce integration**

* After establishing a Salesforce or FTP connection, in Map Attributes page the drop-down arrows for the fields were not displayed in IE, Edge and Safari browsers. Also, some of the pop-up messages were not displayed in the workflows. This issue is fixed. 
* In some cases, when an Administrator tries to sync the .csv imported data in FTP connector, the sync used to fail with replicated entries. This issue is fixed. 

**API Layer**

* When an Administrator authorizes the external learner using OAuth authentication, sometimes the external learners were not able to log in to the application. This issue is fixed.
* Sometimes, when there is an API call for learner Job Aids, unauthorized access error used to display. This issue is fixed. 

**Settings**

In data sources page, when an auto schedule time is set and saved, sometimes it reverts to the old state. This issue is fixed. 

**User group reporting**

User group values in filter were not being populated when report type is chosen as Custom. This issue is fixed. 

**Adobe Connect integration**

Inappropriate heading title used to appear for Adobe Connect integration after completing the connection successfully. The page heading text is corrected. 

**Reports**

Sometimes, even if 'show data for current values' option is selected, the latest data was not shown in the reports. This issue is fixed.

+++

+++Update 18

Release date: July 31, 2016. 

## New features and enhancements {#newfeaturesandenhancements}

For a list of new features and enhancements in Learning Manager July release, refer to [What's New](../whats-new.md).

Some of the enhancement features are listed below for your reference. 

**Learner transcript**

Learning Manager provides you a feature to generate transcripts for your organization's Learning Manager learners. For more information, refer to  [Learner Transcripts feature help content](../administrators/feature-summary/learner-transcripts.md). 

**Export badge as PDF**

Learning Manager allows you to export your badges as PDF files. For more information, refer to  [Badges feature content](../administrators/feature-summary/badges.md). 

**Quiz score for modules**

You can add quiz score for Classroom, Virtual classroom and activity modules. 

**Add users**

* You can move learners from one self registration group to another group. 
* You can move users from one external group to another external group. 
* You can make a user of external group as Manager of the same external group. 
* After adding an external user group to Learning Manager, you can also pause the external users registration process. At any point in time, you can always revoke the blockage (pause) by choosing a Resume option.
* Now, you can edit the name and email id of learners.

**Self-enrollment**

Learners can also unenroll themselves from the learning objects such as course, learning program or certification. However, learner cannot un-enroll from a learning object after completing a learning object. 

**Consuming learning objects**

Now, Administrators can mark a learning activity of learners as complete. 

**Reports**

* You can subscribe to course, learning program or certificate reports. You can also subscribe to individual course reports for data like quiz score and learner status. The subscriptions will be delivered to your email ID as registered in Learning Manager account. You can also change this email id.  
* When you export Certification enrollment report, a new column named **Due Date** is also exported. This column data enables Administrators to know the learners who missed their learning object consumption deadlines. 

**Email templates**

Now, you can edit the header of email templates. 

+++

+++Update 17

Release date: June 15, 2016.

### Issues fixed {#Issuesfixed-8}

**Add users**

When there are large number of Learning Manager users, there was a delay in loading users and user groups page. This issue is fixed. 

**Create user groups**

In some instances, user count was not displayed in default user groups page of Learning Manager. This issue is fixed.

+++

+++Update 16

Release date: June 10, 2016.

## Issue fixed {#Issuefixed-1}

Some customers faced problems in using Single sign-on feature in Learning Manager. This issue has been fixed by referring Learning Manager's entityId to a URL (<https://learningmanager.adobe.com>) instead of a keyword. Learning Manager conforms to SAML 2.0 specification. 

+++

+++Update 15

Release date: May 25, 2016

### Enhancements {#Enhancements-10}

**Certifications/Learning programs**

* In the learners enrollment list for Certifications and Learning programs, full name (first and last names) of learners is displayed. Earlier, only first name of the learners used to appear.
* Skills with highest level credits are considered from the list of courses in certifications/learning programs and displayed on cards as certification/learning program skill. If there are multiple courses with same credits value, then they are picked up in alphabetical order. Earlier, the skill names for certification/learning programs were considered randomly from a list of respective courses.

**Import CSV**

For auto upload feature of CSV using FTP, Administrators receive e-mail notifications if there is any failure in the CSV upload.

**Add external partners**

When external learners visit the registration page using an external profile URL, the name of external profile is displayed in the registration page for better identification. 

### Issues fixed {#Issuesfixed-9}

**Preview and publish courses**

* In author role, when you preview a course which was uploaded from Captivate as a SCORM+SWF content with `code $$cpQuizInfoStudentName$$` variable, null value was displayed for variable. This issue is fixed. 
* When a Presenter course with title containing apostrophe (') is published and viewed in Learning Manager, question marks (???) used to appear in TOC. This issue is fixed. 

**Certifications**

* If a certification is associated with a catalog and when the certification recurs, it appears in all the associated catalogs. Earlier, there were some instances where users could not view the recurring certifications in their catalogs. 
* While creating certifications, if an administrator enters the **days to complete** value which is greater than or equal to validity period of the certification, a warning message appears. Earlier, the warning message was not shown to the administrators. 
* The certification **validity** is displayed to users in terms of months. Earlier, the base value was appearing in terms of years.

**Define learning programs**

The deadline does not appear for default learning program instances. Earlier, a pre-defined deadline used to appear which may not be relevant to users. 

**Create courses using modules**

* When an author updated a module of a blended course, the attendance page did not appear in administrator role. This issue is fixed. 
* When a course instance name contains colon (:), the export action for learners list failed. This issue is fixed. 

+++

+++Update 14

Release date: May 04, 2016

### Enhancements {#Enhancements-11}

**Catalogs**

When a learner accesses catalog, the default focus shifts across tabs based on the availability of learning objects, in the following order: 1. Courses 2. Programs 3. Certifications and 4. Job Aids. For example, if the courses are not available in Courses tab for that learner, the focus shifts to the next learning object which is Programs if there are learning programs. 

**Account settings**

A feedback option is provided in the confirmation dialog of Account de-activation when an Administrator chooses to de-activate an account. 

### Issues fixed {#Issuesfixed-10}

**Export reports**

* Export of learners list used to fail when a large set of users are enrolled in a learning program. This issue is fixed. 
* When a course has two instances with same name and the name of the instance is long, two worksheets were not created in the exported excel file. This issue is fixed.

**Bulk enrollment**

When a large number of learners are enrolled to learning objects such as learning programs, courses, certifications, job-aids and learning plans, the enrollment used to fail. This issue is fixed. 

+++

+++Update 13

Release date: April 20, 2016

### Issues fixed {#Issuesfixed-11}

**Create courses using modules**

When a module content with long file name is uploaded, there were issues with appearance of buttons. Also, the module upload and delete options didn't work as expected. This issue is fixed. 

**Import CSV**

As per the request from US customers, the FTP CSV auto upload time has been changed from midnight GMT to midnight PST. 

**Export reports**

Export of enrollment data used to fail if one of the enrolled learners is deleted after consuming the course. This issue is fixed. 

**E-mail templates**

* The word **partners, **which was used to represent external groups,** **is** **removed from e-mail templates body and title. External groups are not necessarily called partners.  
  **Note:** This updated template does not appear if the default template is modified already. To view the updated template click** Revert to Original**in **Template Preview** dialog. 

* The URL is not clickable in the e-mail received by Administrators whenever **Profile Created(Self-Registration) **and** Profile Created(External/Partners)** email templates are edited. This issue is fixed.

+++

+++Update 12

Release date: April 07, 2016

### Enhancements {#Enhancements-12}

**Job Aids**

Create Job Aids using a URL. You can mention just a URL name in Job Aid creation workflow and create Job Aid if you want to use any existing online content as a Job Aid. 

**Add learners**

Editing of single user's data such as name, e-mail, profile, and Manager's name is allowed. All the corresponding user groups are updated with the latest user data. 

**Export reports**

Manager name, learning object name, and user-defined non-unique value columns from CSV are added to the exported learners list for learning objects. Earlier, only the basic data of learners such as name, date, e-mail and status used to appear. 

**Add external partners**

Learning Manager application does not allow external learners to log into the application after their account is expired. External partners can view their account status in the application. 

**Certifications**

You can renew certifications in terms of months by mentioning the value in **Validity** field. Earlier, the certification renewal was allowed only in terms of years. 

### Issues fixed {#Issuesfixed-12}

**Announcements**

In Administrator login, pagination was not working in Announcements page. This issue is fixed. 

**Learning programs and plans**

* When a learner tries to skip an ordered course module in a learning program, an error message was not displayed. This issue is fixed now. An error message **Can't skip modules**appears. 
* Courses were not being added to learning programs whenever pagination is used on the course list. This issue is fixed. 
* **Retired**tab was appearing twice in Learning programs > instances. This issue is fixed. 

**Job Aids**

* When a learner removes job aids from the **Learning** tab, **Name** sorting was not working as expected until the page is refreshed. This issue is fixed. 

* If a Job Aid is part of multiple courses, the courses were not displayed in the Job Aids list. This issue is fixed. 
* If a learner zooms the browser in or out, the pagination for Job aids list was not working as expected. This issue is fixed. 

**Course taking**

* If a learner zooms the browser in or out, the pagination for courses was not working as expected. This issue is fixed. 

**Create skills**

In learners login, the skill name tool tip in **Skills map** was not displaying the full name. This issue is fixed. 

**Add external partners**

* A text message has been included in the external users registration page as **Users must first register and create a username password for subsequent logins**. 

**User notifications**

* When an external learner clicks the **Open Notes**link in Re-visit course email notification, player opens up but the notes panel was not working. This issue is fixed.  
* When an external learner tries to open the pre-work or test-out modules using **Open Notes** link in Re-visit course email notification, notes content was not visible. This issue is fixed. 

**Create courses using modules**

When an Administrator tries to enroll learners to a blended course that contains expired class room module, the enrollment dialog was not opening up. This issue is fixed.

**Export reports**

If a question text contains more than 255 characters and enabled for SCORM 1.2 format, then quiz reporting of such questions didn't work. This issue is fixed. 

+++

+++Update 11

Release date: March 15, 2016

### Issues fixed {#Issuesfixed-13}

**Create courses with modules**

* In Administrator login, when you try to create new instance for courses from **Retired**tab, an error used to occur. This issue is fixed. 
* In Administrator login of localized content, while enrolling learners to course instance, the actions and enroll screen layouts were distorted. This issue is fixed. 
* When an author is creating Classroom or Virtual classroom modules, the date calendar's default month used to appear as Jan, 2015. This issue is fixed to reflect the current date by default. 
* When a course instance name consists of forward or backward slash, the export action of learners list used to fail. This issue is fixed. 

**Announcements**

When a learner hovers mouse on a video announcement, the cursor was not changing to a pointed finger as expected. This issue is fixed. 

**User notifications**

When an external learner clicks the **Open Notes**link in Re-visit course email notification, it was not working. This issue is fixed now. This link opens up the Player with notes, even when the user is not logged in to Learning Manager.  

**French and German language support**

The Help URLs in CSV upload feature were traversing to English help content. This issue is fixed. 

**Preview and Publish courses**

In author login, when you preview Presenter 10 and 11 TinCan API (SWF/HTML) content, the content was not working. This issue is fixed. 

**Customizable emails**

The title names in Email templates were not appropriate. The content is updated in these template titles to make them readable.  

**Job Aids**

In Internet Explorer 11 browser, Job Aid name and icon were appearing as distorted in Author and Administrator's preview. This issue is fixed. 

+++

+++Update 10

Release date: February 28, 2016.

## New features {#Newfeatures-2}

### Job Aids

Job Aids is a repository of training content that is accessible to learners without any enrollment or completion criteria. Learners can refer to these job aids to get assistance for performing any activity or task in an organization. Administrator can track the number of downloads per Job Aid. 

For more information on this feature, refer to  [Job Aids Help](../learners/feature-summary/job-aids.md).

### Announcements

An announcement is a multimedia message (text, image or video) that an Administrator can craft and broadcast to a defined set of users. Use Announcements to motivate learners to take up trainings and thus build a learning culture.

For more information on this feature, refer to  [Announcements Help](../learners/feature-summary/announcements.md).

### Tin Can API support

Adobe Learning Manager supports the Tin Can API (also known as Experience API or xAPI) specification. You can upload and track Tin Can API compatible content similar to how you track SCORM and AICC content.

For more information, contact Adobe support team.

### Course sequencing

You can create a learning path by assigning a follow-up course or any learning activity automatically.

Events for learning plans have been updated. Couple of new events have been added. Refer to  [Learning plans](../learners/feature-summary/learning-programs.md) for more information.

### Notes reminder

If you take any notes while consuming a course, Learning Manager reminds you after 15 days by sending a notification to review the notes.

### Group level gamification

Administrators can define the scope of gamification by changing the scope settings. You can selectively enable gamification among similar profile users, groups or location. Refer to  [Gamification](../learners/feature-summary/gamification.md) feature for more information.

### French and German language support

Learning Manager application is available in French and German languages. You can customize the language for feedback, course instances and communication.

### Enhancements {#Enhancements-13}

There are significant enhancements to the existing features of Learning Manager. Some of the predominant enhancements are as follows:

### Import CSV

If you delete users, you cannot add the same users back into the application again using single user addition. However, you can add back the deleted user using CSV upload process. There are significant changes to the mandatory fields restriction in CSV upload feature. Refer to  [ FAQ on CSV](../administrators/add-users-in-bulk.md) for more information.

### Course List view

By default, you can view courses as cards. A list view has been introduced in this release. You can click the triple bar icon adjacent to search field to change the view.

### Delete courses

Now you can delete courses at draft and retired stages. Refer to  [Courses](../administrators/feature-summary/courses.md) feature for more information. If a learning object is deleted, all of its reporting data also gets deleted. If a course is deleted and if it was part of any other learning object, then an appropriate message appears to the user. 

**Learning programs and plans**

You can enforce the order in which learners can take up courses within learning programs. You can delete learning programs in draft and retired stages. If a learning object is deleted, all of its reporting data also gets deleted.

**Certifications**

You can delete certifications in draft and retired stages. If a learning object is deleted, all of its reporting data also gets deleted.

**Course effectiveness rating**

In Administrator login, you can export L1 and L3 feedback data for any course. 

**Create courses with modules**

You can enforce learners to complete pre-requisites before taking up the courses. 

**User notifications**

Learners get notifications whenever they are self-enrolled to a learning program. 

**Classroom Modules (ILT)**

You can create classroom courses for a past date. This feature enables the company administrators to feed older classroom courses information also into the Learning Manager and generate reports. 

**Export reports**

Learners report has been enhanced. You can view name, e-mail, status of learning object, enrollment criteria, enrollment date, completion date, and start date in the report. 

**Add external partners**

After enrolling the external learners to Learning Manager account, you can also downsize the number of learners, if required. However, you cannot downsize the learners beyond the used number of seats. As a workaround, you can delete the registered learners first and then enroll again with the required number of seats. 

### Issues fixed {#Issuesfixed-14}

**Learners attendance**

Attendance sheet in Administrator view displays full name of the employee if it is available. Earlier, only first name of the learner used to appear. 

**Learning programs and plans**

All the courses in learning programs are displayed in the expected order. Earlier, there were issues in the ordering of courses in a learning program. This issue is fixed. 

**Add learners**

If an existing self-registered user tries to register again using self-registration process, then an appropriate message appears. The format and the content of the message is fixed. 

**Reports**

If you want the content to identify the time spent by user in consuming content, you can identify it by using a variable, `code cmi.core.session_time`. The variable was not set earlier. This issue is fixed. 

**Create courses with modules**

Whenever an existing course module is replaced by another module, a new version of it is generated. If the quiz of this new module is exported, an exception used to occur and the quiz report was not generated. This issue is fixed now. 

**E-mail templates**

The typos in the e-mail templates are fixed. 

+++

+++Update 9

Release date: February 09, 2016.

## Sign Out behavior updated {#signoutbehaviorupdated}

When users click **[!UICONTROL Sign Out]** in Learning Manager, they are now logged out of the Learning Manager application and also they are logged out of their Adobe IDs.

+++

+++Update 8

Release date: January 20, 2016.

### Enhancements {#Enhancements-14}

**Customizable e-mails**

* Users can modify the footer section of the E-mail templates. You can customize the footer in an e-mail template with the text of your choice. The customized footer is automatically applied to all types of e-mail templates.

**Course taking**

* The resource objects in preview mode of a course are listed one after the other in a new line. Earlier, there were instances where the resources in a course used to appear next to each other in a single line. 

**Direct link to learning objects**

* You can access the learning objects (except Certification) using a direct URL. The **[!UICONTROL Copy url]** option is displayed on the tiles of learning objects. Users can click **[!UICONTROL Copy url]** and paste the link in a separate browser page to access the learning object directly. 

**Create courses using modules**

* While creating a course, authors can arrange pre-requisite courses in any order. Earlier, this option was not available in Learning Manager. 

* Authors can add or delete pre-requisite courses in Published courses. Earlier, this feature was available only to Draft courses.

**User registration**

* Users can log in to Learning Manager without any additional URL verification if their Adobe ID matches Learning Manager e-mail ID. While adding users into the account, the Administrator of an organization provides the Learning Manager e-mail ID. 

**Create catalog**

* In Administrator role, while creating catalogs using **Add learning objects** dialog, the retired courses do not appear in the list of courses. 

**Other fixes**

* In Administrator role, full name of the learners is displayed in **Learners** tab. Earlier, only first name of the learner used to appear. 

+++

+++Update 7

Release date: January 13, 2016. 

### Issues fixed {#Issuesfixed-15}

**Course taking**

* While accessing course contents, the content playbar appears always on the screen. There was an issue earlier with the content playbar as it used to disappear from the screen intermittently. 
* While accessing course content, if the content has a pop-up dialog that appears prompting users whether they really want to quit or stay on the page, hitting stay on such dialog takes the user back to the content. In some scenarios, clicking the stay button used to take the user out of the course content. 

**Other fixes**

* Few issues related to content playback are resolved. 

+++

+++Update 6

Release date: December 22, 2015

### Enhancements {#Enhancements-15}

**Personal dashboard**

* While accessing courses, catalogs, and learning programs in Administrator and Author roles, the ordering of tabs is changed to **Published - Draft - All - Retired**. The default selection is **Published.**

### Issues fixed {#Issuesfixed-16}

**Course taking**

* In learner role while you are consuming a course, if the player is closed using back button of browser or Backspace key in keyboard, the learning time spent on the course is captured in reports. In some scenarios, there was an issue that this duration was not recorded in reports.

**User registration**

* If a user registers a Learning Manager account using SSO enabled self-registration, the username in the users list appears correctly as per records. There were some instances where the username used to appear incorrectly. 

**Create courses using modules**

* When an author duplicates a course, the resource files of the duplicated course can be removed or updated. In some scenarios, users faced issue in updating or removing the resources from duplicated courses. 

**Create custom catalog for user group**

* While using **Add learning objects** dialog in Administrator role, you can filter courses, choose a course, and add using **Add** button at the bottom of the dialog. In some instances, **Add** button was not appearing for some users. 

+++

+++Update 5

Release date: December 11, 2015

### Issues fixed {#Issuesfixed-17}

**User login**

* When a user tries to log in to Learning Manager application without using activation link, the error message was appearing in wrong format. This issue is fixed.

**App for tablets**

* After installing Learning Manager in Android or iPhone tablet, browser compatibility messages do not appear. Earlier, a browser compatibility message used to appear for users. This issue is fixed. 

+++

+++Update 4

Release date: December 09, 2015

### Enhancements {#Enhancements-16}

**Add users**

* In Administrator role, when Administrator registers users or completes adding a single user, a message appears indicating successful completion of the workflow along with the next steps to follow. 
* When a user tries to log in to Learning Manager application directly without using the user activation link, an error message appears prompting users to use the activation link. 

**Supported browsers**

* If any user accesses Learning Manager application in unsupported browsers, the user receives an alert with the list of white-listed browsers. 

### Issues fixed {#Issuesfixed-18}

**Reports**

* In Administrator or Manager role, when you create a Report with secondary axis as learning time spent, apply Manager filter, and save the report, the user was unable to download such reports. You can download all types of reports. 

**Add users**

* There were some typos in the alert message displayed while enabling external learners in Administrator role. The issue is fixed. 
* In Administrator role, an appropriate error message appears when Manager field is not properly selected during single user addition. 

**User registration**

* Welcome e-mail received by new users highlights the importance of linking Adobe ID with the Learning Manager ID for successful login. 

**Customizable emails**

* When you add multiple learners to the classroom courses which have sessions as attachments, some learners were not receiving e-mail notifications. This issue is fixed. 
* E-mails to learners regarding learning objects enrollments and other events contain the specific learning object name in the e-mail subject. 

**Other fixes**

* The issues related to URL links in e-mail templates are fixed. 
* Support provided for

   * Publish to Learning Manager
   * Faster content upload support for CP 8 version (CP803 patch is required)

+++

+++Update 3

Release date: October 26, 2015.

### Enhancements {#Enhancements-17}

**Add users**

* Online Help link provided in Add users > CSV upload dialog for better understanding of the users while uploading the CSV file. 

**Fluidic player**

* When you upload Captivate course content with more than 500 MB size, the content was not playing in Fluidic player. This restriction is removed. Currently, the size limit has been changed to 2 GB. 

**Billing**

* In Administrator role, when a user enters number of learners and clicks **Place order,** a dialog appears with details about monthly and annual subscription charges per user. 

### Issues fixed {#Issuesfixed-19}

**Create courses using modules**

* While creating courses with activity modules, authors can choose valid external URLs even if they contain folder paths in the URL. Earlier, the URLs with folder paths were not supported. This issue is fixed.  
* If the course content is a project which is uploaded with a zip file in Learning Manager and if that zip file contains folder paths, as Zip>folder>content, this type of content was not supported. This issue is fixed. 

**App for tablets**

* When a user tries to download the resource files of a course in Learning Manager Android app, the resource files were not downloadable. This issue is fixed. 
* While consuming a course using Fluidic player, when a user records Note and tries to download it from the course later, it was not downloadable. This issue is fixed. 

+++

+++Update 2

Release date: September 28, 2015

### Enhancements {#Enhancements-18}

**Create courses using modules**

* Learning Manager application supports uploading of SCORM content even if the version is not mentioned in manifest.xml file. By default, the version is considered as 1.2.  
* When you upload Captivate course content with more than 500 MB size, the content was not playing in Fluidic player. As part of Update 2, the size limit has been changed to 800 MB.

**Billing**

* In Administrator role, while purchasing a subscription using credit card, the user can choose the first order starting with 10 learners. The minimum learners required for the first order have been reduced from 100 to 10. 

**User registration**

* A URL link to create Adobe ID has been provided in welcome e-mail received by learners after their registration. 

**Add users**

* In Administrator role, adding users using CSV upload option directly from Exavault account did not work for some customers. This issue is fixed. 

### Issues fixed {#Issuesfixed-20}

**Learning programs and plans**

* Learners can be auto enrolled to same learning program as part of multiple learning plans. Earlier there were some exceptions to this workflow. This issue is fixed. 

**View leaderboard and badges**

* In learner role, after consuming a course that contains a badge, the badge image was not showing up in learner dashboard's badge map and in the downloaded file. This issue is fixed. 

**App for tablets**

* A pop-up appears to indicate learner app availability when learner app url is opened in a browser on android device. 

**Other fixes**

* An issue with user account creation due to Akamai net storage support has been resolved. 
* An issue related to SCORM 1.2 content upload containing a zip file with multiple folders has been resolved. 

+++
