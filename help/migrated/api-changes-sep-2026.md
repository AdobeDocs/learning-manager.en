---
description: Public, learner-facing API endpoints for listing, retrieving, enrolling in, and deleting Personalized Learning Paths in Adobe Learning Manager and API endpoints for checking whether one or more learning objects are directly accessible to a given learner through a catalog assigned to them.
jcr-language: en_us
title: API changes in Sep 2026
---

# API changes in Sep 2026

## Personalized Learning Path API

A Personalized Learning Path is a Learning Path that a learner builds from existing catalogs and courses using the Learning Path Agent. Once created, a learner can view it and consume the Learning Path.

This article covers the public, learner-facing API endpoints for working with Personalized Learning Paths: listing a learner's paths, retrieving path details, enrolling in a path that was shared with you, and deleting a path you created.

### Base URL and conventions {#base-url-and-conventions}

| Item | Value |
|---|---|
| Base path | |
| Content type | application/vnd.api+json;charset=UTF-8 (JSON:API) |
| Authentication | Bearer OAuth token, scoped to the learner |
| Pagination | page[offset] (default 0), page[limit] (default 10) - list endpoint only |
| Sparse fetch | include- comma-separated list of relationship names to expand |

### IDs {#ids}

Every id field returned by these endpoints (path ID, enrollment ID, and so on) is an opaque string. Always pass back the exact id value you received from a prior response. Never construct or parse it.

### Authentication scopes {#authentication-scopes}

Each endpoint requires an OAuth token carrying one of the following scopes:

* **learner:read** - read-only endpoints
* **learner:write** - endpoints that create or delete data (enroll, delete)

### Endpoints {#endpoints}

#### List Personalized Learning Paths

`GET /primeapi/v2/personalizedPaths`

Returns all Personalized Learning Paths the user is enrolled in.

**Scope:** learner:read

| Query parameter | Required | Default | Description |
|---|---|---|---|
| include | No | NA | Comma-separated relationships to expand, for example, include=enrollment,skills,subLOs |
| page[offset] | No | 0 | Pagination offset |
| page[limit] | No | 10 | Page size |

**Sample response**

```json
{
  "data": [
    {
      "id": "personalizedPath:77",
      "type": "personalizedPath",
      "attributes": {
        "dateCreated": "2026-01-15T10:30:00.000Z",
        "dateUpdated": "2026-01-20T08:00:00.000Z",
        "enrollmentType": "Self Enroll",
        "isExternal": false,
        "state": "Active",
        "loType": "personalizedPath",
        "duration": 3600
      }
    }
  ]
}
```

#### Get a Personalized Learning Path

`GET /primeapi/v2/personalizedPaths/{id}`

Returns a single Personalized Learning Path by ID.

**Scope:** learner:read

| Parameter | In | Required | Description |
|---|---|---|---|
| id | path | Yes | Personalized Learning Path ID |
| include | query | No | e.g. include=subLOs,enrollment,skills,subLOs.enrollment,subLOs.enrollment.loResourceGrades,subLOs.instances.loResources.resources |

**Errors:** 400 BAD_REQUEST (code: OBJECT_DOESNT_EXIST) if the ID doesn't exist or is malformed.

#### Enroll in a shared Personalized Learning Path

`POST /primeapi/v2/personalizedPaths/{id}/enrollment`

Enrolls the current learner in a path that was shared with them. Enrollment **cascades**: the learner is automatically enrolled in every course inside the path.

**Scope:** learner:write

| Parameter | In | Required | Description |
|---|---|---|---|
| id | path | Yes | Personalized Learning Path ID |

**Response:** 201 Created. The response body is the full path resource.

#### Delete a Personalized Learning Path

`DELETE /primeapi/v2/personalizedPaths/{id}`

Deletes a Personalized Learning Path. Only the creator of a path can delete it.

**Scope:** learner:write

| Parameter | In | Required | Description |
|---|---|---|---|
| id | path | Yes | Personalized Learning Path ID |

**Response:** 204 No Content.

### Resource schema {#resource-schema}

*personalizedPath* attributes

