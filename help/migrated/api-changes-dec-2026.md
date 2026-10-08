---
description: Learn about the new admin APIs for managing discussion board subscribers and account level notification settings for instructor digest emails
jcr-language: en_us
title: API changes in Nov 2026
exl-id: 7eeb97de-4d6e-44c4-823d-e8204c318b09
---

## APIs for discussion board instructor notifications 

This article describes the new admin APIs that support discussion board instructor notifications. Admins use these APIs to subscribe instructors and cohort managers to discussion boards and to control which activity appears in their digest emails.

### Two new APIs

The new APIs fall into two groups.

| API group | Level | Purpose |
|---|---|---|
| Subscription settings | Account | Set the digest frequency in hours and turn posts, comments, replies, and votes on or off for notifications. |
| Subscribers | Board | Add, list, and remove the users who are subscribed to a discussion board. |

#### Subscription settings API

Use the subscription settings API to configure notifications for the whole account.

* Set the digest frequency in hours. For example, a frequency of 1 hour sends a digest email every hour.
* Turn new posts, comments, and replies on or off for the digest.
* Turn upvote and downvote notifications on or off by using the `notifyVote` setting.
* All event settings are false by default.
* Send a GET request to read the current settings for the account.

#### Subscribers API

Use the subscribers API to manage who receives notifications for each board.

* Retrieve the subscribers of a board by passing the board ID.
* Add subscribers by email address or by user ID.
* Add multiple users in one request. Bulk add is idempotent, so adding a duplicate is treated as success.
* A board subscription is separate from the existing board follow relationship.

#### Authentication and permissions

Only ALM admins can call these APIs. The APIs use the following OAuth scopes:

* `admin:read`: List subscribers and read notification settings.
* `admin:write`: Add or remove subscribers and change notification settings.

#### Bulk add responses

A bulk add request returns HTTP 207 Multi-Status with an `added` result and a `failed` result for each user.

* A request for an inactive, deleted, or retired board is rejected with HTTP 409.
* A user without access to the board is reported with `NO_BOARD_ACCESS`. This does not block the other users in the same request.

>[!NOTE]
>
>Board visibility is checked again when a notification is sent. If a subscriber loses access to a board, delivery is skipped for that board, but the subscription is kept. Delivery resumes if access returns.

#### Limits and considerations

* The digest is intended for instructors and cohort managers who are admins. It is not sent to learners.
* The number of subscribers that can be added is capped.
* The digest is sent as a single email with no pagination, and the email body has a size limit. For boards with heavy activity, choose a digest frequency that keeps each email manageable, such as every 6 hours.
* Digest links open the post, comment, or reply only for users who are logged in.

### API for retrieving board subscribers

Retrieve the list of users who are subscribed to a specific board.

#### Purpose of the API

Admins can subscribe to a board to stay informed about new activity in it. This API lets you retrieve the users who are currently subscribed to a given board, along with details about when and by whom each subscription was created.

Use this API to display a subscriber list in your application, to audit who receives updates for a board, or to sync board subscription data with an external system.

The response is paginated. Use the `page[offset]` and `page[limit]` query parameters to move through large subscriber lists. The data returned is subject to the permissions of the calling user on the requested board.

#### Endpoint

```
GET /primeapi/v2/boards/{id}/subscribers
```

| Property | Value |
|---|---|
| Scope | Learner read access |
| Response format | `application/vnd.api+json;charset=UTF-8` |

#### Parameters

| Parameter | In | Required | Default | Description |
|---|---|---|---|---|
| `id` | path | Yes | NA | The ID of the board whose subscribers you want to retrieve. Access is subject to the caller's permissions on the board. |
| `page[offset]` | query | No | `0` | The starting position of the records to return. |
| `page[limit]` | query | No | `10` | The number of subscribers to return per page. The maximum allowed value is `200`. |

>[!NOTE]
>
>The `id` value is an opaque string. Always pass back the exact value you received from a prior response. Never construct or parse it.

#### Example request

```http
GET /primeapi/v2/boards/1234/subscribers?page[offset]=0&page[limit]=50
Accept: application/vnd.api+json
Authorization: oauth <access-token>
```

#### Example response - 200 OK

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

#### Resource schema

##### boardSubscriber attributes

| Field | Type | Description |
|---|---|---|
| `id` | string | Opaque subscription ID. |
| `type` | string | The resource type. |
| `boardId` | number | ID of the board the user is subscribed to. |
| `dateSubscribed` | number | Timestamp of when the user subscribed to the board. |
| `subscribedByUserId` | number | ID of the user who created the subscription. |
| `user` | object | Details of the subscribed user (embedded, see below). |

##### user (embedded, inside a subscriber)

