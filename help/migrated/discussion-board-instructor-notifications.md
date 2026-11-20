---
description: Learn how Instructors and Cohort Managers get email digests of discussion board activity and how to manage settings and subscribers with APIs
jcr-language: en_us
title: Discussion board Instructor notifications
exl-id: 370c9add-5572-4555-8a95-ddb470c230f4
---

# Discussion board Instructor notifications

## Overview

Discussion board Instructor notifications give Instructors, Cohort Managers, and Administrators an email digest of recent activity on the discussion boards they monitor. This is helpful for Instructors who manage several cohorts and take part in multiple boards at the same time.

A Cohort Manager is the person who manages a group of learners (a cohort) who go through a course or program together on the same schedule.

Instead of opening each board individually, Instructors receive real-time in-app alerts and an email digest, at the frequency you configure, for the boards they're subscribed to. You manage board subscriptions and notification settings through the [`boardSubscriptionSettings` API](api-changes-dec-2026.md#api-sequence) and the [subscribers API](api-changes-dec-2026.md#api-get-subscribers).

## Key capabilities

* You can subscribe active Adobe Learning Manager users to selected discussion boards by using the subscribers API ([`POST /boards/{id}/subscribers`](api-changes-dec-2026.md#api-subscribe-users), scope `admin:write`). A user must have access to the board when notifications are sent.
* Users receive real-time in-app notifications for enabled event types and an email digest grouped by board. The event types are controlled by account-level settings (`notifyNewPost`, `notifyComment`, and `notifyReply`) in the [`boardSubscriptionSettings` API](api-changes-dec-2026.md#api-sequence).
* The digest window is the period of time whose activity is collected into one digest email. You set it at the account level with the `digestFrequencyHours` attribute, from 1 to 168 hours (for example, 24 hours for a daily digest). It applies to all users in the account.
* You can subscribe users by user ID or email address, and you can add several users in one request ([bulk subscriptions](api-changes-dec-2026.md#bulk-subscriptions)). Users are created in Learning Manager in the usual way first.
* The digest email lists each new post, comment, and reply for the enabled event types, with the board name, the author's name and email address, and a direct link. It also shows a count of the updates since the start of the digest period.
* The `boardSubscriptionSettings` API and the subscribers API are public APIs, so you can manage settings and subscriptions without a user interface (API-driven integrations).

## Use cases

The following use cases show how Instructor notifications help:

|Use case|How the notification helps|
|---|---|
|Monitor multiple cohorts|An Instructor responsible for several cohorts can receive summarized activity from the boards associated with those cohorts.|
|Review learner engagement|A Cohort Manager can monitor new contributions and identify active discussions without checking every board separately.|
|Track follow-up conversations|Comments and replies included in the digest help Instructors identify discussions that may require guidance or moderation.|

## Important considerations

* A user must be able to access a board when a notification is sent. Access is checked again at delivery time, not only when the user is subscribed. If a subscriber loses access to a board, the subscription is kept but notifications for that board are skipped.
* The digest is sent as one email, so a busy board can make it very long. For example, a cohort of about 40 learners could post several hundred comments in six hours.
* If your boards are very active, use a shorter digest frequency, such as every six hours, so each email stays manageable. Set the frequency with `digestFrequencyHours` in the [`boardSubscriptionSettings` API](api-changes-dec-2026.md#api-create-settings).
* The number of posts in the email digest is limited to 20 per board per digest. The same cap applies independently to comments (20) and replies (20) per board. Only the displayed lists are truncated; the headline/subheading counts always reflect the true, untruncated activity for the window.
* The number of subscribers is capped at at 200 per board.
* Because the content is sent directly in the email rather than as an attachment, the email body also has a size limit.

## Subscription model, permissions, and eligibility

* A subscriber is a user who receives notifications from a board. A board subscription is independent of the existing follow relationship with the board user.
* Anyone who authenticates with OAuth and has the `admin:read` and `admin:write` scopes can use the subscription settings and subscribers APIs. `admin:read` lets you list subscribers and read settings. `admin:write` lets you add or remove subscribers and change settings.
* You can subscribe any Learning Manager user, but the user must exist, be active, and have access to the board to receive notifications. Access is rechecked when notifications and digests are sent.
* If a user loses access, delivery is skipped for that board and the subscription is retained. Delivery resumes if access returns.
* You can add several users to a board in one request (bulk subscriptions). If a user is already subscribed, the request still succeeds and no duplicate is created. See [Bulk subscriptions](api-changes-dec-2026.md#bulk-subscriptions) for the request format, the 207 Multi-Status response, and the failure cases.

## Digest content

### Included events

The digest includes new posts, comments, and replies when the matching setting is `true` in the [`boardSubscriptionSettings` API](api-changes-dec-2026.md#api-create-settings): `notifyNewPost`, `notifyComment`, and `notifyReply`. You set these with `POST` or `PATCH /boardSubscriptionSettings`. All settings are `false` by default.

### Excluded events

The digest excludes events whose matching setting in the [`boardSubscriptionSettings` API](api-changes-dec-2026.md#api-create-settings) (for example, `notifyComment`) is `false`. No digest is sent when there's no eligible activity.

### Sample digest email layout

A digest email is sent for each subscribed board that had eligible activity. It is structured as follows:

* **Summary line:** The email opens with the total number of updates on the board (for example, seven updates) and a breakdown by type (for example, new posts and comments), along with the time from which the activity is counted.
* **Board section:** Activity is grouped under the board name. Each post is listed beneath it.
* **Item details:** Each post, comment, or reply shows the name and email address of the user who created it, plus a link to the item.
* **Links:** Selecting a link opens the post, comment, or reply directly. The recipient must be logged in for the link to open.
* **Comments and replies:** These appear in the same email as posts, so Instructors can see follow-up conversations along with new topics.

## Configure notifications

### Configure settings using APIs

You manage notifications through two public APIs: the [`boardSubscriptionSettings` API](api-changes-dec-2026.md#api-sequence), which applies at the account level, and the [subscribers API](api-changes-dec-2026.md#api-get-subscribers), which applies per board. Both use the OAuth scopes `admin:read` and `admin:write`. Call them in this sequence:

1. Set the account-level settings with [`POST /boardSubscriptionSettings`](api-changes-dec-2026.md#api-create-settings).
1. Change the settings later, when needed, with [`PATCH /boardSubscriptionSettings`](api-changes-dec-2026.md#api-update-settings).
1. Retrieve the account-level settings with [`GET /boardSubscriptionSettings`](api-changes-dec-2026.md#api-get-settings).
1. List the users subscribed to a board with [`GET /boards/{id}/subscribers`](api-changes-dec-2026.md#api-get-subscribers).
1. Subscribe users to a board with [`POST /boards/{id}/subscribers`](api-changes-dec-2026.md#api-subscribe-users).
1. Unsubscribe a user from a board with [`DELETE /boards/{id}/subscribers/{userId}`](api-changes-dec-2026.md#api-unsubscribe-user).

Use the `boardSubscriptionSettings` API to set the digest frequency in hours and to turn posts, comments, and replies on or off for the digest. For example, an account with a digest frequency of 1 hour receives a digest email every hour. All event settings are `false` by default.

### Manage subscribers

Use the subscribers API to choose which active Learning Manager users are subscribed to which boards. A subscription is separate from the existing board follow relationship. A user must have visibility to a board to receive its notifications, which means the user should be logged in. Losing visibility suppresses delivery but doesn't remove the subscription.

### Enable the feature

To enable Instructor notifications, create the account-level settings and then subscribe users to boards, as described in [API changes in Nov 2026](api-changes-dec-2026.md). After that, the system collects new posts, comments, and replies created during the configured interval. At the end of the interval, subscribers receive a summarized notification covering the eligible activity on subscribed boards.

Learn more about the API changes in [API changes in December 2026](api-changes-dec-2026.md).