| Field | Type | Description |
|---|---|---|
| id | string | Opaque path ID |
| dateCreated | string (ISO-8601) | Creation timestamp |
| dateUpdated | string (ISO-8601) | Last modified timestamp |
| enrollmentType | string | Self Enroll |
| isExternal | boolean | Whether the object is internal or external |
| imageUrl | string | Thumbnail URL |
| bannerUrl | string | Banner URL |
| localizedMetadata | array | Localized name, description, and overview per locale (embedded) |
| state | string | Active |
| loType | string | personalizedPath |
| duration | number | Total duration, in seconds |
| createdByUserId | number | ID of the learner who created the path |
| enrollment | relationship → loInstanceEnrollment | Current user's enrollment for the path. Expand with include=enrollment |
| sections | array | Path sections, each with ordered learning object IDs (embedded - see below) |
| skills | relationship → skill | Associated skills. Expand with include=skills |
| subLOs | relationship → learningObject | All sub-learning objects in the path. Expand with include=subLOs |

#### sections (embedded, inside a path) {#sections-embedded-inside-a-path}

| Field | Description |
|---|---|
| id | Section ID |
| loIds | Ordered learning object IDs (courses / learning programs) in this section |
| localizedMetadata | Section title per locale |

### Error handling {#error-handling}

The following codes apply to these endpoints:

| HTTP status | Error code | When it occurs |
|---|---|---|
| 400 | BAD_REQUEST | Malformed id - on DELETE and enrollment endpoints only |
| 401 | UNAUTHORIZED_ACCESS | The token is missing, invalid, or expired |
| 400 | OBJECT_DOESNT_EXIST | GET by id: path doesn't exist or is malformed - both cases collapse into this same response |

## API for checking catalog access for learning objects

Determine whether the current learner has direct catalog access to one or more learning objects, independent of whether the learner reached that content through a learning path or certification.

### Purpose of the API

When a learner opens a learning path or certification, they can browse the individual courses inside it, even if a specific course isn't directly assigned to them through a catalog. This supports content discovery: learners can explore what a learning path contains before deciding whether to pursue it.

However, being able to view a course this way should not automatically mean the learner can enroll in it. Enrollment should depend on whether the learner has direct catalog access to that specific course, not just indirect access through a containing learning path.

This API lets you check, for a given learner, whether one or more learning objects are directly accessible through a catalog assigned to them. Use the result to control enrollment-related UI, for example, showing an Enroll option only when direct catalog access is confirmed, while keeping the course page itself viewable in both cases.

### Endpoint

`GET /primeapi/v2/learningObjects/isMemberOfVisibleCatalogs`

| Property | Value |
|---|---|
| **Scope** | Learner read access |
| **Response format** | application/vnd.api+json |

### Query parameters

| Parameter | Required | Type | Description |
|---|---|---|---|
| ids | Yes | string or array | One or more learning object IDs to check. Accepts a single ID or a comma-separated list. Maximum of 10 IDs per request. |

### Example request

```
GET /primeapi/v2/learningObjects/isMemberOfVisibleCatalogs?ids=course%3A2400159%2Ccourse%3A2400160%2Ccourse%3A2400161%2Ccourse%3A2400162
Accept: application/vnd.api+json
Authorization: oauth <access-token>
```

>[!NOTE]
>
>Learning object IDs must be URL-encoded. The colon in an ID such as course:2400159 is encoded as %3A, and the comma separating multiple IDs is encoded as %2C.

### Example response - 200 OK

```json
{
  "course:2400162": false,
  "course:2400161": false,
  "course:2400160": true,
  "course:2400159": true
}
```

| Value | Meaning |
|---|---|
| true | The calling learner has direct catalog access to this learning object. |
| false | The learning object is not directly available to the calling learner through a catalog. The learner may still be able to view it if it is reachable through a learning path or certification they have access to. |

### Response codes

| Status | Meaning |
|---|---|
| 200 | The request succeeded. The response contains a result for each requested ID. |
| 400 | A generic bad request error. For example, more than 10 IDs were provided, or an ID was malformed. |
| 401 | The request is missing valid learner credentials, or access was denied due to invalid credentials. |

### Example error response

```json
{
  "status": "BAD_REQUEST",
  "title": "Bad request. Check url, params and headers",
  "source": {
    "info": "Either LO id is blank or not as per public api specification"
  }
}
```

