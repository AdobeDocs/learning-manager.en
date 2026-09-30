---
description: Public, learner-facing API endpoints for listing, retrieving, enrolling in, and deleting Personalized Learning Paths in Adobe Learning Manager and API endpoints for checking whether one or more learning objects are directly accessible to a given learner through a catalog assigned to them.
jcr-language: en_us
title: API changes in Sep 2026
---

# API changes in September 2026

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
Adobe Learning Manager account. For example, changes to Basics, Integrations, or
Advanced account settings over a given date range. Generating the Audit Trail report requires querying and aggregating configuration change records across the requested date range and setting types. Depending on the size of the range and the volume of changes, this can exceed the time limits of a synchronous HTTP request, which risks client or gateway timeouts.

To avoid this, the report is generated asynchronously through the generic Job API:

1. **Create a job.** The admin submits a request specifying the report type, date range, and setting types. The API returns a job ID immediately, without waiting for the report to be compiled.

2. **Poll the job.** The admin periodically retrieves the job by its ID to check its status. When the job completes, the response contains the result, or a reference to it.

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

- `admin:write` create a report job (`ROLE_ADMIN` required)
- `admin:read` read the status and result of a job (`ROLE_ADMIN` required)

Requests made by a caller who does not hold `ROLE_ADMIN` on the account are
rejected; see [Error handling](/help/migrated/api-changes-sep-2026.md#error-handling)

### Endpoints

#### Create an Audit Trail Report job

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

Response: `202 Created`. The response body is the job resource in its initial
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

#### Get the status of an Audit Trail Report job

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

### Error handling {#audit-trail-report-error-handling}

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
