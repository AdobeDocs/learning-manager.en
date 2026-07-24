---
description: All about the Gradebook from the learner's perspective
jcr-language: en_us
title: Gradebook for learners
---

# Gradebook for learners

## Start a course with gradebook

When the gradebook is enabled and visible for a course in Adobe Learning Manager, a **Gradebook** tab appears on the course overview page. Use it to see your weighted score for each module, your current aggregate score, and whether you have passed or still need to complete more of the course.

![](assets/image_0008.png)

## When the gradebook is available

The **Gradebook** tab appears alongside **Modules**, **Notes**, and **Discussions** in the course player when your author or administrator has enabled gradebook visibility for the course. If the tab is not visible, gradebook has not been enabled for this course, or the administrator has disabled learner visibility. Scores may still be recorded and visible to your administrator.

You can open the **Gradebook** tab at any point during your enrollment:

![](assets/image_0009.png)

* **Before starting:** After enrolling, you see the full list of scorable modules with their weightage percentages, the maximum marks for each, and the passing criteria set by the author. This shows you exactly how the course is graded before you begin.
* **While in progress:** As you complete modules and scores are recorded, the gradebook updates to show your scores so far alongside modules not yet attempted or awaiting grading.
* **After completing:** The gradebook shows all final module scores, your calculated aggregate course score, and a **Passed** result in the header.

## View the gradebook

* From **My Learning**, select your course.
* Select the **Gradebook** tab from the course page.

    The gradebook header shows:

    ![](assets/image_0010a.png)

* The **Passing criteria:** The minimum aggregate score and number of modules required
* The number of required modules you have completed out of the total
* Your current **Aggregate score** as a percentage
* Your current course status: **Not started**, **Completion pending**, **Passed**, or **Failed**

The module table below the header shows the following columns for each module:

| **Column** | **What it shows** |
|------------|-------------------|
| **Module** | The module name and type |
| **Status** | Your completion or score status for this module (see status reference below) |
| **Weightage** | The percentage this module contributes to your aggregate score |
| **Score** | Your score for this module (for example, 40/100) |
| **Contribution** | The actual percentage points this module has added to your aggregate score so far |

## View module weightage from the Modules tab

You can also see the weightage of each module from the **Modules** tab without opening the gradebook.

From your course page, select the **Modules** tab.

![](assets/image_0011.png)

The **Modules** tab displays the weightage percentage for each module and the number of modules required to complete the course.

## Module scores with multiple attempts

If a module allows multiple attempts, the score shown in your gradebook depends on how the course author configured it:

* **Highest:** The best score from any attempt is shown. A lower score on a later attempt does not reduce your recorded score.
* **Latest:** The score from your most recent attempt is always shown. A lower score on a later attempt replaces the previous one.

## Understand your module status

Each module in the gradebook shows one of the following statuses:

![](assets/image_0012.png)

| **Status** | **What it means** |
|------------|-------------------|
| **Completed** | Module finished and score recorded |
| **In progress** | Module started but not yet finished |
| **Not started** | Module not yet opened |
| **Failed** | Module scored and the score did not meet the module's passing threshold |
| **Pending review** | Module completed but waiting for a score from an instructor or admin |
| **No weightage** | Module type does not support scoring (PDF, video, and similar); does not contribute to the aggregate |

## How your aggregate score is calculated

Your aggregate score is the sum of each scored module's weighted contribution:

(Score achieved ÷ Maximum score) × Weightage % = Module contribution

The **Contribution** column in the gradebook shows each module's contribution to your current aggregate. Modules marked **No weightage** are excluded from this calculation.

The scoring scale does not need to be the same across all modules. A module scored out of 100, and a module scored out of 10, both contribute correctly. The formula normalizes each one before applying the weightage.

## View and report on gradebook scores

Administrators in Adobe Learning Manager can view weighted gradebook scores for all enrolled learners in a course, drill into individual learner performance by module, download a filtered Learner Transcript, and track gradebook configuration changes in the Content Audit Trail report.

