---
jcr-language: en_us
title: Webhooks
description: Learn about Webhooks to send real-time information, such as course enrollments, course creation and other information, to a specific URL
contentowner: chandrum
exl-id: 472aaf2b-9c2f-4f43-a791-2b2d81e69471
---
# Webhooks

A webhook allows one entity to automatically send real-time data or notifications to another entity when a specific event occurs. It will enable an application to provide other applications with information without constantly requesting it. For example, if a user completes a Learning Management System (LMS) course, a webhook can automatically send that information to another platform, such as a CRM or reporting tool. Webhooks are often used in integrations to automate processes and reduce the need for manual updates between systems. Set up webhooks by providing a callback URL to which you'd send the data.

## Webhooks vs APIs

Webhooks and APIs both help systems communicate with each other, but they work in different ways. With APIs, the information is shared only when the user requests it. For example, if a learner requires course progress data, they send a request to the API, which then provides the information. On the other hand, Webhooks automatically send data immediately when an event happens. For example, if a learner completes a course, it will send the data immediately to the listener URL without any manual requests.

## What are real-time APIs? 

Real-time APIs allow applications to instantly exchange data when an event happens. Unlike traditional APIs, which wait for a user to request information, real-time APIs share data the moment it happens. Webhooks act as a real-time API and help share the data immediately whenever the specified event occurs. The real-time API ensures that this data transfer happens immediately without needing any manual request, which allows systems to stay updated instantly.

## Webhook events

Webhook events are specific actions happening in a system that automatically sends data to a listener URL. For example, when a learner enrolls in a course, a webhook event is triggered and sends the enrollment details to the listener URL.

Webhook events are classified into two categories:

* **Real-time events**: Events are processed and sent in real-time to a target URL
* **Non real-time events**: Events are processed in batches and sent at specified times instead of in real-time

## Listener URL

A Listener URL is an endpoint or destination that receives data information when an event occurs. Whenever a specific event happens, such as a user enrolling in a course, the system automatically sends the details to this URL without any manual request. The listener URL is the address where all these updates are delivered.
Webhook sends the relevant information in a JSON format. Here's a sample payload for an event triggered in Adobe Learning Manager:

```
{
  "accountId": 1010,
  "events": [
    {
      "eventId": "d5fb7071-10a9-46b2-9f9e-79dde346c052",
      "eventName": "COURSE_ENROLLMENT_BATCH",
      "timestamp": 1727414643000,
      "eventInfo": "1727414643000-047210-84242-0",
      "data": {
        "userId": 4279332,
        "loId": "course:7374992",
        "loInstanceId": "course:7376092_10250977",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": 1727414643
      }
    }
  ]
}
```

## Create and manage Webhooks – Integration Admin

Follow the below steps to create Webhooks integration in Adobe Learning Manager: 

1. Log in as an **[!UICONTROL Integration Admin]**. 
2. On the homepage, select **[!UICONTROL Webhooks]** > **[!UICONTROL Add Webhook]**. 

   ![](assets/create-webhook.png)
   _Add a webhook_

3. Type the **[!UICONTROL Name]** and **[!UICONTROL Description]** of the Webhook. 
4. Type the listener URL as a **[!UICONTROL Target URL]** where you want to pass the event data. 
5. Select any one of the authentication methods: 
   Authentication in Webhooks is a security method to make sure that the data sent to a listener URL comes from a trusted source.
    * **[!UICONTROL None]**: No authentication required. 
    * **[!UICONTROL Basic]**: This is credential-based authentication. Enter the username and password. 
    * **[!UICONTROL Signature]**: The system creates a special signature and adds it to the webhook data. The receiving server checks this code to make sure the data is real and hasn't been changed. Generate a signature and use it for authentication. Download the signature as JSON.
6. Select the Webhook events from the **[!UICONTROL Trigger events]** dropdown. 

   >[!NOTE]
   >
   >You can also test the webhooks by selecting the Test Webhooks option from the Add Webhook page. 

7. Select the **[!UICONTROL Activation Status]** toggle to enable the webhook. Once enabled, data will be passed whenever the selected events occur.

>[!NOTE]
>
>You can create and manage up to 5 Webhooks.

### Edit Webhooks – Integration Admin

Follow these steps to edit Webhooks from Adobe Learning Manager:

1. Log in as an **[!UICONTROL Integration Admin.]**
2. Select **[!UICONTROL Webhooks]** on the homepage.
3. Select the webhook you want to edit.

   ![](assets/edit-webhook.png)
   _Edit the webhook_
4. Select **[!UICONTROL Edit]** to modify the webhook's details and select **[!UICONTROL Save]**.

### Remove Webhooks – Integration Admin

Follow these steps to edit Webhooks from Adobe Learning Manager:

1. Log in as an **[!UICONTROL Integration Admin]**.
2. Select **[!UICONTROL Webhooks]** on the homepage.
3. Select the webhook you want to delete.
4. Select **[!UICONTROL Delete]** to remove the webhooks.

