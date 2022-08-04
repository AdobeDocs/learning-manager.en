---
description: Learn about the new features and enhancements in Adobe Learning Manager
jcr-language: en_us
title: New features summary
contentowner: jayakarr
---


# New features summary {#new-features-summary}

Learn about the new features and enhancements in Adobe Learning Manager

The&nbsp;**February 2021**&nbsp;**release of Adobe Learning Manager**&nbsp;focuses on improving Learner Experience, Reporting and Administrative workflows. Some of the highlights include:

* New filters to assist learners in searching for Trainings.
* A brand-new Training Report for Administrators.
* A new ‘trigger’ and ‘action’ in Learning Plans.

Read on to know more.

# What's new and changed {#whatsnewandchanged}

<table> 
 <tbody>
  <tr> 
   <td> <img src="assets/board-view-in-social2x-100.jpg"><h3 id="Boardviewinsocial">Board view in social</h3><p>A&nbsp;Learner&nbsp;can see all boards in a list view. Sign&nbsp;in to&nbsp;your learner app and in your Social&nbsp;Learning&nbsp;page and see the boards as a list.</p> <p>For more information, see <a disablelinktracking="false" href="learners/feature-summary/social-learning-web-user.md#board_view_social">Board view in social</a>.</p><img src="assets/catalog-filters-2x-100.jpg"><h3 id="Catalogfilters">Catalog filters</h3><p>As a learner, you can now filter training based on the&nbsp;format&nbsp;of training, for example,&nbsp;Classroom,&nbsp;Self-paced, or&nbsp;Virtual Classroom.</p> <p>For more information, see <a disablelinktracking="false" href="learners/feature-summary/catalogs.md">Catalog filters</a>.</p></td> 
   <td> <img src="assets/social-banner-customization2x-100.jpg"><h3 id="SocialbannerCustomization">Social banner Customization</h3><p>The Administrator&nbsp;can customize the title and the subtitle&nbsp;that appear on the header image on the Social Learning homepage.</p> <p>For more information, see <a disablelinktracking="false" href="administrators/feature-summary/social-learning-configurations-as-an-admin.md#customize_social_banner" target="_self">Customizing the social banner</a>.</p><img src="assets/unenrollment-fromtraining2x-100.jpg"><h3 id="Unenrollmentfromtraining">Unenrollment from training</h3><p>When adding a Learning Plan, an Administrator can unenroll users from specific trainings based on certain triggers.</p> <p>For more information, see <a disablelinktracking="false" href="administrators/feature-summary/learning-plans.md#unenroll_training">Unenrollment from training</a>.</p></td> 
  </tr> 
 </tbody>
</table>

# Other new features {#othernewfeatures}

## Import users from Salesforce contacts {#importusersfromsalesforcecontacts}

Learning Manager now enhances the&nbsp;Salesforce&nbsp;connector to fetch Contacts as well as&nbsp;Salesforce&nbsp;Users and import them into Learning Manager automatically.&nbsp;

