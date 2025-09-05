---
description: The Learner Transcripts in Adobe Learning Manager (ALM) allows administrators to monitor learner progress in courses, modules, learning paths, and certifications. It supports performance evaluations, compliance monitoring, audits, and external reporting. The report offers a complete summary of a learner's engagement and performance.
jcr-language: en_us
title: Learner Transcripts in Adobe Learning Manager
---

# Learner Transcripts in Adobe Learning Manager

## Overview

The Learner Transcripts in Adobe Learning Manager (ALM) allows administrators to track learner progress at a granular level across courses, modules, learning paths, and certifications. The transcript data helps performance reviews, compliance tracking, audits, and external reporting needs.

>[!NOTE]
>
>Learner Transcripts are available for download by administrators, custom administrators, managers, or learners.

In case of learners, they must launch their profile settings and then download their learning transcripts as an Excel file. This transcript, generated for an individual learner, details their personal learning journey. It includes the names of learning paths, courses, instances, and modules, along with key dates like enrollment, completion, and deadlines. It also tracks their progress through status, grades, quiz scores (including highest scores and maximums), and attempts taken. Additionally, it shows training IDs, durations, unenrollment dates, prices, and any submission comments. This report provides a comprehensive overview of a single learner's engagement and performance.

Organizations may use the Learner Transcripts to add the learning behavior data to an enterprise data warehouse, where one may want to combine learning data with other enterprise data to analyze correlations between learning behavior and other process data.

## Purpose and benefits

* Creates audit-ready records for regulatory requirements with timestamps and evidence of completion.
* Connects learning activities to employee development and skill acquisition. 
* Tracks certification status for roles requiring mandatory training. 
* Supports quantitative measurement of learning program effectiveness. 

## Use cases of Learner Transcripts

Learner Transcripts in Adobe Learning Manager tracks training, compliance, and skill development, enabling departments to verify completion and assess program effectiveness across the organization.  Here are a few use cases that Learner Transcripts addresses: 

* A financial services organization must provide evidence that all customer-facing employees completed mandatory compliance training before the regulatory deadline. 
* The IT department needs to assess current Java programming capabilities against future project requirements. 
* HR wants to evaluate the effectiveness of the new employee onboarding program across different departments. 
* The operations team needs to ensure all field technicians maintain the required safety certifications.

## Access Control and permissions 

**Administrators**

* Can generate transcripts for all learners across all catalogs.
* Can access all reporting functions but may have catalog or user group restrictions. 
* Custom administrators: Access limited by assigned scope and permissions. 

**Scope-based restrictions**

* Custom administrators can only view transcripts for learners within their assigned user groups. 
* Reports will only include learning objects from catalogs that the administrator has permission to access. 

## How to generate Learner Transcripts 

1. Log in to Adobe Learning Manager as an administrator. 
2. Select **[!UICONTROL Reports]** from the left navigation menu. 
3. Select **[!UICONTROL Custom Reports]** within Reports and then select **[!UICONTROL Excel Reports]**. 
4. Select **[!UICONTROL Learner Transcripts]**. 
   
   ![]()

5. Select **[!UICONTROL Generate New]**.
6. Select the date range for which you need the transcript generated. By default, the **[!UICONTROL From]** date is the learner's registration date, and the **[!UICONTROL To]** date is always the current date. You can modify only the start date from when you need the data.
7. Select the following:
    a. Select the learners' names from the **[!UICONTROL Select Learners]** section. You can select users or user groups  , or you can copy and paste the email addresses of the learners for whom you want to generate transcripts. See the section [Generate Learner transcript](#generate-learner-transcript-using-copy-paste) using copy-paste for more information.
    b.Select specific catalogs from the **[!UICONTROL Select Catalogs]** dropdown list. The transcript is only downloaded for the specified catalogs.  
    c. Select the **[!UICONTROL Enrollment Status]**. This drop-down contains the following options: 

       * Select All
       * Completed
       * In Progress
       * Not Started
       * Unenrolled
