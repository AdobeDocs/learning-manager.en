---
description: Learn about the new features and enhancements in the October 2025 release of Adobe Learning Manager
jcr-language: en_us
title: What's new in Adobe Learning Manager October 2025 release
---

# What's new in Adobe Learning Manager October 2025 release

The Adobe Learning Manager October 2025 release introduces significant enhancements designed to improve reporting accuracy, expand integration capabilities, and enhance the learning experience for administrators, authors, and learners.

* Experience Builder: Design fully branded, role-based learning portals tailored to your organization's needs. Create branded, role-based learning portals with widgets, menus, and pages.
* Social tagging in learning boards: Learners can now tag peers using @username in posts and comments, enabling targeted collaboration and notifications within social learning communities.
* Scoped announcement permissions: Custom administrators can create announcements limited to their assigned user groups or catalogs, ensuring targeted communication and reducing information overload.
* Language-based progress tracking: Learner progress is now saved independently for each locale, allowing seamless switching between languages without losing progress.
* Incremental custom role management: Administrators can now manage custom roles more efficiently with support for incremental and multi-incremental imports in Adobe Learning Manager.
* Enhanced APIs for analytics and migration: New and improved APIs provide better quiz performance tracking, migration status monitoring, and support for user tagging in social learning.

## Experience Builder

Experience Builder is a no-code/low-code tool in Adobe Learning Manager that helps you create customized learning portals. It allows you to design branded, user-friendly learning portals without needing technical skills or extensive coding knowledge.
With Experience Builder, you can create new pages, menus, and widgets to deliver personalized learning experiences for your audience quickly and easily. With Experience Builder, you can quickly create new pages, menus, and widgets to deliver personalized learning experiences for your audience.

Before Experience Builder, organizations faced several challenges:

1. **Limited customization**: Portals had fixed designs with few options to reflect your brand. Administrators could only make basic changes, such as modifying headers, footers, or colors, which limited the ability to create unique experiences.
2. **Cost**: Building custom portals required expensive developers and long timelines, often taking 6 to 9 months to complete. This approach increased the total cost of ownership and delayed deployment.
3. **Generic experiences**: Everyone saw the same content, even if it wasn't relevant to their role or needs. This lack of personalization reduced learner engagement and satisfaction.
4. **Technical barriers**: Non-technical administrators struggled to create or update portals because they needed coding knowledge or external support.

Experience Builder solves these problems by providing a simple, no-code/low-code solution for creating personalized, branded portals.

It allows administrators to design portals that meet their organization's needs without relying on technical expertise or external developers.

**Use cases**

* **Branded portals**: Create a portal that matches your company's website with logos, colors, and layouts. For example, a healthcare company can design a portal that reflects its corporate branding while delivering learning content.
* **Role-based learning**: Build pages tailored to specific roles. Sales teams can view product training, while engineers access technical courses.
* **Product training**: Set up dedicated pages for different products, such as Photoshop or Illustrator, with widgets displaying courses, certifications, and related resources.

## Language-based learner progress

Currently, the Adobe Learning Manager tracks learner progress only for the selected locale language, causing significant progress loss when switching languages/locales in the player. This limitation can lead to a poor user experience, as learners may lose their progress when accessing content in different languages. The progress for each module in the player is tracked at both the user and module levels. This leads to a situation where a user's progress is overridden when they switch back to a previously used locale for the same module.

For example, if a learner achieves 75% progress in locale A (English) and then switches to locale B (Spanish), upon returning to locale A, their progress resets to 0% instead of resuming from 75%.

>[!NOTE]
>
>Video content does not support language-based progress tracking.

To resolve these limitations, the feature has been enhanced to support locale-specific progress tracking:

* **Locale-specific storage**: When a learner switches locales (for example, from Locale A to Locale B) within the player, the Adobe Learning Manager now saves the progress state separately for each locale of the content.
* **Progress resumption**: When the user switches back to a previously used locale (from Locale B back to Locale A), the content resumes from where they left off in that specific locale.
* **Independent progress tracking**: Each locale maintains its own state of progress, allowing learners to explore content in multiple languages without losing their individual progress in each language.

