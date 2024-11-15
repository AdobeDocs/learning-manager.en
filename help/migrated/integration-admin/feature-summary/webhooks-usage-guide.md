---
jcr-language: en_us
title: Webhooks usage guide
description: Learn about Webhooks usage, best practices and limitations
contentowner: chandrum
exl-id: e6a63ffb-7fdd-46e4-b5e6-20ce36861cef
---
# Webhooks usage guide

Webhooks are a way for web applications to communicate with each other automatically and in real-time.

Unlike traditional APIs, which wait for a user to request information, real-time APIs share data the moment it happens. Webhooks act as a real-time API and help share the data immediately whenever the specified event occurs.

## Entities

To understand webhooks events, we first need to be aware of the entities involved and the trigger conditions for these events.

### Learning objects

The following are the Supported events for learning objects (Course, Learning Path or Certifications).

#### Draft

Whenever a learning object is created from the UI, it starts in **Draft** mode. This means the learning object is not yet published and is not available for the learners. The **LEARNING_OBJECT_DRAFT** event is triggered as long as the learning object remains a draft. Any successive updates to the draft will also trigger this event.

#### Update

Once the learning object is published, its state changes from **Draft** to **Published**. During this transition, Webhook generates the **LEARNING_OBJECT_MODIFICATION** event because the learning object is being modified from **Draft** to **Published**. All subsequent modifications and updates to the LO will also trigger a **LEARNING_OBJECT_MODIFICATION** event.

The **LEARNING_OBJECT_MODIFICATION** event is also triggered when the learning object is retired. This retired operation marks the underlying instances as updated, as these instances are retired once the parent learning object is in the retired state.

#### Delete

Upon deleting a learning object, the **LEARNING_OBJECT_DELETION** event is generated. This event indicates that the learning object has been deleted and is no longer available for learners to access.

In addition to real-time events, learning object events also have a batch (non-real-time) counterpart, which is triggered as part of the **LEARNING_OBJECT_MODIFICATION_BATCH** event. This event occurs during the creation or modification of a learning object through the migration workflow. Since learning object draft and delete operations are not supported via migration, there are no corresponding draft or deletion events for these actions.

### Learning object instances

The following are the supported events for learning object instances.

#### Update

Once an instance is created, the **LEARNING_OBJECT_INSTANCE_MODIFICATION** event is generated. Learning object instances in Adobe Learning Manager don't have a **Draft** state; therefore, Adobe Learning Manager doesn't support a **LEARNING_OBJECT_INSTANCE_DRAFT event**. This event is generated whenever an instance is created, modified, or retired.

In addition to being generated when an instance is created, updated, or retired, this event is also auto-generated when its parent learning object is marked as **Retired**. This is because when a learning object is retired, the underlying instances need to be marked as **Retired** as well.

#### Delete

When an instance is deleted, the **LEARNING_OBJECT_INSTANCE_DELETION** event is generated. This event only applies to course instances that contain self-paced modules, as Adobe Learning Manager only allows admins to delete course instances where the module type is self-paced. Adobe Learning Manager does not support explicit deletions for other types of course modules not for learning path instances or certification instances.

The learning object instance also has a non-real-time counterpart, exposed as part of the **LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH** event. This event is triggered during the creation or modification of a learning object instance through the migration workflow. Since draft or delete operations for learning object instances are not supported in migration, corresponding draft or deletion events are not available.

### Enrollment

Once a learner performs an enrollment action, a real-time enrollment event is triggered. Depending on the learning object type, the real-time enrollment event can fall into one of the following categories: 

* COURSE_ENROLLMENT
* LEARNING_PATH_ENROLLMENT
* CERTIFICATION_ENROLLMENT

Enrollment events have batch counterparts in addition to these real-time events. Whenever an enrollment is triggered by an admin, manager, or platform, non-real-time enrollment events are triggered. Based on the learning object type, the batch enrollment event can be one of the following:

* COURSE_ENROLLMENT_BATCH
* LEARNING_PATH_ENROLLMENT_BATCH
* CERTIFICATION_ENROLLMENT_BATCH

### Unenrollment

When a learner performs an unenrollment action, a real-time unenrollment event is triggered. Depending on the learning object type, the real-time unenrollment event can fall into one of the following categories: 

