---
description: Learn how to use the board subscription settings and subscribers APIs to configure digest emails and manage board subscribers
jcr-language: en_us
title: API changes in Nov 2026
exl-id: 9b2d3856-810c-4352-bf18-667f698d4d70
---

# API changes in December 2026

## APIs for discussion board instructor notifications

This article describes the new APIs that support discussion board instructor notifications. Use them to subscribe instructors and cohort managers to discussion boards and to control which activity appears in their digest emails.

### API sequence {#api-sequence}

The APIs fall into two groups. The `boardSubscriptionSettings` API works at the account level. The subscribers API works at the board level. Use the APIs in this sequence:

|Step|API|Purpose|Scope|
|---|---|---|---|
|1|[`POST /boardSubscriptionSettings`](#api-create-settings)|Set the account-level settings.|`admin:write`|
|2|[`PATCH /boardSubscriptionSettings`](#api-update-settings)|Update the account-level settings.|`admin:write`|
|3|[`GET /boardSubscriptionSettings`](#api-get-settings)|Retrieve the account-level settings.|`admin:read`|
|4|[`GET /boards/{id}/subscribers`](#api-get-subscribers)|Get the list of users subscribed to a board.|`admin:read`|
|5|[`POST /boards/{id}/subscribers`](#api-subscribe-users)|Subscribe users to a board.|`admin:write`|
|6|[`DELETE /boards/{id}/subscribers/{userId}`](#api-unsubscribe-user)|Unsubscribe a user from a board.|`admin:write`|

### Authentication and permissions

Anyone who authenticates with OAuth and has the `admin:read` and `admin:write` scopes can call these APIs. The APIs use the following OAuth scopes:

* `admin:read`: List subscribers and read notification settings (`GET` requests).
* `admin:write`: Create or change notification settings, and add or remove subscribers (`POST`, `PATCH`, and `DELETE` requests).

>[!NOTE]
>
>Board access is checked again when a notification is sent. If a subscriber loses access to a board, delivery is skipped for that board, but the subscription is kept. Delivery resumes if access returns.

### Limits and considerations

* The number of subscribers that can be added is capped.
* The digest is sent as a single email with no pagination, and the email body has a size limit. For boards with heavy activity, choose a digest frequency that keeps each email manageable, such as every 6 hours.
* Digest links open the post, comment, or reply only for users who are logged in.

## API to create account-level settings {#api-create-settings}

### Purpose of the API {#purpose-create-settings}

Use this API to set the account-level settings for board subscription notifications for the first time. The settings control how notification digests are generated across the account:

* Which discussion board events generate notifications.
* How often digest emails are sent.
* Whether posts, comments, replies, and votes are included.

To change the settings afterward, use [`PATCH /boardSubscriptionSettings`](#api-update-settings).

### Endpoint {#endpoint-create-settings}

```http
POST /primeapi/v2/boardSubscriptionSettings
```

|Property|Value|
|---|---|
|Scope|`admin:write`|
|Request format|`application/vnd.api+json;charset=UTF-8`|
|Response format|`application/vnd.api+json;charset=UTF-8`|

### Request body {#request-body-create-settings}

Send the settings as attributes of a `boardSubscriptionSettings` resource.

|Field|Type|Description|
|---|---|---|
|`notifyNewPost`|boolean|Whether subscribers are notified when a new post is added to a board.|
|`notifyComment`|boolean|Whether subscribers are notified when a comment is added to a post.|
|`notifyReply`|boolean|Whether subscribers are notified when a reply is added to a comment.|
|`digestFrequencyHours`|integer|How often, in hours, the digest email is sent. Valid values range from 1 to 168 (one week). For example, 24 sends a daily digest and 168 sends a weekly digest.|

### Example request {#example-request-create-settings}

```bash
curl -X POST \
--header 'Content-Type: application/vnd.api+json;charset=UTF-8' \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
-d '{
  "data": {
    "type": "boardSubscriptionSettings",
    "attributes": {
      "notifyNewPost": true,
      "notifyComment": true,
      "notifyReply": true,
      "digestFrequencyHours": 24
    }
  }
}' \
'https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings'
```

### Example response - 201 Created {#example-response-create-settings}

```json
{
  "links": {
    "self": "https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings"
  },
  "data": {
    "id": "1010",
    "type": "boardSubscriptionSettings",
    "attributes": {
      "digestFrequencyHours": 24,
      "notifyComment": true,
      "notifyNewPost": true,
      "notifyReply": true
    }
  }
}
```

### Response codes {#response-codes-create-settings}

|Status|Meaning|
|---|---|
|201|The request succeeded. The account-level settings were created.|
|400|A generic bad request error.|
|401|The request is missing valid credentials, or access was denied due to invalid credentials.|

## API to update account-level settings {#api-update-settings}

### Purpose of the API {#purpose-update-settings}

Use this API to update the account-level settings that you created with [`POST /boardSubscriptionSettings`](#api-create-settings). For example, change the digest frequency or turn an event type on or off.

### Endpoint {#endpoint-update-settings}

```http
PATCH /primeapi/v2/boardSubscriptionSettings
```

|Property|Value|
|---|---|
|Scope|`admin:write`|
|Request format|`application/vnd.api+json;charset=UTF-8`|
|Response format|`application/vnd.api+json;charset=UTF-8`|

### Request body {#request-body-update-settings}

Send the attributes that you want to change, in the same format as the create API: `notifyNewPost`, `notifyComment`, `notifyReply`, and `digestFrequencyHours`. Attributes that you don't send keep their current values. For the description of each attribute, see [API to create account-level settings](#api-create-settings).

### Example request {#example-request-update-settings}

```bash
curl -X PATCH \
--header 'Content-Type: application/vnd.api+json;charset=UTF-8' \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
-d '{
  "data": {
    "type": "boardSubscriptionSettings",
    "attributes": {
      "notifyReply": true,
      "digestFrequencyHours": 12
    }
  }
}' \
'https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings'
```

### Example response - 200 OK {#example-response-update-settings}

```json
{
  "links": {
    "self": "https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings"
  },
  "data": {
    "id": "1010",
    "type": "boardSubscriptionSettings",
    "attributes": {
      "digestFrequencyHours": 12,
      "notifyComment": true,
      "notifyNewPost": true,
      "notifyReply": true
    }
  }
}
```

### Response codes {#response-codes-update-settings}

|Status|Meaning|
|---|---|
|200|The request succeeded. The account-level settings were updated, and the response contains the current settings.|
|400|A generic bad request error.|
|401|The request is missing valid credentials, or access was denied due to invalid credentials.|

## API to retrieve account-level settings {#api-get-settings}

### Purpose of the API {#purpose-get-settings}

When users subscribe to a board, Adobe Learning Manager can notify them about activity in that board through digest emails. Account-level settings determine which types of activity trigger a notification and how frequently the digest is sent.

This API lets you retrieve those settings. Use it to display the current notification configuration in your application, or to verify the settings before you build features that depend on them.

### Endpoint {#endpoint-get-settings}

```http
GET /primeapi/v2/boardSubscriptionSettings
```

|Property|Value|
|---|---|
|Scope|`admin:read`|
|Response format|`application/vnd.api+json;charset=UTF-8`|

### Example request {#example-request-get-settings}

```bash
curl -X GET \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
'https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings'
```

### Example response - 200 OK {#example-response-get-settings}

```json
{
  "links": {
    "self": "https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings"
  },
  "data": {
    "id": "1010",
    "type": "boardSubscriptionSettings",
    "attributes": {
      "digestFrequencyHours": 24,
      "notifyComment": true,
      "notifyNewPost": true,
      "notifyReply": true
    }
  }
}
```

### Resource schema {#resource-schema-get-settings}

**`boardSubscriptionSettings` attributes**

|Field|Type|Description|
|---|---|---|
|`notifyNewPost`|boolean|Whether subscribers are notified when a new post is added to a board.|
|`notifyComment`|boolean|Whether subscribers are notified when a comment is added to a post.|
|`notifyReply`|boolean|Whether subscribers are notified when a reply is added to a comment.|
|`digestFrequencyHours`|integer|How often, in hours, the digest email is sent. Valid values range from 1 to 168 (one week). Use this value to tell users how often to expect the digest email. For example, show "Daily" when the value is 24 and "Weekly" when the value is 168.|

### Response codes {#response-codes-get-settings}

|Status|Meaning|
|---|---|
|200|The request succeeded. The response contains the account-level board subscription settings.|
|400|A generic bad request error.|
|401|The request is missing valid credentials, or access was denied due to invalid credentials.|

### Use this API in your integration {#integration-get-settings}

A common use case is a notification preferences screen that shows how board subscription emails are configured for the account.

1. When your application's notification preferences screen loads, call `GET /boardSubscriptionSettings`.
1. Show which types of activity trigger a notification and how often the digest email is sent, using the values in the response.

## API to retrieve board subscribers {#api-get-subscribers}

### Purpose of the API {#purpose-get-subscribers}

Retrieve the list of users who are subscribed to a specific board. Users who are subscribed to a board are notified about new activity in it. This API returns the users who are currently subscribed to a given board, along with details about when and by whom each subscription was created.

Use this API to display a subscriber list in your application, to audit who receives updates for a board, or to sync board subscription data with an external system.

The response is paginated. Use the `page[offset]` and `page[limit]` query parameters to move through large subscriber lists. The data returned is subject to the permissions of the calling user on the requested board.

### Endpoint {#endpoint-get-subscribers}

```http
GET /primeapi/v2/boards/{id}/subscribers
```

|Property|Value|
|---|---|
|Scope|`admin:read`|
|Response format|`application/vnd.api+json;charset=UTF-8`|

### Parameters {#parameters-get-subscribers}

|Parameter|In|Required|Default|Description|
|---|---|---|---|---|
|`id`|path|Yes|NA|The ID of the board whose subscribers you want to retrieve. Access is subject to the caller's permissions on the board.|
|`page[offset]`|query|No|0|The starting position of the records to return.|
|`page[limit]`|query|No|10|The number of subscribers to return per page. The maximum allowed value is 200.|

### Example request {#example-request-get-subscribers}

```bash
curl -X GET \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
'https://learningmanager.adobe.com/primeapi/v2/boards/1234/subscribers?page[offset]=0&page[limit]=50'
```

### Example response - 200 OK {#example-response-get-subscribers}

```json
{
  "data": [
    {
      "id": "1234:5678",
      "type": "boardSubscriber",
      "attributes": {
        "boardId": 1234,
        "dateSubscribed": 1757000000000,
        "subscribedByUserId": 5678,
        "user": {
          "id": "5678",
          "name": "Jane Doe",
          "email": "jane.doe@example.com",
          "avatarUrl": "https://example.com/avatars/5678.png",
          "bio": "Learning enthusiast",
          "contentLocale": "en-US",
          "uiLocale": "en-US",
          "timeZoneCode": "PST",
          "userType": "INTERNAL",
          "state": "ACTIVE",
          "profile": "Learner",
          "roles": ["Learner"],
          "gamificationEnabled": true,
          "pointsEarned": 120,
          "pointsRedeemed": 20,
          "enrollOnClick": true,
          "preferredResolution": "720p",
          "lastLoginDate": "2026-09-23T18:12:04.000Z"
        }
      }
    }
  ]
}
```

### Resource schema {#resource-schema-get-subscribers}

The response includes a new resource, `boardSubscriber`. Its attributes include `boardId`, `dateSubscribed`, `subscribedByUserId`, and `user`. The embedded user object has subscriber information such as the user ID, name, email, profile, and roles, and other user metadata.

**`boardSubscriber` attributes**

|Field|Type|Description|
|---|---|---|
|`id`|string|Opaque subscription ID.|
|`type`|string|The resource type.|
|`boardId`|number|ID of the board the user is subscribed to.|
|`dateSubscribed`|number|Timestamp of when the user subscribed to the board.|
|`subscribedByUserId`|number|ID of the user who created the subscription.|
|`user`|object|Details of the subscribed user (embedded, see below).|

**`user` (embedded, inside a subscriber)**

|Field|Type|Description|
|---|---|---|
|`id`|string|Opaque user ID.|
|`name`|string|Display name of the user.|
|`email`|string|Email address of the user.|
|`avatarUrl`|string|URL of the user's profile picture.|
|`bio`|string|Short biography of the user.|
|`binUserId`|string|Internal identifier of the user.|
|`userUniqueId`|string|Unique identifier of the user in the account.|
|`userType`|string|Type of user, for example, internal or external.|
|`state`|string|Current state of the user account.|
|`profile`|string|Profile assigned to the user.|
|`roles`|array of strings|Roles held by the user.|
|`contentLocale`|string|Locale in which the user prefers to view content.|
|`uiLocale`|string|Locale used for the user interface.|
|`timeZoneCode`|string|Time zone configured for the user.|
|`preferredResolution`|string|Preferred video resolution of the user.|
|`enrollOnClick`|boolean|Whether the user is enrolled automatically on selecting a learning object.|
|`gamificationEnabled`|boolean|Whether gamification is enabled for the user.|
|`pointsEarned`|number|Total gamification points earned by the user.|
|`pointsRedeemed`|number|Total gamification points redeemed by the user.|
|`lastLoginDate`|string|Date and time of the user's most recent login.|
|`fields`|object|Custom user fields and their values.|
|`metadata`|object|Additional metadata associated with the user.|

### Response codes {#response-codes-get-subscribers}

|Status|Meaning|
|---|---|
|200|The request succeeded. The response contains the subscribers of the board.|
|400|A generic bad request error. For example, the board ID or a pagination value is malformed.|
|401|The request is missing valid credentials, or access was denied due to invalid credentials.|

### Use this API in your integration {#integration-get-subscribers}

A common use case is an admin or moderator view that shows everyone who receives updates for a board.

1. When the view loads, call this endpoint with the board ID and a `page[limit]` value suited to your layout (up to 200).
1. Display the `user.name`, `user.email`, and `dateSubscribed` values for each subscriber.
1. If the number of records returned equals `page[limit]`, there might be more subscribers. Call the endpoint again, increasing `page[offset]` by the page size, until a page returns fewer records than requested.

## API to subscribe users to a board {#api-subscribe-users}

### Purpose of the API {#purpose-subscribe-users}

Subscribe one or more users to a discussion board so that they receive digest emails for it. Identify users by user ID, by email address (resolved to user IDs within the account), or both. You can add multiple users in a single request. See [Bulk subscriptions](#bulk-subscriptions).

### Endpoint {#endpoint-subscribe-users}

```http
POST /primeapi/v2/boards/{id}/subscribers
```

|Property|Value|
|---|---|
|Scope|`admin:write`|
|Request format|`application/vnd.api+json;charset=UTF-8`|
|Response format|`application/vnd.api+json;charset=UTF-8`|

### Parameters {#parameters-subscribe-users}

|Parameter|In|Required|Description|
|---|---|---|---|
|`id`|path|Yes|The ID of the board to subscribe users to.|

### Request body {#request-body-subscribe-users}

Send the users as attributes of a `boardSubscriberBulkRequest` resource. At least one of `userIds` or `emails` is required.

|Field|Type|Description|
|---|---|---|
|`data.attributes.userIds`|array of numbers|The IDs of the users to subscribe.|
|`data.attributes.emails`|array of strings|The email addresses of the users to subscribe. Each address is resolved to a user ID within the account.|

### Example request {#example-request-subscribe-users}

```bash
curl -X POST \
--header 'Content-Type: application/vnd.api+json;charset=UTF-8' \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
-d '{
  "data": {
    "type": "boardSubscriberBulkRequest",
    "attributes": {
      "userIds": [
        1234,
        5678
      ],
      "emails": [
        "abc@xyz.com"
      ]
    }
  }
}' \
'https://learningmanager.adobe.com/primeapi/v2/boards/1010/subscribers'
```

### Example response - 207 Multi-Status {#example-response-subscribe-users}

```json
{
  "added": [
    {
      "userId": "12345",
      "status": "SUCCESS"
    }
  ],
  "failed": [
    {
      "userId": "78910",
      "errorCode": "NO_BOARD_ACCESS"
    }
  ]
}
```

**Response attributes**

|Field|Type|Description|
|---|---|---|
|`added`|array|The users who were subscribed. Each entry has a `userId` and a `status`. Users who were already subscribed are also reported here as successes.|
|`failed`|array|The users who couldn't be subscribed. Each entry has a `userId` and an `errorCode`, for example `NO_BOARD_ACCESS`.|

### Response codes {#response-codes-subscribe-users}

|Status|Meaning|
|---|---|
|207|Multi-Status. The request was processed and the response lists the result for each user in `added` and `failed`.|
|400|A generic bad request error.|
|401|The request is missing valid credentials, or access was denied due to invalid credentials.|
|404|The requested resource, such as the board, wasn't found.|
|409|The board is inactive, deleted, or retired, so the whole request is rejected.|

### Bulk subscriptions {#bulk-subscriptions}

Use bulk subscription to add multiple users to a discussion board in a single request. Bulk subscription helps reduce the number of API calls that you need to manage subscribers. It is useful when:

* An instructor manages multiple cohorts.
* A cohort manager needs access to many discussion boards.
* An external system synchronizes board subscriptions in batch.
* Multiple instructors need to be subscribed during cohort creation.

#### Bulk add behavior

A bulk request can contain user IDs, email addresses, or a mix of both. Each user is processed independently.

#### Idempotent behavior

Bulk add is idempotent. If a user is already subscribed to the board, the request succeeds, no duplicate subscription is created, and the existing subscription remains unchanged. This lets clients retry requests safely.

#### Partial success

Some users can be subscribed while others fail validation. The operation doesn't fail because one or more users are invalid.

|Case|Result|
|---|---|
|The user exists and has access to the board|Success|
|The user is already subscribed|Success|
|The user doesn't have access to the board|Failure (`NO_BOARD_ACCESS`)|
|The user doesn't exist|Failure|
|The user is inactive|Failure|
|The user was deleted|Failure|

#### Response format

Bulk subscription returns HTTP 207 Multi-Status with an `added` result and a `failed` result for each user, as in the [example response](#example-response-subscribe-users).

#### Common validation failures

* **The user has no access to the board.** If a user doesn't have visibility to the board, `NO_BOARD_ACCESS` is returned for that user. The remaining users continue to be processed normally.
* **The board is inactive, deleted, or retired.** If the board isn't eligible for subscriptions, the request is rejected with HTTP 409 Conflict.
* **The user is invalid.** If a user account doesn't exist, is inactive, or was deleted, the operation returns a failure entry for that user.

## API to unsubscribe a user from a board {#api-unsubscribe-user}

### Purpose of the API {#purpose-unsubscribe-user}

Unsubscribe a user from a discussion board. After the subscription is removed, the user no longer receives notifications and digest emails for that board.

### Endpoint {#endpoint-unsubscribe-user}

```http
DELETE /primeapi/v2/boards/{id}/subscribers/{userId}
```

|Property|Value|
|---|---|
|Scope|`admin:write`|
|Response format|`application/vnd.api+json;charset=UTF-8`|

### Parameters {#parameters-unsubscribe-user}

|Parameter|In|Required|Description|
|---|---|---|---|
|`id`|path|Yes|The ID of the board.|
|`userId`|path|Yes|The ID of the user to unsubscribe.|

### Example request {#example-request-unsubscribe-user}

```bash
curl -X DELETE \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
'https://learningmanager.adobe.com/primeapi/v2/boards/1234/subscribers/5678'
```

### Example response - 204 No Content {#example-response-unsubscribe-user}

The response has no body.

### Response codes {#response-codes-unsubscribe-user}

|Status|Meaning|
|---|---|
|204|The request succeeded. The user was unsubscribed from the board.|
|400|A generic bad request error.|
|401|The request is missing valid credentials, or access was denied due to invalid credentials.|
|404|The requested resource, such as the board or the subscription, wasn't found.|

## Bookmark API ordering and retired content handling

### Purpose of the API

Learners bookmark trainings they want to revisit. Before this change, the bookmark APIs returned bookmarks in no particular order. Integrations, especially headless implementations, couldn't show the most recently saved bookmarks first. Learners with many bookmarks had to scroll through older items to find recent ones.

Bookmarks to retired learning objects also stayed in the list. Selecting one led to a "Page not found" error.

This change improves the bookmark APIs in two ways:

* Bookmarks are returned in chronological order, newest first.
* Bookmarks to retired learning objects are no longer returned.

No new endpoints, parameters, or response attributes are introduced. Existing integrations continue to work without changes.

### Base URL and conventions

The bookmark APIs use the following base path and conventions:

|Item|Value|
|---|---|
|Base path|`/primeapi/v2`|
|Content type|`application/vnd.api+json`|
|Authentication|OAuth token with learner read access|
|Default order|Newest bookmark first|
|New parameters|None|
|Response structure|Unchanged|

### Endpoints

#### Endpoints that return bookmarks

The following endpoints return bookmarks in the new order:

|Endpoint|Returns|
|---|---|
|`GET /primeapi/v2/learningObjects?filter.bookmarks=true`|Learning objects the learner has bookmarked|
|`GET /primeapi/v2/bookmarks`|The learner's bookmarks|

#### Get bookmarked learning objects in order

`GET /primeapi/v2/learningObjects?filter.bookmarks=true`

<!-- Content Review by Claude: Please confirm the endpoint list. The dev-to-QE hand-off confirms ordering for GET /learningObjects?filter.bookmarks=true. The PRD (ALMER-442) also lists GET /primeapi/v2/bookmarks. Please also confirm the OAuth scope. -->

Returns the learning objects the calling learner has bookmarked. The most recently bookmarked item is first, and the oldest is last.

**Scope:** Learner read access

The endpoint accepts the following query parameter:

|Parameter|In|Required|Description|
|---|---|---|---|
|`filter.bookmarks`|query|Yes|Set to `true` to return only the learning objects the learner has bookmarked|

**Sample request**

```http
GET /primeapi/v2/learningObjects?filter.bookmarks=true
Accept: application/vnd.api+json
Authorization: oauth <access-token>
```

**Sample 200 OK response**

The learner bookmarked Getting Started with Adobe Analytics first, Building Workspace Projects second, and Advanced Segmentation in Adobe Analytics last. The response lists them from newest to oldest. Other attributes are omitted for brevity.

```json
{
  "data": [
    {
      "id": "course:2400162",
      "type": "learningObject",
      "attributes": {
        "name": "Advanced Segmentation in Adobe Analytics"
      }
    },
    {
      "id": "course:2400160",
      "type": "learningObject",
      "attributes": {
        "name": "Building Workspace Projects"
      }
    },
    {
      "id": "course:2400159",
      "type": "learningObject",
      "attributes": {
        "name": "Getting Started with Adobe Analytics"
      }
    }
  ]
}
```

>[!NOTE]
>
>The new order is the default behavior and applies to all accounts.

### Bookmark ordering

#### How bookmarks are ordered

Bookmarks are sorted by the date the learner saved them, from newest to oldest. For example, if a learner bookmarks course A, then course B, and then course C, the response lists course C first, course B second, and course A last.

If a bookmarked LO appearing at 10th position for instance is "unsaved" and later bookmarked again, then it will appear as recent bookmarked and at first in the list.

Integrations that previously sorted bookmarks on the client can remove that logic and display the results in the order returned.

### Retired content handling

#### How retired learning objects are handled

Bookmarks to retired learning objects aren't returned in the response, regardless of whether the learner is enrolled in the learning object.

Retired learning objects that are bookmarked will not show up unless the learner is enrolled to it. 

Learners no longer see bookmarks that lead to a "Page not found" error. The bookmark is hidden from the results, not deleted.

### Compatibility

This change doesn't break existing API consumers:

* The endpoints and their parameters are unchanged.
* The response structure is unchanged, and no attributes are added or removed.
* Only the order of results and the exclusion of retired learning objects differ from earlier behavior.

### Use this API in your integration

A common use case is a "Saved for later" list in a headless learner experience. You want learners to see their most recent bookmarks first, without links to retired content.

1. Call `GET /primeapi/v2/learningObjects?filter.bookmarks=true` when the learner opens the list.
2. Display the learning objects in the order returned. The first item is the most recently bookmarked.
3. Remove any client-side sorting or retired-content filtering you added as a workaround.
4. Show a count of bookmarks using the number of items in the response. Bookmarks to retired learning objects are no longer included.

## API support for multi-enrolled instances in the Learner app {#multi-enrolled-compliance-widget}

The public API supports this behavior through an optional query parameter on the existing enrollments endpoint. If you omit the parameter, the API returns the same results as before, so existing integrations, including headless implementations, continue to work unchanged.

**Endpoint**

```http
GET /primeapi/v2/enrollments
```

**Query parameter**

`includeMultiInstanceEnrollments` (optional)

**Query**

```http
https://learningmanagerstage1.adobe.com/primeapi/v2/enrollments?page[limit]=10&filter.loTypes=course&includeHierarchicalEnrollments=false&includeMultiInstanceEnrollments=true&sort=dateEnrolled
```

**Value**

`true`. The default is `false`.

**Response body**

```json
{
  "links": {
    "self": "https://learningmanagerstage1.adobe.com/primeapi/v2/enrollments?page[limit]=10&filter.loTypes=course&sort=dateEnrolled&includeHierarchicalEnrollments=false&includeMultiInstanceEnrollments=true",
    "next": "https://learningmanagerstage1.adobe.com/primeapi/v2/enrollments?page[limit]=10&filter.loTypes=course&sort=dateEnrolled&includeHierarchicalEnrollments=false&includeMultiInstanceEnrollments=true&page[cursor]=eyJjb3Vyc2VNdWx0aSI6MCwiam9iQWlkIjowLCJjb3Vyc2UiOjEwLCJsZWFybmluZ1Byb2dyYW0iOjAsImNlcnRpZmljYXRpb24iOjB9"
  },
  "data": [
    {
      "id": "course:15067_30122_3400468",
      "type": "learningObjectInstanceEnrollment",
      "attributes": {
        "completionDeadline": "2026-02-24T10:50:45.000Z",
        "enrollmentSource": "MGR_APPROVAL",
        "hasPassed": false,
        "progressPercent": 0,
        "score": 0,
        "state": "PENDING_APPROVAL"
      },
      "relationships": {
        "learner": {
          "data": {
            "id": "3400468",
            "type": "user"
          }
        },
        "learningObject": {
          "data": {
            "id": "course:15067",
            "type": "learningObject"
          }
        },
        "loInstance": {
          "data": {
            "id": "course:15067_30122",
            "type": "learningObjectInstance"
          }
        },
        "loResourceGrades": {
          "data": [
            {
              "id": "course:15067_30122_41715_1_3400468",
              "type": "learningObjectResourceGrade"
            }
          ]
        }
      }
    },
    {
      "id": "course:1108800_1997400_3400468",
      "type": "learningObjectInstanceEnrollment",
      "attributes": {
        "enrollmentSource": "SELF_ENROLL",
        "hasPassed": false,
        "progressPercent": 0,
        "score": 0,
        "state": "PENDING_APPROVAL"
      },
      "relationships": {
        "learner": {
          "data": {
            "id": "3400468",
            "type": "user"
          }
        },
        "learningObject": {
          "data": {
            "id": "course:1108800",
            "type": "learningObject"
          }
        },
        "loInstance": {
          "data": {
            "id": "course:1108800_1997400",
            "type": "learningObjectInstance"
          }
        },
        "loResourceGrades": {
          "data": [
            {
              "id": "course:1108800_1997400_2174574_0_3400468",
              "type": "learningObjectResourceGrade"
            }
          ]
        }
      }
    },
    {
      "id": "course:2027668_3707328_3400468",
      "type": "learningObjectInstanceEnrollment",
      "attributes": {
        "enrollmentSource": "MGR_APPROVAL",
        "hasPassed": false,
        "progressPercent": 0,
        "score": 0,
        "state": "PENDING_APPROVAL"
      },
      "relationships": {
        "learner": {
          "data": {
            "id": "3400468",
            "type": "user"
          }
        },
        "learningObject": {
          "data": {
            "id": "course:2027668",
            "type": "learningObject"
          }
        },
        "loInstance": {
          "data": {
            "id": "course:2027668_3707328",
            "type": "learningObjectInstance"
          }
        },
        "loResourceGrades": {
          "data": [
            {
              "id": "course:2027668_3707328_2665897_0_3400468",
              "type": "learningObjectResourceGrade"
            }
          ]
        }
      }
    },
    {
      "id": "course:2030067_3709862_3400468",
      "type": "learningObjectInstanceEnrollment",
      "attributes": {
        "enrollmentSource": "MGR_APPROVAL",
        "hasPassed": false,
        "progressPercent": 0,
        "score": 0,
        "state": "PENDING_APPROVAL"
      },
      "relationships": {
        "learner": {
          "data": {
            "id": "3400468",
            "type": "user"
          }
        },
        "learningObject": {
          "data": {
            "id": "course:2030067",
            "type": "learningObject"
          }
        },
        "loInstance": {
          "data": {
            "id": "course:2030067_3709862",
            "type": "learningObjectInstance"
          }
        },
        "loResourceGrades": {
          "data": [
            {
              "id": "course:2030067_3709862_2668467_0_3400468",
              "type": "learningObjectResourceGrade"
            }
          ]
        }
      }
    },
    {
      "id": "course:3081896_5749155_3400468",
      "type": "learningObjectInstanceEnrollment",
      "attributes": {
        "enrollmentSource": "MGR_APPROVAL",
        "hasPassed": false,
        "progressPercent": 0,
        "score": 0,
        "state": "PENDING_APPROVAL"
      },
      "relationships": {
        "learner": {
          "data": {
            "id": "3400468",
            "type": "user"
          }
        },
        "learningObject": {
          "data": {
            "id": "course:3081896",
            "type": "learningObject"
          }
        },
        "loInstance": {
          "data": {
            "id": "course:3081896_5749155",
            "type": "learningObjectInstance"
          }
        },
        "loResourceGrades": {
          "data": [
            {
              "id": "course:3081896_5749155_3737554_0_3400468",
              "type": "learningObjectResourceGrade"
            },
            {
              "id": "course:3081896_5749155_3737555_0_3400468",
              "type": "learningObjectResourceGrade"
            }
          ]
        }
      }
    },
    {
      "id": "course:2037893_3717940_3400468",
      "type": "learningObjectInstanceEnrollment",
      "attributes": {
        "enrollmentSource": "MGR_APPROVAL",
        "hasPassed": false,
        "progressPercent": 0,
        "score": 0,
        "state": "PENDING_APPROVAL"
      },
      "relationships": {
        "learner": {
          "data": {
            "id": "3400468",
            "type": "user"
          }
        },
        "learningObject": {
          "data": {
            "id": "course:2037893",
            "type": "learningObject"
          }
        },
        "loInstance": {
          "data": {
            "id": "course:2037893_3717940",
            "type": "learningObjectInstance"
          }
        },
        "loResourceGrades": {
          "data": [
            {
              "id": "course:2037893_3717940_3676856_0_3400468",
              "type": "learningObjectResourceGrade"
            }
          ]
        }
      }
    },
    {
      "id": "course:3049434_5713130_3400468",
      "type": "learningObjectInstanceEnrollment",
      "attributes": {
        "completionDeadline": "2020-05-05T18:29:59.000Z",
        "enrollmentSource": "MGR_APPROVAL",
        "hasPassed": false,
        "progressPercent": 0,
        "score": 0,
        "state": "PENDING_APPROVAL"
      },
      "relationships": {
        "learner": {
          "data": {
            "id": "3400468",
            "type": "user"
          }
        },
        "learningObject": {
          "data": {
            "id": "course:3049434",
            "type": "learningObject"
          }
        },
        "loInstance": {
          "data": {
            "id": "course:3049434_5713130",
            "type": "learningObjectInstance"
          }
        },
        "loResourceGrades": {
          "data": [
            {
              "id": "course:3049434_5713130_3693595_0_3400468",
              "type": "learningObjectResourceGrade"
            }
          ]
        }
      }
    },
    {
      "id": "course:2001397_3679403_3400468",
      "type": "learningObjectInstanceEnrollment",
      "attributes": {
        "enrollmentSource": "MGR_APPROVAL",
        "hasPassed": false,
        "progressPercent": 0,
        "score": 0,
        "state": "PENDING_APPROVAL"
      },
      "relationships": {
        "learner": {
          "data": {
            "id": "3400468",
            "type": "user"
          }
        },
        "learningObject": {
          "data": {
            "id": "course:2001397",
            "type": "learningObject"
          }
        },
        "loInstance": {
          "data": {
            "id": "course:2001397_3679403",
            "type": "learningObjectInstance"
          }
        },
        "loResourceGrades": {
          "data": [
            {
              "id": "course:2001397_3679403_2635974_0_3400468",
              "type": "learningObjectResourceGrade"
            }
          ]
        }
      }
    },
    {
      "id": "course:2037862_3717900_3400468",
      "type": "learningObjectInstanceEnrollment",
      "attributes": {
        "enrollmentSource": "MGR_APPROVAL",
        "hasPassed": false,
        "progressPercent": 0,
        "score": 0,
        "state": "PENDING_APPROVAL"
      },
      "relationships": {
        "learner": {
          "data": {
            "id": "3400468",
            "type": "user"
          }
        },
        "learningObject": {
          "data": {
            "id": "course:2037862",
            "type": "learningObject"
          }
        },
        "loInstance": {
          "data": {
            "id": "course:2037862_3717900",
            "type": "learningObjectInstance"
          }
        },
        "loResourceGrades": {
          "data": [
            {
              "id": "course:2037862_3717900_3676816_0_3400468",
              "type": "learningObjectResourceGrade"
            }
          ]
        }
      }
    },
    {
      "id": "course:2037837_3717863_3400468",
      "type": "learningObjectInstanceEnrollment",
      "attributes": {
        "completionDeadline": "2020-02-29T18:29:59.000Z",
        "enrollmentSource": "SELF_ENROLL",
        "hasPassed": false,
        "progressPercent": 0,
        "score": 0,
        "state": "OTHER"
      },
      "relationships": {
        "learner": {
          "data": {
            "id": "3400468",
            "type": "user"
          }
        },
        "learningObject": {
          "data": {
            "id": "course:2037837",
            "type": "learningObject"
          }
        },
        "loInstance": {
          "data": {
            "id": "course:2037837_3717863",
            "type": "learningObjectInstance"
          }
        },
        "loResourceGrades": {
          "data": [
            {
              "id": "course:2037837_3717863_3597363_0_3400468",
              "type": "learningObjectResourceGrade"
            }
          ]
        }
      }
    }
  ]
}
```

## Last access date for learning path enrollment

Adobe Learning Manager lets you store custom metadata, such as a last access date, on a learning path enrollment. You set and read the metadata through the API. This helps you track time-bound access to learning paths that you assign.

### About Learning Path enrollment metadata

You can already set a last access date on a course enrollment through the API. That date controls how long a learner can access the course. Learning path enrollments now support a generic metadata field, so you can store a last access date or any other value that you want to track.

You do not need to turn on the field or send a special header. The field is empty until you set it.

>[!NOTE]
>
>The metadata is for your own tracking. Adobe Learning Manager does not update it when learners open a learning path or its courses, and it does not control access to the learning path. It is also not propagated to the courses in the path. Each course keeps its own last access date, so courses in the same path can have different dates. Continue to manage course-level access expiration separately.

### Metadata rules

* The value must be a JSON object. A string, number, Boolean, or array returns a `400` error with the message `metadata must be a JSON object`.
* You can use any keys. Adobe Learning Manager does not validate keys or values, and it does not enforce a date format. The examples in this article use epoch milliseconds, the same format as course dates.
* A `PATCH` request replaces the entire metadata object. It does not merge with existing values, so keys that you leave out are removed.
* Setting `"metadata": null` clears all metadata and returns `200`.
* A request with an empty `attributes` object, or without a `metadata` key, leaves the stored metadata unchanged.
* When no metadata is set, or after you clear it, the `metadata` key is not in the response.

### Set metadata on an existing enrollment

Use an admin token.

Send a `PATCH` request to the following endpoint, where `{enrollmentId}` is the learning path enrollment ID in the format `learningProgram:<lpId><instanceId><userId>`:

```http
PATCH /primeapi/v2/users/{userId}/enrollments/{enrollmentId}
```

Use this request body:

```json
{
  "data": {
    "id": "<enrollmentId>",
    "type": "learningObjectInstanceEnrollment",
    "attributes": {
      "metadata": {
        "lastAccessDate": 1745337600000
      }
    }
  }
}
```

### Set metadata when you enroll a learner

Use an admin token.

Send a `POST` request with the learning path and instance IDs. Include an optional `metadata` object in the request body.

```http
POST /primeapi/v2/users/{userId}/enrollments?loId=<lpId>&loInstanceId=<instanceId>
```

* If `metadata` is not a JSON object, the request returns `400` and the user is not enrolled.
* If the user is already enrolled, the request returns `200` and changes nothing. To change metadata for an existing enrollment, use the `PATCH` request.
* The response does not include the metadata. Send a `GET` request to read it.

### Retrieve metadata

You can retrieve metadata with an admin or a learner token. The requests differ by token type.

| Token | Get one enrollment | List learning path enrollments |
|---|---|---|
| Admin | `GET /primeapi/v2/users/{userId}/enrollments/{enrollmentId}` | `GET /primeapi/v2/users/{userId}/enrollments?filter.loTypes=learningProgram` |
| Learner | `GET /primeapi/v2/enrollments/{enrollmentId}`<br>`GET /primeapi/v2/learningObjects/{id}?include=enrollment` | `GET /primeapi/v2/enrollments?filter.loTypes=learningProgram` |

>[!NOTE]
>
>The `include=enrollment` parameter works only with a learner token. It is not supported for the admin role.

The response returns the `metadata` object with the learning path enrollment.

### Use metadata in headless and external portals

External portals and integrations use the same API calls. Use the request that matches the token your portal uses.

* **Show the value in your portal:** Send the `GET` request for your token type from the table above, and read the `metadata` object from the response.
* **Update the value from an external system, such as a commerce platform:** Send the `PATCH` request with an admin token.

## Job API: Export Report Builder reports with generateCustomReport (L2 quiz report: bulk export and json format)

Adobe Learning Manager December 2026 release adds a new job type, `generateCustomReport`, to the Job API. Use it to export any report you created in Report Builder, in an automated way, by passing the report ID.

Combined with the new L2 quiz dataset in Report Builder, you can now:

* Export question-level (L2) quiz data across multiple courses and modules in a single report, instead of running `generateQuizReport` once for each course.
* Automate recurring exports, for example, a daily incremental export to your data warehouse or BI tool.

Existing job types, including `generateQuizReport`, are unchanged.

### Before you begin

* You must be an Admin. The `generateCustomReport` job type isn't available to other roles.
* Create and save the report in Report Builder first. For L2 quiz data, build the report from the L2 quiz dataset, and include the question-level fields you need, such as question text, learner response, score, attempt number, and answered-on date.
* Note the report's ID. You pass it in the request as `reportId`.

### Create a job

**Endpoint**

```http
POST /primeapi/v2/jobs
```

**Request body**

```json
{
  "data": {
    "type": "job",
    "attributes": {
      "description": "Daily L2 quiz export",
      "jobType": "generateCustomReport",
      "payload": {
        "reportId": "1478"
      }
    }
  }
}
```

**Attributes**

| Attribute      | Required | Description                                                                    |
|--------------------|--------------|------------------------------------------------------------------------------------|
| `jobType`          | Yes          | Must be `generateCustomReport`.                                                    |
| `payload.reportId` | Yes          | The ID of the saved Report Builder report, as a string. Must be a positive number. |
| `description`      | No           | A description of your choice for the job.                                          |
| `callbackUrl`      | No           | A URL to call when the job completes. Works the same way as for other job types.   |

### Report requirements

The job fails with an error message if the report doesn't meet these conditions:

* The report definition includes a duration filter.
* The relative duration filter that's configured in the report doesn't span more than 7 days.

>[!NOTE]
>
>The job runs asynchronously. A report that doesn't meet the conditions is rejected when the job is processed, so check the job status for the error.

## Check the job status and download the report

**Endpoint**

```http
GET /primeapi/v2/jobs/{jobId}
```

The response uses the same structure as other job types. When the job completes, `status.code` is `completed`, and `status.data.s3Url` contains the download link.

```json
{
  "data": {
    "type": "job",
    "id": "12345",
    "attributes": {
      "jobType": "generateCustomReport",
      "payload": {
        "reportId": "1478"
      },
      "status": {
        "code": "completed",
        "data": {
          "s3Url": "<time-limited-download-url>"
        }
      }
    }
  }
}
```

>[!NOTE]
>
>The download URL is time-limited. Download the file as soon as the job completes.

### Limits

All existing Job API limits and restrictions apply to `generateCustomReport`. This includes the limit on the number of calls allowed per day. For admin reports, the default limit is 5 calls per day.

### L2 quiz report output {#l2-quiz-report-output}

When you build the report from the L2 quiz dataset in Report Builder:

* The output is a single CSV file. The module is a column in the file, and selecting a course returns only its quiz modules.
* Each row represents one learner's answer to one question in one attempt. It includes the question ID and text, the learner's response, the score achieved, the maximum score, whether the response was correct, the attempt number, the answered-on date, and the module version.
* Learner details, custom and metadata attributes, manager, and course and module names are available through the related user and learning object datasets.
* Data refreshes at the standard Report Builder interval (approximately every 15 minutes).
