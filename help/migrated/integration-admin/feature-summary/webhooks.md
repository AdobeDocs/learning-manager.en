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

## Real-time events

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

## Non–real-time events

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

## Best practices for webhooks

Webhooks enable real-time event-driven communication between services. However, improper implementation can result in lost events, slow system performance, or security risks. Below are the best practices to implement webhooks, focusing on fault-tolerance, reliability, and security. 

### Fault tolerance 

The fault-tolerant of the ALM webhook system provides recommendations for subscribers to handle potential issues, such as event loss, duplicate events, and out-of-order delivery. 

ALM has connection timeout configured to 10 seconds and socket timeout configured to 5 seconds. The expectation is that the client acknowledges the message as soon as it receives them. This is to ensure that the client doesn't lag while processing messages. In case there is some downstream processing which is time consuming, the client should still acknowledge the event instantly and then handle the downstream processing at their end.

#### Data Retention

Events are kept for 7 days. If they aren't processed within this time, they are lost permanently. If recovery happens on the last day and more time is needed, the system won't extend the retention period.
If events are produced faster than they are consumed, some events may be lost. Although this is uncommon, subscribers should monitor to prevent it from becoming a long-term issue.

#### Webhooks disable

When a subscriber fails to respond to webhook events, the ALM system retries webhooks using exponential backoff to avoid overwhelming the subscriber.

The retry process starts with an initial interval of 5 seconds. If the subscriber doesn't respond, the wait time doubles to 10, 20, 40, and 80 seconds, eventually increasing to a maximum of 5 minutes. Once it reaches 5 minutes, the system will continue to retry every 5 minutes until the 7-day retention period is over. If the subscriber still doesn't respond during this entire period, the webhook will be automatically disabled. A reminder email will be sent to the subscriber at regular intervals.

#### Duplicate Events

If a subscriber takes more than 5 seconds to respond after processing an event, the system might try to process the same event again. It is recommended to use event IDs to keep track of which events have already been processed. Also, if the webhook crashes after sending the event but before saving that it was processed, the same group of events might be retried. It is recommended to use batch IDs or individual event IDs to recognize and ignore any duplicates.

#### Out-of-Order Events

ALM tries to keep events in the correct order, but sometimes events can be delivered out of order, especially between real-time and non-real-time events.

If an admin enrolls multiple learners in a course at once, the enrollment events are marked as non-real-time. However, if a learner finishes the course quickly, that completion event is marked as real-time and might be delivered before the enrollment events.

#### Recommendation for fault tolerance

To prevent these faults, subscribers should actively monitor webhook events and set up alerts for issues like missed events, duplicate deliveries, or out-of-order sequences.

## Specific guidelines for Webhook events

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


## Sample payloads for the events

