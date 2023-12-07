---
title: What's new in this release (July 2023)
description: Learn about the new features and enhancements in Adobe Learning Manager
hidefromtoc: yes
---
# What's new in this release (July 2023)

## Improved recommendations

Adobe Learning Manager has introduced a new and revamped recommendation system for courses. This recommendations feature uses AI algorithms and users' interests like Products, Roles, and Levels to provide personalized content recommendations.

For more information, see Recommendations in Adobe Learning Manager.

## Multi-enrollment

In this release of Adobe Learning Manager, we are introducing multi-enrollment for learners that allow learners to enroll in more than one instance of a course at one or different time periods. 

For more information, see [Multiple enrollments](/help/migrated/authors/feature-summary/courses.md).

### Multi-enrollments in mobile app or immersive

Learners cannot enroll in multiple instances from a mobile app/immersive. Multi-enrollment isn't supported in mobile app and immersive mobile web.

>[!NOTE]
>
>Enabling Multi-Enrollment results in multiple rows being added to the Learner Transcript Report for each course (one row for each instance).
>
>If you've reporting automation set up that anticipates only one row per course, you must make the necessary adjustments to the reporting automation before enabling the Multi-Enrollment feature.

### Format of badges in a multi-enrolled instance

To support badges in a multi-enrolled instance, the badge format is changed to `userId_badgeId_COURSE_courseId_courseInstanceId`.

### Launch player in multi-enrollment using a headless mode

In this release, we have changed the library used for communication with the headless player.

In multi-enrollment, you must pass the arguments wrapped inside an object.

```
{{startplayer(argument_object) ,
where
argument_object=
{ loId = <loId>, accountId = <accountId>, userId =<userId>, accessToken = <accessToken>, domId = <elementId>, onModuleLoaded = fn(), isMultiEnrolled=<boolean>, instanceId=<instanceId> }
}}
```

## Deprecation of exavault connector

This release of Adobe Learning Manager will include a new connector, which will use AWS Transfer family's SFTP protocol. 

This change will also replace the ExaVault connector, which will no longer be available for new users. You may use any open-source FTP client as a replacement for ExaVault. For more information, see Transition from Adobe FTP Manager.

## Reminders in outlook for classroom and virtual sessions

Classroom and Virtual Classroom sessions created from Adobe Learning Manager that have been added to the learner's Outlook calendar will now support reminders from Outlook consistently (similar to meeting reminders in Outlook).

## Enhancements to assigning skills to courses

We've made enhancements to the Skill assignment workflow for Authors. The Skills suggestions list on the course Settings page now includes a typeahead search capability. Authors can now search for Skills by typing the first few characters, and suggestions will be displayed in the Skill drop-down list based on the input. With this enhancement, Authors need not scroll through the complete list to find and assign skills to courses.

## Manager-approved course workflow improvements

Manager-approved courses now provide appropriate error information to both managers and learners.

![error messages](assets/error-messages.png)

Managers can now view relevant error messages with information (for example, the enrollment deadline has passed) when they cannot approve a course enrolment request. Learners are shown the error and the remedial action.

## New learning plan report

Admins/custom admins can now export a list of all Learning Plans in the account and metadata such as status, applicable user groups, trigger information, courses/learning paths included within the learning plan, and reminder information.

## Report to track upcoming retired instances

The Trainings Report includes an additional column to display the Completion Deadline of the instances present in the courses or Learning Paths so that admins and authors know which instances will be retired and can take necessary action.

## Enhancements to capture course ratings from learners

A pop-up to capture the star rating for a course displays as soon as the user completes the last module in the course.

![ratings](assets/ratings.png)

## Customize email templates

Email templates in Learning Manager now include fully editable sections, providing greater flexibility to customize email communications based on messaging and branding preferences.

For more information, see [Customize email template](/help/migrated/administrators/feature-summary/email-templates.md).

## Enhancements to scheduling assistant

Fine-tune the process of selecting an instructor for classroom or virtual sessions. A User Group filter has been added to the Instructor field in the Scheduling Assistant. Authors can now filter instructors based on 'Instructor Skills' and any additional parameter such as location, language, designation, and so on.

<!--
There is no User Group Filter section on this page: help/migrated/authors/feature-summary/courses.md

For more information, see User Group filter in Scheduling Assistant.
--> 

## Enhancements to the learning object retiring workflow

Authors can now provide an **Auto Retire** date for a course. This helps prevent catalog inflation over time and the need to go back and manually retire the courses.

Admins can also decide at an account level the nature of access to 'retired' learning objects.

The Training Report includes a new column, **Auto Retirement Date**, to display the retirement date for each learning object (if set).

## Catalog label values by authors