* COURSE_UNENROLLMENT
* LEARNING_PATH_UNENROLLMENT
* CERTIFICATION_UNENROLLMENT

In addition to these events, there are also batch unenrollment events. Whenever an unenrollment is marked by an admin, manager, or platform, non-real time unenrollment events are triggered. Based on the learning object type, the batch unenrollment event can be one of the following: 

* COURSE_UNENROLLMENT_BATCH
* LEARNING_PATH_UNENROLLMENT_BATCH
* CERTIFICATION_UNENROLLMENT_BATCH

### Completion

The real-time completion event is triggered whenever a learner completes a learning object. Based on the learning object type, the real-time completion event can fall into one of the following categories: 

* COURSE_COMPLETED
* LEARNING_PATH_COMPLETED
* CERTIFICATION_COMPLETED

In addition to these real-time events, there are also batch completion events. For example, when an admin, manager, or platform marks a learning object as complete, the non-real-time completion events are triggered. Based on the learning object type, the batch completion event can fall into one of the following categories: 

* COURSE_COMPLETED_BATCH
* LEARNING_PATH_COMPLETED_BATCH
* CERTIFICATION_COMPLETED_BATCH

### Learner progress

Whenever a learner enrolls in a learning object and begins the module, their progress is tracked. This data is included in the **LEARNER_PROGRESS** event. The event may be delayed by up to 15 minutes, as the progress tracking relies on complex aggregation logic, which is not real-time.

### CI stats

The **CI_STATS** real-time event is triggered whenever there is a change in seat or waitlist availability for a course instance. This data is captured only at the instance level. Additionally, this event is triggered for courses and not for other learning paths or certifications, as seat and waitlist availability are attributes specific to a course and its instance.

## Ordering of events

Adobe Learning Manager ensures that events are ordered for each account. However, there may be discrepancies when correlating messages between enrollment or completion and progress events. This happens because the learner progress event can be delayed by up to 15 minutes, as progress tracking relies on complex aggregation logic, which is not real-time. Additionally, progress events come from different data sources, so their order cannot be guaranteed in relation to enrollment and completion events. Therefore, Adobe Learning Manager provides best practices for clients when listening to these events.

If the completion event occurs before the learner progress event, the client can ignore the learner progress event. This is because the learner progress event can be delayed by up to 15 minutes, while the completion event may be triggered before the progress event is received. Since receiving a completion event indicates that the learning object is finished, it implies that progress has reached 100%.

In the rare case that the enrollment event comes after the learner progress event, the client can ignore the enrollment event. This is because progress can only be tracked after the learner has enrolled in the learning object. In other words, receiving a progress event indicates that the learning object has been started, which only happens after a successful enrollment.

## Realtime events vs batched events

Certain events have real-time and non-real-time counterparts, as mentioned above. There may be questions about when to subscribe to real-time events and when to subscribe to non-real-time events. The following are guidelines that can be followed based on the entities described above.

### Real-time events

|S.No| Webhook Events | Description |
|---|---|---|
| 1 |CI_STATS | Triggered when there is a change in seat or waitlist availability for a course instance.|
| 2 |COURSE_ENROLLMENT | Triggered when a learner enrolls in a course.|
| 3 |COURSE_COMPLETED | Triggered when a learner completes a course.|
| 4 |LEARNING_PATH_ENROLLMENT | Triggered when a learner enrolls in a learning path.|
| 5 |LEARNING_PATH_COMPLETED | Triggered when a learner completes a learning path.|
| 6 |CERTIFICATION_ENROLLMENT | Triggered when a learner enrolls in a certification.|
| 7 |CERTIFICATION_COMPLETED | Triggered when a learner completes a certification.|
| 8 |COURSE_UNENROLLMENT | Triggered when a learner unenrolls from a course.|
| 9 |LEARNING_PATH_UNENROLLMENT | Triggered when a learner unenrolls from a learning path.|
| 10 |CERTIFICATION_UNENROLLMENT | Triggered when a learner unenrolls from a certification.|
| 11 |LEARNING_OBJECT_DRAFT | Triggered during the creation of a learning object in draft state.|
| 12 |LEARNING_OBJECT_DELETION | Triggered during the deletion of a learning object.|
| 13 |LEARNING_OBJECT_MODIFICATION | Triggered during the modification of a learning object.|
| 14 |LEARNING_OBJECT_INSTANCE_MODIFICATION | Triggered during the creation or modification of a learning object instance.<div><b>Note:</b> It is recommended to use course instances only after the course is published.</div>|
| 15 |LEARNING_OBJECT_INSTANCE_DELETION | Triggered during the deletion of a learning object instance.|

