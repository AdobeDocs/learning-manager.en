---
jcr-language: en_us
title: Interpret the Learner Transcript CSV
description: Interpret the Learner Transcript CSV
contentowner: saghosh
preview: true
---


# Interpret the Learner Transcript CSV

Learning Manager Learning Programs are renamed to Learning Paths. This change happens immediately after the October 2021 release and the terminology of Learning Path is reflected for all roles.

The Learner Transcript is one of the most popular reports used in Adobe Learning Manager. The report enables one to get nearly every possible detail in a single report in CSV format.

Apart from being a report that users can fetch to track and analyze learning behaviors, the report can also be viewed as the format in which Prime can be set up to export data about learning behaviors to external applications/systems.

A typical enterprise scenario is to take a periodic export of learner transcript for Prime, analyze it to extract learners completing an important learning program, and placing an order for a gift voucher to recognize and reward timely completions.

Another use case is to add the learning behavior data to an enterprise data warehouse, where one may want to combine learning data with other enterprise data to analyze correlations between learning behavior and other process data.

In the rest of the document, we briefly describe how one can fetch the Learner Transcript from Prime; and then proceed to providing the details on how each row and column of the report needs to be interpreted.

This information may be useful for any developer who intends to integrate Prime with other systems by way of processing the exported learner transcript data.

## Fetch Learner Transcript from the User Interface {#fetchlearnertranscriptfromtheuserinterface}

From the Profile Settings, a learner can download his/her transcript. For more information,  see *** [Download Learner Transcript](../../administrators/feature-summary/learner-transcripts.md)***.