Authors can now add their values for catalog labels while creating or editing a course. Admins can enable this feature at an account level. After an author adds a new catalog label value, it becomes part of the typeahead search.

![select catalog](assets/select-catalog.png)

## Enhancements to course search for admin, author, and manager roles

Search enhancements have been made for admin, author, and manager roles. They will now be able to search with keywords for the titles. This applies to Courses, Learning Paths, and Certifications.

## Notifications for migration failures

Integration Admins are notified via email if any import or export operations fail during the migration or while using data connectors such as PowerBI, FTP, Box, etc.

## Multi-manager configuration through APIs

A new API has been added to the Managed Office set of APIs to support multi-manager configuration.

## Enhancements to the enrollment API

Enhancements have been made to the Enrolment API to support and optimize large-scale bulk enrolments.

## Mobile app - Offline content viewing

Learners can download and consume content in offline mode. Nested and flexible Learning Paths are not supported for offline viewing.

*In this release, offline content viewing is supported for only English content.*

## Accessibility

Multiple improvements have been implemented to enhance accessibility, including enhancements to optimize readability by screen readers.

## Mobile app support

With the next major release, Adobe Learning Manager mobile app will support only the three most recent mobile OS versions.

## Content on LinkedIn

LinkedIn content does not load as expected on the Immersive app on the Safari browser. As a workaround, do the following:

1. On the device, select **Settings** > **Safari**.
1. Disable **Prevent Cross-Site Tracking**.
1. Disable **Block all cookies**.
1. Log in to the Immersive app.
1. Play the content.
1. Allow the pop-ups.

## Other enhancements

### Switch instances in MS Teams

A learner can switch to a different course instance until its completion and retain the course progress.

### Multi-enrollment support in MS Teams

A learner can enroll in another course instance irrespective of completion status on any previous instances. Doing so will make the learner enroll in multiple instances of the same course.

### Course notes support multi-enrollment in MS Teams

Course notes are available at a course-instance level to support multi-enrollment.

## API changes

