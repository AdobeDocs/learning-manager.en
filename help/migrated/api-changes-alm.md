---
description: This document describes the various API changes for every update in Adobe Learning Manager.
jcr-language: en_us
title: API changes in Adobe Learning Manager
---

# API changes in the April 2026 release

The April 2026 release of Adobe Learning Manager introduces focused enhancements to the Public API around alternates and equivalents, time‑windowed access to content, content‑driven quiz attempts, non‑logged‑in experiences, and Job Aid handling. The changes are designed to be largely backward‑compatible while enabling more precise integrations.

## Adaptive learning for Learning Paths

This release adds full Public API support for adaptive learning paths. Learning Paths (LPs) can now define adaptive rules that control which sections and sub‑learning objects (sub LOs) are visible to different learner groups, and the Public API reflects this behavior.

The following endpoints are affected:

- GET /primeapi/v2/learningObjects?filter.loTypes=learningPath
- GET /primeapi/v2/learningObjects/{loId}

A new Boolean attribute, attributes.isAdaptive, indicates that a learning program uses adaptive rules. When this flag is true, the sections attribute is interpreted adaptively.

For learner calls, only sections that are visible to the current learner are returned. Each section includes the list of learning object IDs (loIds), a mandatory flag and a mandatoryLOCount that are computed based on the adaptive configuration for that learner, as well as the sectionId. The relationships.subLOs relation is now also filtered, so it contains only those sub‑learning objects that are visible to that learner.

For admin calls, sections can additionally expose an adaptiveConfig array. This describes the adaptive rules per user group, including userGroupId, userGroupName and whether the section is mandatory for that group. Admin‑facing tools can use this to visualize and manage adaptive rules.

Reset completion for learning programs

The release introduces an API to __refresh (reset) completion__ for learning objects, including adaptive learning programs. This supports scenarios such as re‑training, periodic compliance refreshes, or program restarts.

A new endpoint is available:

```
POST /primeapi/v2/learningObjects/{loId}/instances/{loInstanceId}/refreshCompletion
```

This operation requires appropriate write permissions and resets the completion state for the specified learning object instance in the given user context. It is intended for use by admin‑side automations or carefully scoped learner tools.

A bulk version of this capability is planned via a Jobs API. The request shape is designed to target users by email, user ID or user group ID, for example:

```
{  
  "emails": ["[user1@example.com](mailto:user1@example.com)", "[user2@example.com](mailto:user2@example.com)"],  
  "userIds": ["12345", "67890"],  
  "userGroupIds": ["ug1", "ug2"]  
}  

```

Integrations should use this API when they need to restart learners in each program or course. Clients must handle error responses gracefully: the API may reject refresh requests, where a reset isn't applicable (for example, when no completion exists or unsupported learning object types).

## Equivalents and alternate completions

To support implementations where multiple learning objects can satisfy the same requirement, the release introduces Equivalents and Alternates completions as public APIs.

The Learning Object endpoints now contain this information:

```
- GET /primeapi/v2/learningObjects
- GET /primeapi/v2/learningObjects/{loId}
```

A new Boolean attribute attributes.isAlternateComplete indicates whether the learner's completion for a given learning object is the result of an alternate or equivalent learning object rather than the object itself. When this is true, the relationships.alternateCompletions relation lists the learning objects that acted as alternates. This allows downstream reporting and dashboards to distinguish between direct and alternate completions and to show which alternate fulfilled the requirement.

In addition, a related‑learning‑objects view allows discovery of potential alternates that can satisfy a learning object. This is exposed via:

```
GET /primeapi/v2/learningObjects/{loId}/relatedLOs?type=sourceAlternateLOs&limit={n}
```

The response returns learning objects that can act as alternates and includes a meta.count field that indicates the total number of such alternates, independent of the current limit. Integrations can use this to present recommended equivalents, or to build administrative views of alternate mappings.

## Reporting and analytics use cases

Users that generate reports or analytics should update their logic to add isAlternateComplete and alternateCompletions into their reporting workflows.