![](assets/delete-webhooks.png) 
_Remove the webhook_

### Retire Webhooks – Integration Admin

Follow these steps to retire the webhooks:

1. Log in as an **[!UICONTROL Integration Admin]**.
2. Select **[!UICONTROL Webhooks]** on the homepage.
3. Select the webhook you want to edit.
4. Select **[!UICONTROL Edit]** and disable the **[!UICONTROL Activation Status]** to retire the webhook.
 
 ![](assets/retire-webhook.png)
_Retire the webhook_

## Webhooks for Alternates {#webhooks-for-alternates}

ALM provides dedicated webhook events for alternate completions to support automation, integrations, and synchronization with external systems.

These events allow external consumers to reliably distinguish between direct completions and completions granted through alternate relationships.

### Overview

When a learner completes a course via an alternate or relationship, ALM triggers a webhook event that is separate from the standard course completion webhook. This ensures that integrations can respond differently to alternate completions where required.

Webhook events are also triggered when retroactive completion or retroactive incompletion occurs, covering historical updates as well as relationship changes.

### Webhook event behavior

* A distinct webhook event is triggered when a learner receives Completed via Alternate status for a target course.
* The event is generated when the learner completes a configured source course that satisfies the target through an alternate relationship.
* This webhook is not triggered for direct course completions.
* When retroactive completion or retroactive incompletion is enabled, webhook events are emitted for each affected learner and target course.

### Webhook payload details

The alternate completion webhook payload includes the following key attributes:

* **Learner ID**
  Identifies the learner who received the alternate completion.
* **Source course**
  The course or learning path that the learner completed directly.
* **Target course**
  The course that is marked as completed via the alternate relationship.
* **Completion method**
  Indicates that the completion method is alternate.
* **Completion date**
  Derived from the completion date of the source course.
* **Relationship type**
  Specifies whether the relationship is alternate.

For retroactive incompletion scenarios, webhook events indicate that an existing alternate completion has been revoked.

### Integration considerations

External systems can use these webhook events to:

* Update learner records
* Synchronize completion status
* Trigger notifications or downstream workflows
* Maintain audit trails for compliance purposes

Webhook consumers should explicitly differentiate between direct and alternate completions.

Alternate completions do not grant skills, badges, and gamification rewards. Feedback should be handled accordingly in downstream systems.
 
## Webhooks for Adaptive Learning Paths

### Introduction
 
Adobe Learning Manager provides **webhook events** that notify external systems whenever the completion status of a **learning path (learning program)** is refreshed. This allows you to synchronize downstream systems (such as HR, reporting, or analytics platforms) whenever a learner's completion record is rolled back or recalculated. 

Two new webhook event types are available: 

**LEARNING_PATH_COMPLETION_ROLLBACK** – Triggered when a **learner** refreshes the completion status of a learning path for themselves.

**LEARNING_PATH_COMPLETION_ROLLBACK_BATCH** – Triggered when an **administrator** refreshes the completion status of a learning path for **one or more learners** (for example, via bulk operations).

These events use a **common payload structure** and can be consumed by your webhook endpoint to update or reprocess completion data on your side.

### Common payload structure
 
Each webhook request contains the following toplevel structure: 

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "757b9d58-048c-4ae2-9fff-35f9def7ef29",
      "eventName": "LEARNING_PATH_COMPLETION_ROLLBACK",
      "timestamp": "2026-01-20T05:48:10.000Z",
      "eventInfo": "1768888090000-197513-137581-0",
      "data": {
        "userId": 13446697,
        "loId": "learningProgram:157165",
        "loInstanceId": "learningProgram:157165_148769",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2026-01-20T05:44:05.000Z"
      }
    }
  ]
}
```

The **same structure** is used for both event types; only the eventName and the values inside data (for example, userId, loId, enrollmentSource) differ.

#### Example: Learner-initiated refresh
 
When a learner refreshes the completion status of their own learning path, the webhook sends a LEARNING_PATH_COMPLETION_ROLLBACK event:

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "757b9d58-048c-4ae2-9fff-35f9def7ef29",
      "eventName": "LEARNING_PATH_COMPLETION_ROLLBACK",
      "timestamp": "2026-01-20T05:48:10.000Z",
      "eventInfo": "1768888090000-197513-137581-0",
      "data": {
        "userId": 13446697,
        "loId": "learningProgram:157165",
        "loInstanceId": "learningProgram:157165_148769",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2026-01-20T05:44:05.000Z"
      }
    }
  ]
}
```

Use this event to **recalculate or reset learner completion data** in your external systems when the learner explicitly requests a refresh.

#### Example: Admin-initiated batch refresh
 
