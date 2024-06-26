---
description: Learn about the new features and enhancements in tne July 2024 release of Adobe Learning Manager
jcr-language: en_us
title: What's new in this release
---

# What's new in this release {#whatsnewandchanged}

Learn about the new features and enhancements in the July 2024 release of Adobe Learning Manager.

Explore a few of the latest Adobe Learning Manager features, such as:

1. Enhancement in compliance dashboard
1. Enhancement in non-logged in experience
1. Learner user interface revamp
1. HTML5 content support in fluidic player
1. Skills suggestions for authors
1. Course overdue push notifications on the mobile app

## Enhancement in compliance dashboard

### What is a compliance dashboard? {#whatiscompliancedashboard}

The **Compliance Dashboard** in **Adobe Learning Manager** allows managers to monitor and track the learning progress of their team members. They can check if team members are meeting deadlines and keeping up with their learning process, which helps ensure compliance.
To access the compliance dashboard in the admin app, select **Reports** > **Learning Summary** > **Compliance Dashboard**.

### What's changing in the release

The compliance dashboard has been improved with the following updates:

With the new compliance dashboard, admins and managers can view the compliance-type courses/learning path/certifications related to their specific category (for example, Sales, Marketing, and Legal). Admins can categorize custom compliance courses into specific categories. Custom compliance categories are powered by catalog labels.  Admins can create a course dashboard and share it with managers. Managers can then view the same dashboard on their respective instances. Enhancement have also been made to the user interface of the compliance dashboard and compliance email notifications.

![](assets/compliance-dashboard-admin.png)

#### Workflow

Here are the steps for using the new compliance dashboard:

1. Create custom compliance labels. View [Create custom compliance labels](/help/migrated/administrators/feature-summary/reports.md#create-custom-compliance-labels) for more information.
1. Add these labels to the course. View [Add compliance labels to course/learning path/certification](/help/migrated/authors/feature-summary/courses.md#add-compliance-labels-to-courselearning-pathcertification) for more information.
1. Create the dashboard with the compliance course and share it with managers. View [Create and share a compliance dashboard](/help/migrated/administrators/feature-summary/reports.md#create-and-share-a-compliance-dashboard) for more information.
1. Managers view the compliance dashboard. View [View the dashboard](/help/migrated/managers/feature-summary/manager-dashboard.md#view-the-dashboard) for more information.

## Learner user interface revamp

>[!IMPORTANT]
>
>The new learner UI will be released in phases. 

The **Learner UI** has been updated with a more elegant and modern design. The following pages are getting a new and modern look: **Learner Home**, **My Learning**, **Catalog**, and **Course Overview** landing pages. Course cards also have a new design to display details in a modern way. Hovering over a course card shows the course description and publication date. 

>[!NOTE]
>
>The revamped User Interface applies only to the Immersive layout. These changes are not supported on the mobile web/app yet and will be updated in a future release.

![](assets/old-ui.png)
_Old user interface_

![](assets/new-ui.png) 
_New user interface_

### What is changing in this release

The Learner UI has been refreshed with a more elegant and modern design. The new UI aims to provide a consistent user experience. 

**Modernize look and feel**

The new refreshed visual elements align with modern design trends, making the product look intuitive and appealing. This includes a new masthead, side panel, and modern-looking widgets.

**Enhanced user experience (UX)**

Learners will now see a consistent card view on the following pages: Homepage , Catalog, My Learning offering a unified experience. The course overview page also has a cleaner look now.

View [Learner home page](/help/migrated/learners/feature-summary/learner-home-page.md) for more information.

**Changes to the course publication dates**

With this enhancement, the publish dates for LinkedIn and Go1 courses imported into Adobe Learning Manager will be the actual publish dates on LinkedIn and Go1. You can view the actual published dates for the LinkedIn and Go1 courses on the User Interface as well. View [Course cards](/help/migrated/learners/feature-summary/learner-home-page.md#course-cards) for more information.

## Updates to non-logged in experience

The non-logged-in experience allows you to create a real-time experience for non-logged in customers. This serves as a landing page for their marketing campaigns, providing enough information to encourage sign-ups. 

### What's changing in this release

Customers can purchase a premium plan to build this highly scalable non-logged-in experiences. This non-logged experience, powered by the Training Data Access Connector, provides real-time data on seat limits, seats occupied, waitlist limits, and waitlist counts using ALM APIs. Customers can use these APIs to offer non-logged-in learners search and filter capabilities and a complete course summary. 

>[!NOTE]
>
>Please contact the support team or CSM to purchase the premium plan.

## Multiple SKU support on ALM

Learners can now add several courses, learning paths, or certifications to the cart and purchase them together.

### What's changing in the release

Previously, learners could only buy one course at a time. In this release of **Adobe Learning Manager**, they can purchase multiple courses, learning paths, or certifications at once using cart. 

This feature is available only in the learner apps (existing UI, new learner UI, and mobile immersive app).

View [Multi item cart in ALM](/help/migrated/learners/feature-summary/multi-item-cart.md)

## HTML5 content support in fluidic player

**Adobe Learning Manager** now supports uploading HTML5 content as a .zip file to the content library. Once uploaded, these files can be included as modules in a course. Also, authors can define the completion criteria for self-paced HTML5 modules, allowing either learner-marked completion or automatic completion upon launch. 

### What's changing in this release

Adobe Learning Manager now supports HTML5-supported content in self-paced courses. Authors can add HTML5 content as a .zip file to self-paced content. Learners can view the HTML5 content in the fluidic player. With the new feature, learners can mark the course as completed directly in the fluidic player for self-paced courses. View [Add HTML5 file type in the content library](/help/migrated/authors/feature-summary/content-library.md#add-html5-file-type-in-the-content-library) for more information.

With the new enhancement, the course with the external link will automatically be marked as complete when the URL is visited, as long as the author has set the completion criteria to the new option **On Launching content**. The new option **Completion Criteria** has been added in the Activity Module page where the author can set the completion criteria for the external links. View [Add HTML link in the activity module](/help/migrated/authors/feature-summary/courses.md#add-html-link-in-the-activity-module) for more information.

## Course overdue push notifications on the mobile app

Learners will receive push notifications whenever they miss a course deadline. With this new enhancement, learners will now have the option to either snooze a reminder for 24 hours or get reminded next week for each overdue reminder they receive. This is applicable only for deadline overdue notifications. 

## API changes in this release

### Changes in search API

The following are the changes made to the search API in this update:

* Learners can search for tags within catalog filters using the ```GET /search``` API. Learners can search for the tags by selecting ```tag``` as a value for ```filter.loTypes``` parameter.
* The new filters, seat available, waitlist available, and time range filter have been added to the following APIs: ```GET /search``` and `GET /learningObjects`.
* The new filters `filter.session.includeEnrollmentDeadline` has been added to the following API ```GET /search```.

### Changes in account API

The new column `custom_injections`, `showComplianceLabel`, and `complianceLabelDefaultID` have been added in the ```GET /account``` API to get account data of user endpoint.

### Changes in learning object API

The following are the changes made to the learning object API in this update:

* The new response legacy author ID and other details added under `authorDetails` in the `GET /learningObjects` API. Additionally, a new filter, `filter.authors`, has been added to filter legacy authors and their courses.
* The new attribute called `effectivenessIndex` will help you get the course effectiveness data. 
* The new response `whoShouldTake`, which gives details about who should take this course, has been added to the following APIs: `POST /learningObjects/query`, `GET /learningObjects/{id}`, and `GET /learningObjects`.
* The new response `waitlistLimit`, which gives details about waitlist limitation, has been added to the `GET /learningObjects` API.
* The new response `count` which give total count of learning object, has been added to the APIs `GET/ learningObjects` and `POST/ learningObjects/query`
* The new responses, `catalogFieldId` and `fieldValueId` have been added under `catalogLabels` in `GET/ learningObjects` API.
* Learners can get the catalog label values in the API `GET /preview/learningObjects`.

### New API to get marketplace count

In this release, new API `GET /search/marketplace/count` has been added to get the content marketplace count. 

**Sample curl**

```
curl -X GET --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth d8631c7b0e3b5d2ae00422ef30aaecfc' 'https://learningmanagerstage1.adobe.com/primeapi/v2/search/marketplace/count?query=course'
```

**Sample response**

```
{
  "count": 54910
}
```

### Changes in the LO instance API

The following are the changes made to the learning object instance API in this update:

* In this release, a new key called `gamificationEnabled` has been added to the learning object instance API `GET /learningObjects/{loId}/instances/{loInstanceId}`.
* The new `gamificationSettings` attribute to the above API to get the details of the gamification settings. For example: `GET /learningObjects/{loId}/instances/{loInstanceId}/gamificationSettings`.
* The new `leaderboard` attribute to the above API to get the details of the gamification settings. For example: `GET /learningObjects/{loId}/instances/{loInstanceId}/leaderboard`.


### Changes to offset limits

To improve system performance and manage resource utilization more effectively, Adobe has deprecated high offset values in the GET /users endpoint for both ADMIN and LEARNER scopes. We recommend using the Jobs API to retrieve the records with an offset value.

## Changes to reporting

### Compliance dashboard

In this release, the Compliance dashboard has two new columns:

* Status
* Compliance type

This is in addition to the already existing columns:

* User Name
* User Email
* LP/Certification/Course    
* Type    
* Enrollment Date (UTC TimeZone)    
* Deadline (UTC TimeZone)    
* Completion Date (UTC TimeZone)    
* Progress %   

### Training report

The training report in **Admin** > **Reports** > **Custom Reports** and the **Jobs API** used to have columns called **Skill(s)** and **Tag(s)**. These columns are now renamed to **Skills** and **Tags**.

## Bug fixed in this update

**Email template and notification**

* The email notifications, after a session is canceled, are not sent to the last set of instructors when the instructors are removed from the session. 
* The organizer does not receive email notifications for MS Teams after creating a virtual instructor-led training. Only after the course is published and email templates are enabled, are the emails triggered. 
* Sometimes, an email template consists of an incorrect date format and translation. 

**Learning Path**

* After you select a skill in a Learning Path, the dropdown does not display as expected when you select the text field. 
* In some cases, you are unable to remove skills from a Learning Path. 

**Learning Program**

* If a Flexible Learning Program has many courses, the Learning Plan does not get completed even after an Admin marks it complete. 
* The column last_modified_by in the Enrollment report isn't updated when a learner changes instances. 

**Learner**

* When a learner is enrolled in multiple instances of a course, and you download the attendance report, the report contains incorrect information. 

* A user can view another user's private posts if they are added to a public story. 
* In some cases, you are unable to unenroll learners from a certification. An error message displays when attempting to unenroll. 
* A certification is marked as completed even after an Admin marks it completed after selecting only one course. 
* An Admin is unable to mark a VC as complete if the session's end time is changed to a previous date. 
* The Session Attendance report appears as "Not Attended" for learners who are on a waitlist. 

**Report**

* In some cases, an Admin is unable to export the Training report. 
* When a SCORM content contains questions or answers exceeding 32,767 characters, you're unable to download the course quiz report in Excel. 
* After you select Reset Gamification, the Level achieved date does not reset. 

**Custom role**

* In some cases, when a Custom Admin tries to switch to an instructor role, Error 403 forbidden displays. 

**Search** 

* Currently, after exporting all User Groups, deleted User Groups also feature in the output. 
* Due to intermittent search issues, you're unable to search for a certification. 

**Certification**

* Sometimes, re-enrolling a user to a recurring certification fails. 

**Activity submission** 

* Attempting to re-upload a file to the activity submission module fails with an Error 500 in the network call. 

**Learner app** 

* After downloading the course notes as PDF, the notes appear randomly. They don't follow the order. 

**API** 

* Creating a Connect VC meeting fails if multiple instructors have the same email address. 
* After enrolling to a Learning Path, the MS Teams VC displays an incorrect URL on the Overview page. 
* The user report pre-signed URL provided as part of the Job API response expires after six hours. 
* While generating an enrollment report for a course, the Course Name column displays an incorrect course name. 
* The migration worker fails to send the unique lo id when calling the bulk API for course, but the id gets removed. 
* When a course is included in a specific catalog that a user can access (while the default catalog is disabled), despite the setting that prevents unenrolled learners from viewing the course, you can still retrieve the course's metadata through the learningobject/id endpoint. 
* The skills filter does not work as expected when skillname has commas in the name in the GET /learningObject API. 
* There is inconsistency in the timestamp metadata of the file in the data retention worker for SFTP. 
* If any connector is removed and reconfigured, the project migration status appears to be closed. 
* The Training Report has "Tag(s)" as column header instead of "Tags". 
* The Commerce connector export fails if the catalog is disabled and if any of the exported course is only part of the disabled catalog. 