### Non–real-time events

| S.No | Webhook Events | Description |
|---|---|---|
| 1 |COURSE_ENROLLMENT_BATCH | Triggered when an admin/manager/platform enrolls learners in a course. |
| 2 |COURSE_COMPLETED_BATCH | Triggered when an admin/manager/platform marks a course as completed. |
| 3 |LEARNING_PATH_ENROLLMENT_BATCH | Triggered when an admin/manager/platform enrolls learners in a learning path. |
| 4 |LEARNING_PATH_COMPLETED_BATCH | Triggered when an admin/manager marks a learning path as completed.|
| 5 |CERTIFICATION_ENROLLMENT_BATCH | Triggered when an admin/manager/platform enrolls learners in a certification. |
| 6 |CERTIFICATION_COMPLETED_BATCH | Triggered when an admin/manager/platform marks a certification as completed.|
| 7 |LEARNER_PROGRESS | Tracks the progress of a learner when a module is completed. |
| 8 |COURSE_UNENROLLMENT_BATCH | Triggered when an admin/manager/platform unenrolls learners from a course. |
| 9 |LEARNING_PATH_UNENROLLMENT_BATCH | Triggered when an admin/manager/platform unenrolls learners from a learning path. |
| 10 |CERTIFICATION_UNENROLLMENT_BATCH | Triggered when an admin/manager/platform unenrolls learners from a certification. |
| 11 |LEARNING_OBJECT_MODIFICATION_BATCH | Triggered during the modification of a learning object via migration workflow. |
| 12 |LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH | Triggered during the creation or modification of a learning object instance via migration workflow. |

### Learning objects and its instances

* Subscribe to real-time events whenever you want to listen for changes to learning objects made through UI actions by roles such as Admin, Author, etc.
* Subscribe to non-real time or batched events whenever you want to listen for changes to learning objects made through migration workflows.

### Enrollment, unenrollment and completion

* Subscribe to real-time events whenever you want to listen for enrollments, unenrollments, or completions performed by learners.
* Subscribe to non-real time or batched events whenever you want to listen for enrollments, unenrollments, or completions marked by Admin, Manager, Platform, etc.

### Learner progress

* Subscribe to the event whenever you want to listen for progress changes of a learner.

>[!NOTE]
>
>In the above scenarios (enrollment, unenrollment, completion, and progress), the attribute composites consisting of userId and loInstanceId can uniquely identify a record.

### Course instance stats

* Subscribe to the real-time **CI_STATS** event whenever you want to listen for changes in seat or waitlist availability.

## Webhook event payload