### Use this API in your integration

A common use case is a course page that a learner reaches by navigating from a learning path. You want the course page itself to remain accessible for discovery, while showing the **Enroll** action only if the learner has direct catalog access to that course.

1. When the course page loads, call this endpoint with the course's learning object ID.
2. If the response returns true for that ID, show the **Enroll** option.
3. If the response returns false, keep the course page viewable, title, description, and course details, but hide the **Enroll** option.

## Job API for Admin Audit Trail Report {#apiaudittrailreport}

### Purpose of the API

The Administrator Audit Trail Report lists the configuration changes made to an
Adobe Learning Manager account &ndash; for example, changes to Basics, Integrations, or
Advanced account settings &ndash; over a given date range. Because compiling this report
can take longer than a typical request/response cycle, it is generated
asynchronously using the generic Job API: an admin creates a job that asks for
the report, and then polls that job until it finishes.

This article covers the admin-facing API endpoints for working with Audit
Trail report jobs: creating a job that generates a Config Change Audit Trail
report for a date range and a set of setting types, and retrieving the status
and result of that job.

### Base URL and conventions

| Item | Value |
|---|---|
| Base path | `/primeapi/v2` |
| Content type | `application/vnd.api+json;charset=UTF-8` (JSON:API) |
| Authentication | Bearer OAuth token, scoped to an account admin |
| Account context | `x-acap-account` header identifying the calling admin's account |
| Polling | No fixed interval is enforced; poll the Get Job Status endpoint until `status` is no longer `QUEUED` or `IN_PROGRESS` |

### IDs

The job `id` returned when a job is created is an opaque string (for example,
`4593`). Always pass back the exact `id` value you received from the create
response when polling for status. Never construct or parse it.

### Authentication scopes

Each endpoint requires an OAuth token carrying the following scope, and the
calling user must hold the account admin role:

- `admin:write` &ndash; create a report job (`ROLE_ADMIN` required)
- `admin:read` &ndash; read the status and result of a job (`ROLE_ADMIN` required)