For more information, see&nbsp;Import users from [Salesforce contacts](integration-admin/feature-summary/connectors.md#import_salesforce_contacts).

## Updated AEM component {#updatedaemcomponent}

The AEM package for Learning Manager has been updated. To download the latest package and for instructions, see&nbsp; [Integrate Learning Manager with AEM](integrate-aem-captivate-prime.md).

## New APIs {#newapis}

**User group**

GET /usergroups/<ugid>/users -&nbsp;Return all users of a user group.

GET /usergorups?nameContains="Some string" -&nbsp;Return all user groups that matches the string query parameter.&nbsp;A few examples are shown below:

Retrieve a specific active field:

* GET /usergroups?activeField="Department"

Retrieve a&nbsp;combination of a&nbsp;specific active field and value:

* GET /usergroups?activeField="Department"&activeFieldValue="Finance"
* GET /usergroups?activeField="manager"&activeFieldValue="foo@bar.in"

**Get user report of peer&nbsp;account**

POST&nbsp;&nbsp;primeapi/v2/jobs&nbsp; -&nbsp;POST&nbsp;&nbsp;primeapi/v2/jobs

**Get training&nbsp;report**

https://captivateprime.adobe.com/primeapi/v2/jobs -&nbsp;Export training report.

Parameters:

* catalogIds
* includeCourseInfo
* includeModuleInfo
* isNotificationNeeded
* isCsvNeeded
* Object

**APIs for filtering Learning Objects by duration and format**

* GET /learningObjects&nbsp;
* GET /search

*filter.duration.range*&nbsp;&nbsp;&nbsp;&nbsp;

Accepts list of range separated by comma.

Example:&nbsp;*filter.duration.range=0-200,300-1200*

This is an optional&nbsp;filter&nbsp;and&nbsp;the&nbsp;values are in seconds.&nbsp;Negative&nbsp;values are not allowed. The&nbsp;range is inclusive&nbsp;i.e.&nbsp;0-200, which&nbsp;means&nbsp;both lower and upper limits are inclusive.

*filter.loFormat*

Accepts list of values separated by comma.&nbsp;Its&nbsp;an optional filter and its possible values are (Self Paced, Activity, Classroom, Virtual Classroom, Blended).

Example:&nbsp;*filter.loFormat=Self%20Paced%2CVirtual%20Classroom%2CClassroom%2CActivity*

For more information, see the [***Learning Manager API reference***](https://captivateprime.adobe.com/docs/primeapi/v2/).

## Reporting Enhancements {#reportingenhancements}

In this release&nbsp;Learning Manager supports&nbsp;Training Report which allows Administrators to download training details and its associated metadata like author, published date, skills, Catalog labels etc.&nbsp;

On the Admin app, click&nbsp;**Reports > Custom Reports > Excel Reports > Trainings Report**.&nbsp;

You can download reports&nbsp;for the following:

* Selected trainings (Limit 10) - Selects one or multiple trainings (up to 10) from any catalog
* Trainings in the selected Catalogs (Limit 5) - (catalog selection will be available up to five catalogs).
* All trainings - (all trainings in the account).&nbsp;

In the&nbsp;Advanced Options&nbsp;section,&nbsp;the following options are available:

* Include Course mappings with Learning Program / Certification
* Include Module Level information

After selecting the filters and clicking&nbsp;Download, you&nbsp;will receive a notification to download the report in CSV format.

The report will have the following fields:

*Catalog Name, Training Type, Training Id,&nbsp;Training&nbsp;unique id, Training Name, Sub Trainings, Modules, 'Training or Module Duration'  
, Format, Status of Training, Skills, Author, Last Published Date, Last completed Date, Instructors Enrollment Count,&nbsp;Started&nbsp;count, Completion count, Avg L1 score, Avg L2 score, Avg L3 score, L1 responses received, L2 responses received, L3 responses received, Catalog labels & Tags.*

## Customize columns in Learner Transcripts {#customizecolumnsinlearnertranscripts}

In this release of Learning Manager, an Administrator can customize the columns exported in a Learner Transcript report. Admins, Custom Admins, and Managers can configure the columns before exporting the report.&nbsp;

On the&nbsp;**Learner Transcripts**&nbsp;dialog,&nbsp;click&nbsp;**Advanced Options**. In the&nbsp;**Configure Export Format**&nbsp;section, choose the columns that you want to export.

## Timezone enhancements {#timezoneenhancements}

The Administrator can set an account level preference to export the Learning Transcript in the following time zones:

* UTC (Default behavior)
* Account-level time zone preference

The Learner Transcript downloaded using Jobs API also downloads the data in the selected&nbsp;timezone.

There is no change expected in the Learner Transcript by default immediately after the release. Administrators can configure this setting from **Admin > Settings > General > Report&nbsp;Timezone**.

## Download Learner Transcript in user-preferred timezone {#downloadlearnertranscriptinuserpreferredtimezone}

There is a new account-level setting for Learner Transcript for Administrator, Custom Admin, Manager, and Learner.&nbsp;This option, by default, is set to the UTC time.

On the other hand, for Managers,&nbsp;there is an option to download the Learner Transcript based on the&nbsp;timezone&nbsp;that he/she had selected in the profile settings.

If the Manager enables this option, the&nbsp;timezone&nbsp;is picked from the one set in the profile settings page, shown below.

**Note:&nbsp;**For a new&nbsp;Manager, the&nbsp;Timezone&nbsp;checkbox is disabled.

## User report for Peer accounts {#userreportforpeeraccounts}

The Administrator can view the user report of the peer account.&nbsp;The parent account admin can request to access the report and once the peer account admin accepts this,&nbsp;the&nbsp;parent admin will be able to view the&nbsp;number of&nbsp;registered users in&nbsp;the&nbsp;peer account&nbsp;and will be able to download the user report for peer account.

For more information, see [Download user report for peer accounts](administrators/feature-summary/peer-account.md#download_peer_account).

# Enhanced features in this release {#enhanced}

### **Support for accent characters**

In this release, we've added support for accent and diacritical characters in table columns. The following are the areas of impact:

* A user name with accent characters should be treated different from the normal character user name. For example, Râul and Raul are treated as two different user names.
* An email with accent characters should be treated different from the normal character email id. For example, Stéphane.Lancè@junk.com and Stephane.Lance@junk.com are treated as different email ids and should not show email id present.
* User group names having same attribute value with and without accent characters should be treated as different user groups. For example, Lôcation and Location with value Bengaluru are treated as different user groups.

### **Changes in&nbsp;columns in Learner Transcripts**

The following are the changes in the Learner Transcripts fields.

**New&nbsp;columns**

* Training ID
* Training or&nbsp;Module Duration&nbsp;(mins)

### Warning message for submission without file&nbsp;

A warning message is displayed to&nbsp;the&nbsp;Instructor when approving a submission for&nbsp;a&nbsp;learner who hasn't made a submission.

**Workflow**

1. Login as an Author and create a course with Activity submission module.
1. Login as an Admin and enroll a learner to the course.
1. Login as an Instructor and navigate to the submission module page.
1. Click&nbsp;**Approve**.

A warning message is displayed-&nbsp;&nbsp;*Submission&nbsp;file is not available. Please confirm if you want to still go ahead with the&nbsp;approve/reject action*.

### Feedback&nbsp;pop-up

In the Immersive view, a Learner can now see a pop-up of L1 feedback form upon completing a course and Learning Program. The L1 feedback auto pop will appear only if Admin has set up the configuration accordingly.

### Connector changes

You can now increase the frequency for importing users for all connectors that support importing of users. Contact your **CSAM **for more details.

### Duration

When creating a Certificate,&nbsp;or&nbsp;Job Aid, there is an additional field&nbsp;**Duration**.

The Administrator or Author can specify the duration, which gets used as a filter and appear in the report.&nbsp;

**Certification**

When adding an external certification, you can specify the duration (in minutes).&nbsp;For more infrmation, see&nbsp; [Certifications](administrators/feature-summary/certifications.md).

**Activity module**

You can specify the duration&nbsp;while adding an activity module in a course for activity type File Submission and&nbsp;xAPI-based modules. For more information, see [Courses](authors/feature-summary/courses.md).

**Job Aid**

When adding a Job Aid, you can also specify the duration. For more information, see [Job Aids](authors/feature-summary/job-aids.md).

**Content Library**

After adding an audio or video content,&nbsp;you can also specify the duration.&nbsp;However, if you do not specify any value in the&nbsp;Duration&nbsp;field,&nbsp;the duration will be equal to the duration of the uploaded content. For more information, see [Content Library](authors/feature-summary/content-library.md).

### Changes in reporting of quiz scores

Learning Manager allows Administrators to export L2 Quiz score report. This report contains Quiz score and Score percentage for each user. In this release, we are modifying the header of existing column and adding new columns for better readability and analysis.

We’ve added the following columns:

* **Interaction Score**&nbsp;– It’s the&nbsp;sum&nbsp;of all interaction scores received from the content.
* **Quiz Score**&nbsp;– It’s the quiz score grade received from the content.
* **Quiz Score Max**&nbsp;– It’s the&nbsp;maximum&nbsp;quiz score grade received from the content.

**Note:&nbsp;**The column&nbsp;Quiz Score percentage is&nbsp;calculated as&nbsp;the&nbsp;percentage value of ‘Quiz Score’ and ‘Quiz Score Max’.

We plan to remove the column ‘Total User Score/Quiz Score’ from the next release as all the information is now available as separate columns for better readability and analysis.

### Other&nbsp;enhancements

* Added a new attribute called "rootCertificationId" in "learningObject" model. This attribute is specific to certification&nbsp;loType&nbsp;only.
* Learner&nbsp;Transcripts for Admin and Manager&nbsp;has an option Select Columns,&nbsp;where specific columns can be selected to appear in the transcript.
* The Manager can&nbsp;include the&nbsp;timezone&nbsp;in the transcript.

# Data retention updates {#data-retention-updates}

Learning Manager provides you with FTP and Box connectors to help transfer of data to/from Prime. The storage provided by these connectors is meant to be an intermediate temporary buffer space between Prime and an external system, and they are not supposed to be used as storage for the CSV files that flow between Prime and the external system. In addition to User data import, these connectors are also used internally by other connectors that we ship for Adobe Connect,&nbsp;BlueJeans,&nbsp;getAbstract, Harvard Manage Mentor, and Zoom.&nbsp;&nbsp;

In this update of Learning Manager, we will be enforcing the following policies with respect to how long the data (CSV files) used in the context of various workflows are retained, before they are&nbsp;auto-deleted. It is important to take note of this, especially if you have written upstream applications (for data that is inbound to Prime) or downstream applications (for consuming outbound data from Prime). It is also a good idea to back up any files that you already have in Box/FTP folders, if you need them for reference or any other purpose.&nbsp;&nbsp;

The new data retention policy is as follows:&nbsp;&nbsp;

* All CSV files used while importing data using FTP/Box Connector (directly or indirectly) will be deleted 7 days after the import completes. So, users/application uploading data cannot assume that the file will be present after Prime has ingested the data. This policy will also apply on user CSV import workflow.&nbsp;&nbsp;
* All CSV files created during data exports will get deleted automatically after seven days from export. So, users and applications must ensure they consume this export before that.&nbsp;&nbsp;
* The Migration feature provided in Prime also relies on FTP/Box connector to transfer data to Prime. All CSVs used during migration will be automatically deleted after seven days of its most recent use.

# Release Notes {#releasenotes}

For information regarding current and previous releases of Learning Manager web app and device app, see the&nbsp; [***Release notes***](release-note/release-notes.md).

# Bug fixes {#bugfixes}

To see the bugs that are fixed in this update, refer to the&nbsp; [***Bugs fixed***](release-note/release-notes.md#bug-fixes)&nbsp;list.

# Known issues {#knownissues}

To see the known issues in this update, refer to [***Known issues***](release-note/release-notes.md#known-issues) list.

# System Requirements {#systemrequirements}

[Learning Manager system requirements](system-requirements.md)

# Previous releases of Learning Manager {#previousreleasesofcaptivateprime}

* [Learning Manager | December 2020 release](whats-new-december-2020.md)
* [Learning Manager | August 2020 release](whats-new-august-2020.md)
* [Learning Manager | April 2020 release](whats-new-april-2020.md)

# Have a question or an idea? {#haveaquestionoranidea}

<table> 
 <tbody>
  <tr> 
   <td><img src="assets/ask-the-community.svg"></td> 
   <td><p>If you have a question to ask or an idea to share, come and participate in the&nbsp;<a href="https://community.adobe.com/t5/captivate-prime/bd-p/captivate-prime?page=1&amp;sort=latest_replies&amp;filter=all" disablelinktracking="false"><strong><em>Adobe Learning Manager Community</em></strong></a>. We would love to hear from you and address your queries.<br> </p></td> 
  </tr> 
 </tbody>
</table>

### More like this

* [Adobe Learning Manager product guide](https://www.adobe.com/products/captivateprime.html)
* [Adobe Learning Manager playlist](https://www.youtube.com/playlist?list=PLq21ukQtk0URntzGmTxsx7Qt8z9b9Elth)
* [Organize your training in Adobe Learning Manager | Ashwini Jaisim](https://elearning.adobe.com/2020/07/organize-your-trainings-in-adobe-captivate-prime/)
* [Add your Adobe Learning Manager Account URL to your Adobe Connect Central Account Summary Page](https://elearning.adobe.com/2019/10/add-adobe-captivate-prime-account-url-adobe-connect-central-account-summary-page/)