Reporting integrations that consume completion data (for example, LT export, custom data warehouse feeds, or BI dashboards) should extend their logic to read and persist both attributes.isAlternateComplete and relationships.alternateCompletions from the LO APIs:

- When isAlternateComplete == false:  
Treat the record as a __direct completion__ of the LO, as today.
- When isAlternateComplete == true:
    - Flag the record as an __alternate completion__ in your report (for example, a "Completion Method" column with values DIRECT vs ALTERNATE).
    - Use relationships.alternateCompletions.data[*].id to capture __which source LO(s)__ granted this completion (for example, "Course B completed via alternate Course A").

Typical use cases:

- _Compliance reports_ – show that a compliance course was completed via an approved equivalent, and list the source course that fulfilled the requirement.
- _Program progress dashboards_ – distinguish learners who completed a path _directly_ vs those who satisfied it via alternates, for more accurate progress and remediation views.
- _Audit trails_ – for any LO marked isAlternateComplete=true, auditors can see exactly which alternate training(s) were used to grant that completion.

Without incorporating these two fields, downstream reports will treat alternate completions as regular completions and will _not be able to explain_ *why* a learner shows as completed a training they never took directly.

## Learner vs Admin LO API behavior

The multi language job aid structure is identical in both learner and admin LO APIs. Learner scope returns only those job aids visible to the learner, but for each visible job aid it exposes all configured locales via multiple resource entities (one per locale) and multi locale localizedMetadata. Admin scope returns all job aids the admin can manage, with the same LO model and locale specific resource IDs. Clients with learner scope should choose the resource whose attributes.locale best matches the learner's content language, while admin tools can enumerate all locales for reporting and management.

## Checklist with commenting capability

To support workflows where reviewers can share structured feedback on checklist‑based activities, this release surfaces *checklist comments* and reviewer visibility controls through the learning object resource API.

Checklist‑related metadata is exposed on learningObjectResource entities (JApiLOResource, "type": "learningObjectResource") that represent checklist resources within a course or other learning object.

The information is available via:

```
GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources
```

When the learning object instance contains checklist‑type resources, the corresponding learningObjectResource entries in the included array expose comment and reviewer‑visibility attributes under attributes, and reviewer identity under relationships.

### New checklist comment attributes

For checklist resources, the following attributes may be present on the learningObjectResource:

- attributes.checklistComment  
A free‑text comment left by the reviewer for the learner, for example:  
"checklistComment": "Excellent performance! All safety protocols followed correctly."  
This attribute is populated _only if_:
    - showChecklistComment is true, and
    - the checklist configuration has enable_reviewer_remarks enabled.
- attributes.showChecklistComment  
A Boolean flag indicating whether reviewer remarks should be shown to the learner:  
"showChecklistComment": true  
This attribute is present _only when_ enable_reviewer_remarks is enabled in the checklist configuration.  
Clients should use this flag to decide whether to render checklistComment in learner experiences.
- attributes.showReviewerNameToLearner  
A Boolean flag controlling whether the learner should see the reviewer's identity:  
"showReviewerNameToLearner": true  
When true, clients can use the checklistReviewedBy relationship (see below) to resolve and display the reviewer's name (e.g., via a user lookup API).

Other checklist‑specific context such as checklistEvaluationStatus, isChecklistMandatory, resourceSubType: "CHECKLIST", and submissionDate are also available on the same learningObjectResource to support richer checklist UIs and reporting.

### Reviewer identity relationship

When reviewer names are meant to be visible, the learningObjectResource includes a relationship that points to the reviewer user:

```
"relationships": {
  "checklistReviewedBy": {
    "data": {
      "id": "user_id",
      "type": "user"
    }
  }
}

```

This relationship is populated _only if_:

- showReviewerNameToLearner is true, and
- checklistReviewedBy is not null (i.e., the checklist has been reviewed).

Client applications should:

1. Check attributes.showReviewerNameToLearner.
2. If true and relationships.checklistReviewedBy.data is present, call the appropriate user API to resolve "id": "user_id" into a display name.
3. Render the reviewer name next to the checklist comment or status as appropriate.

### Accessing checklist resources and comments

To retrieve checklist resources and their comments for a given learning object, clients should:

- Call  

```
GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources
```

- In the response:
    - Use relationships.instances from the main learningObject to locate the relevant learningObjectInstance entries in included.
    - From each learningObjectInstance, follow relationships.loResources to find learningObjectResource entries.
    - Filter learningObjectResource entries where:
        - attributes.resourceSubType == "CHECKLIST" (for checklist resources), and
        - optionally attributes.showChecklistComment == true to find checklists with learner‑visible comments.

- For each checklist learningObjectResource, consume:
    - attributes.checklistComment (if present and showChecklistComment is true)
    - attributes.checklistEvaluationStatus (e.g., "PASSED")
    - attributes.showReviewerNameToLearner
    - relationships.checklistReviewedBy (when present) to identify the reviewer.

This pattern allows headless or custom clients to render a comprehensive checklist experience, including status, mandatory/optional flags, and reviewer feedback, directly from the Prime APIs.

### Reporting and UX considerations

- _Reporting and analytics_
Integrations that track learner performance on checklists can incorporate:
    - checklistEvaluationStatus for pass/fail or other status indicators.
    - isChecklistMandatory to differentiate required vs. optional checklist activities.
    - Presence or absence of checklistComment and showChecklistComment for audits of feedback coverage.
- _Learner experiences_
UI implementations should:
    - Respect showChecklistComment before displaying remarks.
    - Use showReviewerNameToLearner and checklistReviewedBy to decide whether to display the reviewer's name or keep the review anonymous.
    - Fall back gracefully when comments are disabled or not present, still showing evaluation status and submission information.

## Multi‑language support for job aid

To support implementations where job aids must be delivered in multiple languages to both learners and admins, this release extends job aid handling to return *one resource per locale* instead of a single hard‑coded en-US resource.

Multi‑language job aids continue to use the existing hierarchy:

_learning Object_ (lo) → _learningObjectResource_ (loResource) → _resource_

No changes are required to the API contract. Any localized job aid fits into this structure naturally, with separate resource entities per locale and shared localized metadata at the learningObject / learningObjectResource levels.

Job aid data is exposed via:

```
GET /primeapi/v2/learningObjects/jobAid:{jobAidId}?include=instances.loResources.resources

```

When a job aid has multiple language variants, the included array contains multiple "type": "resource" entries—one for each locale (for example, en-US, fr-FR, es-ES), all linked from a single learningObjectResource.

### Multi‑language job aid structure

Multi‑language job aids use:

- _learningObject (type: learningObject)_
    - Contains localizedMetadata with multiple entries (e.g., en-US, fr-FR) so clients can present job aid title/description in the appropriate language.
- _learningObjectInstance (type: learningObjectInstance)_
    - Refers to one or more learningObjectResource entries via relationships.loResources.
- _learningObjectResource (type: learningObjectResource)_
    - Holds common configuration (content type, version, etc.) and multi‑locale localizedMetadata.
    - Links to one or more resource entities via relationships.resources.
- _resource (type: resource)_
    - *One per locale*, each with its own id, locale, name, and URL (location / downloadUrl).

For a multi‑language job aid, a typical pattern is:

- learningObjectResource with localizedMetadata for en-US and fr-FR
- relationships.resources.data pointing to:
    - resource with locale: "en-US"
    - resource with locale: "fr-FR"

Clients can select the appropriate resource by matching the learner's locale to the resource.attributes.locale field.

### New resource ID format for job aids

To properly distinguish multiple localized variants of a job aid resource, the _resource ID format has changed_.

_Old (legacy) resource ID format_

Previously, job aid resources used an opaque ID format such as:

jobAid:131032_-1_-1_2_resource

This format did not encode locale, and APIs would effectively expose only a single resource (usually en-US).

_New resource ID format (multi‑language aware)_

The new format is:

```
jobAid:<jobAidId>_<version>_<localeCode>
```

Examples:

- jobAid:131032_2_en-US
- jobAid:131032_2_fr_FR
- jobAid:131032_2_es_ES

Visual breakdown:

```
jobAid:131032_2_fr_FR

        │      │ │ │

        │      │ │ └──► Locale Code (fr_FR, en_US, es_ES, etc.)

        │      │ └────► Version (2)

        │      └──────► JobAid ID (131032)

        └─────────────► Resource Type Prefix ("jobAid:")
```

This structure lets clients:

- Quickly identify which job aid and version a resource belongs to.
- Directly infer the locale from the resource ID when needed.

### Backward compatibility: 

```/resources/{resourceId}```

The legacy resource endpoint remains available:

```GET /primeapi/v2/resources/{resourceId}
```

It is now _backward compatible_ with both the old and new ID formats:

- _Old ID format_ (for example, jobAid:131032_-1_-1_2_resource)
    - Continues to work.
    - Returns the _first created resource_ associated with that legacy identifier (typically the original en-US resource).
- _New ID format_ (for example, jobAid:131032_2_fr_FR)
    - Returns the _exact locale‑specific resource_ corresponding to that ID.
    - This allows precise retrieval and manipulation of localized job aid variants.

Integrations that currently store or reference the old resource IDs can continue to function without change, while newer implementations are encouraged to adopt the new ID format for locale‑specific operations.

### Integration and UX considerations

- _Learner/admin UI_
    - Use learningObject.localizedMetadata and learningObjectResource.localizedMetadata to present titles and descriptions in the appropriate language.
    - Use resource.attributes.locale to select the correct URL (location / downloadUrl) for the learner's locale.
    - Implement fallback behavior (for example, fall back to en-US) if a learner's exact locale is not available.
- _APIs and storage_
    - For new integrations, store the _new‑format resource IDs_ (```jobAid:<jobAidId>_<version>_<localeCode>```) to enable unambiguous locale‑specific retrieval.
    - Legacy IDs can still be used with /resources/{resourceId}, but they will not distinguish between locales.

## Time‑slot constraints for starting modules

Some learning experiences must be available only within a defined time window. The release displays time‑slot information on learning object resources and introduces a validation endpoint that checks whether a learner can start a resource at the current time.

Time‑slot metadata is available via the endpoint:

```GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources```

At the learning object resource level, a timeSlot object may now be present in the attributes, with startTime and endTime values in UTC. This specifies the window during which the resource may be started.

Before launching a module, integrations can call a new validation endpoint:

```GET /primeapi/v2/learningObjects/{loId}/instances/{loInstanceId}/loResources/{loResourceId}/canStart```

This endpoint, intended for learner‑read scenarios, returns whether the learner is currently allowed to start the resource, considering the configured time slot, delivery type and other back‑end rules.

Custom players and client applications should use canStart to enforce time‑based access and use the timeSlot metadata to display clear messaging about when content becomes available or expires. Negative responses from canStart should be handled explicitly to inform learners why the content cannot be started yet or anymore.

## Multi‑attempt, content‑driven quizzes

Some content packages implement their own attempt tracking rather than relying solely on Adobe Learning Manager. The release introduces a flag that indicates when attempts are driven by the content itself.

Through:

```GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources```

learning object resources may now expose a Boolean attribute hasContentDrivenAttemptTracking. When this is true, the quiz or module manages attempts internally (for example, via SCORM or xAPI logic), and the platform's standard attempt counters may not fully reflect the learner's experience.

Integrations that display attempt counts or control retry behavior should check this flag. When it's enabled, they should not infer attempt limits solely from platform metadata and should be prepared to rely on content‑side reporting (for example, via xAPI statements) or business‑specific rules.

## Behavioral change in Job Aid resource ID format

This release introduces an important __behavioral change__ in the format of Job Aid resource IDs. While no new endpoint is involved, this has a direct impact on systems that store or parse these IDs.

Previously, Job Aid resource IDs used a format like:

```jobAid:<jobAidId>_-1_-1_2_resource```

In the April 2026 release, this is replaced with a simplified and more explicit format:

```jobAid:<jobAidId>_<version>_<localeCode>```

For example:

jobAid:131032_2_fr_FR

The components are:

- ```<jobAidId>```: the numeric Job Aid ID (for example, 131032),
- ```<version>```: the version number of the Job Aid (for example, 2),
- ```<localeCode>```: the locale code (for example, en_US, fr_FR, es_ES).

