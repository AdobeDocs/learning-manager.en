---
description: Public, learner-facing API endpoints for listing, retrieving, enrolling in, and deleting Personalized Learning Paths in Adobe Learning Manager and API endpoints for checking whether one or more learning objects are directly accessible to a given learner through a catalog assigned to them.
jcr-language: en_us
title: API changes in Sep 2026
---

# API changes in Sep 2026

A Personalized Learning Path is a Learning Path that a learner builds from existing catalogs and courses using the Learning Path Agent. Once created, a learner can view it and consume the Learning Path.

This article covers the public, learner-facing API endpoints for working with Personalized Learning Paths: listing a learner's paths, retrieving path details, enrolling in a path that was shared with you, and deleting a path you created.

## Base URL and conventions

| Item | Value |
|---|---|
| Content type | application/vnd.api+json;charset=UTF-8 (JSON:API) |
| Authentication | Bearer OAuth token, scoped to the learner |
| Pagination | page[offset] (default 0), page[limit] (default 10) — list endpoint only |
| Sparse fetch | include= comma-separated list of relationship names to expand |

## IDs

Every id field returned by these endpoints (path ID, enrollment ID, and so on) is an opaque string. Always pass back the exact id value you received from a prior response. Never construct or parse it.

## Authentication scopes

Each endpoint requires an OAuth token carrying one of the following scopes:

* `learner:read` - read-only endpoints
* `learner:write` - endpoints that create or delete data (enroll, delete)

## Endpoints

### List Personalized Learning Paths

`GET /primeapi/v2/personalizedPaths`

Returns all Personalized Learning Paths the user is enrolled in.

**Scope:** `learner:read`

| Query parameter | Required | Default | Description |
|---|---|---|---|
| include | No | NA | Comma-separated relationships to expand, for example, `include=enrollment,skills,subLOs` |
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

### Get a Personalized Learning Path

`GET /primeapi/v2/personalizedPaths/{id}`

Returns a single Personalized Learning Path by ID.

**Scope:** `learner:read`

| Parameter | In | Required | Description |
|---|---|---|---|
| id | path | Yes | Personalized Learning Path ID |
| include | query | No | For example, `include=subLOs,enrollment,skills,subLOs.enrollment,subLOs.enrollment.loResourceGrades,subLOs.instances.loResources.resources` |

**Errors:** `400 BAD_REQUEST` (code: `OBJECT_DOESNT_EXIST`) if the ID doesn't exist or is malformed.

### Enroll in a shared Personalized Learning Path

`POST /primeapi/v2/personalizedPaths/{id}/enrollment`

Enrolls the current learner in a path that was shared with them. Enrollment **cascades**: the learner is automatically enrolled in every course inside the path.

**Scope:** `learner:write`

| Parameter | In | Required | Description |
|---|---|---|---|
| id | path | Yes | Personalized Learning Path ID |

**Response:** `201 Created`. The response body is the full path resource.

### Delete a Personalized Learning Path

`DELETE /primeapi/v2/personalizedPaths/{id}`

Deletes a Personalized Learning Path. Only the creator of a path can delete it.

**Scope:** `learner:write`

| Parameter | In | Required | Description |
|---|---|---|---|
| id | path | Yes | Personalized Learning Path ID |

**Response:** `204 No Content`.

## Resource schema

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
| enrollment | relationship → loInstanceEnrollment | Current user's enrollment for the path. Expand with `include=enrollment` |
| sections | array | Path sections, each with ordered learning object IDs (embedded — see below) |
| skills | relationship → skill | Associated skills. Expand with `include=skills` |
| subLOs | relationship → learningObject | All sub-learning objects in the path. Expand with `include=subLOs` |

### sections (embedded, inside a path) {#sections-embedded-inside-a-path}

| Field | Description |
|---|---|
| id | Section ID |
| loIds | Ordered learning object IDs (courses / learning programs) in this section |
| localizedMetadata | Section title per locale |

## Error handling

The following codes apply to these endpoints:

| HTTP status | Error code | When it occurs |
|---|---|---|
| 400 | BAD_REQUEST | Malformed id — on DELETE and enrollment endpoints only |
| 401 | UNAUTHORIZED_ACCESS | The token is missing, invalid, or expired |
| 400 | OBJECT_DOESNT_EXIST | GET by id: path doesn't exist or is malformed — both cases collapse into this same response |


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