For more information on the API changes, see the [Adobe Learning Manager API reference](https://captivateprime.adobe.com/docs/primeapi/v2/).

### API support for new recommendations

**GET /account**

Returns if prlRecommendation is enabled.

**Request**

`https://learningmanagerstage1.adobe.com/primeapi/v2/account`

**GET /data?filter.recommendationCriteria=product**

Returns list of Products/Topics. Results depend on account settings which confirm if all products will be visible to the learner or catalog visible to products/topics.

**Request**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=product&filter.showAllRecommenda`

**`GET /data?filter.recommendationCriteria=role`**

Returns list of recommended Roles. 

**Request**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=role&filter.showAllRecommendationCriteria=false`

**`GET /data?filter.recommendationCriteria=level`**

Returns list of recommended Roles. 

**Request**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=level&filter.showAllRecommendationCriteria=false`

**POST /search/query**

The search also includes products and role parameters in query. There is no change in query and body. We will add new sorting options 

**Request**

`https://learningmanagerstage1.adobe.com/primeapi/v2/search/query?...`

**GET /learningObjects**

The Learning Object model returns author-tagged recommendations if the PRL recommendation is live.

**Request URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/learningObjects?sort=recommendationScore&filter.recommendationProducts=...&filter.recommendationRoles=...&filter.excludeIgnoredRecommendations=true`

POST /learningObjects/query

The following attributes are supported in body of query call:

```javascript {line-numbers="true"}
{
  "filter.announcedGroups": [
    "string"
  ],
  "filter.bookmarks": true,
  "filter.catalogIds": [
    "string"
  ],
  "filter.cityName": [
    "string"
  ],
  "filter.duration.range": [
    "string"
  ],
  "filter.effectiveModifiedDate.fromDate": "string",
  "filter.effectiveModifiedDate.toDate": "string",
  "filter.excludeIgnoredRecommendations": true,
  "filter.ignoreEnhancedLP": true,
  "filter.ignoreHigherOrderLOEnrollment": true,
  "filter.lang.subLOs": true,
  "filter.lang.twoLetterCode": true,
  "filter.learnerState": [
    "string"
  ],
  "filter.loFormat": [
    "string"
  ],
  "filter.loTypes": [
    "string"
  ],
  "filter.price": "string",
  "filter.priceRange": [
    "string"
  ],
  "filter.recommendationLevels": [
    "string"
  ],
  "filter.skill.level": [
    "string"
  ],
  "filter.skillName": [
    "string"
  ],
  "filter.tagName": [
    "string"
  ],
  "language": [
    "string"
  ],
  "preferredSortPartitionOrder": [
    "string"
  ],
  "showLoContentSource": true,
  "useCache": true,
  "filter.recommendationProducts": [
    {
      "levels": [
        "string"
      ],
      "name": "string"
    }
  ],
  "filter.recommendationRoles": [
    {
      "levels": [
        "string"
      ],
      "name": "string"
    }
  ]
}
```

**GET /recommendationProducts**

Retrieves PRL product by recommendationProduct Id. 

**Request URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationProducts`

GET /recommendationRoles

Retrieves PRL product by recommendationProduct Id. Only visible roles of (Learning Objects) will be returned.

**Request URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/prlRecommendations/roles`

`POST /users/{id}/recommendationPreferences`

Creates / Re-Create (Override) PRL recommendation Preferences. Sample payload:

```javascript {line-numbers="true"}
{
    "data": {
        "id": "userRecommendationPreferences:14755328",
        "type": "userRecommendationPreferences",
        "attributes": {
            "products": [
                {
                    "id": "recommendationProduct:1",
                    "dateCreated": "2023-05-07T20:00:00.000Z"
                },
                {
                    "id": "recommendationProduct:37",
                    "dateCreated": "2023-05-07T21:00:00.000Z"
                }
            ],
            "roles": [
                {
                    "id": "recommendationRole:23",
                    "dateCreated": "2023-05-07'T'21:00:00.000'Z'"
                },
                {
                    "id": "recommendationRole:1",
                    "dateCreated": "2023-05-07'T'20:01:00.000'Z'"
                },
                {
                    "id": "recommendationRole:2",
                    "dateCreated": "2023-05-07'T'19:02:00.000'Z'"
                },
                 {
                    "id": "recommendationRole:3",
                    "dateCreated": "2023-05-07'T'18:02:00.000'Z'"
                },
                {
                    "id": "recommendationRole:20",
                    "dateCreated": "2023-05-07'T'17:02:00.000'Z'",
                    "levels": [
                        "INTERMEDIATE"
                    ]
                }
            ]
        }
    }
}
```

**`GET /users/{id}/recommendationPreferences`**

**Request URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2//users/123/recommendationPreferences`

**`DELETE /users/{id}/recommendationPreferences`**

Deletes PRL recommendation user preferences for a product or role.

**Request URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/users/123/recommendationPreferences?ids=recommendationRole:123,recommendationRole:234`

Params :

Ids = List of ids to delete

**PATCH /users/{id}/recommendationPreferences**

Partial Addition / Updation. Sample payload:

```javascript {line-numbers="true"}
{
  "data": {
    "id": "userRecommendationPreferences:<USER_ID>",
    "type": "userRecommendationPreferences",
    "attributes": {
      "roles": [
        {
          "id": "recommendationRole:123",
          "type": "recommendationRole",
          "attributes": {
            "levels": [
              "INTERMEDIATE"
            ]
          }
        },
        {
          "id": "recommendationRole:123",
          "type": "recommendationRole",
          "attributes": {
            "levels": [
              "ADVANCED"
            ]
          }
        }
      ]
    }
  }
}
```

**POST /recommendationPreferences/learningObjects/{id}/ignore**

Add LO to blocked recommendations.

**Request URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationPreferences/learningObjects/{id}/ignored`

**`DELETE /recommendationPreferences/learningObjects/{id}/ignore`**

Deletes LO from blocked recommendations.

**Request URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationPreferences/learningObjects/{id}/ignored`

**`GET /users/{id}/recommendationStrips`**

Retrieves all strips to be used to show prl recommendations

### Multi enroll support for API

**GET /primeapi/v2/account**

Two new attributes are added :

* instanceSwitchEnabled
* multiEnrollmentEnabled

**GET /users/{userId}/userNotifications**

Added course instance id in notifications in the new metadata attribute. 

**GET /learningObjects**

The enrollment relationship displays only primary enrollment, i.e., first enrolled or first completed.

**`GET /learningObjects/{id}`**

The enrollment relationship displays only primary enrollment, i.e., first enrolled or first completed.

**`GET /learningObjects/{loId}/instances/{loInstanceId}`** 

A new relationship is added to the LO instance model.

**`GET /enrollments/{id}`**

Retrieve enrollment of multi-enrolled courses.

**`DELETE /enrollments/{id}`**

Unenrolls from a particular learning object instance.

**POST /enrollments**

Supports enrollment in different instances.

**GET /enrollments**

Gets enrollments for only primary enrollments for the Learning Object.

**`GET /learningObjects/{id}/note`** 

Retrieves a list of notes for a course.

**`GET /learningObjects/{lo_id}/instances/{loi_id}/note`**

Retrieves a list of notes for a course and the instance.

**`GET /learningObjects/{id}/resources/{loResourceId}/note`** 

Retrieves a list of notes for a resource in a course.

**`POST /learningObjects/{id}/resources/{loResourceId}/note`** 

Adds a note in a module for a course for a given course.

**`DELETE /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`** 

Deletes specific notes from a given module against a specific instance (part of loResource Id).

**`GET /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`** 

Retrieves a specific note in a module in a course for a given instance (part of loResourceId).

**`PATCH /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`** 

Updates specific notes from a given module against a specific instance (part of loResource Id).

**Admin API changes**

* GET /users/{id}/enrollments
* POST /users/{id}/enrollments 
* DELETE /users/{id}/enrollments/{enrollmentId} 
* PATCH /users/{id}/enrollments/{enrollmentId}

### Enforcedfields for endpoints

Products and Roles are loaded only when enforced.

Example request

* GET `https://learningmanagerstage1.adobe.com/primeapi/v2/learningObjects/course%3A7418798?enforcedFields[learningObject]=products`
* GET `https://learningmanagerstage1.adobe.com/primeapi/v2/users/11255638/userBadges?include=model&page[offset]=0&page[limit]=10&sort=dateAchieved&enforcedFields[learningObject]=products,roles`

### Search API changes stemming implementation (English locale)

Stemming is the process of reducing a word to its root form. This ensures variants of a word match during a search. For example, walking and walked can be stemmed to the same root word: walk. Once stemmed, an occurrence of either word would match the other in a search.

In this release, we've added stemming for English locales, which includes the following variants - en_US, en_AU, en_GB. 

The stemmed attribute mentions if stemming is required in search results. This is by default set to False

### Removal of V1 endpoints

V1 APIs will stop working in this release. For more information, see the [Developer manual](/help/migrated/integration-admin/feature-summary/developer-manual.md).

### Notifications for course enrollment or unenrollment

This release introduces support for course instance id with notifications in the new metadata attribute.

### L1 feedback support

Enables the learner to provide feedback at each instance level of the Multi Enrollment feature.

**API:** `POST /enrollments/{id}/l1Feedback`

### LO enforced field list

In this release, you must send sections,  prequisiteConstraints, prerequisiteLOs, subLOs,  supplementaryResources, supplementaryLOs, instances, catalogLabels to the learningObject explicitly.

For example,  

`enforcedFields[learningObject]=prerequisiteLOs,instances`

### Deprecation notice for the next release

* Override flag for Learner APIs.
* We'll change the default for highlightResults=false. Also, we'll change the default of snippetType=courseName.
* We'll deprecate matchType=bool in the search endpoint.
* autoCompleteMode has the [Deprecated] tag and to provide the same functionality of autoCompleteMode =false, we have a matchType added called Match.

### Badge id format with multi enrollment

To support multi-enrolled instance badges, we are changing the format of course badges from `userId_badgeId_COURSE_courseId to userId_badgeId_COURSE_courseId_courseInstanceId` to uniquely identify badges. 

## Release Notes

For information regarding current and previous releases of Learning Manager web app and device app, see the [Release notes](/help/migrated/release-note/release-notes.md).

## Known issues or limitations in this release

The following are the limitations of this release:

### Viewing offline content in the mobile app

The following are not supported while viewing offline content in the app:

* Flex Courses, Learning Plans, or Certifications.
* Enhanced Courses, Learning Plans, or Certifications.
* Multi-quiz enabled-Courses, Learning Plans, or Certifications.
* Harvard Manage Mentor, Content Marketplace, GetAbstract, or LinkedIn Courses, Learning Plans, or Certifications.
* Learning Plans and Certificates with pre-requisites enabled.
* Retired Courses, Learning Plans, or Certifications.
* Courses, Learning Plans, or Certifications whose deadline has expired.
* External Certificates.
* eCommerce-enabled Courses, Learning Plans, or Certifications.

The following Learning Paths, Courses, or Certifications have a few issues with offline sync:

* All Learning Paths.
* All internal certificates.
* Content with POST calls.

### Recommendations

The following are not supported for Product/Role/Level in the new recommendation system:

* Adobe Experience Manager, Teams, SFDC, and Non-logged in.
* The mobile app does not support editing Products and Roles on the Recommendation page.
* The mapping isn't possible during migration.
* Auto-tagging LinkedIn, Content marketplace, and other external Courses, Learning Plans, or Certifications.
* Reverting to Skill-based or Classic after going live.
* The search menu for Products and Roles on the Learner app.
* Bulk mapping of Courses, Learning Plans, or Certifications, and Users on the Admin app.

## System Requirements

[Learning Manager system requirements](/help/migrated/system-requirements.md)
