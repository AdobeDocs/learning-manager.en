---
description: Read this article to know how to manage the attendees, send course related emails and reminders for your sessions.
jcr-language: en_us
title: Managing learners for your session
contentowner: shhivkum
exl-id: 2f4f8589-2350-4683-a141-809084d6309a
---
# Managing learners for your session

Read this article to know how to manage the attendees, send course related emails and reminders for your sessions.

## See sessions or modules with pending reviews {#pending}

As an instructor, you can see the sessions or modules with pending reviews. 

On the Sessions/Modules page, you can see a column **Reviews Pending** that shows the number of pending reviews for the corresponding session/activity.

## Manage waitlist for your session {#managewaitlistforyoursession}

As the Learners register for your module, you can see the latest status of the enrollment and waitlist from the Waitlist page.

1. From the Instructor App, select Upcoming Sessions > Waitlist in the left navigation pane.

   You can view the Seat Limit, number of seats that are currently filled, and the number of seats vacant. A table also lists the Learners who have been waitlisted. This is blank if there are no waitlist queues.

   ![](assets/waitlist.png)
   *View waitlisted learners*

1. From the Waitlist table, select the Learner or Learners whom you want to confirm.
1. Select Actions > Confirm Learners.

   The learners whom you have confirmed, are added to the Confirmed Learners list.

Instructors have the capability to unenroll learners from sessions. This also unenrolls them from corresponding learnings. Select **[!UICONTROL Waitlist]** tab. Select the learners to unenroll using the checkbox. To unenroll, select **[!UICONTROL Actions]** > **[!UICONTROL Unenroll learners]**.

![](assets/unenroll-learners.png)
*Unenroll the learners*

### Waitlist report

Adobe Learning Manager's new **[!UICONTROL Waitlist Report]** allow instructors to download waitlisted learners list for all instances of a course. Instructors can access this report from the **[!UICONTROL Waitlist]** section on the **[!UICONTROL Session Overview]** page.

Following the columns available in the Waitlist report:

* Course Name
* Instance Name
* Instance ID
* Instance Status
* User Name
* Email
* User Unique ID
* Date Enrolled (UTC TimeZone)
* Status
* Waitlist Number
* Waitlist Limit
* Seat Limit

To download the report from Instructor section:

1. Log in as **[!UICONTROL Instructor]**.
2. Select any session from the home page.
3. Select the **[!UICONTROL Waitlist]** option in the **[!UICONTROL Session Overview]** page.
4. Select **[!UICONTROL Actions]** > **[!UICONTROL Export Report]** to download the **[!UICONTROL Waitlist]** report.

## Mark attendance for your session {#markattendanceforyoursession}

You can view the number of confirmed Learners who are attending the session, their names, attendance status of the Learners, and other details from the Learners page.

1. In the left navigation pane, click Upcoming Sessions > Learners.
1. Select the Learner or Learners from the list of Attendees and do one of the following:

   * To mark attendance, click Actions > Mark Attendance. Once the status has been marked as Attended, you cannot change the status.
   * To mark the non-attendance, click Actions > Not Attended.
   * To delete a learner due to cancellation or other reasons, click Actions > Delete Learners.

   A Learner cannot complete a module until the Attendance status reads Attended.

   ![](assets/markattendance.png)
   *Mark learner attendance*

### Download QR codes for learner enrollment and attendance

Instructors can download QR codes for their assigned sessions to allow learners to enroll in a course instance and mark attendance or completion by scanning the QR code.

This enables instructors to manage session participation independently, without requiring administrator assistance.

The following steps are suitable for both:

- Physical classroom sessions
- Online classroom sessions

For a physical classroom session, as an Instructor, you have to generate the right QR code and paste it in the classroom (or pass it around) where the learners are attending the session so that they can scan the QR code and mark their enrollment or attendance or both depending on the QR code.

For an online classroom session, as an Instructor, you can send the generated QR code through mail, a messaging system or any other means so that the learners can scan the QR code and mark their enrollment or attendance or both depending on the QR code.


#### Download QR codes for a session

1. Sign in to Adobe Learning Manager with the **Instructor** role.
2. Go to the **Instructor dashboard**.
3. Open the relevant **course instance**.
4. Select the **Sessions** tab.
5. Choose a session assigned to you.
6. Select **Session QR Code**.
![](assets/instructor-QR-code.png)

You can download the following QR codes:

* **Enrollment QR code** – allows learners to enroll in the course instance
* **Attendance QR code** – marks attendance for the session
* **Enrollment + Attendance QR code** – enrolls learners and marks attendance in a single scan

The QR code is downloaded as a PDF and can be shared digitally or displayed during the session.

#### What happens when learners scan the QR code

* Learners scan the QR code using a mobile device.
* Adobe Learning Manager validates the learner and session.
* Based on the QR code type:
  * Learners are enrolled in the course instance, or
  * Attendance and completion are recorded for the session

All updates are reflected automatically in learner records, transcripts, and reports.

#### Notes

* QR codes are available only to instructors assigned to the session.
* Enrollment, attendance, and completion rules configured for the course and session continue to apply.
* Existing learner progress and reporting workflows remain unchanged.

#### Use cases

* Organizations running large volumes of onsite sessions (for example, product training for professionals) can enable instructors to print session-specific QR codes that enroll and mark attendance with one scan.

* In retail, manufacturing, and healthcare training, where learners often join sessions directly from the floor or without pre-enrollment, an "Enroll + Attendance" QR code can be placed at the door. This allows learners to self-serve their enrollment and attendance via their phones.

* Training events for partners or customers allow the on-site trainer to easily adapt to changes in the room, additional sessions, or extra attendees without needing to consult the administrator for new QR codes.

