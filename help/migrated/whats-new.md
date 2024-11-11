---
description: Learn about the new features and enhancements in the November 2024 release of Adobe Learning Manager
jcr-language: en_us
title: New features summary
---
# New features summary {#new-features-summary}

Learn about the new features and enhancements in the November 2024 release of Adobe Learning Manager.

* **AI-powered Search:** Combines lexical and semantic search for smarter, context-aware results. 
* **Webhooks**: Integrate with Webhooks to send real-time information to specific URLs. 
* **Learning Tools Interoperability (LTI)**: Supports LTI for interoperability with other LMS platforms. 
* **Credly integration**: Manage and share external badges via Credly. 
* **Compliance dashboard enhancements**: Share dashboards with other admins and set default compliance widgets on learner homepages. 
* **Multi-Language support**: Create language-specific instances for Classroom and Virtual Classroom modules. 
* **Custom roles**: Enhanced control over user roles and permissions. 
* **Completion comments**: Add comments when marking learners as complete. 
* **User Group report**: Manage user groups with detailed reports. 
* **Waitlist report**: Download the waitlisted learners list for course instances. 
* **Accessibility enhancements**: Support for alt text on mastheads and company logos. 
* **Support for Hindi**: Interface language support for Hindi. 
* **Profanity check**: Block social posts containing prohibited words. 
* **Email template optimization**: Combined and optimized email templates for instructor assignments and session cancellations. 
* **MS Teams completion criteria**: Set minimum attendance time for VILT sessions. 
* **New migration workflows**: Migration changes include completion criteria for courses and modules and migrating modules into folders. 

## AI-powered search in Adobe Learning Manager 

Adobe Learning Manager is revamping the way learners search courses or training. It introduces an AI-powered search capability that combines lexical and semantic search. The search is now smarter, as it looks for specific terms and understands the context and intent behind them. The advanced search understands the meaning of your query and provides relevant results. It identifies the main focus of the search to give you the most complete set of results.

Refer this article [Advanced Search](/help/migrated/learners/feature-summary/advanced-search.md) for more information.

## Webhooks

Adobe Learning Manager allows integrating with Webhooks to send real-time information, such as course enrollments, course creation and other information, to a specific URL.

A webhook in ALM allows one entity to automatically send data to another application via HTTP. It will enable an application to provide other applications with information without constantly requesting it. For example, if a user completes a learning management system (LMS) course, a webhook can automatically send that information to another platform, such as a CRM or reporting tool. Webhooks are often used in integrations to automate processes and reduce the need for manual updates between systems. Set up webhooks by providing a callback URL to which you'd send the data.

Refer this article [Webhooks](/help/migrated/integration-admin/feature-summary/webhooks.md) for more information.

## Learning Tools Interoperability

Adobe Learning Manager now supports LTI to enhance interoperability between Adobe Learning Manager and other Learning Management Systems (LMS).

### What is LTI?

LTI (Learning Tools Interoperability) is a standard that allows third-party tools and content providers to connect with a Learning Management System (LMS). Users can access external learning content from external content providers directly within their LMS without signing in or navigating to a different LMS.

LTI as a tool provider: LTI as a tool provider allows external systems to integrate with an LMS. Adobe Learning Manager acts as an LTI Tool Provider, allowing other LMS platforms to access course, certificates, or learning paths from the Adobe Learning Manager directly within their LMS. 

LTI as a tool consumer: LTI as a Tool Consumer allows LMS to integrate external tools via Learning Tools Interoperability (LTI). In this scenario, LMS is a consumer of services provided by external tools. Adobe Learning Manager acts as an LTI Tool Consumer, allowing it to integrate third-party learning tools. This allows Adobe Learning Manager learners to consume the courses, certificates, or learning paths from the third-party tools within the Adobe Learning Manager.

Refer this article [Learning Tool Interoperability](/help/migrated/integration-admin/feature-summary/learning-tools-interoperability.md) for more information. 

## Credly

Using Credly, an admin in ALM allows learners to manage and share external badges from the platform across various social media channels.

### What is Credly?