Any integration that indexes resources or persists in Job Aid resource IDs must update its parsing and storage logic to recognize the new format. Because the identifiers themselves change, it's strongly recommended that you rebuild any local indexes keyed by Job Aid resource IDs after upgrading to the April 2026 release.

## Set course banner images via migration

You can now set or update course banner images in Adobe Learning Manager as part of your standard migration workflow. This helps you launch or clean up large catalogs while keeping your course pages visually consistent, without manually editing 

### Where banner images are defined

Banner images are configured in the _course.csv_ migration file, which you already use to provide course metadata such as:

- id  
- courseName  
- courseCreationDate  
- state  
- author  
- thumbnailUrl

With this enhancement, the course.csv specification includes an additional _optional column_ for the course banner image. The exact header name is defined in the CSV specification you download from your Learning Manager account (for example, it may appear as bannerUrl or bannerImageUrl).

The banner column:

- Points to the image file you want to use as the _course banner_.
- Works in the same way as thumbnailUrl, using images available in your configured content repository (Box/FTP).

### Preparing banner images for migration

1. Upload banner images: Place your banner image files in the same Box or FTP location that you use for other migration assets, following your existing directory structure.
2. Check file format: 
Use one of the supported image formats (for example png, jpg, jpeg, gif), as described in the system requirements:
    1. [*System requirements*](/help/migrated/system-requirements.md)
3. Update course.csv: In the new banner column, reference the relative path or identifier of the banner image. A conceptual example:

```
id,courseName,courseCreationDate,state,author,thumbnailUrl,bannerUrl  
12345,DEMO1,2018-05-05T08:56:21.000Z,Published,Sudheer,pic1.png,banners/banner1.png  
45678,DEMO2,2018-05-05T08:56:21.000Z,Published,Sudheer,pic2.png,banners/banner2.png  
```

### Apply banners during a migration run

Once your course.csv is updated, the flow is the same as any other migration:

1. _Upload CSVs_
Upload the updated course.csv (and any other relevant files) to the Box/FTP folder configured for migration. File names must match the names specified in csv_specifications.zip exactly (they are case‑sensitive).
2. _Start a sprint run_
In Adobe Learning Manager, as the Integration Admin, start a migration _sprint run_ that includes course.csv.  
The migration engine reads the banner column and applies the banner image to each course.
3. _Review results and error logs_
After the sprint:
    1. Verify banners in the _Author_ and _Learner_ apps.
    2. If some rows fail (for example, due to an invalid file path or unsupported format), download the error CSV from the migration run and correct the data.

### New courses vs. existing courses

The banner field works in both scenarios:

- _New courses created via migration_
When a course is created for the first time from course.csv and the banner column is populated, that banner is set immediately.
- _Existing courses (retrofit / corrections)_
If you re‑run migration with the same course id and a new banner value:
    - Learning Manager locates the existing course.
    - The banner image is _updated_ to the new image specified in the CSV.

Your actual column names and paths must match the _downloaded CSV specification_ and your content repository layout.

## Remove order column in LearningProgramCourse

Adobe Learning Manager now supports a simplified model for _course ordering inside Learning Paths (Learning Programs)_ during migration. As part of this change, the _order column is removed_ from the learning_program_course.csv migration file.

Previously, the learning_program_course.csv file included a column (often called order or similar) that was used to:

- Explicitly set the _position_ of each course inside a Learning Program, based on the numeric value in that column.
- Require administrators or scripts to maintain this numeric sequence manually, especially when inserting or re‑ordering courses.

Now, Adobe Learning Manager no longer uses the order column in learning_program_course.csv to determine course ordering. Instead, the migration CSV focuses on _which courses belong to which Learning Program_, rather than how they are ordered numerically.

## Impact on migration CSVs

### learning_program_course.csv

You should treat the legacy order column as removed or ignored:

- Do not rely on order to control sequence of courses in a Learning Program during migration.
- If you still have an order column from older templates:
    - Learning Manager will ignore it for ordering.
    - You can safely remove it from your CSV over time to simplify your migration files.
