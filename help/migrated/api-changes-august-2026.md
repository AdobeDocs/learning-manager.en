---
description: API changes in ALM
jcr-language: en_us
title: API changes in the August 2026 release of Adobe Learning Manager
---

# API changes in the August 2026 release of Adobe Learning Manager

## User groups admin API in Adobe Learning Manager

This release adds three new Admin-scoped public API endpoints for managing custom user groups programmatically. You can create, rename, and delete custom user groups without using the Admin app, enabling you to automate group management as part of your identity or provisioning workflows.

These endpoints work only with custom user groups. System-managed groups, such as the All Users group and auto-generated user groups, have readOnly: true in the API response and cannot be modified or deleted through these endpoints.

For API authentication requirements, see [Adobe Learning Manager API authentication](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual#authentication-using-oauth-20).

### User groups API endpoints

All three endpoints require an admin access token with write permissions (ROLE_ADMIN).

| **Method** | **Path** | **Operation** | **Success code** |
|---|---|---|---|
| POST | /primeapi/v2/userGroups | Create a custom user group | 201 Created |
| PUT | /primeapi/v2/userGroups/{id} | Update a group's name or description | 200 OK |
| DELETE | /primeapi/v2/userGroups/{id} | Delete a custom user group | 204 No Content |

## **Common request headers**

All three endpoints require the following headers.

```
Authorization: Bearer \<access-token\>
X-acap-user: \<user-id\>
X-acap-account: \<account-id\>
X-acap-caller-role: ROLE_ADMIN
Content-Type: application/vnd.api+json
Accept: application/vnd.api+json
```

### **Create a user group**

```
POST /primeapi/v2/userGroups
```

Creates a new custom user group with an initial list of members. The group is immediately available for use in the Admin app.

#### **Request body**

```
{
  "name": "Marketing Team",
  "description": "Custom user group for marketing onboarding",
  "data": [
    { "type": "user", "id": "11282373" },
    { "type": "user", "id": "11282374" }
  ]
}
```

#### **Request parameters**

| **Parameter** | **Required** | **Type** | **Description**                                                                     |
|---------------|--------------|----------|-------------------------------------------------------------------------------------|
| name          | Yes          | string   | Display name of the group. Must not be blank or whitespace-only.                    |
| description   | No           | string   | Optional description of the group's purpose.                                        |
| data          | Yes          | array    | Initial member list. Minimum 1 item, maximum 100 items.                             |
| data[].type   | Yes          | string   | Must be "user". No other resource types are accepted.                               |
| data[].id     | Yes          | string   | Numeric user ID string. The user must belong to the account and have ACTIVE status. |

> **Note:** The data array is only used at creation to set the initial member list. To add or remove members after creation, use the existing user group membership endpoints.

#### **Response 201 Created**

```
{
  "links": {
    "self": "https://<host>/primeapi/v2/userGroups"
  },
  "data": {
    "id": "2769204",
    "type": "userGroup",
    "attributes": {
      "dateCreated": "2026-06-04T14:19:53.000Z",
      "description": "Custom user group for marketing onboarding",
      "name": "Marketing Team",
      "readOnly": false,
      "userCount": 2
    }
  }
}
```

#### **Validation rules POST**

| **#** | **Validation**                                        | **Error code**                                           | **Trigger**                                    |
|-------|-------------------------------------------------------|----------------------------------------------------------|------------------------------------------------|
| 1     | name is present and not blank                         | USERGROUP_CREATE_NAME_REQUIRED                           | Name omitted or whitespace-only                |
| 2     | data contains at least 1 user                         | USERGROUP_CREATE_USERS_REQUIRED                          | data absent or empty array                     |
| 3     | data contains 100 or fewer users                      | USERGROUP_USERS_MAX_LIMIT_EXCEEDED                       | More than 100 entries in data[]                |
| 4     | All user IDs are numeric strings                      | INVALID_USER_IDS                                         | Non-numeric string found in data[].id          |
| 5     | All users exist in the account and have ACTIVE status | INVALID_USER_IDS / USERGROUP_CREATE_USERS_NOT_IN_ACCOUNT | User not found or not active                   |
| 6     | Account has not reached the custom group limit        | 400                                                      | Account-level limit for custom groups exceeded |

### **Update a user group**

```
PUT /primeapi/v2/userGroups/{id}
```

Updates the name and/or description of an existing custom user group. This endpoint cannot add or remove group members.

Either field may be omitted; omitting a field leaves its current value unchanged. Passing null for description clears it. Passing a blank string for name is rejected.

#### **Request body**

```json
{
  "name": "Updated Group Name",
  "description": "Updated description text"
}
```

#### **Request parameters**

| **Parameter** | **Required** | **Type** | **Description**                                                           |
|---------------|--------------|----------|---------------------------------------------------------------------------|
| name          | Yes          |  string   | New display name. Must not be blank if provided. Omit to leave unchanged. |
| description   | No           | string   | New description. Pass null to clear. Omit to leave unchanged.               |

#### **Response 200 OK**

```
{
  "data": {
    "type": "userGroup",
    "id": "2767870",
    "attributes": {
      "name": "Updated Group Name",
      "description": "Updated description text",
      "readOnly": false,
      "state": "Active",
      "userCount": 3
    }
  }
}
```

#### **Validation rules PUT**

| **#** | **Validation**                      | **Error code**                         | **Trigger**                                              |
|-------|-------------------------------------|----------------------------------------|----------------------------------------------------------|
| 1     | data is null or absent              | USERGROUP_UPDATE_USERS_NOT_ALLOWED     | Caller passed non-null data attempting membership change |
| 2     | name, if provided, is not blank     | USERGROUP_UPDATE_NAME_BLANK            | name sent as whitespace-only string                      |
| 3     | Group exists in this account        | INVALID_USER_GROUP_ID                  | Unknown {id} path parameter                              |
| 4     | Group is not already deleted        | DELETED_USERGROUP                      | Group was previously deleted                             |
| 5     | Group readOnly is false             | READ_ONLY_USERGROUP                    | System-managed group                                     |
| 6     | Group is a custom (non-system) type | USERGROUP_UPDATE_OPERATION_NOT_ALLOWED | System-internal group type                               |

### **Delete a user group**

```
DELETE /primeapi/v2/userGroups/{id}
```

Marks the specified custom user group as deleted. The group record is not permanently removed — its state is set to DELETED, which makes it invisible in the Admin app and ineligible for use in new configurations. The group ID cannot be reused.

#### **Request example**

```
DELETE /primeapi/v2/userGroups/2767870
Authorization: Bearer <access-token>
X-acap-user: <user-id>
X-acap-account: <account-id>
X-acap-caller-role: ROLE_ADMIN
```

#### **Response 204 No Content**

The response body is empty.

> **Note:** DELETE is not idempotent. Sending a second DELETE request to the same group ID returns a 400 error with the DELETED_USERGROUP code — not 204. Treat a 400 DELETED_USERGROUP response as confirmation that the group is already deleted. Bulk deletion is not supported; each group requires a separate DELETE request.

#### **Validation rules DELETE**

| **#** | **Validation**                      | **Error code**                         | **Trigger**                                       |
|-------|-------------------------------------|----------------------------------------|---------------------------------------------------|
| 1     | Group exists in this account        | INVALID_USER_GROUP_ID                  | Unknown {id} path parameter                       |
| 2     | Group is not already deleted        | DELETED_USERGROUP                      | Repeat DELETE on a group already in DELETED state |
| 3     | Group readOnly is false             | READ_ONLY_USERGROUP                    | System-managed group                              |
| 4     | Group is a custom (non-system) type | USERGROUP_UPDATE_OPERATION_NOT_ALLOWED | System-internal group type |

## External learning API in Adobe Learning Manager

This release adds five new Learner-scoped API endpoints for the External Learning feature. These endpoints allow learners to create, retrieve, and update external learning submissions programmatically, for example, from a mobile app, an integrated HR system, or a custom learning portal.

The external learning workflow through the API mirrors the workflow in the Learner app: a learner submits training details and an optional proof document, their direct manager receives a notification to review the submission, and on approval the record appears in the learner's transcript.

All five endpoints are learner-scoped. A learner can only access their own submissions — the API returns an error if a learner attempts to access another learner's data.

For API authentication requirements, see [Adobe Learning Manager API authentication](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual#authentication-using-oauth-20).

### External Learning API endpoints

All endpoints require a learner access token (ROLE_LEARNER).

| **Method** | **Path**                              | **Operation**                    | **Success code** |
|------------|---------------------------------------|----------------------------------|------------------|
| GET        | /primeapi/v2/externalLearningSettings | Fetch account form configuration | 200 OK           |
| GET        | /primeapi/v2/externalLearnings        | List the caller's submissions    | 200 OK           |
| GET        | /primeapi/v2/externalLearnings/{id}   | Fetch a single submission        | 200 OK           |
| POST       | /primeapi/v2/externalLearnings        | Create a new submission          | 201 Created      |
| PUT        | /primeapi/v2/externalLearnings/{id}   | Update a pending submission      | 200 OK           |

### Common request headers

```
Authorization: Bearer <access-token>
X-acap-user: <user-id>
X-acap-account: <account-id>
X-acap-caller-role: ROLE_LEARNER
Accept: application/vnd.api+json
Content-Type: application/vnd.api+json (POST and PUT only)
```

### Submission status lifecycle

| **Status** | **Set by**       | **Meaning**                             | **Can learner update?**     |
|------------|------------------|-----------------------------------------|-----------------------------|
| PENDING    | System on create | Awaiting manager review                 | Yes- via PUT                |
| APPROVED   | Manager          | Accepted; appears in learner transcript | No- PUT returns 409         |
| REJECTED   | Manager          | Declined; review comment attached       | No- create a new submission |

APPROVED and REJECTED are terminal states. A rejected submission cannot be reopened; the learner must create a new submission.

### Fetch account form configuration

```
GET /primeapi/v2/externalLearningSettings
```

Returns the account-level form configuration. Call this endpoint before rendering a submission form. The response defines which fields to display, which are mandatory, their data types, and any custom fields configured by the administrator.

Check the top-level enabled attribute before proceeding, if false, the External Learning feature is not active for this account, and submission endpoints will return errors.

#### Response 200 OK

```
{
  "data": {
    "id": "8627",
    "type": "externalLearningSettings",
    "attributes": {
      "enabled": true,
      "updatedAt": "2026-06-05T06:51:20.000Z",
      "coreFields": [
        { "id": "title", "type": "TEXT", "mandatory": true, "editable": false, "order": 0 },
        { "id": "description_notes", "type": "TEXT", "mandatory": false, "editable": true, "order": 1 },
        { "id": "date", "type": "TIMESTAMP", "mandatory": false, "editable": true, "order": 2 },
        { "id": "score", "type": "NUMBER", "mandatory": true, "editable": true, "order": 3 },
        { "id": "duration", "type": "TEXT", "mandatory": false, "editable": true, "order": 4 },
        { "id": "attachments", "type": "FILE_UPLOAD", "mandatory": true, "editable": true, "order": 5 }
      ],
      "customFields": [
        {
          "id": "960369b2-...",
          "type": "NUMBER",
          "mandatory": true,
          "order": 0,
          "label": { "en_US": "Employee Code" }
        },
        {
          "id": "3c6cc6d9-...",
          "type": "DROPDOWN",
          "mandatory": true,
          "order": 1,
          "label": { "en_US": "Department" },
          "options": [
            { "option_id": "opt_1", "label": { "en_US": "IT" } },
            { "option_id": "opt_2", "label": { "en_US": "HR" } },
            { "option_id": "opt_3", "label": { "en_US": "FIN" } }
          ]
        }
      ]
    }
  }
}
```

#### Core field reference

| **Field ID**      | **Type**    | **Default mandatory** | **Notes**                                                                                                |
|-------------------|-------------|-----------------------|----------------------------------------------------------------------------------------------------------|
| title             | TEXT        | Yes                   | Training name. Always present. Cannot be disabled by the administrator.                                  |
| description_notes | TEXT        | No                    | Free-text description or notes.                                                                          |
| date              | TIMESTAMP   | No                    | Date range. Value shape: { "start_date": "<ISO-Z>", "end_date": "<ISO-Z>" }. Either value may be null.   |
| score             | NUMBER      | Yes                   | Value shape: { "achieved_score": <number>, "max_score": <number> }. Both values must be numeric.         |
| duration          | TEXT        | No                    | Freeform string, for example "40 hours".                                                                 |
| attachments       | FILE_UPLOAD | Yes                   | Proof of completion. **Not** passed inside fields[] — use the top-level submissionUrl attribute instead. |

Custom fields are defined by the administrator and returned in customFields[]. Their IDs, types, mandatory flags, labels, and dropdown options vary by account configuration.

### List submissions

```
GET /primeapi/v2/externalLearnings
```

Returns a paginated list of the authenticated learner's own submissions, sorted by modifiedAt descending (most recently modified first).

#### **Query parameters**

| **Parameter** | **Default** | **Maximum** | **Description**                                                                                       |
|---------------|-------------|-------------|-------------------------------------------------------------------------------------------------------|
| page[offset]  | 0           | 5000        | Zero-based record offset.                                                                             |
| page[limit]   | 10          | 100         | Records per page. Values above 100 are silently clamped to 100.                                       |
| ls_qp_status  | —           | —           | Filter by status. Omit for all results. Valid values: PENDING, APPROVED, REJECTED (case-insensitive). |

#### **Response 200 OK**

```
{
  "links": {
    "next": "/primeapi/v2/externalLearnings?page[offset]=10&page[limit]=10"
  },
  "data": [
    { "id": "1001", "type": "externalLearning", "attributes": { "status": "PENDING", ... } },
    { "id": "1002", "type": "externalLearning", "attributes": { "status": "APPROVED", ... } }
  ]
}
```

### Fetch a submission

```
GET /primeapi/v2/externalLearnings/{id}
```

Returns the full record for a single submission belonging to the authenticated learner.

#### **Response 200 OK

```
{
  "data": {
    "id": "1001",
    "type": "externalLearning",
    "attributes": {
      "submissionUrl": "https://<cdn-url>/cert.pdf",
      "title": "Java Fundamentals Certification",
      "status": "PENDING",
      "creationSource": "LEARNER",
      "createdAt": "2026-04-14T08:30:00.000Z",
      "modifiedAt": "2026-04-16T11:45:00.000Z",
      "fields": [ "...resolved against live settings..." ]
    },
    "relationships": {
      "reviewerUser": { "data": null }
    }
  }
}
```

### Create a submission

```
POST /primeapi/v2/externalLearnings
```

Creates a new external learning submission in PENDING state. All mandatory fields defined in the account settings must be included. After a successful POST, the learner's manager receives an in-platform notification to review the submission.

### **File upload**

The attachments field is handled separately from the other fields. Do not include it inside fields[]. Instead:

1.Obtain a pre-signed S3 upload URL from the ALM file upload endpoint.

2.Upload the file to that URL.

3.Pass the resulting URL as the top-level submissionUrl attribute in your POST request.

#### **Request body**

```
{
  "data": {
    "type": "externalLearning",
    "attributes": {
      "submissionUrl": "<pre-signed-upload-url>",
      "fields": [
        { "id": "title", "type": "TEXT", "value": "Java Fundamentals Certification" },
        { "id": "description_notes", "type": "TEXT", "value": "Completed via online course platform." },
        { "id": "date", "type": "TIMESTAMP", "value": { "start_date": "2026-05-01T00:00:00.000Z", "end_date": "2026-05-15T00:00:00.000Z" } },
        { "id": "score", "type": "NUMBER", "value": { "achieved_score": 88, "max_score": 100 } },
        { "id": "duration", "type": "TEXT", "value": "40 hours" },
        { "id": "960369b2-...", "type": "NUMBER", "value": "1225" },
        { "id": "3c6cc6d9-...", "type": "DROPDOWN", "value": "opt_3" }
      ]
    }
  }
}
```

#### Field value shapes

| **Field type** | **Value shape**                                         | **Example**                                                    |
|----------------|---------------------------------------------------------|----------------------------------------------------------------|
| TEXT           | String                                                  | "Java Fundamentals"                                            |
| NUMBER         | Object with achieved_score and max_score                | { "achieved_score": 88, "max_score": 100 }                     |
| TIMESTAMP      | Object with start_date and end_date (ISO 8601, or null) | { "start_date": "2026-05-01T00:00:00.000Z", "end_date": null } |
| DROPDOWN       | option_id string from account settings                  | "opt_3"                                                        |
| FILE_UPLOAD    | Not allowed inside fields[] — use submissionUrl         | —                                                              |

#### Validation rules POST

| **#** | **Validation**                                                  | **Trigger**                                              |
|-------|-----------------------------------------------------------------|----------------------------------------------------------|
| 1     | External Learning is enabled for the account                    | Feature flag disabled                                    |
| 2     | All mandatory fields are present in fields[]                    | Mandatory field omitted                                  |
| 3     | Each field id, type, and value shape match the account settings | Wrong type or malformed value object                     |
| 4     | FILE_UPLOAD type not present inside fields[]                    | Attachment sent inside fields[] instead of submissionUrl |
| 5     | submissionUrl is a valid S3 pre-signed URL                      | CDN URLs and non-S3 URLs rejected at create time         |
| 6     | submissionUrl present when attachments.mandatory is true        | Attachments are required but submissionUrl is missing    |

### Update a submission

```
PUT /primeapi/v2/externalLearnings/{id}
```

Updates an existing PENDING submission. Only PENDING submissions can be updated. Attempting to PUT an APPROVED or REJECTED submission returns a 409 error.

**This endpoint uses full-replace semantics.** Provide the complete fields[] array in every PUT request, not just the fields you are changing. Fields omitted from the array are cleared.

#### Fields the learner can update

| **Field / attribute** | **Learner can update** | **Notes**                                                                  |
|-----------------------|------------------------|----------------------------------------------------------------------------|
| fields[]              | Yes                    | Full replace — include all fields, not just changed ones                   |
| submissionUrl         | Yes                    | CDN URLs are accepted on PUT; S3 pre-signed URLs are required only on POST |
| reviewerUserId        | No                     | Set by manager action; read-only to learner                                |
| reviewedAt            | No                     | Set by manager action; read-only to learner                                |
| reviewerComment       | No                     | Set by manager action; read-only to learner                                |
| status                | No                     | Controlled by manager: PENDING → APPROVED or REJECTED                      |
| creationSource        | No                     | Always LEARNER for API-created submissions                                 |
| createdAt             | No                     | Set at create time; immutable                                              |

#### Request body

```
{
  "data": {
    "type": "externalLearning",
    "attributes": {
      "submissionUrl": "<cdn-url>/cert-v2.pdf",
      "fields": [
        { "id": "title", "type": "TEXT", "value": "Java Fundamentals — Updated" },
        { "id": "description_notes", "type": "TEXT", "value": "Updated notes." },
        { "id": "date", "type": "TIMESTAMP", "value": { "start_date": null, "end_date": null } },
        { "id": "score", "type": "NUMBER", "value": { "achieved_score": 92, "max_score": 100 } },
        { "id": "duration", "type": "TEXT", "value": "42 hours" },
        { "id": "960369b2-...", "type": "NUMBER", "value": "1227" },
        { "id": "3c6cc6d9-...", "type": "DROPDOWN", "value": "opt_2" }
      ]
    }
  }
}
```

## API for learner-relevant certification ID and root certification ID in LT

When a recurring certification renews, Adobe Learning Manager creates a new version of the certification and automatically enrolls active learners into it. If your integration queries certification data directly rather than relying on the Adobe Learning Manager learner experience, you can use this API to determine exactly which version of a recurring certification is relevant to a specific learner at any point in time.

### Purpose of the API

Recurring certifications generate a new certification ID each time they renew. In the native Adobe Learning Manager learner experience, only the version relevant to each learner is shown. Older versions are hidden automatically once a learner moves to a newer one.

If your integration retrieves certification data independently, for example, to display certification information on an external portal, it may not automatically apply this filtering. Without it, a learner could see every historical version of a recurring certification, including those no longer relevant to them, with no indication of which to act on.

This API addressed that gap. Given the root certification ID, it returns the specific certification version that applies to a given learner, accounting for their enrollment history and any recurrences.

### Understand certification recurrence

When a certification is configured to recur, each renewal creates a new certification version with its own unique ID. All versions trace back to a single **root certification ID,** the ID of the original certification when it was first created.

For example, a certification that recurs every month might produce a sequence of versions over time, where each new version is generated automatically when the recurrence interval is reached. Learners who are actively enrolled when a recurrence occurs are automatically enrolled into the new version.

Because each version has a distinct ID, a learner's relevant version depends on their individual enrollment timeline:

- A learner who enrolled before a recurrence and completed their certification before the next recurrence occurred will have moved through several versions over time.

- A learner who enrolls partway through a recurrence cycle is enrolled directly into whichever version is current at the time they enroll.

### Determine the relevant certification version

Use the certification version API to identify which version of a recurring certification is relevant to a specific learner.

Provide the **root certification ID** as an input. The API evaluates the learner's enrollment history and returns the appropriate version based on the following rules:

| **Learner state**                                | **What the API returns**                                                                                                                     |
|--------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Learner is not yet enrolled in the certification | The latest available version of the certification                                                                                            |
| Learner is currently enrolled                    | The specific version the learner is currently enrolled in, accounting for any recurrences that have occurred since their original enrollment |

This means two learners querying the same root certification ID at the same time may receive different results, depending on each learner's individual enrollment history.

**Note**: There may be a brief window during a recurrence, while the new version is being created, and enrollments are being migrated, in which the API may return the version that is about to be superseded rather than the newly created one.

**Example**

Consider a certification that recurs monthly, where four versions have been created over time because of successive recurrences:

- A learner who enrolled in the first version and progressed through each recurrence as it occurred will be returned to the version, they are currently active in, which reflects their own completion and recurrence history, not necessarily the very latest version that exists.

- A learner who has not yet enrolled at all will be returned to the most recently created version, since that is the version new enrollments should join.

This allows the integration to always direct a learner to the certification version that is relevant to them, rather than showing every historical version or guessing which one applies.

### API reference

**Get the applicable certification for a root certification**

```
GET /primeapi/v2/learningObjects/{loId}/applicableCertification
```

Resolves the certification version that applies to the current learner, given the ID of a root certification. For learners who are enrolled, this returns the version they are currently enrolled in. For learners who are not enrolled, this returns the latest active version.

| **Property**                                             | **Value**                |
|----------------------------------------------------------|--------------------------|
| **Scope**                                                | Learner read access      |
| **Rate limit (standard learner calls)**                  | 70 requests per minute   |
| **Rate limit (elevated or admin-level API credentials)** | 500 requests per hour    |
| **Response format**                                      | application/vnd.api+json |

**Note**: This API returns version information for a single learner at a time. It does not return a list of all versions of a certification.

**Path parameters**

| **Parameter** | **Required** | **Type** | **Description**                                                                                                                                                           |
|---------------|--------------|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| loId          | Yes          | string   | The ID of the Learning Object, specifically, the root certification, for which the applicable version is being requested. This is subject to standard access permissions. |

**Query parameters**

| **Parameter** | **Required** | **Type** | **Description**                                                                                                                                                                                                                 |
|---------------|--------------|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| include       | No           | string   | A comma-separated list of related models to include in the response alongside the resolved certification, such as subLOs or enrollment. Uses the same include syntax as other Adobe Learning Manager learning object endpoints. |

**Example request**

```
GET /primeapi/v2/learningObjects/certification%3A167658/applicableCertification?include=subLOs
Accept: application/vnd.api+json
Authorization: oauth <access-token>
```

```
curl -X GET --header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
'https://<host>/primeapi/v2/learningObjects/certification%3A167658/applicableCertification?include=subLOs'
```

**Note**: The loId value must be URL-encoded. The colon in a certification ID such as certification:167658 is encoded as %3A.

**Example response 200 OK**

The response uses the same structure as a standard Learning Object response, returning the resolved certification.

**Important:** The id field in the response is the **resolved** certification's ID, the specific version applicable to this learner. It will commonly be different from the root certification ID you passed in as loId, since the whole purpose of this API is to translate a root ID into the correct current version.

```
{
  "data": {
    "id": "string",
    "type": "string",
    "attributes": {
      "authorNames": [
        "string"
      ],
      "bannerUrl": "string",
      "catalogs": [
        ...
      ]
    }
  }
}
```

**Response codes**

| **Status** | **Meaning**                                                                                                                                                                                                                                                                                                                                                   |
|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 200        | The applicable certification was resolved successfully and is returned in response.                                                                                                                                                                                                                                                                           |
| 400        | The provided loId is either not a certification, or it is not a root certification. Pass the ID of the original certification, not a recurrence version, as the loId.                                                                                                                                                                                         |
| 401 / 403  | The request is missing valid learner credentials, or the credentials do not have the required access.                                                                                                                                                                                                                                                         |
| 404        | No active certification could be resolved for this root certification. For example, because every version in the chain has been retired or deleted, or because the certification has no recorded root certification reference at all. A 404 can also occur if a version is resolved successfully, but the calling learner does not have catalog access to it. |
| 500        | An unexpected server error occurred while resolving the certification. Retry the request; if the error persists, contact support.                                                                                                                                                                                                                             |

**Example error response**

```
{
  "meta": {
    "error": "string",
    "detail": "string"
  }
}
```

**Note:** This API resolves the version for one learner per call. It does not return a list of every version that exists for a root certification.

**Important points**

- **Non-recurring certifications: I**f the loId you pass is a certification that is not configured to recur, the API returns that certification itself.

- **Skipped intermediate versions: I**f a learner's active enrollment moved directly from an earlier version to a later one without an active enrollment between, the API still resolves correctly to the learner's actual current version. The presence of intermediate versions that the learner did not actively engage with does not affect resolution.

- **Deleted versus retired certifications:** A certification version that has been deleted is excluded from resolution entirely. A retired certification may still be considered depending on its state; if you are relying on a specific version remaining resolvable, confirm its current state rather than assuming retirement alone removes it from consideration.

- **Resolution is deterministic:** If a learner's enrollment data is in an inconsistent state (for example, more than one enrollment is marked as current), the API resolves to the most recently created version rather than returning an unpredictable result or an error.

**Note**: An administrator-scoped equivalent of this API is not currently available and is being evaluated for a future release.

### Use this API in your integration

A common use case is an external page or portal that lists certifications a learner can access. Rather than linking directly to a specific certification ID, which may become outdated after a recurrence. Link using the root certification ID and resolve the correct version at the moment the learner selects it.

1.Store or reference certifications in your integration using the **root certification ID,** the ID of the certification as it was first created, before any recurrences.

2.When a learner selects a certification to view or act on, call GET /primeapi/v2/learningObjects/{loId}/applicableCertification, passing the root certification ID as loId.

3.Use the certification version returned in the response to direct the learner to the correct destination, whether that is an enrollment action or a view of their current progress.

This ensures learners always land on the version of the certification that matches their actual enrollment and progress, even as the certification recurs over time and generates new versions.

## Reporting: Root Training ID in the Learner Transcript

The **Root Training ID** column is available by default in the Learner Transcript for all accounts.

| **Row type**                                                    | **Root Training ID value**                                                     |
|-----------------------------------------------------------------|--------------------------------------------------------------------------------|
| Certification configured to recur                               | The root certification ID that this version traces back to                     |
| Certification not configured to recur                           | The same value as the Training ID for that row                                 |
| A course embedded within a certification                        | The root certification ID of the parent certification, not the course's own ID |
| A course or learning path that is not part of any certification | The same value as the Training ID or Embedded Course ID for that row           |

**Note**: For very large accounts with a high volume of certifications, Root Training ID values in the Learner Transcript are resolved in batches. This does not change the accuracy of the data, but very large transcripts may take longer to generate.

This column lets you group and report on a learner's complete history across every version of a recurring certification, rather than treating each recurrence as an unrelated, independent record. Each recurrence still appears as its own row in the Learner Transcript. The Root Training ID column simply identifies which rows belong to the same underlying certification.

**Note:** Use the Root Training ID column when you need to trace a learner's full participation history across a recurring certification.