Administrators can generate Learner Transcripts for the whole organization, a specific set of users or a specific set of learning objects, or a specific set of users and learning objects. They can also get all learning records for a time interval duration and indicate if module level information is required (by default, module level information is omitted). For more details, see [***Download Learner Transcripts***](https://helpx.adobe.com/captivate-prime/administrators/feature-summary/learner-transcripts.html).

<!--Update above link?-->

Administrators can also set up the system to email the Learner Transcript periodically.

The Learner Transcript generated via the UI will be an Excel file, which also contains the "Skill Transcript". In this document, we will refer to what is generated in the CSV format, a report containing learning activities pertaining to enrollment, starting, progress or completion of a learning object.

## Export Learner Transcript {#exportlearnertranscript}

When the Learner Transcript has to be consumed by an external system, Prime provides a feature called Export Data, where Learner Transcript is one of the types of data that can be exported. As explained in the Preamble, this is required for integration of Prime with an external system that needs to process learning behavior data or for populating an enterprise data warehouse with learning behavior data.

For details of how the connectors that supporting Export of Learner Transcript, see the [Export Data section](https://helpx.adobe.com/captivate-prime/integration-admin/feature-summary/connectors.html) in the FTP, Box and PowerBI Connectors.

The purpose served by these connectors is to export data to a downstream application periodically (once in N days). So, these connectors export only the incremental learning behavior data in every run. Note that these connectors don't allow for fetching records pertaining to specific subset of users or learning objects - it is always data about all users and all learning objects in that account.

In the case of PowerBI, the customer should provide a workspace where Prime can keep exporting this data incrementally into a dynamically created dataset. This connector merely exports data, and the customers must build their own reports/dashboards based on this dataset as need be.

The next section provides the details on how a downstream system should interpret the records in the learner transcript.

## Interpret the Learner Transcript {#interpretthelearnertranscript}

Each row in a Learner Transcript can be thought of as some learning behavior that was captured in Prime in a specific time period. Typically, the connectors export "incremental data" and so the rows represent learning activities that happened between the last run of the connector and the current run.

Of course, the connectors also allow you to fetch the learner transcript on demand, and in this case the user can specify a start date and the end date is assumed to be now. Usually one would do this once initially and then set up the connector for exporting the incremental learner transcript at a specific time of day, once in N days (the default value of N, being 1).

Let us now define what is meant by Incremental Learner Transcript

In the learner transcript, every row represents a specific activity involving a specific learner and a specific learning object. We are primarily interested in what state a learner is with respect to the learning object - **Enrolled**, **Started**, **In Progress**, and **Completed**. Therefore, the learner transcript captures four corresponding dates as well.

Now there are three types of learning objects, where Prime tracks learner progress; and the exported data contains progress information at the module level, which is the most granular unit of content that a learner can experience in Prime.

* **Course** - a composition of one or more modules
* **Learning Program** - a composition of one or more courses
* **Certification** - a composition of one or more courses.

Every row in the Learner Transcript could be pertaining to a specific user's engagement with a Module, Course, Learning Program or Certification. When a user is enrolled to a Learning Program, the transcript will indicate that the user is e

The columns of the Learner Transcript provide various pieces of information pertaining to each learning activity, and the following tables describe the semantics of each column.

## Learner Transcript

<table> 
 <tbody> 
  <tr> 
   <th width="158" valign="bottom"><p><b>Column Name</b></p></th> 
   <th width="160" valign="bottom"><p><b>Type of value</b></p></th> 
   <th width="306" valign="bottom"><p><b>Description</b></p></th> 
  </tr> 
  <tr> 
   <td><p><b>Name</b></p></td> 
   <td><p>Never empty</p></td> 
   <td><p>Name of the learner</p></td> 
  </tr> 
  <tr> 
   <td><p><b>email</b></p></td> 
   <td><p>Never empty</p></td> 
   <td><p>Email address of the learner</p></td> 
  </tr> 
  <tr> 
   <td valign="bottom"><b>Adobe ID</b></td> 
   <td valign="bottom">Can be empty</td> 
   <td valign="bottom">Adobe ID of the learner</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>User Unique ID</b></td> 
   <td height="19" width="283">Can be empty</td> 
   <td height="19" width="728">User Unique Id of the Learner. This column is based on the backend setting whether enabled/ disabled at account level.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Learning plan Name</b></p></td> 
   <td valign="middle"><p>Can be empty</p></td> 
   <td valign="middle">Name of the learning plan (if any), through which the user has been automatically assigned to.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>LP/Certification/Course</b></p></td> 
   <td valign="middle"><p>Never empty</p></td> 
   <td valign="middle"><p>Name of the learning pogram, Certification or Course</p></td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Type</b></p></td> 
   <td valign="middle">Never Empty</td> 
   <td valign="middle"><p>The type of the learning object, the user was enrolled into.</p></td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Course</b></p></td> 
   <td valign="middle"><p>Can be empty</p></td> 
   <td valign="middle">Name of course in which user is enrolled to. When it is empty, the row represents either a Certification or Learning Program. </td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>LO Unique ID</b></td> 
   <td height="19" width="283">Can be empty</td> 
   <td height="19" width="728">Learnig Object Unique Id of the LO. This column is based on the setting whether enabled/ disabled at account level</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Instance  </b></p></td> 
   <td valign="middle">Never Empty</td> 
   <td valign="middle">Name of the instance of the LO user is enrolled into. </td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Selection Criteria</b></p></td> 
   <td valign="middle"><p>Never empty</p></td> 
   <td valign="middle"><p>Basis of enrollment (how this learner got enrolled to this LO).</p></td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Module</b></p></td> 
   <td valign="middle"><p>Can be empty</p></td> 
   <td valign="middle">Name of module inside the Courses. When empty, this row represents either a course, learning program or certification.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Version</b></td> 
   <td height="19" width="283">Can be empty</td> 
   <td height="19" width="728">Version of the module</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Delivery Type</b></td> 
   <td height="19" width="283">Can be empty</td> 
   <td height="19" width="728">Delivery Type of the module - eLearning, F2F, VC, Activity.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Language</b></td> 
   <td height="19" width="283">Can be empty</td> 
   <td height="19" width="728">Language in which the module is consumed by learner. This column shows value only for eLearning modules.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Comment</b></td> 
   <td height="19" width="283">Can be empty</td> 
   <td height="19" width="728">Comments added by Admin, Instructor for the learner while marking the user attendance.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Enrollment Date (Asia/Calcutta TimeZone)</b></td> 
   <td height="19" width="283">Never Empty</td> 
   <td height="19" width="728">Date of enrollment by the learner to the LO type.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Started Date (Asia/Calcutta TimeZone)</b></td> 
   <td><p>Can be empty</p></td> 
   <td height="19" width="728">Date on which learner started the LO. Empty implies the learner has not yet started this.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Completion Date (Asia/Calcutta TimeZone)</b></td> 
   <td><p>Can be empty</p></td> 
   <td><p>Date on which learner completed this. Empty implies the learner has not yet completed this.</p></td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Deadline (Asia/Calcutta TimeZone)</b></td> 
   <td><p>Can be empty</p></td> 
   <td height="19" width="728">Date on which learner is expected to complete this LO. Empty implies that there is no deadline for this.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Overdue</b></td> 
   <td height="19" width="283">Yes/ No</td> 
   <td height="19" width="728">Current overdue status of the Learner enrolled to the LO. Yes/No</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Status</b></p></td> 
   <td valign="middle">Not started/Completed/In Progress/Unenrolled</td> 
   <td valign="middle">Current Progress % of the Learner enrolled to the LO.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Progress %</b></p></td> 
   <td valign="middle">Can be empty</td> 
   <td valign="middle"><p>Indicates the extent to which learner has completed this.</p></td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Time Spent(minutes)</b></td> 
   <td height="38" width="283">Can be empty</td> 
   <td height="38" width="728">Learning time spent by the learner in the LO, the module level rows displays the individual module wise Learning Time Spent. The Course / Program / Certificate level rows displays the aggregated learning time spent.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Grade</b></p></td> 
   <td valign="middle">Pass/ Fail</td> 
   <td valign="middle">Indicates success of learner. 'Pass', if user has met success criteria for this, 'Fail' otherwise.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Quiz Score</b></p></td> 
   <td valign="middle">Can be empty</td> 
   <td valign="middle">The latest quiz score obtained by learner. Can be empty, if learner has not attempted the quiz or content doesn't have any quiz in it or Admin/ Instructor haven't assigned any score.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Quiz_score_max</b></td> 
   <td height="38" width="283">Can be empty</td> 
   <td height="38" width="728">The latest maximum quiz score possible for the module. Can be empty if learner has not attempted the quiz or content doesn't have any quiz in it.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Highest_Quiz_score</b></td> 
   <td height="38" width="283">Can be empty</td> 
   <td height="38" width="728">The highest quiz score obtained by the learner across multiple attempts. Can be empty, if learner has not attempted the quiz or content doesn't have any quiz in it or Admin / Instructor haven't assigned any score.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Highest_Quiz_score_max</b></td> 
   <td height="38" width="283">Can be empty</td> 
   <td height="38" width="728">The highest maximum quiz score possible for the module. Can be empty if learner has not attempted the quiz or content doesn't have any quiz in it.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Attempts Taken</b></td> 
   <td height="19" width="283">Can be empty</td> 
   <td height="19" width="728">The total number of attempts taken by learner so far for this module.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Maximum Allowed Attempts</b></td> 
   <td height="19" width="283">Can be empty</td> 
   <td height="19" width="728">The maximum number of allowed attempts for the learner to consume the module.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>userState</b></p></td> 
   <td valign="middle">Never Empty</td> 
   <td valign="middle">User state of the learner: Active / Deleted / Suspended.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Groupable Active Field</b></td> 
   <td height="38" width="283">Can be empty</td> 
   <td height="38" width="728">For each groupable Active Field in account, there will be a column, where the column name is that of Active Field and the value will be the specific value the learner has for that field.</td> 
  </tr> 
  <tr> 
   <td><p><b>Manager Name</b></p></td> 
   <td><p><i>Can be empty</i></p></td> 
   <td height="19" width="728">Manager Name of the learner</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Enrollment Count</b></td> 
   <td height="38" width="283">1 or 0</td> 
   <td height="38" width="728">Enrollment Count of the learner for the LO. The highest level LO row shows a value = '1'. The subtrainings displays a value 0.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Started Count</b></td> 
   <td height="19" width="283">1 or 0</td> 
   <td height="19" width="728">Started Count of the learner for the LO. The highest level LO row shows a value = '1'. The subtrainings displays a value 0.</td> 
  </tr> 
  <tr> 
   <td height="58" width="283"><b>Completion Count</b></td> 
   <td height="58" width="283">1 or 0</td> 
   <td height="58" width="728">Completion Count of the learner for the LO. The highest level LO row shows a value = '1' if learner is pending completion in that training. The subtrainings displays a value 0 even when in Pending state. The highest level LO row shows a value = '0', if learner has completed the training.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Due in N Days</b></td> 
   <td height="38" width="283">1 or 0</td> 
   <td height="38" width="728">This shows a value of '1' or '0' depending on the instance deadline of the training learner is enrolled to. It depends on the value entered on Learning Sumary I sheet &gt; 'Due Date Coming up in' field.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Due in N Days for User</b></td> 
   <td height="38" width="283">1 or 0</td> 
   <td height="38" width="728">This shows a value of '1' or '0' depending on the instance deadline of the training learner is enrolled to. It depends on the value entered on Learning Sumary II sheet &gt; 'Due Date Coming up in' field.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Count of (Progress Greater than N %)</b></td> 
   <td height="38" width="283">1 or 0</td> 
   <td height="38" width="728">This shows a value of '1' or '0' depending on the learner progress in the training. It depends on the value entered on Learning Sumary I sheet &gt; 'Progress Greater than' field.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Count of (Progress Greater than N %) for User</b></td> 
   <td height="38" width="283">1 or 0</td> 
   <td height="38" width="728">This shows a value of '1' or '0' depending on the learner progress in the training. It depends on the value entered on Learning Sumary II sheet &gt; 'Progress Greater than' field.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283">T<b>raining ID</b></td> 
   <td height="19" width="283">Never Empty</td> 
   <td height="19" width="728">Training ID of the training.</td> 
  </tr> 
  <tr> 
   <td height="20" width="283"><b>Training or Module Duration (mins)</b></td> 
   <td height="20" width="283">Never Empty</td> 
   <td height="20" width="728">Total Training or Module Duration (mins) of the default instance of the training.</td> 
  </tr> 
 </tbody> 
</table>

### Learning summary I

<table cellpadding="1" cellspacing="0" border="1"> 
 <tbody> 
  <tr> 
   <th>Column name<br></th> 
   <th>Type of value</th> 
   <th>Description</th> 
  </tr> 
  <tr> 
   <td height="19" width="264">Type</td> 
   <td height="19" width="253">All, Learning Program, Certificate, Course.</td> 
   <td height="19" width="412">The LO type for which the Learning Sumary table should show data.</td> 
  </tr> 
  <tr> 
   <td height="19" width="264">Groupable field(profile)</td> 
   <td height="19" width="253">Never Empty</td> 
   <td height="19" width="412">The profile for which the learning summary table should show data.</td> 
  </tr> 
  <tr> 
   <td height="38" width="264">Manager Name</td> 
   <td height="38" width="253">Never Empty</td> 
   <td height="38" width="412">The manager name, whose subordinates LO engangement data is to be displayed on the Learning summary table.</td> 
  </tr> 
  <tr> 
   <td height="19" width="264">Row Labels</td> 
   <td height="19" width="253">Never Empty</td> 
   <td height="19" width="412">The LO name with the list of learners enrolled to the LO.</td> 
  </tr> 
  <tr> 
   <td height="19" width="264">Number of Learners enrolled</td> 
   <td height="19" width="253">Never Empty</td> 
   <td height="19" width="412">Number of learners enrolled the LO.</td> 
  </tr> 
  <tr> 
   <td height="19" width="264">Number of Learners Who Have Started</td> 
   <td height="19" width="253">Never Empty</td> 
   <td height="19" width="412">Number of learners who have started the LO.</td> 
  </tr> 
  <tr> 
   <td height="19" width="264">Number of Learners Who Have Completed</td> 
   <td height="19" width="253">Never Empty</td> 
   <td height="19" width="412">Number of learners who have completed the LO.</td> 
  </tr> 
  <tr> 
   <td height="38" width="264">Number of Learners who have progressed &gt;= N %</td> 
   <td height="38" width="253">Never Empty</td> 
   <td height="38" width="412">Number of Learners who have progressed &gt;= N % (values).</td> 
  </tr> 
  <tr> 
   <td height="39" width="264">Number of Learners with due date in N days</td> 
   <td height="39" width="253">Never Empty</td> 
   <td height="39" width="412">Number of Learners with due date in N days (values).</td> 
  </tr> 
 </tbody> 
</table>

### Learning summary II

| Column name |Type of value |Description |
|---|---|---|
| Type |All, Learning Program, Certificate, Course. |The LO type for which the Learning Sumary table should show data. |
| Groupable field(profile) |Never Empty |The profile for which the learning summary table should show data. |
| Manager Name |Never Empty |The manager name, whose subordinates LO engangement data is to be displayed on the Learning summary table. |
| Row Labels |Never Empty |The Learner name with the list of LOs learner is enrolled to. |
| Number of Learning Objects Enrolled |Never Empty |Number of Learning Objects learner is enrolled to. |
| Number of Learning Objects Started |Never Empty |Number of Learning Objects learner has started. |
| Number of Learning Objects Completed |Never Empty |Number of Learning Objects learner has completed. |
| Number of Learning Objects which have progressed >= N % |Never Empty |Number of Learners Objects learner have progressed >= N %. |
| Number of Learning Objects with due date in N days |Never Empty |Number of Learning Objects with due date in N days. |

### Compliance Summary

| Column name  |Type of value |Description |
|---|---|---|
| Type |All, Learning Program, Certificate, Course. |The LO type for which the Learning Sumary table should show data. |
| Row Labels (Left side column) |Never Empty |The Learner name with the list of LOs learner is enrolled to. |
| Row Labels (Left side column) |Never Empty |The Learner name with the list of LOs learner is enrolled to. |

### Skill Transcript

| .Column name |Type of value   |Description |
|---|---|---|
| Name |Never Empty |Name of the learner |
| email |Never Empty |Email address of the learner |
| Adobe ID |Can be empty |Adobe ID of the learner |
| User Unique ID |Can be empty |User unique ID of the learner. This column is based on the backend setting whether enabled/disabled at account level. |
| Skill |Never Empty |Assigned skill name to the learner. |
| Skill Level |Never Empty |Assigned skill level to the learner. |
| Credits Required |Never Empty |Total Credits required by Learner to achieve the Skill. |
| Credits Earned |Never Empty |Total Credits earned by Learner for the Skill. |
| Completion Percentage |Never Empty |Progress Percentage to achieve the skill. |
| Date Assigned (UTC TimeZone) |Never Empty |Date on which the Skill was assigned to the Learner. |
| Date Achieved (UTC TimeZone) |Never Empty |Date on which Learner achieved the Skill. |
| userState |Never Empty |User state of the learner: Active / Deleted / Suspended. |
| Groupable Active Field |Can be empty |For each groupable Active Field in account, there will be a column, where the column name is that of Active Field and the value will be the specific value the learner has for that field. |
| Manager Name |Can be empty |Manager Name of the learner. |

### Skill Summary I

| Column name |Type of value |Description |
|---|---|---|
| After |Never Empty |Number of learners who achieved the skill, before the entered (value) number of days which needs refreshing. |
| Name |All or any Learner name |The learner name who has a skill assigned. |
| Manager Name |Never Empty |The manager name, whose subordinates skill engangement data is to be displayed on the Skill summary table. |
| Row Labels |Never Empty |The Skill name with the list of learners assigned to the Skill. |
| Number of users who should have this skill |Never Empty |Number of learners assigned to the Skill. |
| Number of users who have achieved this skill |Never Empty |Number of learners who have achieved the Skill. |
| Number of learners whose skill needs refreshing |Never Empty |Number of learners whose Skill needs refreshing. |
| Percentage of Compliance (Based on skill achieved) |Never Empty |The progress percentage of the assigned Skill. |

### Skill summary II

| Column name |Type of value |Description |
|---|---|---|
| After |Never Empty |Number of learners, who achieved the skill before the entered (value) number of days which needs refreshing. |
| Skill |All or any Skill name |The Skill names that are assigned to Learners. |
| Manager Name |Never Empty |The manager name, whose subordinates skill engangement data is to be displayed on the Skill summary table. |
| Row Labels |Never Empty |The Learner name with the list of Skills assigned. |
| Number of Skills Each User Should Have |Never Empty |Number of Skills asigned to the learner. |
| Number of Skills Each User Has |Never Empty |Number of Skills achieved by the learner. |
| Number of Skills that need Refreshing |Never Empty |Number of learners whose Skill needs refreshing. |
| Percentage of Compliance |Never Empty |The progress percentage of the assigned Skill. |

* Sometimes administrators may mark completion for a Learning Object manually (especially for Class Room courses) much after the class. In such a scenario, if Export Data is set up to export LT daily, the actual date of completion may have passed already and so the export will never get such completion records that were marked as completed much after the class happened. When this is detected, consider exporting the transcript from a given start date till date (on demand) in the UI; and then take it to the downstream application for "late processing". While doing  this, you may have to ignore records that have already been processed.
* Multiple Attempts for a module depends on whether that is enabled for that LO. When enabled, what you now see in a CSV row related to a module is one attempt. Not all attempts in a day may be reported and so you may see the total number of attempts see increment by more than one. Also an attempt may not necessarily improve a score, and at any given point you will only the best score. 