As part of the Webhooks response payload, Adobe Learning Manager will emit attributes required to uniquely identify an entity. These will be emitted in the same format and according to the standards used by the public API, ensuring that the webhook data is in sync with the public API data. View [Sample payloads](/help/migrated/integration-admin/feature-summary/webhooks-usage-guide.md#sample-payloads-for-the-events) for see payloads for the various events.

## Using webhooks to build an external DB or notification service

One of the use cases we've heard where Webhooks might be useful is for building a database on the customer's side. Adobe Learning Manager has its own database and schema, but customers don't have access to it. 

The question is: how can customers build a database using events from webhooks?

Since Adobe Learning Manager won't directly expose the table records and schema, customers can rely on the Webhooks solution to build an external database by consuming the events to populate it. In this release, we are providing events for learning objects, learning object Instances, enrollment, unenrollment, completion, progress, and course instance stats.

### Building a database from learning object events

The learning object events expose `loId` and `loType` to identify an entity. However, these attributes alone are not sufficient to build an external learning object database. Customers will need additional fields to further describe the learning object.
There are two approaches to fetch the additional data:

#### Generate a training data report to fetch all the data

This approach should be used when learning objects are created in bulk via workflows like migration. The goal here is to generate the **[!UICONTROL Training Data]** report with all the learning objects ingested as part of the migration workflow. To optimize the import process, it is recommended to set the export start time to the time when the migration was triggered. This will ensure that only the learning objects brought in via migration are exported in the report, as historical data will already be available in the customer's database.

#### Query the information from the public API GET /learningObjects - Admin scope

This approach should be used when learning objects are created via real-time workflows. The customer should have their own caching layer to batch the learning objects emitted via the events and then query the `GET /learningObjects` API by passing these learning object IDs. The reason for having a caching layer is to ensure that the public API rate limits are not exceeded. Currently, we have admin rate limits set to 500 requests per hour for` GET /learningObject` APIs. If this limit is exceeded, the public API service will respond with an **HTTP 429 Too Many Requests message**.

### Building database from learning object instance and CI_STATS events

The learning object Instance event emits the `loInstanceId`, `loId`, and `loType` attributes for courses and learning paths. Similarly, the **CI_STATS** event is applicable only to courses since `seatLimit`, `seatAvailability`, `waitListLimit`, `waitlistAvailability`, etc., are only applicable to courses.

In certain use cases, additional instance data like instance name, state etc., are required. To fetch additional instance data, the following approach is to be followed:

#### Query the information from public-api GET /learningobjects - Admin scope

Customers can consume the `GET /learningObjects` API as mentioned above, along with instances included to fetch the information about instances. They should still follow the approach mentioned in the [section](/help/migrated/integration-admin/feature-summary/webhooks-usage-guide.md#query-the-information-from-the-public-api-get-learningobjects-admin-scope) to ensure that the rate limits are not breached.


>[!NOTE]
>
>1. Certifications don't have the concept of instances in ALM.
>2. There is no need to fetch additional data for CI_STATS since the same information would have already been fetched as part of the learning object Instance events.

### Building database from enrollment, unenrollment, completion and progress events

Learner enrollment, unenrollment, completion, and progress are emitted as separate events in Adobe Learning Manager. The learner is identified by the `userId` attribute. However, there may be certain scenarios where additional learner information, such as Name, Email, etc., is required for downstream workflows on the customer side. To fetch this data, customers can follow the approach outlined below:

#### Export the user report from admin or connectors

This approach should be followed whenever bulk workflows are involved, such as bulk enrollment, bulk unenrollment, etc. The User Report from Adobe Learning Manager contains all information pertaining to a user. By correlating the `userId` obtained from the webhook event, customers can look up this report (which may be exposed on the customer side as a database, cache, or API endpoint) to fetch additional details like Name, Email, UUID, etc. This approach can be used to sync users on a weekly or daily basis.

#### Query information from public API GET /users - Admin Scope

This approach can be followed when the users are not available in the above report. The combination of approaches 1 and 2 ensures that all existing users who were created in the past can be covered by the **[!UICONTROL User Report]**, while newly created users can still be fetched from the API. If the **[!UICONTROL User Report]** does not have the data, the customer can send the userIds as input arguments to the `GET /users` API to fetch user information. This information should be cached on the customer side to prevent repeated invocations of the public API for the same set of users. Please note that we currently have Admin rate limits set to 500 requests per hour for GET /users APIs. Any requests beyond this limit will result in an **HTTP 429 Too Many Requests** response.

## Fault tolerance 

The fault-tolerant of the ALM webhook system provides recommendations for subscribers to handle potential issues, such as event loss, duplicate events, and out-of-order delivery. 

ALM has connection timeout configured to 10 seconds and socket timeout configured to 5 seconds. The expectation is that the client acknowledges the message as soon as it receives them. This is to ensure that the client doesn't lag while processing messages. In case there is some downstream processing which is time consuming, the client should still acknowledge the event instantly and then handle the downstream processing at their end.

### Data retention

Events are kept for 7 days. If they aren't processed within this time, they are lost permanently. If recovery happens on the last day and more time is needed, the system won't extend the retention period.
If events are produced faster than they are consumed, some events may be lost. Although this is uncommon, subscribers should monitor to prevent it from becoming a long-term issue.

### Webhooks disable

When a subscriber fails to respond to webhook events, the ALM system retries webhooks using exponential backoff to avoid overwhelming the subscriber.

The retry process starts with an initial interval of 5 seconds. If the subscriber doesn't respond, the wait time doubles to 10, 20, 40, and 80 seconds, eventually increasing to a maximum of 5 minutes. Once it reaches 5 minutes, the system will continue to retry every 5 minutes until the 7-day retention period is over. If the subscriber still doesn't respond during this entire period, the webhook will be automatically disabled. A reminder email will be sent to the subscriber at regular intervals.

### Duplicate events

If a subscriber takes more than 5 seconds to respond after processing an event, the system might try to process the same event again. It is recommended to use event IDs to keep track of which events have already been processed. Also, if the webhook crashes after sending the event but before saving that it was processed, the same group of events might be retried. It is recommended to use batch IDs or individual event IDs to recognize and ignore any duplicates.

### Recommendation for fault tolerance

To prevent these faults, subscribers should actively monitor webhook events and set up alerts for issues like missed events, duplicate deliveries, or out-of-order sequences.

## Specific guidelines for webhook events

1. If you get a LEARNER_PROGRESS event first, then ignore the events listed below:

   * COURSE_ENROLLMENT
   * COURSE_ENROLLMENT_BATCH
   * LEARNING_PATH_ENROLLMENT
   * LEARNING_PATH_ENROLLMENT_BATCH
   * CERTIFICATION_ENROLLMENT
   * CERTIFICATION_ENROLLMENT_BATCH

2. Ignore the LEARNER_PROGRESS event if it comes after the following events:

   * COURSE_COMPLETED
   * COURSE_COMPLETED_BATCH
   * LEARNING_PATH_COMPLETED
   * LEARNING_PATH_COMPLETED_BATCH
   * CERTIFICATION_COMPLETED
   * CERTIFICATION_COMPLETED_BATCH

3. Use the timestamp field to determine whether to ignore or process the event, except for LEARNER_PROGRESS event.

## Webhooks Events consumption best practices

* The webhook solution is used to handle high-throughput systems where speed and low latency are essential. Therefore, the customer should ensure that the event is acknowledged as soon as it is received. Even if additional processing is needed on the customer's side (such as fetching data from reports, API or performing other actions), the acknowledgement should be sent as soon as the event is received, and it is up to the client to process the event later.
* Failing to acknowledge the event as soon as possible could impact the real-time nature of the events, as subsequent events will only be emitted once the previous acknowledgement is received.
* Clients can respond with an HTTP 202 Accepted status code to acknowledge that the event has been accepted.

## Limitations

* Job Aids are not considered for Webhook events under the category of LOs because they are typically used to help learners complete other learning objects.
* An learning object instance retirement would be considered an update event. There wouldn't be a delete event for an instance since it can only be retired, not deleted.
* Session changes would be captured as part of the instance update event. This applies only to courses. There will be no upward propagation from lower-level entities for learning path instances or certification instances.
* If an learning path contains a course and a learner completes the course via the learning path, two **LearnerProgress** events will be generated—one for the course and one for the learning path.
* Certain workflows compute attributes of learning objects, such as duration and delivery type, asynchronously. Therefore, events for these learning object will be generated once the cron job finishes processing.

## Sample payloads for the events

+++CI_STATS

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "12345-0458-4450-b5dd-6bc1ef4f8b50",
      "eventName": "CI_STATS",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123456785-LoSt",
      "data": {
        "loInstanceId": "course:12345678_14448475",
        "waitlistCount": 0,
        "enrollmentCount": 10,
        "seatLimit": 30
      }
    }
  ]
}
```

+++

+++COURSE_ENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "12345c1-4576-4ec5-a057-3a6f078cc9d6",
      "eventName": "COURSE_ENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123424713000-040366-10488-0",
      "data": {
        "userId": 12345678,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14450088",
        "loType": "course",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++COURSE_ENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1234ec1-4576-4ec5-a057-3a6f078cc9d6",
      "eventName": "COURSE_ENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123424713000-040366-10488-0",
      "data": {
        "userId": 12345678,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14450088",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++COURSE_COMPLETED

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "c2345c-6c98-4ed3-b0b0-ba3da5087c1c",
      "eventName": "COURSE_COMPLETED",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "12345823000-040363-12018-0",
      "data": {
        "userId": 11080928,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14448484",
        "loType": "course",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z",
        "hasPassed": true
      }
    }
  ]
}
```