When an administrator performs a completion refresh for one or more learners (for example, correcting historical completions for a group), the webhook emits a LEARNING_PATH_COMPLETION_ROLLBACK_BATCH event: 

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "757b9d58-048c-4ae2-9fff-35f9def7ef29",
      "eventName": "LEARNING_PATH_COMPLETION_ROLLBACK_BATCH",
      "timestamp": "2026-01-20T05:48:10.000Z",
      "eventInfo": "1768888090000-197513-137581-0",
      "data": {
        "userId": 13446698,
        "loId": "learningProgram:157166",
        "loInstanceId": "learningProgram:157166_148770",
        "loType": "learningProgram",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": "2026-01-21T05:44:05.000Z"
      }
    }
  ]
}
```

In batch operations, your webhook endpoint may receive **multiple event objects in a single request**, one per learner whose completion has been refreshed. Your integration should iterate over the events array and process each event independently.

### How to use these events in integrations
 
You can use these webhook events to: 

**Synchronize completion records** with external LMS/LRS, HR, or reporting systems when a completion is rolled back or recalculated. 

**Trigger downstream workflows** such as reassignments, notifications, or recalculation of certifications and badges. 

**Maintain audit trails** by logging eventId, timestamp, and eventInfo along with the learner and learning path identifiers. 

At minimum, your webhook handler should: 

Validate the payload and parse events[]. 
Use eventName to determine whether the change was **learnerinitiated** or **admin/batchinitiated**. 

Use userId, loId, and loInstanceId to locate and update the corresponding record in your system. 
Leverage eventId to prevent duplicate processing if the same event is delivered more than once.

## Webhooks for adding and removing user group membership

Two new webhook event types carry the final statuses:

* RESPONSE:ASYNCAPI_USERGROUP_USER_ADDED
* RESPONSE:ASYNCAPI_USERGROUP_USER_REMOVED

### Sample payload

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "cd2972c8-cb15-47a0-a23f-e4a16cb720f5",
      "eventName": "RESPONSE:ASYNCAPI_USERGROUP_USER_REMOVED",
      "timestamp": "2026-03-18T13:38:12.000Z",
      "eventInfo": "cd2972c8-cb15-47a0-a23f-e4a16cb720f5",
      "data": {
        "status": "SUCCESS",
        "request": {
          "metadata": { "event_id": "cd2972c8-cb15-47a0-a23f-e4a16cb720f5" },
          "data": [ { "type": "user", "id": "13446641" } ]
        }
      }
    }
  ]
}
```

### Key elements

* `accountId` identifies the ALM account.
* `events` is an array of event objects.
* `eventId` matches the original async request identifier.
* `eventName` indicates add or remove operation.
* `timestamp` shows completion time.
* `data.status` currently reports "SUCCESS" for successful batches.
* `data.request` contains the exact request you sent.

Your integration should primarily key off `eventId` (or `metadata.event_id`) and `status`.

### Examples

#### Adding users asynchronously

**Step 1. Make the async call**

POST /primeapi/v2/async/userGroups/12345/users

```
{
  "metadata": {
    "event_id": "sync-2026-03-30T10:15:00Z-ug-12345",
    "sourceSystem": "HRIS",
    "batchId": "hr_2026_03_30_0001"
  },
  "data": [
    { "type": "user", "id": "11101219" },
    { "type": "user", "id": "11101220" }
  ]
}
```

**Step 2. Read the immediate response**

```
{ "event_id": "sync-2026-03-30T10:15:00Z-ug-12345" }
```

You can now mark this job as submitted in your system.

**Step 3. Handle the Webhook**

Webhook callback example:

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "sync-2026-03-30T10:15:00Z-ug-12345",
      "eventName": "RESPONSE:ASYNCAPI_USERGROUP_USER_ADDED",
      "timestamp": "2026-03-30T10:15:43.000Z",
      "data": {
        "status": "SUCCESS",
        "request": {
          "metadata": {
            "event_id": "sync-2026-03-30T10:15:00Z-ug-12345",
            "sourceSystem": "HRIS",
            "batchId": "hr_2026_03_30_0001"
          },
          "data": [
            { "type": "user", "id": "11101219" },
            { "type": "user", "id": "11101220" }
          ]
        }
      }
    }
  ]
}
```

A typical consumer will:

* Locate the internal job.
* Optionally verify membership using GET /userGroups/{id}/users.
* Mark the job as completed.

#### Removing users asynchronously

Removal is symmetric, using DELETE with the same body structure.

```
{
  "metadata": {
    "event_id": "sync-2026-03-30T11:00:00Z-ug-12345",
    "sourceSystem": "HRIS",
    "batchId": "hr_2026_03_30_0002"
  },
  "data": [ { "type": "user", "id": "11101219" } ]
}
```

Immediate response:

```
{ "event_id": "sync-2026-03-30T11:00:00Z-ug-12345" }
```

Later, a RESPONSE:ASYNCAPI_USERGROUP_USER_REMOVED Webhook arrives with the same eventId.

View [Asynchronous public API for user group membership](/help/migrated/api-changes-alm.md#asynchronous-public-apis-for-user-group-membership) for more information.