+++CI_STATS

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "01234567-0458-4450-b5dd-6bc1edr4560",
      "eventName": "CI_STATS",
      "timestamp": 1725604147,
      "eventInfo": "1725604145-LoSt",
      "data": {
        "loInstanceId": "course:1234567_123456775",
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
      "eventId": "29123ec1-4576-4ec5-a057-3a6dr45t9d6",
      "eventName": "COURSE_ENROLLMENT",
      "timestamp": 1725524713,
      "eventInfo": "1725524713000-040366-10488-0",
      "data": {
        "userId": 1234567,
        "loId": "course:1234567",
        "loInstanceId": "course:1234567_1234567",
        "loType": "course",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": 1725524713
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
      "eventId": "29572ec1-4576-4ec5-a057-3wsd43r59d6",
      "eventName": "COURSE_ENROLLMENT_BATCH",
      "timestamp": 1725524713,
      "eventInfo": "1725524713000-040366-10488-0",
      "data": {
        "userId": 1234567,
        "loId": "course:1234567",
        "loInstanceId": "course:12345678_123456788",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": 1725524713
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
      "eventId": "c1a3168c-6c98-4ed3-b0b0-ba3da5087c1c",
      "eventName": "COURSE_COMPLETED",
      "timestamp": 1725523823,
      "eventInfo": "1725523823000-040363-12018-0",
      "data": {
        "userId": 12345678,
        "loId": "course:12345671",
        "loInstanceId": "course:1234567_12345674",
        "loType": "course",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": 1725523818,
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
      "eventId": "c1a3168c-6c98-4ed3-b0b0-ba3da5087c1c",
      "eventName": "COURSE_COMPLETED_BATCH",
      "timestamp": 1725523823,
      "eventInfo": "1725523823000-040363-12018-0",
      "data": {
        "userId": 112345678,
        "loId": "course:12345678",
        "loInstanceId": "course:1234567_12345678",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": 1725523818,
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
      "eventId": "96ed0791-338f-4c4c-83bc-9fwfr4564965",
      "eventName": "LEARNING_PATH_ENROLLMENT",
      "timestamp": 1725604249,
      "eventInfo": "1725604248000-040653-71396-0",
      "data": {
        "userId": 11234567,
        "loId": "learningProgram:123456",
        "loInstanceId": "learningProgram:12345_134567",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": 1725604248
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
      "eventId": "96edft791-338f-4c4c-83bc-9f7erf94965",
      "eventName": "LEARNING_PATH_ENROLLMENT",
      "timestamp": 1725604249,
      "eventInfo": "1725604248000-040653-71396-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:12347",
        "loInstanceId": "learningProgram:12345_12345",
        "loType": "learningProgram",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": 1725604248
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
      "eventId": "e207104e-d554-4027-944b-08fty6fdddf",
      "eventName": "LEARNING_PATH_COMPLETED",
      "timestamp": 1725604392,
      "eventInfo": "1725604391000-040653-314618-0",
      "data": {
        "userId": 11080928,
        "loId": "learningProgram:12345",
        "loInstanceId": "learningProgram:12345_95662",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": 1725604380,
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
      "eventId": "e207104e-d554-4027-944b-086debefdddf",
      "eventName": "LEARNING_PATH_COMPLETED",
      "timestamp": 1725604392,
      "eventInfo": "1725604391000-040653-314618-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:12345",
        "loInstanceId": "learningProgram:12345_95662",
        "loType": "learningProgram",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": 1725604380,
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
      "eventId": "8bdfr76-148e-4128-80e9-b89123456755",
      "eventName": "CERTIFICATION_ENROLLMENT",
      "timestamp": 1725604672,
      "eventInfo": "1725604672000-040654-559128-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:1234567",
        "loInstanceId": "certification:123456_160299",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": 1725604672
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
      "eventId": "8b2ee776-148e-4128-80e9-12345678",
      "eventName": "CERTIFICATION_ENROLLMENT_BATCH",
      "timestamp": 1725604672,
      "eventInfo": "1725604672000-040654-559128-0",
      "data": {
        "userId": 123456788,
        "loId": "certification:1234567",
        "loInstanceId": "certification:12345678_160299",
        "loType": "certification",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": 1725604672
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
      "eventId": "b8b63bf8-7521-4bc0-bc51-7f951ff63ea9",
      "eventName": "CERTIFICATION_COMPLETED",
      "timestamp": 1725604769,
      "eventInfo": "1725604768000-040654-756257-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:1245678",
        "loInstanceId": "certification:1234567_160299",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": 1725604740
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
      "eventId": "b8b63bf8-7521-4bc0-bc51-7f951ff63ea9",
      "eventName": "CERTIFICATION_COMPLETED_BATCH",
      "timestamp": 1725604769,
      "eventInfo": "1725604768000-040654-756257-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:134567",
        "loInstanceId": "certification:1234567_160299",
        "loType": "certification",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": 1725604740
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
      "eventId": "dd04d3a4-c3df-44fa-a1cf-7edd6e3d2075",
      "eventName": "LEARNER_PROGRESS",
      "timestamp": 1725604552,
      "eventInfo": "1725604551000-297002-5823-0",
      "data": {
        "loId": "course:7542090",
        "loType": "course",
        "userId": 12345678,
        "loInstanceId": "course:1234567_11234567",
        "dateStarted": 1725604380,
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
      "eventId": "f3417817-8cb8-40ea-a441-813bec1c7724",
      "eventName": "COURSE_UNENROLLMENT",
      "timestamp": 1725515824,
      "eventInfo": "1725506253000-040298-24078-0",
      "data": {
        "userId": 12345671,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14450088",
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
      "eventId": "f3417817-8cb8-40ea-a441-8123e45724",
      "eventName": "COURSE_UNENROLLMENT_BATCH",
      "timestamp": 1725515824,
      "eventInfo": "1725506253000-040298-24078-0",
      "data": {
        "userId": 123456781,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14450088",
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
      "eventId": "8e5df878-1dfd-47ac-9bfe-7d123456d1",
      "eventName": "LEARNING_PATH_UNENROLLMENT",
      "timestamp": 1725516573,
      "eventInfo": "1725506667000-040299-28209-0",
      "data": {
        "userId": 12345678,
        "loId": "learning_program:1234567",
        "loInstanceId": "learning_program:1234567_109139",
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
      "eventId": "8e5df878-1dfd-47ac-9bfe-7d4952e3edd1",
      "eventName": "LEARNING_PATH_UNENROLLMENT",
      "timestamp": 1725516573,
      "eventInfo": "1725506667000-040299-28209-0",
      "data": {
        "userId": 1234567,
        "loId": "learning_program:1234567",
        "loInstanceId": "learning_program:1234567_109139",
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
      "eventId": "7902766b-54d8-472d-b933-7e89d1b75ef8",
      "eventName": "CERTIFICATION_UNENROLLMENT",
      "timestamp": 1725517341,
      "eventInfo": "1725507900000-040304-1065-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:1234567",
        "loInstanceId": "certification:12345678_162078",
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
      "eventId": "7902766b-54d8-472d-b933-7e89d1b75ef8",
      "eventName": "CERTIFICATION_UNENROLLMENT_BATCH",
      "timestamp": 1725517341,
      "eventInfo": "1725507900000-040304-1065-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:1234567",
        "loInstanceId": "certification:1234567_162078",
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
      "eventId": "1712349f-26ec-453c-b56a-cdf18a841948",
      "eventName": "LEARNING_OBJECT_DRAFT",
      "timestamp": 1725519188,
      "eventInfo": "1725519188000-040344-48604-0",
      "data": {
        "loId": "course:12345671",
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
      "eventId": "023456-5517-4c09-9cde-d953cdd8582c",
      "eventName": "LEARNING_OBJECT_DELETION",
      "timestamp": 1725605296,
      "eventInfo": "1234567800-040656-662792-0",
      "data": {
        "loId": "course:1234567",
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
  "accountId": 1234,
  "events": [
    {
      "eventId": "22345668-af3e-4dd3-a515-ce19d7234873",
      "eventName": "LEARNING_OBJECT_MODIFICATION_BATCH",
      "timestamp": 1725523081,
      "eventInfo": "123456000-039736-54153-0",
      "data": {
        "loId": "learningProgram:1234567",
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
  "accountId": 1234,
  "events": [
    {
      "eventId": "2234567068-af3e-4dd3-a515-ce19d7234873",
      "eventName": "LEARNING_OBJECT_MODIFICATION_BATCH",
      "timestamp": 1725523081,
      "eventInfo": "123456700-039736-54153-0",
      "data": {
        "loId": "learningProgram:1234567",
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
      "eventId": "b131da98-ab8d-43e9-b671-e79131cd69dc",
      "eventName": "LEARNING_OBJECT_INSTANCE_MODIFICATION",
      "timestamp": 1725603298,
      "eventInfo": "1723456000-040649-741781-0",
      "data": {
        "loInstanceId": "course:12345678_14453691",
        "loId": "course:12345678",
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
      "eventId": "b23458-ab8d-43e9-b671-e79131cd69dc",
      "eventName": "LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH",
      "timestamp": 1725603298,
      "eventInfo": "112345000-040649-741781-0",
      "data": {
        "loInstanceId": "course:12345678_14453691",
        "loId": "course:1234568",
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
      "eventId": "1234560-d73a-457b-83f3-666ba9654edb",
      "eventName": "LEARNING_OBJECT_INSTANCE_DELETION",
      "timestamp": 1725605491,
      "eventInfo": "17223456700-040657-236307-0",
      "data": {
        "loInstanceId": "course:1234567_14453849",
        "loId": "course:1234567",
        "loType": "course"

      }
    }
  ]
}
```

+++
