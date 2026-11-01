---
description: Learn how team submissions and rubric-based evaluation work in Adobe Learning Manager, and what each role does from setup to evaluation.
jcr-language: en_us
title: Team submissions and rubrics in Adobe Learning Manager
exl-id: fa22d160-770e-4a39-aa66-0f0c58eb1980
---

# Group (team) submissions and rubric based assessments

## Overview

Team submissions let learners in a course instance work together and submit one file for the whole team. Rubric-based evaluation lets an instructor assess a submission against criteria that the author defines. You can use each feature on its own or together.

>[!NOTE]
>
>Adobe enables team submissions for your account. If you don't see the team-based option, contact your Adobe Customer Success Manager or Adobe Support.

## How team submissions work {#how-team-submissions-work}

Instructors divide the learners in a course instance into teams. Any team member can upload the file, and the instructor evaluates it as one submission. The outcome applies to every member of the team.

Authors add a team-based file submission module to the course. Teams can be created manually by an instructor or automatically before the instance starts. One course can mix team and individual submission modules. All team modules in an instance share the same teams.

## How rubric-based evaluation works

A rubric is called an evaluation plan in the file submission module. Each module has at most one plan, and you can't reuse a plan in another module. The author describes the assessment and adds criteria. Instructors answer each criterion when they evaluate a submission.

* **Objective** has answer options. With criteria-based scoring, each option has points.
* **Subjective** questions are open questions. The instructor enters a written response.

Authors can make a criterion optional, and can turn on remarks for each criterion and for the whole assessment. Because every instructor answers the same criteria, evaluation stays consistent across learners. The evaluation plan works for individual and team submissions.

## What each role does

* **Admins** turn on automatic team formation for the account. View [how to turn on automatic team formation](/help/migrated/administrators/feature-summary/settings/basic-settings.md#enable-auto-team-formation).
* **Authors** add a team-based module, create the evaluation plan, and publish the course. View [how to add a team-based module](/help/migrated/authors/feature-summary/courses.md#add-team-based-submission-module).
* **Instructors** create teams and evaluate submissions. View [Create and manage teams](/help/migrated/instructors/feature-summary/learners.md#create-manage-teams).
* **Learners** view their team and upload the team file. View [Submit an assignment as a team](/help/migrated/learners/feature-summary/submit-assignment-as-team.md).

## Where team submissions apply

Teams belong to a course instance, not to a learning path or certification.

* A team-based course can be part of a learning path or a perpetual certification. Teams form from the instance's enrolled learners, however they enrolled.
* If a learning path has several team-based courses, the instructor manages the teams for each course separately.
* Automatic team creation uses the course instance start date, not a learning path date.
* A team-based course can't be part of a recurring certification.
* Adaptive courses don't support team-based modules.

## How automatic team formation works

When an admin turns on automatic team formation and an author sets the rules for a course, Adobe Learning Manager creates teams for each instance before it starts. The feature does nothing unless the course has a team-based file submission module and the instance has a start date.

**When are teams created**

* Teams are created once for each instance, at 12:00 am on the lead-time day, in the time zone of the instance. With a lead time of 3 days, teams are created at 12:00 am three days before the start date.
* Creation happens before any submission, not at submission time.
* No creation job runs if the instance has no start date, or if the start date is closer than the lead time. Instructors then create teams manually.
* If the start date moves later, the job is scheduled again.

**Which learners are included**

* Only learners who are enrolled and not yet on a team when the job runs.
* Learners who enroll later stay unassigned until an instructor adds them.

**How learners are assigned**

* The author chooses one rule for the course: **Members per team** or **Number of teams**. The value must be 1 or higher.
* A team can have up to 100 members.
* With **Members per team**, teams below the size are filled first, then full teams form. Leftover learners join existing teams one each if there are half the team size or fewer. If there are more, they form a new team.
* With **Number of teams**, learners are divided evenly, so team sizes differ by at most one. If there are fewer learners than teams, fewer teams are created. No team is ever empty.

**What automatic formation doesn't change**

* It never moves or removes a learner who is already on a team.
* It doesn't change locked teams.
* If everyone is already on a team, nothing happens.
* Teams that instructors created manually are not regrouped.

**After teams are formed**

* Instructors can rename teams, move learners, create teams, and delete teams. Learners can't change teams.
* Automatic teams behave like manual ones. Any member can submit, the submission belongs to the team, and the instructor's evaluation applies to every member.
* A team locks after its first submission. Unsubmitting unlocks it.

## How approval and scoring affect completion

The author controls what happens after a team submits.

* **Reviewer approval is required:** The instructor must approve or reject the submission. The module completes only after approval.
* **Reviewer approval is not required:** The module completes for every team member as soon as the team submits. The instructor can evaluate once, but the approve and reject options don't appear.

For scoring, the author chooses manual scoring or criteria-based scoring. With manual scoring, the instructor enters one overall score. With criteria-based scoring, the system calculates the score from the points on the selected options.

## What happens when an instructor unsubmits

An instructor can unsubmit a submission when the course isn't yet complete for the team. The team unlocks, and the module returns to the pending submission state. Learners receive a notification and an email. A new submission replaces the earlier one, and the new evaluation replaces the earlier evaluation.