View [My Learning](/help/migrated/learners/feature-summary/courses.md#language-based-progress-management) for more information on language-based learner progress.

## Incremental and multi-incremental support for custom roles

Adobe Learning Manager now supports incremental and multi-incremental imports for custom roles and role assignments. With incremental imports, administrators can upload only new, updated, or deleted records of the users instead of re-uploading the entire CSV file.

Multi-incremental imports extend this capability by allowing large organizations to split incremental files by region or department (for example, US, EU, APAC) and process them in parallel. Adobe Learning MAnager also supports up to 20 incremental user CSVs and their corresponding custom roles CSVs, making it scalable for large operations.

Administrators can now upload role and user-role files (role.csv and user_role.csv) incrementally, along with user files (user.csv), instead of always doing full uploads.Each user import (user1.csv) is linked with its own role and role-mapping files (user1_role.csv, user1_user_role.csv), stored in separate FTP folders.

Following three additional columns have been added to the following CSVs:

* User Registration State (user.csv): Indicates the current registration status of the user in the system (for example, active, inactive, or deleted).
* Role State (role.csv): Indicates whether a custom role is currently active or inactive in the account.
* User Role State (user_role.csv): Defines the status of the mapping between a user and a role, showing if the assignment is active or has been removed.

The Adobe Learning Manager now captures add, update, and delete actions in the user audit and custom role reports, giving administrators better visibility into changes.

>[!NOTE]
>
>These changes are applicable only to the accounts that use incremental users.

View [Incremental and multi-incremental support for custom roles](/help/migrated/integration-admin/feature-summary/configure-role-csv-files.md#incremental-and-multi-incremental-support-for-custom-roles) for more information on incremental and multi-incremental support for custom roles. 

## Go1 integration enhancements

Go1 integration is enhanced to allow direct curation of Go1 courses for creating Learning Programs (LP) within Adobe Learning Manager. This update supports the inclusion of Go1 courses in recurring certifications and introduces a new version of the Go1 content hub experience, enabling more efficient course curation.

**What's new**

* Create and manage playlists directly within Go1 using AI chat assistance or manual selection.
* Include Go1 courses in recurring certification cycles with automatic progress reset. View [Certifications](/help/migrated/administrators/feature-summary/certifications.md) for more information on creating certificates. 
* Upgraded content discovery interface for improved browsing and content curation.

**Important notes**

* All Go1 features require an active Go1 license.
* Previous free Go1 content will be decommissioned. Organizations must preview and purchase required content bundles.
* Administrators and authors can create and manage playlists; learners maintain view-only access.

View [Add Go1 playlist to the learning path](/help/migrated/administrators/feature-summary/content-marketplace/add-go1-playlist.md) for more information on adding Go1 courses to the learning path. 

## Support for vimeo URLs in Activity Module

The Activity module now supports embedding Vimeo URLs, similar to YouTube embeds. This enhancement allows administrators to add Vimeo video links directly into the Activity module. When authors create a course and add an Activity module, they now see an option to include a Vimeo URL. Similar to how YouTube links are added, authors can paste a Vimeo link directly into the module setup. Once published, learners can play the Vimeo video seamlessly within the Learner app without being redirected outside the platform.

View [Add modules](/help/migrated/authors/feature-summary/courses.md#add-modules) article for more information on adding modules to the courses. 

## Time Zone information for CR/VC modules

Time zone details are now displayed for Classroom (CR) and Virtual Classroom (VC) modules on the Course Overview page, Instance page, Learner Preview page, and in calendar widget. Learners and administrators can clearly see the time zone associated with scheduled sessions across key pages and calendar invites. Learners can better plan and join sessions without time zone misunderstandings. This enhancement is available only in the Immersive Learner app.

Learners in different regions can confirm the session time in the correct time zone. Clear time zone visibility helps avoid missed sessions or incorrect calendar planning. 

## Auto-populate the name of the author while creating a course

During course creation, the **[!UICONTROL Author(s)]** field is now automatically populated with the name of the author who is creating the course. Authors no longer need to manually enter their own names. Additional authors can still be added or updated as needed.

For organizations with strict content ownership rules, auto-population ensures the author is always correctly attributed. When editing an existing course, authors can update or add co-authors without losing the auto-populated entry.
 for
View [Create a course](/help/migrated/authors/feature-summary/courses.md#create-a-course---advanced-workflow) for more information on creating a course. 

## Search external profiles while changing profile

Previously, administrators scrolled through the entire list of external profiles and manually selected the desired profile when reassigning learners. This made the process time-consuming, especially for accounts with many profiles. With this enhancement, administrators and custom administrators can now search for external profiles directly in the tab during the change profile workflow. 

**Use cases**

* In accounts with hundreds of external profiles (e.g., franchise locations, partner companies, or regional groups), admins can now locate the exact profile instantly using search, reducing errors and saving time.
* During organizational changes, such as mergers or department realignments, learners may need to be moved in bulk to new external profiles. The search-based reassignment makes this task smoother and more accurate.

View [Change the external profile](/help/migrated/administrators/feature-summary/add-users-user-groups.md#change-profile) for more information on changing the profile. 

## Add a co-organizer for Microsoft Teams sessions

Previously, authors could only assign a single organizer to Microsoft Teams sessions. With this enhancement, administrators can now add co-organizers to a session. A new field, **[!UICONTROL Co-Organizer]**, has been introduced in Microsoft Teams sessions, allowing authors to assign additional organizers alongside the primary organizer. 

Authors can assign multiple co-organizers for each Microsoft Teams session. Co-organizers have the same access and permissions as the primary organizer. Authors can add up to 10 organizers per session, which provides greater flexibility and improves session management.

**Use case**

When conducting large-scale sessions with many learners, co-organizers can help manage attendance, moderate discussions, and monitor chat while the primary organizer focuses on delivering the training.

View View [Add modules](/help/migrated/authors/feature-summary/courses.md#add-modules) article for more information on adding CR/VC sessions to the courses. 

## Download interested learners report

When an administrator retires all course instances (for example, at the end of the course lifecycle), the **[!UICONTROL Enroll]** button on the **[!UICONTROL Course Overview]** page is replaced with a [!UICONTROL Register Interest] option. Learners can select this option to express their interest in taking the course. Administrators can now view and export a list of learners who have registered interest in a course.

Administrators can then access this list and download it as a report. An **[!UICONTROL Interested Learners]** button has been added to the course page when no active instances are available. It displays the learner's name and the date they registered interest in the administrator UI. 

Administrators can select the **[!UICONTROL Actions]** and then select **[!UICONTROL Export Report]** to export the **[!UICONTROL Interested Learners report]**.

![](assets/register-interest.png)
_Course overview section where learners can view the Register Interest option_

View [Download the interested learner](/help/migrated/administrators/feature-summary/courses.md#download-the-interested-learner-report) for more information on Interested Learner report

## Reset recommendations in Salesforce app

Previously, learners using the Adobe Learning Manager Salesforce app could select roles and recommendation preferences only once. If their role changed, they had to switch to the native Adobe Learning Manager app to update their profile and receive relevant course recommendations. With the latest enhancement, learners can now quickly reset their preferences directly within the Salesforce app whenever their job role, team, or responsibilities change. 

This streamlined process ensures they continue receiving updated, relevant course recommendations without leaving Salesforce. Administrators benefit from higher learning completion rates and better alignment between user roles and recommended content, all without providing extra support or guidance on switching platforms.

**What's new**

Adobe Learning Manager now features a  **[!UICONTROL Reset Interests]** button within the Salesforce app. Learners can now reset their roles and learning preferences without needing to leave Salesforce or sign in into the native Adobe Learning Manager app. 

View [Reset recommendations in Salesforce app](/help/migrated/learners/feature-summary/sfdc-app.md#reset-recommendations-in-salesforce-app) for more information on reset recommendations in Salesforce app.

## Calendar widget enhancement

Learners can now see both past and upcoming sessions in the calendar widget. They can move through the calendar to any date and check the session details. This means they can review sessions that have already happened, helping them track what they missed or attended. They can also view all upcoming sessions for the next 12 months, including the current month, making it easier to plan ahead and manage their schedules.

View [Calendar](/help/migrated/learners/feature-summary/learner-home-page.md#calendar) for more information on Calendar widget. 

## Tag users in social boards

Social learning boards now support user tagging functionality, enabling more targeted discussions and improved collaboration within learning communities. Learners can be tagged in social learning posts and comments through the learner app, APIs, and Adobe Learning Manager reference site.

Users outside the board's scope cannot be tagged, preventing unwanted notifications. If a tagged user is deleted from the system, their mention appears as "anonymous". Tagging user groups or "@all" is not permitted to prevent notification spam.

**What's new**

* **@username tagging**: Users can tag other board members using the "@username" format.
* **Scope-restricted tagging**: Only users with access to the specific board can be tagged, ensuring privacy and relevance.
* **Multi-channel notifications**: Tagged users receive both in-app and email notifications with direct links to relevant posts or comments.

**Use cases**

* Healthcare professionals seeking input from specific colleagues on medical cases: Tagging allows doctors and nurses to quickly notify the right specialists, ensuring timely and accurate advice on complex patient cases.
* Subject matter experts being consulted on specialized topics: By tagging experts, teams can directly involve the right people, reducing response time and improving decision-making for technical or niche queries.
* Team discussions requiring input from specific stakeholders: Tagging stakeholders ensures that the relevant decision-makers are aware of updates and can provide input, keeping projects on track and aligned with business goals.

View [User tagging in social learning boards](/help/migrated/learners/feature-summary/social-learning-web-user.md#tag-users-in-social-board-posts) for more information on tagging users in social boards.

## Scoped announcement permissions for custom administrators

Custom administrators can now create announcements, but only for their assigned user groups or catalogs. This prevents unintended communication across organizational boundaries. Custom administrators can only create announcements for users within their assigned scope. Announcements can be scoped to specific user groups or catalogs. Full administrators maintain visibility and control over all announcements, including those created by scoped custom administrators.

**Key benefits**

* Targeted communication ensuring announcements reach only relevant audiences.
* Reduced information overload by preventing irrelevant notifications from reaching unintended users.
* Maintains organizational boundaries and prevents accidental cross-communication.

**Important notes**

* If a custom administrator's scope changes, affected announcements display a warning icon and require individual scope resets.
* Each announcement must be updated individually when scope changes occur.
* The [Notification Announcement](/help/migrated/administrators/feature-summary/announcements.md) report shows only learners within the custom administrator's assigned scope.

**Use cases**

* Franchise organizations where regional managers need to communicate only with their franchisees.
* Large organizations with regional or departmental administrators targeting announcements to their teams.

View [Create announcement for the assigned scope](/help/migrated/administrators/feature-summary/announcements.md#create-announcement-for-the-assigned-scope) for more information on creating announcement for assigned scope.

## Select custom role while publishing a content from Adobe Captivate

When publishing content from Adobe Captivate to Adobe Learning Manager, if a user has multiple custom roles, they will be prompted to select the specific custom role under which the course should be published. This ensures that the correct role ownership and permissions are applied to the published course.

View [Publish a project to Adobe Learning Manager (ALM)](https://helpx.adobe.com/in/captivate/help/publish-projects-adobe-captivate.html#publish-to-alm) for more information on publishing a project to Adobe Learning Manager. 

## Enhancements to the Saved by Me widget

Previously, selecting the **[!UICONTROL Saved By Me]** strip displayed all courses available in the catalog. Now, learners see only their bookmarked courses in the **[!UICONTROL Saved By Me]** strip on the learner homepage. Selecting this strip takes learners to the catalog page, where only the courses they have saved are displayed.

Within the catalog, learners can apply additional filters to refine their search. When a filter is applied, only courses that meet the selected criteria are shown. Previously bookmarked courses appear only if they match the applied filter.

View [Configure saved courses widgets in AEM sites](/help/migrated/integrate-aem-learning-manager.md#configure-my-saved-courses-widgets-in-aem-sites) for more information on saved courses widget in AEM sites.

## Support to display the author names in shared courses

Previously, when a course was shared with a [peer account](/help/migrated/administrators/feature-summary/peer-account.md), the author appeared as External Author. Now, it displays the author's name, whether they are an internal user of the main account or a legacy author (i.e., any name entered as a string in the author field during course creation). Selecting an author shows the number of courses they have shared with the peer account; however, these authors are not actual users in the peer account.

If a user is deleted from the main account, their data is removed there, but the author information remains in any peer accounts where their content has been shared.

In the Learning Objects API, author information is now returned differently for shared courses and main account courses:

* Shared courses (Peer Account): Author information is returned under the `authorDetails` attribute.
* Main account Courses: Author information continues to be returned under the `authors` attribute.

>[!NOTE]
>
>This is a flag-based feature, contact our Customer Support team at [learningmanagersupport@adobe.com](mailto:learningmanagersupport@adobe.com) to enable this option. 

 View [Peer account](/help/migrated/administrators/feature-summary/peer-account.md) for more information on sharing contents to peer account.

## Search visibility for lower order Learning Objects

Previously, search results did not consistently display individual courses when they were part of higher-order learning objects such as Learning Paths or Certifications. If a learner was enrolled only in a Learning Path or Certification, the search returned only the higher-order structure and not the individual course. 

With this enhancement, learners can now see individual courses in search results, even when those courses are part of Learning Paths or Certifications. A new administrator setting, **[!UICONTROL Show all enrolled courses in search results]**, has been introduced. When enabled, this setting ensures that searching for a specific course always displays the course itself along with any related Learning Paths or Certifications.

View [Settings](/help/migrated/administrators/feature-summary/settings.md#general-settings) for more information on general settings.

## API changes

### Migration API enhancements

Adobe Learning Manager now supports the migration of various data objects into an account via the migration process. This process can be initiated via both APIs and the User Interface. When a migration fails, errors are available for download via the interface. These errors are useful in debugging migration errors and managing the migration runs. 

With this release, the error logs will also be available to download via the APIs for efficient, programmatic error tracking and debugging.

**API changes**

There is a new migration API, `runStatus`, which allows integration administrators to check the status of migration runs triggered via the API, something not possible in previous versions of Adobe Learning Manager. 

Additionally, `runStatus` API now provides a direct link to download error logs (CSV) for completed runs. Note that the link is valid for seven days only, and the logs are retained for one month.

The `startRun` API's response has been updated to include the migration project ID, sprint ID, and sprint run ID, which are required to query the new status endpoint. 

#### runStatus API

**Description**

Retrieves the status of an existing migration run.

**Endpoint**

```
GET /bulkimport/runStatus
```

**Parameters**

* **migrationProjectId**: (Required). A unique identifier for a migration project. A migration project is used to transfer data and content from an existing Learning Management System (LMS) to Adobe Learning Manager. Each migration project can consist of multiple sprints, which are smaller units of migration tasks.

* **sprintId**: (Required). A unique identifier for a sprint within a migration project. A sprint is a subset of migration tasks that includes specific learning items (e.g., courses, modules, learner records) to be migrated from an existing LMS to Adobe Learning Manager. Each sprint can be executed independently, allowing for phased migration.

* **sprintRunId**: (Required). A unique identifier used to track the execution of a specific sprint within a migration project. It's associated with the actual migration process for the items defined in a sprint. The sprintRunId helps in monitoring, troubleshooting, and managing the migration job.

**Response**

```
{
  "sprintId": 2510080,
  "sprintRunId": 2740845,
  "migrationProjectId": 2509173,
  "startTime": 1746524711052,
  "endTime": 1746524711052,
  [
    {
      "id": 2609923,
      "lastHeartbeatTime": 1746524711052,
      "objectName": "content",
      "jobState": "COMPLETED",
      "errorCsvLink": "",
      "errorLogLink": "migration/5830/2509173/2510080/2740845/content_err.csv",
      "sequenceNumber": 1
    },
    {
      "id": 2609922,
      "lastHeartbeatTime": 1746524713577,
      "objectName": "course",
      "jobState": "WAITING_IN_QUEUE",
      "errorCsvLink": "",
      "errorLogLink": null,
      "sequenceNumber": 2
    }
  ]
}
```

#### startRun API

The `startRun` API response was updated to include three additional fields- migrationProjectId, sprintId, and sprintRunId. These fields allow users to track and query the status of specific migration runs using the new runStatus API.

```
curl -X GET --header 'Accept: text/html' 'https://learningmanager.adobe.com/primeapi/v2/bulkimport/runStatus?migrationProjectId=001&sprintId=10001&sprintRunId=7'
```

Produces the following response. The response contains:

* `migrationId`
* `sprintId`
* `sprintRunId`

**Response**

```
{
  "status": "OK",
  "title": "BULKIMPORT_RUN_INITIATED_SUCCESSFULLY",
  "source": {
    "info": "Success",
    "migrationInfo": {
      "migrationProjectId": "001",
      "sprintId": "10001",
      "sprintRunId": "7"
    }
  }
}
```

### Social API changes (user tag, comments, and replies)

Adobe Learning Manager now supports @user tagging functionality in Social Learning boards, enabling learners to mention and notify peers within posts, comments, and replies. This feature enhances collaboration and content discovery across the platform.

This release introduces new API capabilities to support user mentions, including enhanced POST and GET endpoints, as well as a new search functionality for tagged users.

**API changes overview**

* Updated POST APIs for creating posts/comments/replies with user mentions
* Updated GET APIs with user mention data in responses

**Format of user mentions**

A user is mentioned using the format: @(user:userId)

#### Create post with mentions

**Endpoint**

```
POST /primeapi/v2/posts
```

**Description**

Create a new social learning post with user mentions.

**Request body**

```
{
  "data": {
    "type": "post",
    "attributes": {
      "boardId": 13282,
      "accountId": 11152,
      "text": "<p>This is a new post mentioning @[user:11257229]</p>",
      "createdByUserId": 11257228,
      "postType": "discussion"
    },
    "id": null
  }
}
```

**Response**

Standard post creation response with mention data included in the _userMentions_ relationship.

#### Create comment with mentions

**Endpoint**

```
POST /primeapi/v2/comments
```

**Description** 

Add a comment to a post with user mentions.

**Request body**

```
{
  "data": {
    "type": "comment",
    "attributes": {
      "postId": 20746,
      "accountId": 11152,
      "text": "<p>Test Comment @[user:11257229]</p>",
      "createdByUserId": 11257228,
      "commentLevel": 0
    },
    "id": null
  }
}
```

#### Create reply with mentions

**Endpoint**

```
POST /primeapi/v2/replies
```

**Description**

Reply to a comment with user mentions.

**Request body**

```
{
  "data": {
    "type": "reply",
    "attributes": {
      "postId": 20746,
      "accountId": 11152,
      "text": "<p>Thanks for the update @[user:11257229]</p>",
      "createdByUserId": 11257228,
      "commentLevel": 1,
      "parentCommentId": 55621
    },
    "id": null
  }
}
```

#### Retrieve posts with mentions

**Endpoint**

```
GET /primeapi/v2/posts/{id}
```

**Description**

Retrieve post details, including mentioned users.

**Response**

```
{
  "links": {
    "self": "https://learningmanager.adobe.com/primeapi/v2/posts/7522"
  },
  "data": {
    "id": "7522",
    "type": "post",
    "attributes": {
      "commentCount": 3,
      "dateCreated": "2025-06-10T11:33:29.000Z",
      "dateUpdated": "2025-06-25T14:52:04.000Z",
      "downVote": 0,
      "postingType": "DEFAULT",
      "richText": "<p>my updated fourth post @[user:14707776] second mention my first post</p>",
      "state": "ACTIVE",
      "text": "my updated fourth post @[user:14707776] second mention my first post",
      "upVote": 0,
      "viewsCount": 0
    },
    "relationships": {
      "createdBy": {
        "data": {
          "id": "14707776",
          "type": "user"
        }
      },
      "parent": {
        "data": {
          "id": "3971",
          "type": "board"
        }
      },
      "userMentions": {
        "data": [
          {
            "id": "14707776",
            "type": "user"
          }
        ]
      }
    }
  },
  "included": [
    {
      "id": "14707776",
      "type": "user",
      "attributes": {
        "avatarUrl": "https://cpcontents.adobe.com/public/images/default_user_avatar.svg",
        "binUserId": "45664b87-75a3-43ec-b0b7-5064958eac6f",
        "email": "user@example.com",
        "enrollOnClick": false,
        "fields": {
          "Location": "BLR"
        },
        "gamificationEnabled": true,
        "lastLoginDate": "2025-06-27T11:21:17.000Z",
        "name": "John Doe",
        "pointsEarned": 1690,
        "pointsRedeemed": 0,
        "preferredResolution": "AUTO",
        "profile": "admin",
        "roles": [
          "Learner",
          "Admin",
          "Author",
          "Instructor",
          "Integration Admin",
          "Manager"
        ],
        "state": "ACTIVE",
        "userType": "Internal"
      },
      "relationships": {
        "account": {
          "data": {
            "id": "9238",
            "type": "account"
          }
        }
      }
    }
  ]
}
```

### Social API changes (user search)

**Endpoint**

```
GET /primeapi/v2/users/search?q={searchTerm}&context=tagging
```

**Description**

Search for users available for tagging based on social scope settings.

**Request parameters**


* q (required): Search term (minimum 3 characters).
* context: Set to "tagging" to get users eligible for mentions.
* boardId (optional): Board ID to filter users based on access permissions.

**Response**

```
{
  "data": [
    {
      "id": "11257229",
      "type": "user",
      "attributes": {
        "name": "Jane Smith",
        "email": "jane.smith@example.com",
        "avatarUrl": "https://cpcontents.adobe.com/public/images/default_user_avatar.svg",
        "userType": "Internal",
        "state": "ACTIVE"
      }
    }
  ]
}
```

### Learner API enhancements for quiz performance tracking

The `GET /loResourceGrades` API has been enhanced to provide detailed quiz performance data, enabling more sophisticated analytics and automated decision-making.

**What's new**

The API response now includes two additional fields:

* **[!UICONTROL highestScore]**: The best score achieved by a learner across all quiz attempts
* **[!UICONTROL maxScore]**: The total possible score for the quiz

**API response example**

```
{
    "links": {
        "self": "https://learningmanagerstage1.adobe.com/primeapi/v2/loResourceGrades/course:15067_30122_41715_1_3400468"
    },
    "data": {
        "id": "course:15067_30122_41715_1_3400468",
        "type": "learningObjectResourceGrade",
        "attributes": {
            "completed": false,
            "duration": 0,
            "hasPassed": false,
            "highestScore": 0,
            "maxScore": 0,. 
            "progressPercent": 0,
            "score": 0
        },
        "relationships": {
            "loResource": {
                "data": {
                    "id": "course:15067_30122_41715_1",
                    "type": "learningObjectResource"
                }
            }
        }
    }
}
```

In response, **course:15067_30122_41715_1_3400468** is the ID of the Learning Object resource grade for which the information is being requested. The `learningObjectResourceGrad`e id can be obtained from the `GET /enrollments/{id}` API.  

### API responses supports case sensitivity for author names

The API response now gives the exact case of legacy author names as entered during course creation or update. This ensures that names appear consistently across the learner UI and public APIs.

**What's new**

* When a new author name is added, the case is stored and returned exactly as entered.
* If an existing author name is removed and re-added with a different case, the updated case will be honored and reflected across all courses using that author name.
* No automatic migration will be done for previously stored names; only newly added or updated names will follow this behavior.

### Calendar API enhancement

The calendar now loads sessions for the month selected by the user. To fetch both past and upcoming sessions through the API, a new `year` parameter has been added to the learner endpoint `GET /users/{id}/calendar`. The `month` and `year` parameters must be provided together to retrieve session details.

**Sample curl**

```
curl -X GET --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth a4ae04eb9f06f4bf88abcde17' 'https://abc.adobe.com/primeapi/v2/users/12345678/calendar?month=7&year=2025&currentMonthOnly=false&filter.allSessions=false'
```

### Support for mark completion through Administrator API

Previously, the public API did not support instance-based completion marking in multi-enrollment scenarios. With this enhancement, you can now include course instance ID in the request body of `POST /users/{userId}/userModuleGrade` and administrator can mark completion for a specific instance.

### Set user ID preference for SCORM reporting

Some customers require the learner's UUID (Universally Unique Identifier) instead of the default user_id for SCORM content completion. Using the UUID provides more accurate tracking across learning programs and prevents duplication of license usage in MAU (Monthly Active User) accounts.

 To support this, a new account-level setting, `reporting_userid_preference`, has been added. When enabled, this setting sends the UUID in place of the user_id whenever learners complete SCORM content.

>[!NOTE]
>
> Contact our Customer Support team at [learningmanagersupport@adobe.com](mailto:learningmanagersupport@adobe.com) to configure this setting.

The new attribute `reportingUserIdPreference` has been introduced to `get /account` track the user ID preferences.

### Author information in shared courses

In the Learning Objects API, the way author information is returned has been updated to distinguish between main account courses and courses shared with peer accounts:

* Shared Courses (Peer Account): Author details are now returned under a new attribute, `authorDetails`. This attribute provides the author name even when the course originates from another account.

* Main Account Courses: Author information continues to be returned under the existing `authors` attribute, with no change to current behavior.

This change ensures consistency in how author data is exposed via API for both main and shared courses, while also preserving compatibility for existing integrations.

### Search visibility for courses in higher-order Learning Objects

To support improved search visibility, a new parameter `filter.ignoreHigherOrderLOEnrollment` (Type: Boolean (true / false)) has been added to the `GET /learningObjects` API.

When set to true, the API includes individual courses in the response even if they are only part of a higher-order Learning Object (such as a Learning Path or Certification) where the learner is already enrolled.

When set to false (default behavior), courses that are only available through a higher-order Learning Object, and not directly enrolled by the learner, will be excluded from the results.

## Webhooks changes

### Register LinkedIn Learning webhooks using the connector

Previously, administrators had to manually register LinkedIn Learning webhooks to Adobe Learning Manager through APIs. With this enhancement, the LinkedIn Learning (LIL) connector now supports webhook registration automatically during new connection setup in ALM. The **OAuth Server  URL** and **Tenant Server URL** will be auto-populated on the LinkedIn Learning configuration page.

View [LinkedIn Learning](/help/migrated/integration-admin/feature-summary/connectors.md#linkedin-learning-connector) for more information on LinkedIn Learning integration.

### Changes to MAU license usage in LinkedIn Learning

Previously, for MAU accounts, when a learner completed a LinkedIn Learning course directly on the LinkedIn Learning platform, Adobe Learning Manager did not count the license usage. License consumption was triggered only for courses taken through the Adobe Learning Manager player, resulting in inaccurate tracking of Monthly Active Users (MAU).

With this enhancement, Adobe Learning Manager now generates an external webhook whenever a learner consumes a course in the LinkedIn Learning platform. When Adobe Learning Manager receives this webhook, it calculates license usage to ensure accurate tracking across both platforms. 

View this [Webhooks](/help/migrated/integration-admin/feature-summary/webhooks.md) for more information on configuring Webhooks.

## Reporting changes

### Instructor-marked completions in Learner Transcripts

Incremental Learner Transcripts now capture instructor-marked completions, even if attendance is recorded after the session date.
This enhancement addresses a critical gap in incremental Learner Transcripts where instructor-marked completions were previously missed if attendance was recorded after the original session date.

Incremental Learner Transcripts are scheduled reports that capture only the changes (such as completions or progress updates) that occur within a specified period, rather than providing a full historical data dump. They are commonly used for automation, dashboards, and integrations, allowing users to efficiently track recent learning activities without processing the entire transcript history each time.

**What's new in the Learner Transcript**

* **Mark Completed Date (UTC TimeZone) column**: A new timestamp column that captures the exact date and time when an instructor marks a session or module as complete.
* **Enhanced completion source tracking**: Tracks the specific instructor and module (for example, "Classroom") where completions were recorded.

These changes ensure that completions marked after the session date are accurately reflected in incremental Learner Transcripts.

**Use cases**

* Organizations with classroom sessions where instructors may mark attendance days after the actual session. 
* Automated systems or dashboards relying on incremental Learner Transcripts for compliance or reporting. 

![Learner Transcript reports showing marked completed dates (highlighted in yellow) for course completion tracking in Adobe Learning](/help/migrated/assets/mark-completion-column.png)
_Learner Transcript report displays a new column in yellow highlighting individual completion dates for each user_

View [Learner Transcript](/help/migrated/administrators/feature-summary/learner-transcripts.md) for more information on Learner Transcript report.

### Enhanced User Report with extended data fields

The User Report now includes additional fields to enhance user tracking and organizational mapping. These updates simplify user identification, support integration with downstream user management workflows, improve understanding of reporting relationships, and maintain organizational boundaries to prevent accidental cross-communication.

**What's new in the User Report**

* Internal User ID column: Provides unique internal identifiers for smooth user tracking across different systems and API endpoints.
* Manager Email column: Includes direct manager contact information for organizational hierarchy tracking.

![User Report showing the internal user ID and manager email columns highlighted in yellow](/help/migrated/assets/user-report-columns.png) 
_User Reports highlighting internal user IDs and manager email addresses to streamline user management_

View [Download the user report](/help/migrated/administrators/feature-summary/add-users-user-groups.md#download-the-user-report) for more information on User Report.

### FTP User Report with Internal User ID information

**Overview**

The FTP-based User Report now includes the Internal User ID, providing a unified and consistent approach to data export and integration for headless implementations. This enhancement simplifies data management, improves consistency across reporting periods, and supports automated workflows for bulk operations and analytics. The downloaded User Report from the FTP folder now contains the new Internal User ID column.

**What's new**

* User Reports are now available through [Custom FTP](/help/migrated/integration-admin/feature-summary/connectors.md#custom-ftp) alongside existing reports (Gamification Transcripts, Learner Transcripts, Trainings Report).
* The Internal User ID column is now consistent across all export methods (FTP, Jobs API, and UI).

View [Learning Manager FTP connector](/help/migrated/integration-admin/feature-summary/connectors.md#learning-manager-ftp-connector) for more information on FTP connector. 

### Include suspended users in Learner Transcripts

**Overview**

Organizations can now include suspended users (those with disabled external profiles) in Learner Transcripts, ensuring comprehensive historical learning data retention.

**What's new**

* Account-level flag to configure suspended user visibility, allowing suspended users to appear in Learner Transcripts.
* Historical data retention even after deactivation of suspended external profiles.

**Implementation requirements**

* Contact your Customer Success Manager (CSM) to enable the account-level flag.

>[!NOTE]
>
>This flag is disabled by default for existing accounts and must be explicitly requested for new accounts.

View [Learner Transcript](/help/migrated/administrators/feature-summary/learner-transcripts.md) article more information.

### Job Aids report with direct access links

**Overview**

The Job Aids report has been enhanced to include direct download links to job aids, streamlining content management and audit processes for administrators and authors. This enhancement gives direct file downloads and URL access from within the report. Eliminates manual effort in locating and downloading job aids for compliance or accessibility audits. 

**What's new**

* Job Aid Link column: Direct access to job aid files and external URLs from within the report.
* Role-based access control: Link accessibility depends on user roles and catalog permissions.
* Deleted job aids remain accessible if still linked to active courses.

**Use cases**

* Authors or administrators conduct regular accessibility audits on job aids, as required by large organizations.
* Any scenario where quick, role-based access to job aid files is needed for review or compliance.

![](/help/migrated/assets/job-aid-report.png) 
_Job Aids Report displays direct download links, making it easy to access and download job aids in Adobe Learning Manager_

View [Job Aids Report](/help/migrated/administrators/feature-summary/reports.md#job-aids-report) for more information o Job Aids report.

## Bug fixed in this update

* The signature is now correctly sent to the target host when the authentication mechanism is set to Signature during connection configuration.
* Dummy users created during Adobe Connect sessions were not deleted after session completion. The SnapLogic pipeline now correctly removes these users, even when the `principals-delete` API previously returned a 200 response without deleting them.
* `null` `eventDetail` objects in API responses no longer cause exceptions. The system now skips null entries and processes the entire array, ensuring complete recordings.
* L2 Quiz scores are now correctly generated for Non-Interactive Quizzes, including details of users who completed them.
* The Date of Feedback column in feedback reports now displays the correct date. Previously, seconds were incorrectly passed to the Date constructor, which expects milliseconds, causing dates to appear as January 1970. This has been corrected to ensure accurate date display when generating feedback reports.
* Learners can now update enrollment in a Flex Learning Path even if one of the course instances is retired. Previously, selecting a new instance caused a console error (Cannot read properties of undefined) and prevented the update.
* Resource names in Learning Paths now display correctly without breaking mid-word.
* LinkedIn Learning webhooks are now enabled from the LIL connector when creating connections for new users. The system also registers the account via the private API and displays additional configuration info (OAuth URL and Tenant URL) on the LinkedIn Learning configure page.
* User attribute values updated via SAML workflows (`UpdateUserWorkerTask`) are now saved with their original case instead of being converted to lowercase.
* Reordering modules in a course no longer resets the number of Mandatory Modules to "All"; the count now stays as configured.
* Go1 pipelines now handle language codes consistently by mapping 2-letter codes to 4-letter codes, similar to LinkedIn Learning pipelines.
* In Retire+ accounts, learners previously saw "This Course does not exist" when launching a Learning Path course after unenrolling from a Certification. Enrollment sources are now updated correctly, allowing courses in Learning Paths to launch without errors.
* When the module_version.csv file contains contentType fields with blank or null values, course creation now works without any issues.
* Courses now appear correctly when filtering by Catalog or Catalog Label. Previously, applying these filters on the course page did not display courses, even if they were associated with the catalog.
* In the Learner App, pressing TAB in the Fluidic Player was getting stuck on the "Enter Fullscreen" button. Keyboard navigation now moves correctly through all screen elements.
* Hovering over long course names in the Manager app's Compliance Dashboard now displays the full name for enrolled or compliant courses.
* Only Shared or HIDDEN are accepted for the module visibility column in module.csv. Any other value will trigger an error during migration, preventing failures on the backend.
* Creating a new admin with a mixed-case email no longer generates duplicate user entries when UUID is disabled. The system now consistently handles email casing to prevent duplicates.
* Notes PDFs now display correctly for courses in languages such as Arabic, Greek, Hebrew, Hindi, Thai, and Ukrainian. Previously, characters appeared distorted in the downloaded PDF even though they displayed correctly in the player.

## System requirements

View [Adobe Learning Manager system requirements](/help/migrated/system-requirements.md).

## Release notes

Check out the [release notes](/help/migrated/release-note/release-notes.md) for latest release updates. 

## Previous releases of Adobe Learning Manager

* [Adobe Learning Manager May 2025 release](/help/migrated/whats-new-may-2025.md)
* [Adobe Learning Manager November 2025 release](/help/migrated/whats-new-nov-24.md)
