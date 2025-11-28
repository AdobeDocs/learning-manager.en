---
title: Course Report in Adobe Learning Manager
jcr-language: en_us
description: Learn more about how to download and interpret Course Reports to track learner progress and performance.
---

# Course report

## Overview

The Course report in Adobe Learning Manager provides detailed tracking of learner interactions with specific course content. This report specifically captures granular course-level engagement metrics including enrollment status, progress milestones across instances, completion timestamps, or quiz performance.

## Purpose and benefits

* Quantifies training effectiveness through completion rates and assessment scores.
* Identifies underutilized or high-impact course content.
* Flags learners at risk of missing critical training deadlines.

At an organization-level, the Course report:

* Facilitates data-driven decisions regarding investments in learning content. 
* Ensures compliance with regulatory requirements through timestamped completion records. 
* Offers an early warning system through course status and due dates for interventions with struggling learners.

## Use cases

### Regulatory compliance verification

A Healthcare organization must provide evidence that 100% of clinical staff completed annual HIPAA training by the deadline. The administrator filters for "HIPAA Essentials" course and sorts the report by completion date to identify completed and outstanding requirements.

### Training effectiveness analysis

Sales leaders are worried about the new product training after poor launch results. To understand why, the training admin created a detailed report on the "New Product Certification" quiz scores. This report looks at how employees answered each question, helping to find gaps in what the sales team knows about the new product.

### Learning experience optimization

High abandonment rates in critical cybersecurity training, affecting organizational risk mitigation standards. The administrator generates the report for Cybersecurity course and analyzes **[!UICONTROL Enrollment Date]** vs. **[!UICONTROL Completion Date]** patterns.

## How to download the Course reports

1. Log in to Adobe Learning Manager as an administrator.
2. Select **[!UICONTROL Reports]** from the left navigation menu.
3. Select **[!UICONTROL Custom Reports]** within Reports and then select **[!UICONTROL Excel Reports]**.
4. Select **[!UICONTROL Course Reports]**.
5. Select the course or **[!UICONTROL Course Unique ID]** for which you want to generate a report. Generate a report for course enrollment and quiz scores.
    a. **[!UICONTROL Enrollment Report]**: Select this option to generate a report that shows enrollment status, progress, and completion of data for learners in the selected course.
    b. **[!UICONTROL Quiz Score Report]**: Select this option to generate a report focused on learners' quiz scores for the selected course. This option also provides details of the questions used in the quiz.

![]

## Download course enrollment report

1. Select **[!UICONTROL Enrollment Report]**.
2. Select **[!UICONTROL Generate]** to download the report.

## What does the course enrollment report contain

| Column | Description |
|--------|-------------|
| Learners | The name of the learner enrolled in the course. |
| Email | The learner's registered email address. |
| User Unique ID |The unique identifier assigned to the learner by Adobe Learning Manager. The UUID uniquely identifies learners, even if they have similar names or email addresses. It ensures that learner-specific data, such as progress, enrollment, and completion details, is accurately recorded and retrieved. |
| Course Name | Name of the course the learner is enrolled in. |
| LO Unique ID | The unique ID of the Learning Object (course) assigned to the learner.<br><br><b>Note:</b> The LO Unique ID column appears in the report only if you've selected the Unique Learning Object Ids checkbox while setting up the account. |
| Status | The current enrollment status of the learner. The available options are:<li>Enrolled</li><li>Completed</li><li>Not Started</li>|
| Selection Criteria | In Adobe Learning Manager, learners can enroll in learning objects through several methods:<li>Manager Nominated Enrollment: Managers nominate learners for specific courses. Learners cannot self-enroll in these courses.</li><li>Manager Approved Enrollment: Learners sign up for courses, but enrollment requires the manager's approval.</li><li>Self-Enrolled: Learners directly enroll themselves in courses without requiring approval.</li><li>Administrator-Enrolled: Administrators manually enroll learners into courses.</li> |
| Enrollment Date / Unenrollment Date | Date and time stamp of enrollment by the learner to the Learning Object type, which is course, certification, or Learning Path. |
| Completion Date | Date and time when the learner completed the course (UTC TimeZone). |
| Due Date | Deadline by which the learner is expected to complete the course. |
| Started Date | Date and time when the learner first accessed the course. |
| Quiz Score | Score achieved in the course quiz, if applicable. |
| Manager Name | The name of the learner's manager. |
| userState | The state of the user on the platform, for example, ACTIVE or DELETED. |
| Comments | Notes or remarks related to the learner's enrollment.<br>The column captures the feedback or remarks provided by learners during or after completing a course. This column helps administrators and instructors understand learner opinions, suggestions, or issues related to the course content. |
| Number of Visits | The frequency of the learner's course access.<br>The total number of times a learner has accessed a specific course. It indicates how frequently learners revisit the course. Administrators can use this data to evaluate course effectiveness. |
| Visit Dates and Timestamps | The course access dates and times.<br>The column provides detailed information about the specific dates and times when a learner accessed a course. |
| Time Spent (mins) | Total time the learner spent in the course, in minutes. |
| Extension Enrollment State | Indicates if the enrollment was extended. |

