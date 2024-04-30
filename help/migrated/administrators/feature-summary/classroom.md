---
jcr-language: en_us
title: Add classroom locations
description: Administrators can now set up a library of classroom locations. For each Classroom Location, the administrators can set the metadata that includes Location Name, Seat Limit as well as additional information such as the Location URL. Authors and Administrators can then use these pre-configured classroom locations for setting up instructor-led training events (classroom modules).
contentowner: saghosh
exl-id: 51a1e38f-d4e2-4c19-bbf7-6696505c0dfd
---
# Classroom

## Overview

Administrators can now set up a library of classroom locations. For each Classroom Location, the administrators can set the metadata that includes Location Name, Seat Limit as well as additional information such as the Location URL. Authors and Administrators can then use these pre-configured classroom locations for setting up instructor-led training events (classroom modules).

You can use the following two ways to add a classroom location.

## Add classroom using the UI

You can add a classroom location by using the UI:

1. In the Admin app (the UI for administrator roles), click **[!UICONTROL Settings]** > **[!UICONTROL Classroom Locations]**.  

1. Click **[!UICONTROL Add]** > **[!UICONTROL New Location]**.  

1. In the **[!UICONTROL Classroom Location]** dialog box, enter the following details:

   * Type the **[!UICONTROL Location Name]**. Use a unique name. Otherwise, Learning Manager displays an error message.
   * Type the location description in the **[!UICONTROL Location Information]** field. This field is optional.
   * Type the **[!UICONTROL Location URL]**. Learner can see this information in the classroom details. The URL can also be a maps location URL, if required. This is an optional field.
   * Type and select the **[!UICONTROL Location Region]**. This field i optional.
   * Type the number of available seats in the **[!UICONTROL Seat Limit]** field. This indicates the seat capacity of the classroom. This value can be changed when creating the actual instructor-led training event.

   ![](assets/add-classroom-location.png)

   *Add a classroom location*

After adding the location, the **[!UICONTROL Settings]** > **[!UICONTROL Classroom Locations]** page lists the meeting rooms:

![](assets/list-meeting-rooms.png)

*View all meeting rooms*

The list has the following fields:

**[!UICONTROL Location Name]** - Name of the classroom location.

**[!UICONTROL Future Sessions]** - Number of events that will occur in the corresponding location. Click the number to view the details in a dialog box.

![](assets/sessions-list.png)

*View future sessions*

The dialog box displays the details of each session including the name of the session, name of the training that includes the session, and session schedule. The displayed time aligns with the system time zone of the learner.

The **[!UICONTROL Future Sessions]** field displays **zero** when the classroom is not used for any session or when the classroom is associated with past sessions.

**[!UICONTROL Seat Limit]** - Displays the seat capacity of the classroom.

**Location URL** - URL that you provided when creating the classroom location.

**Location Information** - The classroom information that you provided when creating the classroom.

### Edit the classroom locations

To edit the classroom locations, follow the below steps:

1. In the Admin app (the UI for administrator roles), select **[!UICONTROL Settings]** > **[!UICONTROL Classroom Locations]**.  

1. Hover over the desired classroom location you want to edit. 

1. Select **[!UICONTROL Edit Classroom Location]** icon. 

1. Modify the classroom location and select **[!UICONTROL Save]**. 

## Add classroom using CSV

Alternatively, you can add one or more classroom locations by importing a CSV that contains the classroom information.

In **[!UICONTROL Admin app]** > **[!UICONTROL Settings]** > **[!UICONTROL Classroom Locations]** > **[!UICONTROL Add]**, click the **[!UICONTROL Bulk import locations]** button. Browse to the location containing the CSV file and select the file.

The CSV file uses these fields to store details about one or more classroom locations:

* name
* info
* url
* region
* seatLimit

You can customize the headers.

The CSV file must mandatorily contain all columns in the same order as specified here.

After the system imports the CSV file, the locations are added in the library.

## Search for classrooms

To search for classrooms, select the virtual classroom course, then go to **[!UICONTROL Instances]** > **[!UICONTROL Sessions]**. An Author or Administrator can start typing the location name to see the relevant results that start appearing. They can then select a location from the displayed results. If no location is displayed in the type ahead results, the user can still add the new classroom location name. Note that this location name created using the session creation workflow is not added to the location library created by the Administrator.

