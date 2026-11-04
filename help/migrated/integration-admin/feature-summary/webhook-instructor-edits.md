---
description: Get webhook events in Adobe Learning Manager when instructors edit session details, and keep learner notifications and connected systems current.
jcr-language: en_us
title: Receive webhook events for instructor session edits
exl-id: 6fa4b71b-a8f4-40a2-ab57-bb7f3016542c
---

# Webhook events for LO instance edits by instructors

Adobe Learning Manager provides webhook events that notify external systems when a learning object (LO) instance, such as a session of an instructor-led course, is modified. Previously, these events were triggered only when an administrator or author modified an LO instance. Webhook events are now also triggered when an instructor edits the details of a session.

You can use these events to keep external systems, such as email services, calendars, reporting tools, or analytics platforms, up to date with instructor changes. For example, you can notify learners when a session time changes.

Instructor edits use the existing learning object instance modification event, so no new event type is introduced.

>[!NOTE]
>
>Instructor edits trigger a webhook only if an active webhook subscribes to the learning object instance modification event. Learn how to [create and manage webhooks as an Integration Admin](/help/migrated/integration-admin/feature-summary/webhooks.md#create-manage-webhooks).

## Supported instructor edits

The webhook event is triggered when an instructor edits any of the following session details:

* Session timings

* Credits

* Time zone

* Venue

* Enrollment limit

* Waitlist limit

* Allow submissions

## Webhook payload structure

Each webhook request contains the following top-level structure:

```json
{
  "accountId": 1010,
  "events": [
    {
      "eventId": "d5fb7071-10a9-46b2-9f9e-79dde346c052",
      "eventName": "<LO_INSTANCE_MODIFICATION_EVENT_NAME>",
      "timestamp": "2026-10-20T09:15:43.000Z",
      "eventInfo": "1760951743000-047210-84242-0",
      "data": {
        "loId": "course:7374992",
        "loInstanceId": "course:7374992_10250977",
        "loType": "course"
      }
    }
  ]
}
```

The same structure is used regardless of who modifies the LO instance. The payload doesn't indicate whether an instructor, an administrator, or an author made the change.

When an instructor changes a session detail, such as the time zone, enrollment limit, or waitlist limit, the webhook sends this event to your listener URL. Use the event to retrieve the latest session details and notify learners or update your external systems.

## Retrieve the updated session details

The webhook event identifies the LO instance that was modified. To get the updated session details, call the Learning Manager public API (Prime API) using the `loId` from the event:

```http
GET /primeapi/v2/learningObjects/{loId}
```

Locate the instance that matches `loInstanceId` in the response, and then compare it with the data stored in your system.

## Build integrations with webhook events

You can use these webhook events to:

* Send learner notifications through an external email or messaging service when session details such as date, time, time zone, or venue change.

* Synchronize session data with external calendars, reporting, or analytics systems.

* Track capacity changes when the enrollment limit or waitlist limit of a session is modified.

* Maintain audit trails by logging `eventId`, `timestamp`, and `eventInfo` along with the LO and instance identifiers.

At minimum, your webhook handler should:

* Validate the payload and parse `events[]`.

* Use `eventName` to identify the learning object instance modification event.

* Use `loId` and `loInstanceId` to locate the corresponding record in your system, and call the public API to retrieve the current session details.

* Use `eventId` to prevent duplicate processing if the same event is delivered more than once.

The same event is sent for edits made by instructors, administrators, and authors, so your integration may receive it more often than before. Compare the retrieved session details with the data in your system before you send a notification. Learners are then notified only when relevant details change.