8. Advanced options: Select **[!UICONTROL Advanced options]** to download the transcripts to include the following:

    a. Download transcripts for learners who have been deleted from an account by selecting the checkbox **[!UICONTROL Include deleted Learners]**.
    b. Download module level information in the Learner transcript by enabling the **[!UICONTROL Enable module level information]** checkbox. In this case, module names and the time spent on each module are fetched as a part of the transcript if this option is enabled.
    c. Download skills data and summary sheets by enabling the option **[!UICONTROL Include skills data and summary sheets]** checkbox. See the Excel reports section for more information.
9. You can also select the column values  to be populated in your report. This provides flexibility to download reports with specific column values as required. Select the columns from the dropdown menu.
   
   ![]

Transcripts are generated and downloaded to your computer as .zip files when the skills data is not included. If the Skills data checkbox is enabled transcripts are generated and downloaded as . xlsx files.  

### Generate Learner transcript using copy-paste

Fetching Learner transcripts becomes a tedious process as it can be obtained only for a learner or user group one at a time. Here, with the copy-paste feature you can copy the list of Learner email ids and paste it at once.

1. Select **[!UICONTROL Email IDs]** tab to enter the copied list of unique email ids.

   ![]

2. Paste unique email IDs of Learners you want to add, separated by a comma, semi-colon or line break.
3. Select **[!UICONTROL Validate Emails Ids]** to check if the email ID you've entered is valid. In case the entered email id is incorrect, it would be highlighted in red along with a validation message.

    >[!NOTE]
    >
    >The Generate button will remain disabled unless all the email IDs entered are correct.

4. Select **[!UICONTROL Generate]** to generate Learner Transcripts for all the mentioned email ids. 

    >[!NOTE]
    >
    >Generating Learner Transcripts can be combined for Email IDs entered under both Users and Email IDs tab.

### What does the Learner Transcripts report contain

The Learner Transcript report is a combination of user, enrollment and Learning Objects-related information.
The following tables describe each type:

**User-related information**

The following columns identify the learner. 

|Field |Description |
|---|---|
|Name |Name of the learner. |
|Email |Learner's email address.|
|Adobe ID |This field is populated only when users log in using their Adobe ID. If they access Adobe Learning Manager through an organization-defined [Single Sign-On (SSO)](/help/migrated/administrators/feature-summary/multiple-sso-logins.md), the Adobe ID field will remain blank. |
|User Unique ID | User Unique ID is an external ID generated by accounts in case they don't have email IDs of all users, or unique email IDs of all users. <br>The User Unique ID field is an optional field that can be enabled for an account. The main purpose of the field is to allow accounts to tag each user with a unique ID to track them, update user records via APIs, audit, or sync data in automated workflows. The tagging of each user happens via CSV import of users.</br><br>If an account has opted for Unique User ID, then reports, such as Learner Transcripts, Adobe Learning Manager provides the column in the reports.</br> |

**Enrollment-related information**

The following columns capture activity, progress, or attempts.