## View the gradebook for a course

When gradebook is enabled for a course, a new **L2 Feedback – Gradebook** section appears in the left navigation under **Reports** when you open the course.

* Sign in to Adobe Learning Manager as an administrator.
* In the left navigation, select **Courses** and open the course you want to review.
* In the course navigation, under **Reports**, select **L2 Feedback – Gradebook**. The **Active Feedback Gradebook** page opens.

![](assets/image_0013.png)

It shows:

1. The passing criteria for the course (minimum modules required and minimum aggregate score)
2. A filter row to view learners by grade: **Passed**, **Failed**, or **Pending completion**
3. The aggregate score formula: Aggregate score = Σ (Score achieved ÷ Maximum score) × Weightage, for each module
4. A learner list showing each learner's **Aggregate score** and their score for each scorable module
5. An instance dropdown to switch between course instances when a course has multiple instances

Learners who have not yet attempted any scored modules show dashes in the score columns. Modules that do not support scoring, PDF, video, audio, and similar, do not appear as score columns.

## View an individual learner's scores

In the **Active Feedback Gradebook**, select a learner's name.

![](assets/image_0014.png)

The individual learner view shows:

1. The learner's name, email, and status (**Completion pending**, **Passed**, or **Failed**)
2. The aggregate score and how many required modules the learner has completed
3. A module table showing: module name, type, whether it is required, status, weightage, score achieved, and contribution to the aggregate

The module table includes all scorable and non-scorable modules. Scorable modules show their score and contribution. Non-scorable modules show dashes in the Score and Contribution columns.

## Score modules

Scoring behavior for administrators and instructors is unchanged from the current workflow:

* **SCORM, AICC, xAPI, and native quiz modules** are scored automatically when the underlying content reports a score.
* **Classroom sessions, virtual classroom sessions, and Activity modules** are scored by instructors or administrators from the **Attendance and Scoring** page.

## Download the Learner Transcript for a course

You can download a Learner Transcript filtered to this course directly from the gradebook page in one of the two ways:

* In the **Active Feedback Gradebook**, select **Download learner transcript** in the upper-right corner of the page.
* On the administrator home page, select **Reports**, and then select **Custom Reports**. Select **Learner Transcripts** from the list of available reports.

See Reporting changes in the release for more information.

## Content Audit Trail events

The Content Audit Trail captures two gradebook-specific configuration events:

| **Event** | **When it appears** |
|-----------|---------------------|
| **Gradebook updated** | When an author enables or disables gradebook for a course |
| **Module Weight Updated** | When an author changes the weightage percentage for a module |

See Reporting changes in the release for more information.

Use these entries to track who changed gradebook configuration and when, particularly in environments where multiple authors collaborate on the same course.

## Troubleshooting

**The L2 Feedback – Gradebook section does not appear in the course navigation**

Gradebook must be enabled by the course author when creating the course. Confirm that the author enabled the gradebook for course creation. If the course was created before the gradebook was available, it cannot be added retroactively. A new course version is required.

**A learner's aggregate score is 0 despite completed modules**

Confirm that the course has at least one scorable module with a weightage value assigned. If all modules the learner completed are non-scorable (PDF, video, audio), no aggregate score is calculated. Also, confirm that scored modules are not still in **Pending review** status. Ungraded modules are excluded from the aggregate until an instructor enters a score.

**The Weightage column is missing from the downloaded Learner Transcript**

This column appears only when the gradebook is enabled, and at least one module has a weightage value saved. Confirm the author enabled the gradebook and saved the weightage values totaling 100%.

**A learner has completed all required modules but shows Completion pending**

One or more modules may still be awaiting a score from an instructor or admin (**Pending review** status). The course cannot be completed until all required modules have both a completion and a score recorded. Enter the outstanding score from **Attendance and Scoring** to clear the pending state.
