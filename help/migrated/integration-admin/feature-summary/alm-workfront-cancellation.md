---
description: Learn how to cancel and reactivate ILT and VILT sessions in Adobe Learning Manager by setting the session state in Workfront migration data
jcr-language: en_us
title: ALM Workfront cancellation
exl-id: 01500cf2-6e39-4ac3-84e2-823a5215f6cf
---

# ALM-Workfront cancellation/update trigger

## Overview

Adobe Learning Manager (Learning Manager) can now cancel and reactivate instructor-led and virtual instructor-led (ILT/VILT) sessions based on changes made in Workfront. If your organization schedules sessions in Workfront and brings them into Learning Manager through the Workfront-to-Learning Manager migration, you can set the state of each session to Active or Cancelled in the migration data. Learning Manager then applies the change as if an admin had cancelled the session in the user interface.

Cancelling a session through migration behaves the same as cancelling it from the Learning Manager user interface. The one deliberate difference is reactivation, which is described in [Reactivate a cancelled session](#reactivate-a-cancelled-session).

### The requirement

Updates to a session, such as date and time, instructor, location or link, and capacity, already flow from Workfront to Learning Manager through migration. Cancellations did not. When a session was cancelled in Workfront, Learning Manager had no way to know, which caused the following problems:

* Learners stayed enrolled in a session that no longer ran, leading to confusion and no-shows.
* Admins had to repeat the cancellation manually in Learning Manager.
* Workfront and Learning Manager drifted out of sync, which undermined Workfront as the source of truth for scheduling.

### How it works

1. A delivery manager cancels a session in Workfront.
1. The session row in the migration data includes the new session state column, set to Cancelled.
1. A systems administrator runs the migration through the API.
1. Learning Manager marks the matching session as cancelled and sends the same notifications that a cancellation from the user interface sends.

>[!NOTE]
>
>This feature extends the existing migration process rather than adding a second, real-time integration path.

### End-to-end workflow

The following diagram shows how a session row moves from Workfront to Learning Manager.

![Flowchart showing a Workfront session row moving through migration to create, update, or cancel the matching session](assets/alm-workfront-cancellation-visual1.png "Workfront-to-Learning Manager session state workflow")

## Use cases

The following roles are involved in a cancellation that starts in Workfront.

### Roles involved

| Role | Description |
|---|---|
| Delivery manager | Schedules and manages the training calendar in Workfront, including cancelling sessions. Delivery managers do not use the Learning Manager user interface. Migration is the only path by which their cancellation reaches Learning Manager. |
| Systems administrator | Runs the migration through the API. This role operates the Workfront-to-Learning Manager pipeline and is separate from the delivery manager and the Learning Manager admin. |
| Admin | Manages course and session data in the Learning Manager user interface. Admins no longer need to cancel sessions manually after being told about a change in Workfront. |
| Author | Owns the course and session content in the Learning Manager user interface. Authors receive a cancellation notification for sessions they authored, whether the cancellation starts in the user interface or in migration. |
| Instructor | Is assigned to sessions. Instructors see the correct session state and are notified when a session they instruct is cancelled. |
| Learner | Is enrolled in a session through Learning Manager. Learners are told promptly when their session is cancelled. |

### Common scenarios

| Scenario | What you do | Result |
|---|---|---|
| A session is cancelled in Workfront, for example because a resource is unavailable or a vendor has an issue. | Set the session state to Cancelled in the migration row for the session and run the migration. | The session is cancelled in Learning Manager and the affected people are notified. |
| The details of an active session change in Workfront. | Include the changed values in the migration row. Set the session state to Active, or leave it blank. | The session is updated. Learning Manager sends a session-updated email. |
| A cancelled session is reinstated in Workfront. | Set the session state to Active in the migration row and run the migration. | The session becomes active and can be modified and cancelled again. |
| Updated details are sent for a cancelled session without setting the state to Active. | No action is required from the user. | The session stays cancelled, the row returns a validation error, and no details are changed. |
| A migration row does not include a session state. | Leave the column blank or omit it. | The current state of the session in Learning Manager is left unchanged. |

## Key features

* **Session state column.** The migration schema includes an optional session state field that supports Active and Cancelled.
* **Cancellation through migration.** When a row has the state Cancelled, the matching session in Learning Manager is cancelled. Learning Manager uses the same matching key that migration already uses to create and update sessions.
* **No manual work in Learning Manager.** Admins do not need to cancel the session again in the user interface.
* **Same behavior as cancelling in the user interface.** Enrollment handling, learner-facing visibility, reporting, the audit trail, and notifications match a cancellation from the user interface.
* **Reactivation.** You can set a cancelled session back to Active by setting the state explicitly in the migration data.
* **Protection for cancelled sessions.** Migration does not change the details of a cancelled session unless the row explicitly sets the state to Active.
* **Backward compatibility.** The state column is optional, so existing migration files continue to work without changes.
* **Complete notifications.** Learners, instructors, admins, authors, and managers receive the same cancellation emails as they do for a cancellation from the user interface.

## Session states

Every session in Learning Manager is in one of two states.

| State | Meaning |
|---|---|
| Active | The default state. The session is live and learners can enroll in and attend it. |
| Cancelled | The session is cancelled. Enrolled learners, admins, authors, and managers are notified, as they are for a cancellation from the user interface. |

### State transition rules for migration

The following table shows what happens when a migration row is processed. Learning Manager identifies the session by using the matching key that migration already uses for create and update.

| Current state in Learning Manager | Session state in the migration row | Result |
|---|---|---|
| Session does not exist | Active or blank | The session is created as active. |
| Active | Active or blank | The session stays active. Changed values in the row are applied. |
| Active | Cancelled | The session is cancelled and notifications are sent. |
| Cancelled | Cancelled | The row is skipped. A cancelled session cannot be cancelled again. |
| Cancelled | Active | The session is reactivated. Changed values in the row are applied. |
| Cancelled | Blank | The session stays cancelled. If the row has changed values, a validation error is returned and no details are changed. |

### Rules for the session state column

* The column is optional on every row.
* If you leave the column blank or omit it for an existing session, the session keeps its current state. Learning Manager does not infer a state change from an empty value, whatever other fields the row contains.
* If you leave the column blank for a new session, the session is created as active.
* A session becomes active again through migration only when the column explicitly says Active.

Use one of the following values in the session state column:

* `state = Active`
* `state = Cancelled`

>[!NOTE]
>
>The exact column header and the accepted values are being confirmed. Use the names that your migration documentation specifies.

## Updates to cancelled sessions

You cannot update the details of a cancelled session through migration. If a row for a cancelled session contains changed values and does not set the state to Active, Learning Manager returns a validation error, leaves the session cancelled, and neither applies nor stores the changed details. Learning Manager does not send a session-updated email for the attempt.

### Cancel a session by using migration

Use this procedure when a session has been cancelled in Workfront and you want Learning Manager to reflect the change.

**Before you begin**

* The session already exists in Learning Manager, imported through the Workfront-to-Learning Manager migration.
* You know the matching key that your migration uses to identify the session.

1. In Workfront, cancel the session.
1. In the session CSV file that you use for migration, locate the row for the session. Make sure the matching key is the same as the one used when the session was created.
1. In the session state column, enter Cancelled.
1. Run the migration through the API.
1. In Learning Manager, verify that the session is cancelled.

Learning Manager marks the session as cancelled, handles the enrolled learners as it does for a cancellation from the user interface, and sends the cancellation notifications. No action is required in the Learning Manager user interface.

>[!NOTE]
>
>If the session is already cancelled, Learning Manager skips the row.

### Update an active session

For an active session, the existing migration update behavior remains available. Set the session state to Active or leave it blank, and include the changed values in the row. You can continue to update details such as date and time, instructor, location or link, and capacity through the migration pipeline.

Active keeps the existing create and update behavior. Cancelled invokes the same session cancellation that the user interface provides, through the session CSV migration.

### Reactivate a cancelled session

A cancelled session returns to the active state only when you set the state to Active explicitly. You can reactivate a session through migration or by editing it in the user interface.

1. In the session CSV file, locate the row for the cancelled session. Make sure the matching key is the same as the one used when the session was created.
1. In the session state column, enter Active.
1. (Optional) Update any other values in the row that you want to change, such as date and time, instructor, location or link, or capacity.
1. Run the migration through the API.

The session becomes active and its details can be modified. A session that is reactivated through migration or through the user interface can be cancelled again through either path.

>[!IMPORTANT]
>
>If you send updated session details for a cancelled session without setting the state to Active, the session stays cancelled and the row returns a validation error.

## Notifications

Learning Manager sends every email that it sends for a cancellation from the user interface when a session is cancelled through migration. Recipient coverage is not reduced, and the content uses the same template, so recipients cannot tell how the cancellation was started.

The recipients, as applicable to the session, are as follows.

| Recipient | Notification |
|---|---|
| Learners | Learners enrolled in the session are told that the session is cancelled. |
| Instructors | Instructors assigned to the session are notified of the cancellation. |
| Admins | Admins receive the cancellation notification. |
| Authors | Authors of the course and session receive the cancellation notification. |
| Managers | Managers receive the cancellation notification. |

### Emails for cancelled sessions

A cancelled session does not generate session-updated emails. While a session is cancelled, changes to date and time, instructor, location or link, and capacity do not trigger the session-updated email. Only cancellation and reactivation notifications apply to a cancelled session.

## Considerations and limitations

* Because the feature uses migration, a cancellation made in Workfront reaches Learning Manager when the migration runs. Webhook-based, real-time cancellation is not supported.
* Migration cannot change the details of a cancelled session. To change them, first set the state to Active.
* The session state column is optional. Rows that omit it never change the state of a session.
* The feature extends the existing migration integration. It does not add a second, real-time integration path.
* The migration schedule or trigger depends on the tooling that your organization uses to run it. This guide does not define a fixed schedule.
* Delivery managers work only in Workfront. They do not need access to the Learning Manager user interface to cancel a session.

## Success measures

| Measure | Target |
|---|---|
| Cancellations that admins or customer support replicate manually | Reduced to 0 within one full release cycle after launch. |
| Workfront cancellations reflected in Learning Manager | 100% of cancellation events processed within one migration cycle. |
| Notification parity between user interface and migration cancellations | 0 gaps in recipient coverage (admins, authors, managers, and learners) and 0 unnecessary update emails for cancelled sessions. |

## Troubleshooting

| Issue | Expected or possible cause | Action |
|---|---|---|
| A session remains active after it is cancelled in Workfront. | Migration has not processed the cancellation yet, or the migration row did not carry the explicit Cancelled state. | Verify the migration input and the processing result. |
| The details of a cancelled session do not change. | Expected behavior while the session stays cancelled. | Reactivate the session by setting the state to Active, and then apply the changes. |
| No session-updated email is sent for a cancelled session. | Expected behavior. Ordinary update emails are suppressed for cancelled sessions. | Use the cancellation and reactivation lifecycle instead of a details-only update. |
| A cancellation row is skipped. | The matching session in Learning Manager is already cancelled. | No further cancellation is needed. Reactivate the session first if it must return to active. |
| A recipient received the same cancellation email as for a user interface cancellation. | Expected behavior. Migration cancellation is designed to match the user interface. | No action is required. |
| The behavior is unclear when the session state is blank. | The source requirements conflict on blank-state handling. | Confirm the release behavior before you rely on a blank state for any transition. |