|Field |Description |
|---|---|
|Enrollment Date (UTC TimeZone) |Date and time stamp of enrollment by the learner to the Learning Object type, which is course, certification, or Learning Path. |
|Mark Completed Date (UTC TimeZone)  |Date and time stamp of when an instructor marks a session or module as complete. Note that if a session has not happened, the column appears blank in the report. Also, if a session has happened and the instructor has not marked the session as complete, the column appears blank in the report.|
|Started Date (UTC TimeZone) |Date and time on which the learner started the Learning Object. Empty implies the learner has not yet started this.|
|Completion Date (UTC TimeZone) |Date and time on which learner completed this. Empty implies that the learner has not yet completed this. |
|Deadline (UTC TimeZone) |Date and time on which learner is expected to complete this Learning Object. Empty implies that there is no deadline for this. |
|Overdue |Current overdue status of the Learner enrolled in the Learning Object. Yes/No |
|Status  |Indicates the learner's status when taking the course, certification, or Learning Path.  The available statuses are Not Started, Unenrolled, In Progress, or Completed.  |
|Progress %  |Current progress % of the learner taking the course, certification, or Learning Path. |
|Time Spent(minutes)  |Learning time spent by the learner in the LO, the module level rows display the individual module wise Learning Time Spent. The Course / Learning Path  / Certificate level rows display the aggregated learning time spent.|
|Grade  |  Indicates the success of the learner. 'Pass', if user has met success criteria for this, 'Fail' otherwise. |
|Quiz_score |   The latest quiz score obtained by the learner. Can be empty, if the learner has not attempted the quiz or content doesn't have any quiz in it, or the administrator/Instructor hasn't assigned any score. |
|Quiz_score_max  |The latest maximum quiz scores possible for the module. It can be empty if the learner has not attempted the quiz or the content doesn't have any quizzes in it. |
|Highest_Quiz_score |The highest quiz score obtained by the learner across multiple attempts. Can be empty, if the learner has not attempted the quiz or content doesn't have any quiz in it, or the administrator or instructor hasn't assigned any score. |
|Highest_Quiz_score_max |The highest maximum quiz scores possible for the module. It can be empty if the learner has not attempted the quiz or the content doesn't have any quizzes in it. |
|Attempts Taken  |The total number of attempts taken by the learner so far for this module. |
|Maximum Allowed Attempts |The maximum number of attempts allowed for the learner to consume the module. |
|Submission Comments |Comments from a learner's manager after they complete a Learning Object.<br>The submission comments data provided by the instructor are included in the file submission module . See <a href=https://experienceleague.adobe.com/en/docs/learning-manager/using/instructor/modules#filesubmissionforactivitymodules>Modules-Adobe Learning Manager for more information.</a></br>|
|Completion Source |<b>Note:</b> For VC connector attendance workflows, when a learner is marked as attended automatically, the source will display "SELF, (learner_email)". |
|Completion Comment |The comments made by the administrator when they mark a learner as complete after they complete a course, certification, or Learning Path. The administrator can add the completion comments for one or multiple learners. See <a href=https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/courses#completion-comments>Completion comments</a> for more information. |

**Learning Objects-related information**

These refer to courses, modules, Learning Paths, certifications, and so on.

|Field |Description |
|---|---|
|Learning plan Name |Title of the Learning Plan. |
|LP/Certification/Course |The title of the Learning Object.|
|Type |The type of Learning Object, the user was enrolled in. For example,<ul><li>Learning Path</li><li>Certification</li><li>Course</li></ul> |
|Embedded Path |An Embedded Path is a type of learning path that is included as part of another course     or a Learning Path. The field indicates that a learner is completing that learning path as part of another Learning Path rather than as a standalone assignment. |
|Course |Name of course in which the user is enrolled. When it is empty, the row represents either a Certification or Learning Path. <br><b>Note:</b> Although Learning Paths and Certifications    are composed of individual courses or nested Learning Paths, each component retains its own independent record. This ensures that progress, completion, and reporting data are tracked separately for both the parent and the child elements.</br> |
|LO Unique ID |The unique ID of the Learning Object. It is needed if the customer has the LO in an external system which has its own ID. This is useful if you want to map the external system's LO Id and Adobe Learning Manager LO.<br>An administrator can enable the  option Unique Learning Object Ids in the Settings page. When enabled, Adobe Learning Manager assigns a unique ID to a Learning Object every time an author creates a course, certification, or Learning Path. </br>| 
|Instance  |The name of the instance of  the Learning Object user is enrolled in. |
|Selection Criteria  |Basis of enrollment (how this learner got enrolled in this Learning Object).<br>In Adobe Learning Manager, learners can enroll in learning objects through several methods: Manager Nominated Enrollment: Managers nominate learners for specific courses. Learners cannot self-enroll in these courses.</br><ul><li>Manager Approved Enrollment: Learners sign up for courses, but enrollment requires the manager's approval.</li><li>Self-Enrolled: Learners directly enroll themselves in courses without requiring approval.</li><li>Administrator-Enrolled: Administrators manually enroll learners into courses.</li></ul>|
|Module | Name of module inside the courses. Only the modules that have status as Completed or In Progress appear in the report. If the status is Not Started or Unenrolled, the Module column stays empty.<br>Download module-level information in the Learner transcript by selecting the <b>Enable module level information</b> checkbox. In this case, module names and the time spent on each module are fetched as part of the transcript if this option is enabled.</br>|
|Module ID |The unique ID of the module.<br><b>Note:</b> The Module ID column appears in the report only if you've selected the Include module information checkbox while generating the transcript.</br>|
|Version |The module version refers to the specific version of a module that a learner has interacted with. This is particularly useful when a module has undergone updates or changes, as it allows administrators to track which version of the module was accessed by the learner.<br>When an author uploads a new version of a module, Adobe Learning Manager treats it as a new version of the existing module. This enables content to be updated without disrupting all learners.</br><br>The Version appears if <b>Enable module level information</b> checkbox was selected while generating the report.</br><br>See <a href=https://elearning.adobe.com/2023/03/updating-the-module-in-adobe-learning-manager-how-to-replace-a-content-module-in-a-course-without-disturbing-the-users-progress/>Updating a module in Adobe Learning Manager</a> for more information.</br>|
|Delivery Type |Indicates how the module is delivered: Blended, Classroom, or Virtual Classroom. |
|Language |Language in which the module is consumed by the learner. This column shows value only for eLearning modules.|
|Overdue |Current overdue status of the Learner enrolled in the Learning Object. Yes/No|
|Grade |Indicates the success of the learner. 'Pass', if user has met success criteria for this, 'Fail' otherwise.|