- The core required mapping remains:
    - Learning Program ID ↔ Course ID (and any other still‐documented columns such as id, learningProgramId, courseId, and dates).

Always refer to the latest [_CSV specifications_](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/migration-manual) from your Learning Manager account (via csv_specifications.zip) to confirm the current header set and requirements.

## timeZoneCode on Course Instances

From this release onwards, the Course Instance model (learningObjectInstance) exposes a new attribute:

timeZoneCode -- a string field that explicitly links a course instance to one of the account's configured time zones.

This allows clients to:

- Resolve a course instance's time zone in a consistent, API-driven way.
- Interpret and display all instance-level dates/times correctly for that instance, regardless of the user's own time zone.

### Where timeZoneCode appears

The field is added in the attributes of the learningObjectInstance model
for course instances only.

Example:

``` 
{
  "id": "course:1262748_1359228",
  "type": "learningObjectInstance",
  "attributes": {
    "dateCreated": "2019-08-06T13:50:39.000Z",
    "isAET": false,
    "isDefault": true,
    "timeZoneCode": "356",
    "isFlexible": false,
    "state": "Active",
    "localizedMetadata": [
      {
        "locale": "en-US",
        "name": "Default instance"
      }
    ]
  }
}
```

### How to resolve timeZoneCode

The numeric timeZoneCode is a lookup key into the account's time zone catalog, which is exposed via the Account API:

``` http
GET /primeapi/v2/account
Authorization: Bearer <access_token>
```

Within the response, time zones are listed in:

``` 
"data": {
  "attributes": {
    "timeZones": [
      {
        "name": "Etc/GMT+12",
        "timeZoneCode": "356",
        "utcOffset": -720,
        "utcOffsetCode": "UTC-12:00(Etc/GMT+12)",
        "zoneId": "Etc/GMT+12"
      },
      "..."
    ]
  }
}
```

### Recommended client flow:

1. Call GET /account once, cache attributes.timeZones for the tenant.
2. For each course instance:
    - Read attributes.timeZoneCode.
    - Find the corresponding entry in timeZones where timeZoneCode matches.
    - Use that entry's zoneId, utcOffset, and utcOffsetCode for display and scheduling logic.

## Asynchronous public APIs for user group membership

### Introduction

Adobe Learning Manager exposes two _admin async APIs_ to manage user group (UG) membership:

- POST /async/userGroups/{userGroupId}/users – add users to a UG asynchronously
- DELETE /async/userGroups/{userGroupId}/users – remove users from a UG asynchronously

Instead of updating membership in the same request, these APIs accept your batch and return an _event ID_. The actual result is delivered later via webhooks.

Use them when:

- You're managing large groups or frequent batch updates.
- Latency is less important than reliability and throughput.
- You're building integrations (HR, CRM, LXP) rather than UI clicks.

For small, interactive admin actions, you can continue using the synchronous `/userGroups/{id}/users` APIs.

### Authentication and base URL

These APIs are part of the standard __v2 Admin API__ surface.