Requests made by a caller who does not hold `ROLE_ADMIN` on the account are
rejected; see [Error handling](#audittrailreporterrorhandling).

### Endpoints

#### Create an Audit Trail report job

`POST /primeapi/v2/jobs`

Creates an asynchronous job that generates a Config Change Audit Trail report
for the given date range and setting types. The response returns immediately
with a job resource in `QUEUED` state; the report itself is produced in the
background.

Scope: `admin:write`

| Parameter | In | Required | Description |
|---|---|---|---|
| `jobType` | body | Yes | Must be `generateConfigChangeAuditReport` for this report |
| `payload.fromDate` | body | Yes | Start of the reporting window, ISO-8601 with offset, for example `2026-09-15T00:00:00.000+05:30` |
| `payload.toDate` | body | Yes | End of the reporting window, ISO-8601 with offset, for example `2026-09-23T23:59:59.000+05:30` |
| `payload.settingTypes` | body | Yes | Array of one or more setting categories to include; supported values are `Basics`, `Integrations`, and `Advanced` |

Sample request body

```json
{
  "data": {
    "type": "job",
    "attributes": {
      "jobType": "generateConfigChangeAuditReport",
      "payload": {
        "fromDate": "2026-09-15T00:00:00.000+05:30",
        "toDate": "2026-09-23T23:59:59.000+05:30",
        "settingTypes": ["Basics", "Integrations", "Advanced"]
      }
    }
  }
}
```

Response: `202 Accepted`. The response body is the job resource in its initial
`QUEUED` state.

```json
{
  "data": {
    "id": "4593",
    "type": "job",
    "attributes": {
      "jobType": "generateConfigChangeAuditReport",
      "status": "QUEUED",
      "dateCreated": "2026-09-23T18:12:04.000+05:30"
    }
  }
}
```

>[!NOTE]
>
>A `fromDate`/`toDate` window that spans a very large date range, or that
>requests all setting types for an account with a long change history, can
>take longer to process. Poll the Get Job Status endpoint rather than
>assuming the report is ready after a fixed delay.

#### Get the status of an Audit Trail report job

`GET /primeapi/v2/jobs/{id}`

Returns the current status of a previously created job. While the job is
still running, `attributes.status` is `QUEUED` or `IN_PROGRESS` and
`attributes.result` is absent. Once the job finishes, `attributes.status` is
either `COMPLETED`, with the report location in `attributes.result`, or
`FAILED`, with failure details in `attributes.error`.

Scope: `admin:read`

| Parameter | In | Required | Description |
|---|---|---|---|
| `id` | path | Yes | Job ID returned when the job was created |

Sample response while the job is still running

```json
{
  "data": {
    "id": "4593",
    "type": "job",
    "attributes": {
      "jobType": "generateConfigChangeAuditReport",
      "status": "IN_PROGRESS",
      "dateCreated": "2026-09-23T18:12:04.000+05:30"
    }
  }
}
```

Sample response once the job has completed

```json
{
  "data": {
    "id": "4593",
    "type": "job",
    "attributes": {
      "jobType": "generateConfigChangeAuditReport",
      "status": "COMPLETED",
      "dateCreated": "2026-09-23T18:12:04.000+05:30",
      "dateCompleted": "2026-09-23T18:12:41.000+05:30",
      "result": {
        "downloadUrl": "https://learningmanager.adobe.com/primeapi/v2/jobs/4593/download",
        "expiresAt": "2026-09-24T18:12:41.000+05:30"
      }
    }
  }
}
```

### Resource schema

#### Job attributes

| Field | Type | Description |
|---|---|---|
| `id` | string | Opaque job ID |
| `jobType` | string | `generateConfigChangeAuditReport` for this report |
| `status` | string | `QUEUED`, `IN_PROGRESS`, `COMPLETED`, or `FAILED` |
| `dateCreated` | string (ISO-8601) | When the job was created |
| `dateCompleted` | string (ISO-8601) | When the job finished; present once `status` is `COMPLETED` or `FAILED` |
| `payload` | object | The request parameters the job was created with (embedded &ndash; see below) |
| `result` | object | Where to download the finished report; present only when `status` is `COMPLETED` (embedded &ndash; see below) |
| `error` | object | Failure details; present only when `status` is `FAILED` |

#### Payload (embedded, inside the create request)

| Field | Description |
|---|---|
| `fromDate` | Start of the reporting window |
| `toDate` | End of the reporting window |
| `settingTypes` | Setting categories included in the report: `Basics`, `Integrations`, `Advanced` |

#### Result (embedded, inside a completed job)

| Field | Description |
|---|---|
| `downloadUrl` | Signed URL from which the generated report can be downloaded |
| `expiresAt` | When `downloadUrl` stops being valid; request a fresh status check to get a new link after this time |

### Error handling {#audittrailreporterrorhandling}

The following codes apply to these endpoints:

| HTTP status | Error code | When it occurs |
|---|---|---|
| 400 | `BAD_REQUEST` | `toDate` is earlier than `fromDate`, `settingTypes` is empty or contains an unsupported value, or a date is not valid ISO-8601 &ndash; create endpoint only |
| 401 | `UNAUTHORIZED_ACCESS` | The token is missing, invalid, or expired |
| 403 | `FORBIDDEN` | The caller does not hold `ROLE_ADMIN` on the account |
| 400 | `OBJECT_DOESNT_EXIST` | Get by id: job doesn't exist or the id is malformed &ndash; both cases collapse into this same response |

Example error response

```json
{
  "status": "BAD_REQUEST",
  "title": "Bad request. Check url, params and headers",
  "source": {
    "info": "toDate must be on or after fromDate"
  }
}
```

### Use this API in your integration

A common use case is an admin-facing "Download audit trail" action in the
account settings screen.

1. When the admin picks a date range and one or more setting types and
   confirms, call the create-job endpoint with those values.
2. Store the returned job `id` and poll the Get Job Status endpoint at a
   reasonable interval (for example, every few seconds).
3. While `status` is `QUEUED` or `IN_PROGRESS`, keep showing a progress state
   in the UI.
4. When `status` becomes `COMPLETED`, use `result.downloadUrl` to let the
   admin download the report before `expiresAt` passes.
5. When `status` becomes `FAILED`, surface `error` to the admin and let them
   retry.