| Field | Type | Description |
|---|---|---|
| `id` | string | Opaque user ID. |
| `name` | string | Display name of the user. |
| `email` | string | Email address of the user. |
| `avatarUrl` | string | URL of the user's profile picture. |
| `bio` | string | Short biography of the user. |
| `binUserId` | string | Internal identifier of the user. |
| `userUniqueId` | string | Unique identifier of the user in the account. |
| `userType` | string | Type of user, for example, internal or external. |
| `state` | string | Current state of the user account. |
| `profile` | string | Profile assigned to the user. |
| `roles` | array of strings | Roles held by the user. |
| `contentLocale` | string | Locale in which the user prefers to view content. |
| `uiLocale` | string | Locale used for the user interface. |
| `timeZoneCode` | string | Time zone configured for the user. |
| `preferredResolution` | string | Preferred video resolution of the user. |
| `enrollOnClick` | boolean | Whether the user is enrolled automatically on selecting a learning object. |
| `gamificationEnabled` | boolean | Whether gamification is enabled for the user. |
| `pointsEarned` | number | Total gamification points earned by the user. |
| `pointsRedeemed` | number | Total gamification points redeemed by the user. |
| `lastLoginDate` | string | Date and time of the user's most recent login. |
| `fields` | object | Custom user fields and their values. |
| `metadata` | object | Additional metadata associated with the user. |

#### Response codes

| Status | Meaning |
|---|---|
| 200 | The request succeeded. The response contains the subscribers of the board. |
| 400 | A generic bad request error. For example, the board ID or a pagination value is malformed. |
| 401 | The request is missing valid credentials, or access was denied due to invalid credentials. |

##### Example error response

```json
{
  "meta": {
    "error": "BAD_REQUEST",
    "detail": "Bad request. Check url, params and headers"
  }
}
```

#### Use this API in your integration

A common use case is an admin or moderator view that shows everyone who receives updates for a board.

1. When the view loads, call this endpoint with the board ID and a `page[limit]` value suited to your layout (up to `200`).
2. Display the `user.name`, `user.email`, and `dateSubscribed` values for each subscriber.
3. If the number of records returned equals `page[limit]`, there might be more subscribers. Call the endpoint again, increasing `page[offset]` by the page size, until a page returns fewer records than requested.

### API for subscription settings

#### Purpose of the API

When users subscribe to a board, Adobe Learning Manager can notify them about activity in that board through digest emails. Account-level settings determine which types of activity trigger a notification and how frequently the digest is sent.

This API lets you retrieve those settings. Use it to display the current notification configuration in your application, or to verify the settings before you build features that depend on them.

#### Endpoint

```
GET /primeapi/v2/boardSubscriptionSettings
```

| Property | Value |
|---|---|
| Scope | Learner read access |
| Response format | `application/vnd.api+json;charset=UTF-8` |

#### Parameters

This endpoint doesn't accept any path or query parameters.

#### Example request

```http
GET /primeapi/v2/boardSubscriptionSettings
Accept: application/vnd.api+json
Authorization: oauth <access-token>
```

#### Example response - 200 OK

```json
{
  "data": {
    "id": "boardSubscriptionSettings",
    "type": "boardSubscriptionSettings",
    "attributes": {
      "notifyNewPost": true,
      "notifyComment": true,
      "notifyReply": false,
      "digestFrequencyHours": 24
    }
  }
}
```

#### Resource schema

##### boardSubscriptionSettings attributes

| Field | Type | Description |
|---|---|---|
| `notifyNewPost` | boolean | Whether subscribers are notified when a new post is added to a board. |
| `notifyComment` | boolean | Whether subscribers are notified when a comment is added to a post. |
| `notifyReply` | boolean | Whether subscribers are notified when a reply is added to a comment. |
| `digestFrequencyHours` | integer | How often, in hours, the digest email is sent. Valid values range from `1` to `168` (one week). |

#### Response codes

| Status | Meaning |
|---|---|
| 200 | The request succeeded. The response contains the account-level board subscription settings. |
| 400 | A generic bad request error. |
| 401 | The request is missing valid credentials, or access was denied due to invalid credentials. |

##### Example error response

```json
{
  "meta": {
    "error": "UNAUTHORIZED_ACCESS",
    "detail": "Access is denied due to invalid credentials"
  }
}
```

#### Use this API in your integration

A common use case is a notification preferences screen that shows how board subscription emails are configured for the account.

1. When the screen loads, call this endpoint.
2. Use `notifyNewPost`, `notifyComment`, and `notifyReply` to show which types of activity trigger a notification.
3. Use `digestFrequencyHours` to tell users how often to expect the digest email. For example, show "Daily" when the value is `24` and "Weekly" when the value is `168`.