>[!INFO]
>
>The following columns are hidden in the Learner Transcripts:
>
>* Enrollment Count
>* Started Count
>* Completion Count
>* Due in N Days
>* Due in N Days for User
>* Count of (Progress Greater than N %)  
>* Count of (Progress Greater than N %) for User 
>
>These columns only appear if you've selected Include Skills data and summary sheets while generating the transcript. These columns are used to calculate summary details of a learner, enrolled to a Learning Object.

|Fields |Description |
|---|---|
|Training ID  |A system-generated unique identifier assigned to each learner's enrollment in a specific course, cert  ification, or learning path. If a learner re-enrolls in the same course, a new Training ID will be generated. One learner may have multiple Training IDs for the same course.|
|Training or Module Duration (mins) |This column shows the expected duration (in minutes) of a course, module, or training activity as defined when creating the course. It is not the actual time a learner spends, but the configured/assigned duration that represents how long the training is supposed to take. <br>This column shows the total duration (in minutes) of the assigned learning item, which can be either a learning path or an individual course.</br><br><b>Learning Path duration:<b> If the training item is a learning path, its duration is calculated as the sum of the durations of all courses inside the learning path.</br><br>Example: If Course 1 = 50 mins and Course 2 = 60 mins, then the Learning Path Duration = 110 mins.</br><br><b>Individual course duration:</b>If the training item is an individual course (not part of a learning path), the duration reflects the time required for that course alone.</br>|
|Embedded_Course_ID |The ID for the course that is a part of a Learning Path or part of any other course.<br>The column is populated when the row represents a Learning Path or certification itself. It shows the IDs of the individual courses embedded within the Learning Path or certification. It is not populated when the row itself is a course on ly, since there are no embedded items.</br>|
|Embedded Path ID |The ID for the path in which the embedded course exists.<br>The column identifies the unique ID of embedded Learning Paths. It helps track courses within Learning Paths and provides visibility into the hierarchical structure of Learning Paths.</br>|
|Unenrollment Date (UTC TimeZone) |Date of unenrollment by the learner to the Learning Object type.|
|Price($) |The price of the Learning Object for which it is purchased from the course catalog. For this column to appear in the Learner Transcript, the administrator must enable the Enable pricing for Courses/ Learning Paths/ Certifications checkbox from account settings.|

## Excel reports

The Learner Transcripts dialog box also allows you to download skills data and summary sheets as excel files. Select the **[!UICONTROL Include Skills data and summary sheets]** checkbox and then select **[!UICONTROL Generate]** to download an excel file with the following sheets:

* Learning Summary I
* Learning Summary II
* Compliance Summary
* Skill Transcript
* Skill Summary I
* Skill Summary II

![]

### What does the Learning Summary I sheet contain

Track Learning Paths, courses or certifications that are actively utilized. Track the in-progress activity as well as any upcoming due dates for training.

* Number of Learners Enrolled: Indicates how many learners have been enrolled in a particular learning object (course, learning path, or certification), regardless of whether they have started it.
* Number of Learners Who Have Started: Shows the count of learners who have launched or begun the course, certification, or Learning Path.
* Number of Learners Who Have Completed: Displays how many learners have successfully completed the training and met all its completion criteria.
* Number of Learners Who Have Progressed ≥ N%: Reflects the count of learners who have achieved at least the specified progress threshold (e.g., 70%) in the training, even if they haven't completed it.
* Number of Learners with Due Date in N Days: Indicates how many learners have training due within the next "N" days (e.g., 7 days), useful for identifying upcoming deadlines.

### How to interpret the data

This Learning Summary I report tracks two Learning Paths assigned to the learner.
From the example,

![]
 
* The user is enrolled in two Learning Paths and has started both.
* Neither of the learning paths has been completed yet.
* The learner has not yet progressed beyond the 70% threshold in either path.
* No due dates fall within the next seven days for either training.

### What does the Learning Summary II sheet contain

Track learning activity per learner. Track enrollments, in-progress activity as well as due dates for learners.

* Number of Learning Objects Enrolled: Total count of Learning  Objects (LOs) the learner is enrolled in each course, certification, or Learning Path. counts separately  .
* Number of Learning Objects Started: Indicates how many of the enrolled Learning Objects the learner has launched or begun.
* Number of Learning Objects Completed: Shows how many of the started LOs the learner has fully completed.
* Number of Learning Objects which have progressed ≥ N%: Reflects the number of LOs in which the learner has achieved at least the specified progress threshold (in this case, 70%).
* Number of Learning Objects with due date in N days: Identifies LOs that are due within the next set number of days (in this case, 7 days), helping track approaching deadlines.

### How to interpret the data

From the example,
 
![]

* The learner is enrolled in two learning objects and has started both.
* No learning objects have been completed.
* The learner has not yet reached 70% progress in any of them.
* None of the learning objects are due in the next 7 days.

### What does the Compliance Summary sheet contain

Track learners who have upcoming due dates for key Courses, Learning Paths or Certifications.

|Column |Description |
|---|---|
|Type |The LO type for which the Learning Summary table should show data.|
|Row Labels (Left side column) |The Learner name with the list of LOs the learner is enrolled in.|

### What does the Skill Transcript sheet contain  

|Column |Description |
|---|---|
|Name | Full name of the learner associated with the skill transcript.|
|Email |Email address of the learner.|
|User Unique ID |Organization-defined unique identifier for the learner.|
|Skill |The name of the skill assigned to the learner (for example, Java Programming, Leadership).|
|Skill Level |The level of expertise within the skill that the learner is expected to attain (for example, Beginner, Intermediate, Advanced).|
|Credits Required |Number of learning credits needed to achieve the assigned skill level.|
|Credits Earned |Number of credits the learner has earned toward completing the assigned skill level.|
|Completion Percentage |The percentage of required credits the learner has completed.|
|Date Assigned (UTC) |The date when the skill was assigned to the learner.|
|Date Achieved (UTC) |The date when the learner achieved the required credits and fulfilled the skill level criteria.|
|Manager Name |Name of the learner's manager who oversees the learning progress.|

### What does the Skill Summary I sheet contain