- [Base URL (prod)](https://learningmanager.adobe.com/docs/primeapi/v2/)
- Auth: OAuth 2.0 access token with `admin:write` scope
- Required headers:
  - Authorization: Bearer <access_token>
  - Content-Type: application/json
  - Accept: application/json

For general Admin API behavior and scopes, see:

- [Developer manual](/help/migrated/integration-admin/feature-summary/developer-manual.md)
- [API reference guide](https://learningmanager.adobe.com/docs/primeapi/v2/)

### Request format

Both __add__ and __remove__ use exactly the same body shape.

#### Body

```
{
  "metadata": {
    "event_id": "my-optional-correlation-id",
    "sourceSystem": "HRIS",
    "batchId": "hr_2026_03_30_0001"
  },
  "data": [
    { "type": "user", "id": "11101219" },
    { "type": "user", "id": "11101220" }
  ]
}
```

#### data (required)

data is the list of user resource identifiers for this batch.

- `type` must be "user".
- `id` is the _numeric user ID_ in ALM (not email, not UUID).

#### Constraints

- `data` must be present and non-empty.
- At least one user is required.
- The maximum payload size is 20 users per request.
- All IDs must be numeric and must refer to valid users.

If any of these conditions fail, the API returns an error and nothing is queued.

#### metadata (optional)

`metadata` is any additional correlation data you want echoed back in the Webhook.

Typical usage:

- `event_id` – correlation ID you generate.
- `sourceSystem` – name of your upstream system.
- `batchId` – batch or job identifiers.

The service returns this object unchanged in the Webhook response, so you can match the callback to your internal job.

Constraints:

- Optional; may be omitted entirely.
- Combined length of all keys and values must not exceed 1000 characters.

### Response format

Both endpoints respond synchronously with an event ID:

```
{ "event_id": "cd2972c8-cb15-47a0-a23f-e4a16cb720f5" }
```

Behavior:

- If `metadata.event_id` is passed, that value is used.
- Otherwise, the service generates a UUID.

You should always:

- Store this `event_id` as the primary identifier for the batch.
- Expect to receive the same value in the Webhook callback.

View [Webhooks for adding and removing user group membership](/help/migrated/integration-admin/feature-summary/webhooks.md#webhooks-for-adding-and-removing-user-group-membership) for more formation.

## Frequently asked questions

_How does the April 2026 release change the learningObjects API for adaptive learning programs?_

This release adds an isAdaptive flag on learning programs and makes sections and subLOs learner‑aware. In adaptive programs, learners only see the sections and sub‑learning objects that are visible to them based on adaptive rules, while admins can see the underlying adaptive configuration for a user group.

_Do I need to update my integration if it assumes all sections and sub LOs are always returned?_

Yes. For adaptive learning programs, the API now returns only the sections and sub LOs that are visible to the current learner. Client code should treat the response as the authoritative, possibly filtered view, instead of assuming a complete list.

_How can I programmatically reset a learner's completion for a course or learning program?_

Use the new endpoint:

```POST /primeapi/v2/learningObjects/{loId}/instances/{loInstanceId}/refreshCompletion```
This resets completion for the targeted instance when permissions and state allow it.

_How do I tell if a learner completed something via an alternate or equivalent learning object?_

Check the isAlternateComplete attribute on the learning object. If it's true, the alternateCompletions relationship lists the learning objects that acted as alternates for that learner's completion.

_How can I find all alternates that can satisfy a particular learning object?_

Use the following endpoint:

```GET /primeapi/v2/learningObjects/{loId}/relatedLOs?type=sourceAlternateLOs&limit={n}```

and use the data array (for the alternates) and meta.count (for the total number of alternates).

_How do I know whether a learner is allowed to start a module at this moment?_

First, fetch the resource's timeSlot from:

```GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources``` 
and then use:

```GET /primeapi/v2/learningObjects/{loId}/instances/{loInstanceId}/loResources/{loResourceId}/canStart```

_What does hasContentDrivenAttemptTracking mean on a resource?_

It indicates that attempt tracking is controlled by the content itself (for example, via SCORM/xAPI logic) rather than just by platform counters. When it's true, don't rely solely on platform attempt counts or limits for your UX and reporting.

_How do I get menus appropriate for non‑logged‑in users (public experiences)?_  

Use:

```GET /primeapi/v2/templates/menus?include=pages,subMenus.pages&isNonLoggedIn=true```

This returns menu and page structures filtered for anonymous users, suitable for Experience Builder or other headless sites.

_What has changed in Job Aid filtering with effectiveModifiedDate?_ 

Requests that combine filter.effectiveModifiedDate with filter.loTypes=jobAid now correctly return only Job Aids within the specified date window. 

_What has changed in the Job Aid resource ID format and how should I handle it?_

The ID format changed from values like:

```jobAid:<jobAidId>_-1_-1_2_resource```

to:

```jobAid:<jobAidId>_<version>_<localeCode>```

for example jobAid:131032_2_fr_FR. Any system that stores or parses Job Aid resource IDs must be updated, and you should plan to rebuild local indexes keyed by these IDs after upgrading to the April 2026 release.