When a classroom is added, the learning platform also indicates if the classroom is already booked for the mentioned time-period. It even provides alternate time slots as suggestions. Therefore, this enables the Author to adjust the meeting time if he decides to use the same classroom location.

![](assets/classroom-search.png)

*Search for classrooms*

## Administrator

As an admin, you can manage the instructors and the course instances.

### Setting up instructors:

In the Admin app, under **[!UICONTROL Settings]** > **[!UICONTROL General]**, administrators can find the **[!UICONTROL Instructor Management]** option. This feature ensures that only pre-approved users assigned as instructors can be added to conduct sessions.

To assign an instructor, follow these steps:

1. Go to the **[!UICONTROL Getting Started]** page, and select **[!UICONTROL Users]** on the left pane.

1. Select the user you want.

1. Assign the user the instructor role by selecting **[!UICONTROL Actions]** > **[!UICONTROL Assign Role]**.

### Cancelling Sessions:

On the **[!UICONTROL Course Instance]** page, administrators can cancel one or more sessions. When sessions are cancelled, the system removes all session details but retains the seat limit.

Additionally, administrators can:

* **[!UICONTROL View Enrollment]**: Get information on enrolled and waitlisted learners for each session.
* **[!UICONTROL Unenroll Learners]**: Remove learners from a course with cancelled sessions without changing their enrollment status.
* **[!UICONTROL Attendance Management]**: Mark attendance for sessions, even if the sessions get cancelled.
* **[!UICONTROL Course Completion]**: Administrators can mark a course as complete even if sessions have been cancelled.
* **[!UICONTROL Rescheduling]**: Schedule cancelled sessions for later dates, and add an instructor during the rescheduling.

Note that after cancellation, learners stay enrolled in the training instance. Their enrollment status—like confirmed enrollment, waitlisted, and awaiting manager approval—stays unchanged. This is helpful because the administrator can set up and reschedule the cancelled session in the future.

## Author

If the administrator selects the **[!UICONTROL Instructor Management]** option, an author can only search for and add the users with instructor role to the classroom sessions, virtual classroom sessions, checklists, and the file submission modules.

In addition, an author can:

* Add and remove instructors from the existing sessions.
* Add instructors to the existing sessions that already have one or more instructors.

Therefore, after an administrator enables the **[!UICONTROL Instructor Management]** option, only the users with instructor role can be added as an instructor.

>[!NOTE]
>
>This is not applicable when you migrate sessions using the sessions CSV file. In this case, a user who does not have the instructor role can be added as an instructor.

On the **[!UICONTROL Course Instance]** page, an author can cancel one or more sessions. When sessions are cancelled, the system removes all session details but retains the seat limit.

Therefore, an author can use the **[!UICONTROL Cancel Session]** links to cancel one or more classroom sessions or virtual classroom sessions available in the same or different course instances.

## Confine to pre-determined list of instructors

Presently, the users can add any registered user as an instructor when creating a classroom or virtual-classroom session. This functionality remains unchanged in this release.

However, Administrators now have an additional option to further control who gets assigned as an instructor on the learning platform. This prevents any accidental addition of a new Instructor when creating a session.

## Cancel existing session

An Author or Administrator can cancel a session and reschedule it, if required.

When a user cancels a session, the system sends a meeting cancellation email to all the enrolled learners and instructors. The email includes the updated session details.

There is a template called **[!UICONTROL Session Cancellation]** that helps in cancelling a session.

On the **[!UICONTROL Course Instance]** page, every session listed under a course instance includes an option to cancel the session.

![](assets/cancel-session.png)

*Cancel an existing session*

When you click the **[!UICONTROL Cancel Session]** link, a warning message appears.

On the warning message dialog box, if you click **[!UICONTROL Proceed]**, the system cancels the session.

The system also clears the following details after cancelling a session:

* Start date of the session
* End date of the session
* Start time of the session
* End time of the session
* Instructors added to the session
* Virtual classroom URL
* Location/venue added to the session
* Waitlist limit added by the instructor