## Download quiz score report

1. Select **[!UICONTROL Quiz Score Report]**.
2. Select the course instance for which you want to generate the quiz score report.
 
    ![]

3. Select **[!UICONTROL Generate]** to download the report.

## What does the quiz score report contain

Each row represents a single quiz attempt by a learner. Multiple attempts by the same learner are listed in separate rows.

| Column | Description |
|--------|-------------|
| Learner/Question | Name of the learner or quiz question reference.<br>Identifies the learner or labels the question section. In data rows, it contains the learner's full name, serving as the primary identifier for grouping attempts. In header rows, it marks the start of question-related columns.</br><br>In data rows, it contains the full name of the individual who took the quiz (e.g., "John Smith"). In header rows (e.g., row 1), it labels the start of the question columns. This column acts as the primary identifier for grouping attempts by learners. </br> <br><b>Note:</b> Learners with multiple attempts  appear in multiple rows. </br><br>Each quiz question has a pair of columns:</br><li>Quiz Score: The numerical score awarded for the question, reflecting correctness. Every question has a defined maximum score, and this field captures how much the learner scored out of that maximum (e.g., 0 for incorrect, 10 for correct).</li><li>Response: The learner's answer, either as a descriptive option (e.g., for multiple-choice) or Boolean (e.g., "True"/"False").</li><br>Each question has a maximum score, set by the course author, and the score obtained by the learner after attempting the question.</br>|
| Attempt Number | Indicates the attempt status (for example, Unattempted). Indicates the sequential number of the quiz attempt for the learner. This tracks retries or multiple submissions, allowing analysis of improvement over time. |
| Total User Score/Quiz Score | The learner's score over the total score (for example, 30.0/40.0). The cumulative score for the attempt, formatted as "achieved/maximum" (e.g., "30.0/50.0"). This summarizes overall performance. |
| Score Percentage | Score expressed as a percentage. The percentage of the total score achieved, calculated as (achieved / maximum) × 100. Used for quick performance assessment. |
| Email | The email address of the learner. |
| User Unique ID | Unique system-generated identifier for the learner. A unique alphanumeric identifier assigned to the user within Adobe Learning Manager. |
| Manager Name | The name of the learner's manager. |
| userState | The state of the user on the platform, for example, ACTIVE, INACTIVE, or DELETED. Even if a learner is DELETED in the platform and has taken a quiz, their records appear in the report. |
| Quiz question columns | Column(s) added for each question in a quiz (score and response). |
| Interaction Score | Score based on user interaction (maybe blank if unused). If the learner has attempted an interactive module for example, an Adobe Captivate SCORM module, their scores appear in the column. The score depends on the number of attempts set by the course author. |
| Quiz Score | The learner's score for the quiz. |
| Quiz Score Max | The maximum achievable score for the quiz. |

## Additional considerations for quiz report

**Multiple attempts in a module**

Exported quiz score report will contain the score details for every attempt if the multi attempt option is configured for the module.

**Quiz data unavailable**

When quiz data is unavailable, the message "No data available" will be displayed.

**Can a manager download a quiz report?**

Yes, a manager can download a quiz report if the backend flag quiz_report_visible_to_mgr is enabled from the course page.

**Connector support**

You cannot download a quiz report using [connectors](/help/migrated/integration-admin/feature-summary/connectors.md).