|Column |Description|
|---|---|
|After |Represents the number of learners who achieved a skill before a defined period (in days), beyond which the skill is considered outdated or requiring refresh. Useful for identifying learners with approaching or expired skill achievements.<br>See <a href=https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/skills-levels>skill levels</a> for more information.| 
|Name |Full name of the learner to whom the skill is assigned.|
|Manager Name |Name of the learner's reporting manager.| 
|Row Labels |The specific skill name assigned to learners appearing in this row. Used as a grouping header to summarize learner skill data under each skill category.|
|Number of users who should have this skill |Total number of learners who have been assigned the specific skill.|
|Number of users who have achieved this skill |Number of learners who have successfully completed the required Learning Objects to attain the skill.|
|Number of learners whose skill needs refreshing |The number of learners whose skill achievement dates exceed the defined refresh threshold.|
|Percentage of Compliance (Based on skill achieved) |The compliance or adoption rate for the skill.|


### What does the Skill Summary II sheet contain

|Column |Description|
|---|---|
|After |Number of skills achieved by the learner before the defined refresh threshold (in days). This identifies skills that may be outdated and need to be refreshed.|
|Skill |Name of the skill(s) assigned to learners. This could be linked to one or more Learning Objects, such as courses, certifications, or Learning Paths.|
|Manager Name |The name of the learner's direct manager.|
|Row Labels |The learner's full name. For each learner, the skills and progress are displayed in subsequent columns.|
|Number of Skills Each User Should Have |Total number of skills assigned to the learner.  |
|Number of Skills Each User Has |Total number of skills the learner has successfully achieved through completion of the associated Learning Object(s).|  
|Number of Skills that need Refreshing |The number of skills achieved that have crossed the refresh duration and now require revalidation. This value helps track training renewal needs for compliance or continuous development.|
|Percentage of Compliance |Indicates the learner's overall compliance level based on skill achievement.|

## History of Learner Transcript downloads

The history of Learner Transcript downloads allows administrators to track who downloaded each learner's transcript and which users they accessed. This feature is particularly beneficial in enterprise and compliance-focused settings where several stakeholders may need to view learning records.

After downloading a Learner Transcript, the Learner Transcripts page lists all transcripts that are generated by anyone in the platform.

![]
 
The list displays the following attributes:

* From and To: Duration of the transcripts to be downloaded.
* Generated by: The email of the user who has downloaded the report or requested the download.
* Learners: The learners or learner groups whose transcripts are to be downloaded.
* Filters Applied: The filters that were applied for Enrollment Status.
* Additional Data Included: The additional data (deleted learners, module information, and skills data and summary sheets) the administrator had requested from the Advanced option in the Add learner transcript modal  
* Status: Downloaded, queued, or in progress.
* Cancel: Cancel the report generation at any time.

## Additional considerations for Learner Transcripts

Learner Transcripts include several behaviors that administrators should be aware of:

**Learning Path and course progress display** 

All courses that are part of a Learning Path (LP) will appear in the Learner Transcript, even if the learner has made progress in only one of the courses. This ensures complete visibility of a Learning Path, even when progress is partially completed.

**Data for deleted learners**

If a learner has been deleted from the platform, their transcript will not show their records in any reports generated for the user group they were part of. This means that the records of deleted learners will be excluded from any filtered reports created using user group filters.

But you can still download the data of the deleted learners. If you've selected the option **[!UICONTROL Include deleted learners]** while setting the filters for generating the report, you can download the report for the deleted learners.

![]

**Behavior for custom administrators**

Custom administrators with a defined scope (for example, limited to specific catalogs or user groups) will see filtered transcript data based on their scope:

* User group scope: Only learners in the custom administrator's scoped user group will be included in the report.
* Catalog scope: Only Learning Objects (courses, certifications, and Learning Paths) assigned to the scoped catalogs will be included in the report.
* Filtered columns: Columns stay the same. Only the rows will be scoped based on scopes of catalogs and user groups. 

This ensures that scoped custom administrators view only the learner's data and learning content they are authorized to manage.

**Connector support**

The Learner Transcript report can be accessed through administrator User Interface, [FTP, Box, Job API, or Power BI](/help/migrated/integration-admin/feature-summary/connectors.md). It is not included in the unified reports from Salesforce, Power BI, and Marketo Engage. 

Unified reports downloaded from Salesforce, Marketo Engage, and Power BI contain fewer columns than Learner Transcripts.