+++

+++COURSE_COMPLETED_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "c23458c-6c98-4ed3-b0b0-ba3da5087c1c",
      "eventName": "COURSE_COMPLETED_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123456823000-040363-12018-0",
      "data": {
        "userId": 12345678,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14448484",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z",
        "hasPassed": true
      }
    }
    ]
}
```

+++

+++LEARNING_PATH_ENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1234791-338f-4c4c-83bc-9f73ea794965",
      "eventName": "LEARNING_PATH_ENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123404248000-040653-71396-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:1234567",
        "loInstanceId": "learningProgram:1234567_109139",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++LEARNING_PATH_ENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "12340791-338f-4c4c-83bc-9f73ea794965",
      "eventName": "LEARNING_PATH_ENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123404248000-040653-71396-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:1234557",
        "loInstanceId": "learningProgram:1234557_109139",
        "loType": "learningProgram",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++LEARNING_PATH_COMPLETED

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "123404e-d554-4027-944b-086debefdddf",
      "eventName": "LEARNING_PATH_COMPLETED",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1234604391000-040653-314618-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:92348",
        "loInstanceId": "learningProgram:92348_95662",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z",
        "hasPassed": true
      }
    }
  ]
  }
```

+++

+++LEARNING_PATH_COMPLETED_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "12344e-d554-4027-944b-086debefdddf",
      "eventName": "LEARNING_PATH_COMPLETED_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123404391000-040653-314618-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:92348",
        "loInstanceId": "learningProgram:92348_95662",
        "loType": "learningProgram",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z",
        "hasPassed": true
      }
    } 
    ]
    }