Credly is a digital credentialing platform that allows learners and organizations to earn, share, and verify professional achievements, such as badges or certifications. Learners can manage and share badges through their Credly profile on social media and other places. 

### Integrate Credly with Adobe Learning Manager

First, add the Credly connector in Adobe Learning Manager (ALM). Next, migrate the existing badges from Credly to ensure the continuity of learner achievements. Finally, create a skill in Adobe Learning Manager to the appropriate learning path to enhance learner development and recognition. 

Refer to this article [Credly](/help/migrated/integration-admin/feature-summary/credly-integration.md) for more information

## Compliance dashboard

In this release, admins can now share the dashboard with other admins, custom admins, and store managers, giving them instant access to the compliance dashboards. They can now set the default compliance widget on the learner's homepage, allowing learners to track their compliance requirements. Refer to this article [Compliance dashboard](/help/migrated/administrators/feature-summary/reports.md#share-compliance-dashboard-with-admins-and-custom-admins) for more information.

## Multi-Language Support

Adobe Learning Manager (ALM) now allows authors to create language-specific instances using language tagging for Classroom and Virtual Classroom modules. Learners can access CR/VC modules in their preferred language. For example, an author can create a CR/VC module with two instances: one in English and one in French. Learners can select the instances in their preferred language.

Refer to this article [Add learning objects in different locales](/help/migrated/authors/feature-summary/add-new-language-learning-objects.md#multi-language-support-for-crvc-instances-with-language-tagging) for more information.

## Custom roles

Custom roles allow admins to define specific roles and responsibilities for different user groups, ensuring better management and control. With this release, ALM enhances custom roles by providing more detailed control over the following sections.

* Users
* Courses
* Learning Paths
* Certifications
* Job Aids
* Catalogs

Admins can assign precise permissions based on user responsibilities, ensuring each group only has access to relevant features and content. These enhanced controls allow more granular management of key sections.

Log in as an admin and navigate to **[!UICONTROL Users]** > **[!UICONTROL Custom Roles]** to create and manage the Custom Roles.

Refer this article [Custom roles](/help/migrated/administrators/feature-summary/custom-role.md) for more information.

## Completion comments 

Admins can now add comments when marking learners as complete in courses, learning paths, or certifications. Admins can add comments for one or multiple learners at the same time, and the comments will appear in the [Learner Transcripts](/help/migrated/administrators/feature-summary/reports.md#learner-transcripts) report.

Refer this article [Completion comments](/help/migrated/administrators/feature-summary/courses.md#completion-comments) for more information.

## User group report

Adobe Learning Manager's new **[!UICONTROL User Group Report]** helps manage user groups by providing visibility into groups left unmanaged when admins left. Admins can access the reports under the **[!UICONTROL Users]** > **[!UICONTROL User Group]** section. It provides detailed information about each group, including:

* User group type
* Group name
* Description
* Created by (Name)
* Created by (Email)
* Created on (UTC Timezone)
* Number of Users

Refer this article [User group report](/help/migrated/administrators/feature-summary/add-users-user-groups.md#user-group-report) for more information.

## Waitlist report

Adobe Learning Manager's new **[!UICONTROL Waitlist Report]** allow admins to download waitlisted learners list for all instances of a course. Admins and instructors can access this report from the **[!UICONTROL Waitlist]** section on the **[!UICONTROL Course]** or **[!UICONTROL Session Overview]** page. The waitlist report can be downloaded from the Admin and Instructor sections.

Following the columns available in the Waitlist report:

* Course Name
* Instance Name
* Instance ID
* Instance Status
* User Name
* Email
* User Unique ID
* Date Enrolled (UTC TimeZone)
* Status
* Waitlist Number
* Waitlist Limit
* Seat Limit

Refer this articles [Waitlist report](/help/migrated/administrators/feature-summary/courses.md#waitlist-report) and [Waitlist report](/help/migrated/instructors/feature-summary/learners.md#waitlist-report) to download report from Admin and Instructor section.

## Accessibility in learner homepage 

Adobe Learning Manager now supports alt text for all mastheads to improve accessibility for learners. This allows learners with special needs to use screen readers to read the alt text and understand the image. You can select multiple languages and provide alt text for each language. Make sure to add the alt text in the respective languages. Make sure the company logo in your account also includes alt text with the company name.
Refer this article [Announcement](/help/migrated/administrators/feature-summary/announcements.md#masthead) for more information.

## Support for Hindi

Adobe Learning Manager now introduces Hindi as one of the platform's interface languages and supports the platform's growth in India. Support for native Hindi speakers ensures that all features, reports, and the overall user experience are fully accessible to the users.  

To change the interface language, follow these steps:

1. Log in as an **[!UICONTROL Admin]**.
2. Go to **[!UICONTROL Profile Settings]** > **[!UICONTROL Interface Language]**.
3. Select **[!UICONTROL Hindi]** as an interface language.


## Profanity check for social posts

Adobe Learning Manager now blocks social posts in the Learners app that contain prohibited words. This helps keep things professional and compliant, especially in sensitive fields like healthcare.

## Email template optimization

### Email learners when an instructor is assigned

The existing emails **[!UICONTROL You have been added as an Instructor]** and **[!UICONTROL VCProvider Session Details]** have been combined into one email **[!UICONTROL You have been added as a UserType]**. The **[!UICONTROL UserType]** will be either **[!UICONTROL Instructor]** or **[!UICONTROL Organizer]**, based on the user's role. These emails were not available in the UI before. They have now been combined into a single email and added to the UI. Admins can access this template in the **[!UICONTROL Email Template]** section. It will be enabled by default for all new and existing accounts, but admins can disable or enable it from the same section. This email will be sent whenever a session is created and an instructor is assigned, whether it's for sessions like Zoom, Teams, Connect, or other services. 

### Email learners when a session is cancelled

The instructors who are removed from a session will now receive only a session cancellation email. Previously, they received both a cancellation and an update email. Instructors who remain in a session will receive a session update email along with a new invite for the session.

## MS Teams completion criteria

Currently, learners are marked as attended even if they join a Virtual Instructor-Led Training (VILT) session for just a few seconds. With this release, we've introduced completion criteria for Teams modules to ensure more accurate attendance. Authors can now set a minimum time that learners must spend in a VILT session for their attendance to be counted.

This is a backend feature that is disabled by default. Please contact your CSM to have it enabled.

## Migration changes

The following changes are made in the migration workflow:

* Migrate modules into specific folders.
* Added completion criteria for modules.
* Added completion criteria for courses

### Changes in modules migration

When you migrate modules into ALM, they will be saved in the public folder by default. In this release, we added a new column called `folder` in the [module_version.csv](assets/module_version.csv) file. Admins can use this column to specify the folder name where the modules should go after migration. Admins can also place a single module into multiple folders by listing the folder names separated by commas. 

The folder column uses the string data type and it is an optional column. The following are the conditions for the folder column:

* The folder name you add should be an existing content folder in the ALM account.
* The values should be a comma-separated string.
* If you add a new folder name for a module already present in a different folder, the new value will not overwrite or replace the assigned folder. The module will be added to the new folder and remain available in the existing folder as well.
* If the value is blank, the folder will default to **[!UICONTROL Public]**.

Refer [module_version csv spec](assets/4-module_version.xlsx) file for more information.

### Changes in modules migration - completion criteria

Admins can specify the completion criteria of the modules during module migration. In this release, we added a new columns `completionCriteria`, `viewPercent` and `quizData` in the [module_version.csv](assets/module_version.csv). 

Following are the conditions for the new columns:

1. `completionCriteria`: 

    * The data type should be a string values and supported values are:
      * `LAUNCH_CONTENT`
      * `VIEW_PERCENT`
      * `QUIZ`
      * `MARK_COMPLETE`
    * Add completion criteria at the module level only for self-paced module types.
    * The supported values for static content are `LAUNCH_CONTENT` and `VIEW_PERCENT`.
    * The supported values for interactive content are `LAUNCH_CONTENT`, `VIEW_PERCENT`, and `QUIZ`.
    * The supported values for HTML5 content are `LAUNCH_CONTENT` and `MARK_COMPLETE`.

2. `viewPercent`:

   * The data type for this column should be an integer, and the value must be between 0 and 100.
   * When completionCriteria is set to `VIEW_PERCENT`, enter the required view percentage in this column or leave it blank.

3. `quizData`:

   * The data type should be a string values and supported values are `QUIZ_ATTEMPTED`, `QUIZ_PASSED`, and `QUIZPASSED_OR_LIMITREACHED`.
   * When `completionCriteria` is set to `QUIZ`, enter the appropriate quiz value in the `quizData` column.

Refer [module_version csv spec](assets/4-module_version.xlsx) file for more information.

### Changes in course migration – Completion criteria

Admins can specify the completion criteria for the courses during course migration. In this release, we added a new column called `completionCriteria` in the [course.csv](assets/course.csv).

Following are the conditions for the `completionCriteria` column:

* The data type should be either string or number, and it is an optional field.
* The values should be `ALL`, `X`, and `SELECTEDMODULES`.
* X is an integer value that should be greater than 0 and less than the total number of modules.
* If you set `completionCriteria` to `SELECTEDMODULES`, you need to mark the mandatory modules in the [course_module.csv](assets/course_module.csv) file.
* In the `optionalCriteria` column, enter `TRUE` or `FALSE`. If you set the value as `TRUE` will make the module mandatory.

Refer [course csv spec](assets/3-course.xlsx) and [course_module csv spec](assets/6-course_module.xlsx) file for more information.

## API changes

The following are the API changes:

* **Search API**:
   * New mode filter with options: classicSearch and advanceSearch.
   * New loMetadata option for snippetTypes.
* **Announcement API**:
   * Includes altText attribute for masthead descriptions.
* **Instance APIs**:
   * New locale attribute to retrieve locale details.
* **Profanity Check**:
   * Updated APIs to check for prohibited words in comments and replies on social posts: 
* **RPM and Burst Limitation**:
   * Added RPM (Requests Per Minute) and burst limits for all APIs.
* **Badge APIs**:
   * New attribute externalProvider to retrieve information about external badges.
* **Job API**:
   * Download User Group Report and Custom Role Audit Report using the Job API.

### Changes in search API

The search API now has a new mode filter with two options: `classicSearch` and `advanceSearch`. There's also a new `loMetadata` option for `snippetTypes`. To get the best results, include `loMetadata` in `snippetTypes` when using `advanceSearch` mode.

### Changes in announcement API

The `GET /announcements API` now includes the `altText` attribute to provide the masthead description.

#### Sample request using cURL:

```
curl -X GET --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 12345678' 'https://abcd.adobe.com/primeapi/v2/announcements/123456'
```

#### Sample response:

```
{
  "links": {
    "self": "https://abcd.adobe.com/primeapi/v2/announcements/123456"
  },
  "data": {
    "id": "12345",
    "type": "adminAnnouncement",
    "attributes": {
      "actionUrl": "google.com",
      "announcementType": "MASTHEAD",
      "expiryDate": "2038-01-19T03:14:07.000Z",
      "liveDate": "2024-07-31T11:11:30.000Z",
      "contentMetaData": [
        {
          "contentType": "IMAGE",
          "contentUrl": "https://abcd.adobe.com",
          "locale": "en-US",
          "altText": "Moonlight - english changed new",
          "thumbnailUrl": "https://abcd.adobe.com/"
        },      ]
    }
  }
}
```

### Changes in instance APIs

The new `locale` attribute has been added to the following APIs to retrieve locale details. 

* `GET /learningObjects/{loId}/instances/{loInstanceId}`
* `GET /learningObjects/{id}?include=instances,enrollment.loInstance`
* `GET /learningObjects?include=instances,enrollment.loInstance`
* `GET /learningObjects/{id}/relatedLOs?include=instances,enrollment.loInstance`
* `POST /learningObjects/query?include=instances,enrollment.loInstance`
* `POST /search/query?include=model.instances`
* `GET /search?include=model.instances`

#### Sample request using cURL:

```
curl --location 'http://abcd.com/primeapi/v2/learningObjects/course:1234567/instances/course:1234567_1234567' \
```

#### Sample request:

```
{
    "links": {
        "self": "http://abcd.com/primeapi/v2/learningObjects/course:1234567/instances/course:1234567_1234567"
    },
    "data": {
        "id": "course:1234567_1234567",
        "type": "learningObjectInstance",
        "attributes": {
            "dateCreated": "2024-02-27T09:21:25.000Z",
            "isAET": false,
            "isDefault": true,
            "isFlexible": false,
            "locale": "en-US",
            "state": "Active",
            "localizedMetadata": [
                {
                    "locale": "en-US",
                    "name": "Default instance"
                }
            ]
        },
        "relationships": {
            "learningObject": {
                "data": {
                    "id": "course:1234567",
                    "type": "learningObject"
                }
            },
            "loResources": {
                "data": [
                    {
                        "id": "course:123456_1234567_1234567_1",
                        "type": "learningObjectResource"
                    }
                ]
            }
        }
    }
}
```

### Public API changes for profanity check

The following APIs have been updated to perform profanity checks for comments and replies on social posts. 

* `POST /boards/{id}/posts `
* `PATCH /posts/{id}`
* `POST /posts/{id}/comments`
* `PATCH /comments/{id}`
* `POST /comments/{id}/replies` 
* `PATCH /replies/{id}`

If a restricted word is found in the post, the following response will be sent.

#### Sample response:

```
{
  "status": "FORBIDDEN",
  "title": "BAD_WORD_FOUND",
  "source": {
    "info": "Unacceptable word found in post"
  }
}
```

### Changes in RPM and burst limitation

In this release, RPM (Requests Per Minute) and burst limits have been added for all APIs. The maximum RPM for each API can be checked on the Swagger page.

RPM is the number of requests you can send to the API server in one minute. The burst limit allows a higher number of requests for a short time, going beyond the usual rate limit. For example, the `learningObject` API allows a maximum of 15 requests per minute. If this limit is exceeded, the API will return an error message.

### Changes in badge APIs

The new attribute `externalProvider` has been added to the following APIs to retrieve information about external badges including badge ID and provider name.

* `GET /badges `
* `GET /badges/{id}`
* `GET /skills?include=levels.badge`
* `GET /skills/{id}?include=levels.badge`
* `GET /learningObjects/{loId}/instances/{loInstanceId}?include=badge`
* `GET /users/{userId}/userBadges`
* `GET /users/{userId}/userBadges/{id}`

#### Sample request using cURL:

```
curl -X GET --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 123456789' 'https://abcd.adobe.com/primeapi/v2/badges/44'
```

#### Sample response:

```
{
  "links": {
    "self": "https://abcd.adobe.com/primeapi/v2/badges/44"
  },
  "data": {
    "id": "44",
    "type": "badge",
    "attributes": {
      "imageUrl": "https://abcd.com/accountassets/1/badges/download.png",
      "name": "external badge",
      "state": "Active",
      "externalProvider": {
        "id": "1234sjd-b272-4de1-9b60-1234567",
        "provider": "credly"
      }
    }
  }
}
```

### Download user group and custom role audit reports via job API

User can download the **[!UICONTROL User Group Report]** and **[!UICONTROL Custom Role Audit Report]** using the `Job API`.

#### Sample request for User Group Report download:

```
curl -X POST --header 'Content-Type: application/vnd.api+json;charset=UTF-8' --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 12345678' -d '{ \ 
     "data": { \ 
         "type": "job", \ 
         "attributes": { \ 
             "jobType": "generateUserGroupReport" \ 
         } \ 
    } \ 
 }' 'https://abcd.adobe.com/primeapi/v2/jobs'
```

#### Sample request for Custom Role Audit Report download:

```
curl -X POST --header 'Content-Type: application/vnd.api+json;charset=UTF-8' --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 1234567' -d '{
    "data": {
        "type": "job",
        "attributes": {
            "description": "description of your choice",
            "jobType": "generateCustomRoleAuditReport",
            "payload":{
                 "fromDate": "2020-01-01T18:30:00.000Z",
                 "toDate": "2024-09-31T18:30:00.000Z",
                 "locale":  "en-US"
            }
        }
   }
}
```

### Error messaging for no request body

We have introduced specific error messages for cases where the request body is mandatory but not supplied in the API. 

#### Sample error message:

```
{
    "status": "BAD_REQUEST",
    "title": "Generic Error"
}
```

## Reporting enhancements 

Admins can find these reporting changes in the **Admin** > **Reports** section.

### Learning Transcripts report 

The **[!UICONTROL Learning Transcripts]** report will contain two new columns: 

* **[!UICONTROL Module ID]**: Displays the unique identifier for each module. This new column has been added after the existing **[!UICONTROL Module]** column.
* **[!UICONTROL Course Instance ID]**: Displays the unique identifier for each course instance.This new column has been added after the existing **[!UICONTROL Instance]** column.
* **[!UICONTROL Completion Comment]**: This column captures the comments entered by the admin when marking user completion. This new column has been added at the end of the report.


### Session Summary report 

The **[!UICONTROL Session Summary]** report will contain three new columns: 

* **[!UICONTROL Module ID]** column has been added before the **[!UICONTROL Session Name]** column.
* **[!UICONTROL Session ID]** column has been added before the **[!UICONTROL Session Name]** column.
* **[!UICONTROL Course Instance ID ]** column has been added after the **[!UICONTROL Instance Name]** column.
* **[!UICONTROL Completion Count]** column has been added after the **[!UICONTROL Enrollment Count]** column.

## Bugs fixed in this update

* Fixed the error that occurred while uploading videos from the activity module during file submission on Android and iOS devices.
* Fixed the issue with opening courses on the mobile app; the web version is functioning correctly.
* Fixed the problem with viewing Job Aids and other resources in Safari.
* Fixed the issue that prevented users from downloading Job Aids on the mobile app.
* Fixed the error in the documentation for Patch User API.
* Fixed the issue where organizers were not receiving email notifications when a session was deleted from the course.
* Fixed the issue where organizers do not receive session cancellation emails when a module is removed from the course and republished.
* Added support for including special characters "+" and "-" in email addresses during external user creation.
* Fixed the issue where the Marketo connector unified report sync fails, if the user skill report contains double quotes in the CSV record value
* Fixed the issue where the `/skills` endpoint returns the correct state for the Admin API, but the Learner API consistently shows incorrect or cached data.
* Fixed the issue with Go1 onboarding for freemium courses failing when the account does not have the Go1 connector set up.
* Fixed the issue where courses in the Learning Path (LP) are not accessible via migration if the learner has already completed the LP.
* Fixed the issue where the incremental user CSV fails when both the user's manager and skip-level manager are set as SU (Super User) instead of admin and are not included in the CSV.
* Fixed the scope issues for store managers in dashboard reports.
* Fixed the issue where xapi_iri was not being removed when a draft course was deleted.
* Fixed the issue that prevented the addition of a Unique LO ID in certain scenarios.
* Fixed the issue where the IsEmbeddable property in the learning plan was not updating correctly in shared learning plans.
* Fixed the issue affecting the total duration display of Learning Paths in the Learner view.
* Fixed the issue allowing learners to register or sign up via Self-Registration Links even after their accounts have been deleted.
* Fixed the issue where `www`was being removed when adding links in the course description during course creation.
* Fixed the issue where the hide information and download Job Aids was not functioning properly.
* Fixed the issue where Single Sign-On (SSO) was not functioning for new users added via the self-registration link with an IP ID.
* Fixed the issue where notification message data was not being fetched after an announcement was deleted.
* Fixed the issue of insufficient search results when searching for users by email.

## System requirements

View [Adobe Learning Manager system requirements](/help/migrated/system-requirements.md).

## Previous releases of Adobe Learning Manager

* [July 2024 release](/help/migrated/whats-new-july-2024.md)
* [March 2024 release](/help/migrated/whats-new-march-2024.md)