### Calendar invites

* When a learner or instructor is enrolled in a classroom or virtual classroom session, Learning Manager sends a calendar invite (ICS file).
* The calendar invite includes:
  * Session date and time
  * Session details
  * **Direct session join link** in the calendar description

Participants can open the calendar event and join the session directly from their calendar.

#### Joining a session from Gmail

1. Open **Google Calendar**.
2. Select the session event.
3. In the event details, click the **session join link**.
4. The session opens directly in Adobe Learning Manager or the configured virtual classroom tool.

You do not need to open the original email to access the session link.

#### Joining a session from other calendar clients

The session link is included in the calendar event body and is accessible from:

* Microsoft Outlook
* Apple Calendar
* Other calendar applications that support ICS files

#### Notes

* Calendar invites are generated automatically by Learning Manager.
* Time zone information in the calendar invite adjusts based on the learner's selected time zone.
* This enhancement applies to newly generated calendar invites.
* No additional configuration is required by administrators or instructors.


## Mark success for learners

Instructors can mark each learner's success status as Pass or Fail directly from the Learners page. This feature allows instructors to accurately record the outcome of classroom or virtual classroom sessions based on learner performance.

To mark the success for learners:

1. Log in to Adobe Learning Manager as an instructor.
2. Select **[!UICONTROL Upcoming Sessions]** in the left navigation pane. 
3. Select **[!UICONTROL Learners]**.
4. Select the learners and then select **[!UICONTROL Actions]**. 
5. Select any of the options from the following to mark the success for the selected learners:

      * **[!UICONTROL Mark Attended and Pass]**: Learners marked as Pass have successfully completed the module.
      * **[!UICONTROL Mark Attended and Fail]**: Learners marked as Fail have completed the module but did not pass.

      ![The Actions dropdown menu highlighting "Mark Attended and Pass" and "Mark Attended and Fail" options for instructors to set each learner's success status](/help/migrated/instructors/feature-summary/assets/mark-success-instructor.png)
      _Learners page showing the Actions menu with Mark Attended and Pass and Mark Attended and Fail options highlighted for recording learner outcomes_
      
6. Select **[!UICONTROL Yes]** in the confirmation prompt.

## Send emails to learners {#sendemailstolearners}

You can send emails to specific or all attendees for your session. The Send Email feature is very useful if you want to confirm the attendance of learners, or if you want to send out communication regarding the session. You can also use the Send Email to All option to email the assignment and session material, or send out general communication to all the learners.

To send emails to learners, from the Learners page in the Instructor app, do one of the following:

* To send emails to specific attendees, select the attendee, and click Actions > Send Email to Selected.
* To send emails to all the attendees to send a course material or an assignment, click Actions > Send Email to All.

## Capture invitation responses

Instructors can capture learners' invitation responses only when the **[!UICONTROL Invite Reply]** option is enabled by the ACAP administrator. To enable this feature, administrators need to contact the support team at [learningmanagersupport@adobe.com](mailto:learningmanagersupport@adobe.com).

Once done, you can view invitation responses in the **[!UICONTROL Learners]** section. Go to any session, select **[!UICONTROL Learners]**, and select the invitation response from the dropdown menu.

![](assets/invitation-status.png)

## Exporting learners list {#exportinglearnerslist}

As an instructor, you can easily mark the attendance for all your learners by exporting the attendee list as a pdf. To export the attendee list, from the Learner from the left pane. Click Actions > Export Learner List (PDF). 

After the attendee list is confirmed for your session, you can export the list as a PDF. This easy-to-print pdf displays the learners as a table. You can then mark the attendance or provide scores, and make or provide notes for the learner, all in the same PDF. 

Notice a QR code at the top right corner of this PDF. This functionality allows individual learners to scan the code using the Learning Manager mobile app for learners to mark their attendance. 

![](assets/exportpdf.png)
*Scan the QR code to mark attendence* 

## Approve or reject submissions {#approveorrejectsubmissions}

If leaners have uploaded documents like assignments, reports, or assessments for your session, you can view the documents in the Submissions page. You can use the materials for grading the learner, and either approve or reject the submission.

1. From the left pane, click either Upcoming Sessions or Past Sessions, based on the schedule of your session.
1. Click the Course for which you want to view the submissions.

   From the left pane, click Submissions.

1. You can view the submissions from learners for the session that you selected. Select the submission that you want to approve or reject, and click Approve or Reject.

   The status of the submission changes to Approved or Rejected, based on your action.

## Configure reminders for your session {#configureremindersforyoursession}

1. From the left pane, click Upcoming Sessions.
1. Click the course for which you want to set the reminder. From the left pane, click Reminders.
1. From the Select Reminder tile, click Set Reminder.

   ![](assets/setreminder.png)
   *Configure reminders for your session*

1. Do the following:

   * In the Reminder Settings dialog box, set the option on when to send the reminder to learners: Before deadline, On deadline, or After deadline.
   * In the days before deadline field, set the number of days prior to the deadline when you want to send the reminder to learners.
   * Set the recurrence for your reminder.

   ![](assets/remindersettings.png)
   *View reminder settings*

1. Do one of the following:

   * Click the tick mark to save the reminder.
   * Click the cross mark to cancel the reminder.

   An automated course reminder is sent to all the learners at the set date that you have indicated in your reminder settings.

   If you have already set reminders for your sessions, you can see them under the Existing Reminder tiles. Further, you can also add additional reminders to your existing reminders.

   To delete an existing reminder, click on the reminder. From the pop-up that appears, click the Delete icon (Trash icon) to delete the reminder.