```

+++

+++CERTIFICATION_ENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1234e776-148e-4128-80e9-b896a460b655",
      "eventName": "CERTIFICATION_ENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "12344672000-040654-559128-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:123418",
        "loInstanceId": "certification:123418_160299",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
}
```

+++

+++CERTIFICATION_ENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "123472ec1-4576-4ec5-a057-3a6f078cc9d6",
      "eventName": "COURSE_ENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1234524713000-040366-10488-0",
      "data": {
        "userId": 12345678,
        "loId": "course:123456798",
        "loInstanceId": "course:12345678_14450088",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++CERTIFICATION_COMPLETED

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1234bf8-7521-4bc0-bc51-7f951ff63ea9",
      "eventName": "CERTIFICATION_COMPLETED",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123454768000-040654-756257-0",
      "data": {
        "userId": 123456728,
        "loId": "certification:123418",
        "loInstanceId": "certification:134518_160299",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++CERTIFICATION_COMPLETED_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "123453bf8-7521-4bc0-bc51-7f951ff63ea9",
      "eventName": "CERTIFICATION_COMPLETED_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1234604768000-040654-756257-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:123418",
        "loInstanceId": "certification:123418_160299",
        "loType": "certification",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++LEARNER_PROGRESS

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "d1234d3a4-c3df-44fa-a1cf-7edd6e3d2075",
      "eventName": "LEARNER_PROGRESS",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235604551000-297002-5823-0",
      "data": {
        "loId": "course:7542090",
        "loType": "course",
        "userId": 12380928,
        "loInstanceId": "course:7232090_10423047",
        "dateStarted": "2024-11-08T03:49:52.000Z",
        "progressPercent": 50
      }
}
]
}
```

+++

+++COURSE_UNENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "f3237817-8cb8-40ea-a441-813bec1c7724",
      "eventName": "COURSE_UNENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1345506253000-040298-24078-0",
      "data": {
        "userId": 12311591,
        "loId": "course:12324298",
        "loInstanceId": "course:12324298_14450088",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
      }
    }
  ]
}
```

+++

