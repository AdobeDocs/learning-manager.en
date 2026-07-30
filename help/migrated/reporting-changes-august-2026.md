---
description: This document summarizes August 2026 reporting changes in Adobe Learning Manager. It covers new and updated columns across Learner Transcript, Training, Enrollment, Waitlist, Attendance, Content audit, and user reports. It also explains adaptive course behavior, gradebook scoring, external learning records, Gen AI credit reporting, root certification tracking, timestamp standardization, and API author updates.
jcr-language: en_us
title: Reporting changes in the August 2026 release of Adobe Learning Manager
---

# Reporting changes in the August 2026 release of Adobe Learning Manager

The August 2026 release of Adobe Learning Manager introduces reporting enhancements across gradebook, external learning, Gen AI credit usage, and more. This article summarizes the new columns, reports, and behavioral changes available to administrators in this release.

## What has changed

The reporting updates span eight feature areas: gradebook scoring, external learning, incremental user exports, Gen AI credit usage, root certification tracking, and webhook timestamp alignment. The changes affect the following reports most significantly:

- Learner Transcript (LT)
- Training report
- Enrollment report
- Waitlist report
- Content audit report

Most updates introduce new columns. Some introduced new report types. A few changed how existing data is modeled or formatted.

<!--
## Adaptive course reporting changes

### Training report

Three new columns in the Training report support adaptive course behavior.

| **Column**               | **Description**                                          | **Supported Values**                                                   |
|--------------------------|----------------------------------------------------------|------------------------------------------------------------------------|
| Adaptive Learning Object | Identifies whether a course is adaptive                  | true (adaptive), false (non-adaptive)                                  |
| Visibility User Groups   | Lists user groups that can view each module              | One or more user group names (for example, All Learners, UG-Australia) |
| Mandatory                | Indicates whether a module is mandatory for a user group | User group names for which the module is mandatory; blank = optional   |

You can combine **Visibility User Groups** and **Mandatory** to interpret adaptive completion rules directly in the report. For example, a module may be visible to **All Learners** but mandatory only for the **Administrator group**.


### Learner Transcript

A new **Previous Completions** column captures historical completion data when adaptive logic triggers recompletion.

| **Sub-field**         | **Description**                         |
|-----------------------|-----------------------------------------|
| completionRefreshDate | Timestamp when the completion was reset |
| completedDate         | Previous completion timestamp           |
| progressAtRefresh     | Learner progress before reset           |
| gradeAtRefresh        | Learner score at the time of reset      |

The Learner Transcript now supports multiple completion cycles. When a recompletion event occurs, for example, due to course updates or new mandatory modules, the previous completion moves to the **Previous Completions** column. The current completion remains in the standard transcript fields.

### Enrollment report

A new **Waitlisted** column indicates whether a learner is waitlisted in any module within a course.

| **Value** | **Meaning**                                             |
|-----------|---------------------------------------------------------|
| true      | The learner is waitlisted in one or more modules        |
| false     | Learner has confirmed enrollment in all visible modules |

### Waitlist report

Two new columns and an enhanced status-detail support module enable waitlist tracking at the module level.

| **Column**      | **Description**                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Module**      | Name of the module (classroom or virtual classroom session) where the learner is waitlisted. Appears after the Instance Status column. |
| **Module ID**   | Identifier of the module where the learner is waitlisted. Appears after the Module column.                                             |
| **Embedded In** | The learning path name and ID of any learning path that contains this course. Blank if the course is not part of a learning path.      |

The Waitlist report has shifted from a course-level model to a module session–level model. A learner can now be enrolled in some modules and waitlisted in others. The report also supports waitlist tracking within Flex learning paths, where seat limits are enforced at the module level.

### LP Enrollment report

The Learning Path Enrollment report also receives a new **Remarks** column. When a learner is in a waitlisted state on any classroom or virtual classroom session within the courses that make up the learning path, the Remarks column shows **Waitlisted**. When all sessions are confirmed, the column is blank.

### Attendance report

The **Learner status** column now distinguishes between confirmed and waitlisted learners.

| **Value**  | **Meaning**                            |
|------------|----------------------------------------|
| Confirmed  | The learner has an allocated seat      |
| Waitlisted | The learner is pending seat allocation |

-->

## Gradebook reporting changes

### Learner Transcript

A new **Weight** column represents each scorable module's contribution toward the overall course score.

| **Value**                                    | **Description**                                      |
|----------------------------------------------|------------------------------------------------------|
| Numeric percentage (for example, 20, 30, 50) | Module's contribution to the course score            |
| Blank                                        | Module is not scorable (for example, PDFs or videos) |