+++COURSE_UNENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "f2317817-8cb8-40ea-a441-813bec1c7724",
      "eventName": "COURSE_UNENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "17235506253000-040298-24078-0",
      "data": {
        "userId": 12311591,
        "loId": "course:12324298",
        "loInstanceId": "course:12324298_14450088",
        "loType": "course",
        "enrollmentSource": "SELF_ENROLL"
    }
   }
  ]
}
```

+++

+++LEARNING_PATH_UNENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "823df878-1dfd-47ac-9bfe-7d4952e3edd1",
      "eventName": "LEARNING_PATH_UNENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235506667000-040299-28209-0",
      "data": {
        "userId": 12311591,
        "loId": "learning_program:123157",
        "loInstanceId": "learning_program:123157_109139",
        "loType": "learning_program",
        "enrollmentSource": "SELF_ENROLL",
      }
    }
]
}
```

+++

+++LEARNING_PATH_UNENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "8e23f878-1dfd-47ac-9bfe-7d4952e3edd1",
      "eventName": "LEARNING_PATH_UNENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235506667000-040299-28209-0",
      "data": {
        "userId": 12311591,
        "loId": "learning_program:123157",
        "loInstanceId": "learning_program:123157_109139",
        "loType": "learning_program",
        "enrollmentSource": "ADMIN_ENROLL"
      }
    }
]
}
```

+++

+++CERTIFICATION_UNENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "7232766b-54d8-472d-b933-7e89d1b75ef8",
      "eventName": "CERTIFICATION_UNENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235507900000-040304-1065-0",
      "data": {
        "userId": 12311591,
        "loId": "certification:123199",
        "loInstanceId": "certification:123199_162078",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL"
      }
    }
  ]
}
```

+++

+++CERTIFICATION_UNENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "7202766b-54d8-472d-b933-7e89d1b75ef8",
      "eventName": "CERTIFICATION_UNENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1735507900000-040304-1065-0",
      "data": {
        "userId": 12511591,
        "loId": "certification:139199",
        "loInstanceId": "certification:139199_162078",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL"
      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_DRAFT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "12345da9f-26ec-453c-b56a-cdf18a841948",
      "eventName": "LEARNING_OBJECT_DRAFT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1234519188000-040344-48604-0",
      "data": {
        "loId": "course:1234091",
        "loType": "course"
      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_DELETION

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1234a690-5517-4c09-9cde-d953cdd8582c",
      "eventName": "LEARNING_OBJECT_DELETION",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235605296000-040656-662792-0",
      "data": {
        "loId": "course:12319716",
        "loType": "course"
      }
    }
   ]
}
```

+++

+++LEARNING_OBJECT_MODIFICATION

```
{
  "accountId": 8308,
  "events": [
    {
      "eventId": "223e068-af3e-4dd3-a515-ce19d7234873",
      "eventName": "LEARNING_OBJECT_MODIFICATION",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123350842000-039736-54153-0",
      "data": {
        "loId": "learningProgram:123836",
        "loType": "learningProgram"
      }
    }
   ]
}
```

+++

+++LEARNING_OBJECT_MODIFICATION_BATCH

```
{
  "accountId": 8308,
  "events": [
    {
      "eventId": "1234e068-af3e-4dd3-a515-ce19d7234873",
      "eventName": "LEARNING_OBJECT_MODIFICATION_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235350842000-039736-54153-0",
      "data": {
        "loId": "learningProgram:123836",
        "loType": "learningProgram"
      }
    }
   ]
}
```

+++

+++LEARNING_OBJECT_INSTANCE_MODIFICATION

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "121da98-ab8d-43e9-b671-e79131cd69dc",
      "eventName": "LEARNING_OBJECT_INSTANCE_MODIFICATION",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235603297000-040649-741781-0",
      "data": {
        "loInstanceId": "course:12324298_14453691",
        "loId": "course:12324298",
        "loType": "course"
      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1231da98-ab8d-43e9-b671-e79131cd69dc",
      "eventName": "LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123603297000-040649-741781-0",
      "data": {
        "loInstanceId": "course:12324298_14453691",
        "loId": "course:12324298",
        "loType": "course"
      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_INSTANCE_DELETION

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "12d16e90-d73a-457b-83f3-666ba9654edb",
      "eventName": "LEARNING_OBJECT_INSTANCE_DELETION",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235605491000-040657-236307-0",
      "data": {
        "loInstanceId": "course:12319674_14453849",
        "loId": "course:12319674",
        "loType": "course"
      }
    }
  ]
}
```

+++