### Content audit report

Two new events capture gradebook configuration changes.

| **Event**             | **Triggered when**                                              | **Captured data**                                        |
|-----------------------|-----------------------------------------------------------------|----------------------------------------------------------|
| Gradebook updated     | Gradebook is enabled, disabled, or modified at the course level | Change in gradebook state; grading configuration updates |
| Module weight updated | Weightage assigned to a module is modified                      | Module identifier; updated weightage value               |

The Learner Transcript reflects the latest weightage. The Content audit report tracks historical changes. Together, they give you a full picture of current scoring logic and how it has evolved.

## External learning reporting changes

### Learner Transcript

Three new columns are added to support external learning records.

| **Column**             | **Description**                                                                                     |
|------------------------|-----------------------------------------------------------------------------------------------------|
| External Learning Name | Name of the external learning activity submitted by the learner                                     |
| Custom fields          | One column per custom field configured for external learning (text, numeric, checkbox, or dropdown) |
| Completion Comment     | Manager remarks entered during approval or rejection                                                |

**Note:** In the Learner Transcript (learner self-service view), column placement differs from the Admin Learner Transcript:

- **External Learning Name** is added immediately after the existing **Module** column.

- **Completion Comment** is added immediately after the existing **Reviewer's remarks** column.

- Custom field columns (one per configured custom field) are appended at the end of the transcript.

In the Admin Learner Transcript, all new columns, including External Learning Name and Completion Comment, are appended at the end, followed by custom field columns.

### Type column in Learner Transcript

External learning entries now appear alongside existing learning objects (courses, learning paths, certifications) in Administrator LT. The **Type** column includes a new external learning classification for easy filtering.

External learning data flows into both the Learner Transcript and Admin LT. Core fields such as completion date, status, and score map to existing columns. Custom fields are appended as additional columns.

## Incremental user report changes

A new incremental export model lets you export only users whose data has changed within a specified time window, rather than generating full data exports each time.

| **Export mode**    | **Behavior**                                                    |
|--------------------|-----------------------------------------------------------------|
| Full export        | Returns all users in the account                                |
| Incremental export | Returns only users with changes within the specified date range |

To use incremental export, filter by **from date** and **to date** to define the change window. User reports are now generated using a data platform pipeline, and output is returned in chunks to support large accounts.

## Gen AI credit reporting

A new credit dashboard and two reports give administrators visibility into Gen AI credit consumption.

### Credit dashboard

The dashboard surfaces the following metrics at the account level.

| **Metric**        | **Description**                                   |
|-------------------|---------------------------------------------------|
| Purchased credits | Total credits provisioned for the account         |
| Used credits      | Credits consumed across AI-powered features       |
| Remaining credits | Available credits after consumption               |
| Per-feature usage | Credit consumption split by individual AI feature |

### New reports

| **Report**           | **Description**                                                                             |
|----------------------|---------------------------------------------------------------------------------------------|
| Monthly usage report | Summarizes credit consumption by month, feature, and credits consumed                       |
| Audit trail report   | Provides user-level details: user identifier, feature name, credits consumed, and timestamp |

## Other behavioral changes

### Root certification: Root Training ID

A new **Root Training ID** column is added at the end of both the **Admin Learner Transcript** and the **Learner Transcript** (learner self-service view). It captures the unique identifier that links all recurrences of a certification to a single root entity. This allows for associating all recurring instances of a certification with a single root ID for tracking and filtering.

### Webhook and Learner Transcript timestamp standardization

Webhook timestamps are now aligned to Learner Transcript formatting. Every date and time field within the **data object** of a webhook payload now has its seconds value set to 00, providing minute-level granularity consistent with Learner Transcript reports. This eliminates the need to normalize timestamp formats when comparing webhook data with Learner Transcript data.

### Author information in the API response for shared courses

When a course is shared from one Adobe Learning Manager account to another via catalog sharing, the API's learning object (LO) response now returns only the original author details from the source account. Previously, the accepting account's administrator appeared as the course author in the API response for their account

This change affects peer (receiving) accounts only. When you query the LO detail endpoint for a shared course in a receiving account, the authorNames field now reflects the original author from the source account, not the receiving account's administrator.

There is no change to how author details appear when querying the LO in the source account.

**Note:** If your integration relies on the authorNames field in the LO API response for shared courses, verify that the updated author data does not break any downstream logic that assumed the receiving account's administrator name would appear in this field.
