---
description: Learn how team submissions and rubric-based evaluation work in Adobe Learning Manager, and what each role does from setup to evaluation.
jcr-language: en_us
title: Team submissions and rubrics in Adobe Learning Manager
exl-id: fa22d160-770e-4a39-aa66-0f0c58eb1980
---

# Team submissions and evaluation in Adobe Learning Manager

Many training programs depend on two things: learners who collaborate on real work, and instructors who evaluate that work consistently. For example, a sales onboarding program might ask new hires to analyze a client in small teams. A group of coaches then reviews every submission against the same standards. Team submissions and rubric-based evaluation in Adobe Learning Manager support programs like this.

Team submissions allow learners in a course instance to collaborate and submit a single file for the team. One member uploads the file, the instructor evaluates it once, and the score and feedback go to every team member. Rubric-based evaluation lets an instructor assess a submission against criteria that the author defines, so every learner is measured against the same standards. You can use each feature on its own or together. A rubric works for both individual and team submissions.

>[!NOTE]
>
>Adobe enables team submissions for your account. If you don't see the team-based option, contact your Adobe Customer Success Manager or Adobe Support.

## Common use cases

These features suit cohort-based programs, such as employee onboarding, partner enablement, and customer education. Typical scenarios include the following:

* **Collaborative assignments.** A cohort of 25 new hires is divided into five teams of five. Each team analyzes a client company and its industry, and one member submits the team's analysis. The submission is complete for all five members, and the instructor evaluates it once.
* **Consistent evaluation across coaches.** An organization wants every coach to apply the same standards. The author builds a rubric with criteria such as brevity, personalization, and question type, each rated on a four-level scale. The overall score is calculated from the ratings, so results don't depend on who evaluates.
* **Detailed, actionable feedback.** Learners view their result for each criterion, their overall score, the instructor's written feedback, and the reviewer's name. They can apply that feedback in their next activity.
* **Shared review workload.** One cohort can have several coaches. Any instructor assigned to the course instance can evaluate its submissions, so coaches can divide the work and finish quickly.
* **Correcting mistakes.** An instructor evaluates the wrong learner, for example because two learners have similar names. The instructor unsubmits that submission and evaluates the correct learner. This works while the course isn't yet complete for the learner.

Use team submissions when the work is collaborative. Use a rubric alone when each learner submits individually but you need consistent evaluation.

## How team submissions work

Authors add a team-based file submission module to the course before they publish it. One course can mix team and individual submission modules, and all team modules in an instance share the same teams.

Instructors then divide the learners in each course instance into teams. They can create teams manually, or Adobe Learning Manager can create them automatically before the instance starts.

Any team member can upload the file for the team, and the instructor evaluates it as one submission. The outcome applies to every member of the team.

## How rubric-based evaluation works

A rubric is called an evaluation plan in the file submission module. Each module has at most one plan, and you can't reuse a plan in another module. The author describes the assessment and adds criteria. Instructors answer each evaluation parameter when they evaluate a submission.

* **Evaluation parameter** questions have answer options. With parameter-based scoring, each option has points.
* **Subjective** questions are open questions. The instructor enters a written response.

Authors can make a parameter optional, and can turn on remarks for each parameter and for the whole evaluation plan. Because every instructor responds to the same evaluation parameters, evaluation stays consistent across learners. The evaluation plan works for individual and team submissions.

## What each role does

* **Authors** add a team-based file submission module and an evaluation plan to a course, and then publish it. View how to add a team-based module.
* **Instructors** create teams for each course instance and evaluate each team's submission. View how to create and manage teams.
* **Learners** work with their team, submit one file for the whole team, and view the evaluation result. View how to submit as a team.
* **Administrators** can optionally turn on automatic team formation for the account. Team submissions work without it, and instructors can always create teams manually. View how to turn on automatic team formation.

## Where team submissions apply

Teams belong to a course instance, not to a learning path or certification.

* A team-based course can be part of a learning path or a perpetual certification. Teams form from the instance's enrolled learners, however they enrolled.
* If a learning path has several team-based courses, the instructor manages the teams for each course separately.
* A team-based course can't be part of a recurring certification.

## How teams are formed

Instructors create teams for each course instance from the learners who are enrolled in it. An instructor can create one team at a time or divide unassigned learners into several teams at once. Instructors can edit teams until a team submits its first file, which locks the team.

Optionally, Adobe Learning Manager can create teams automatically before an instance starts.

## How automatic team formation works

Instructors can create teams manually. If you want Adobe Learning Manager to create teams for you, an admin can turn on automatic team formation for the account, and authors then set the rules for each course. Adobe Learning Manager then creates teams for each instance before it starts. The feature does nothing unless the course has a team-based file submission module and the instance has a start date.

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
* **Members per team:** You set the size of each team. Adobe Learning Manager forms as many full teams of that size as it can. Any learners who don't fill a whole team are leftovers.

  * If the leftovers are half a team or fewer, each one joins a different team. Those teams end up one learner larger.
  * If the leftovers are more than half a team, they form one smaller team of their own.
  * If there aren't enough learners to form even one full team, all of them form one team.
  * If some teams already exist and have fewer members than the size you set, Adobe Learning Manager fills them first.

  With a team size of 5, one or two leftover learners join existing teams. Three or four leftover learners form a new team.

  | Learners | Result with a team size of 5 | Reason |
  |---|---|---|
  | 25 | 5 teams of 5 | No leftovers. |
  | 27 | 3 teams of 5 and 2 teams of 6 | 2 leftovers join two different teams. |
  | 28 | 5 teams of 5 and 1 team of 3 | 3 leftovers are more than half a team, so they form their own team. |
  | 3 | 1 team of 3 | Too few learners for a full team. |

* **Number of teams:** You set how many teams you want. Adobe Learning Manager divides the learners as evenly as possible, so the largest team is never more than one learner bigger than the smallest. A team is never empty. If there are fewer learners than teams, fewer teams are created.

  | Learners | Result with 5 teams | Reason |
  |---|---|---|
  | 25 | 5 teams of 5 | Divides evenly. |
  | 23 | 3 teams of 5 and 2 teams of 4 | The 3 extra learners go to three different teams. |
  | 3 | 3 teams of 1 | Fewer learners than teams, so only 3 teams are created. |

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
* **Reviewer approval is not required:** The module completes for every team member as soon as the team submits.

For scoring, the author chooses manual scoring or criteria-based scoring. With manual scoring, the instructor enters one overall score. With criteria-based scoring, the system calculates the score from the points on the selected options.

## What happens when an instructor unsubmits

Unsubmitting lets an instructor send a submission back so the team can submit again. For example, a team might have uploaded the wrong file, or a team member might have left and the team needs to change. An instructor can unsubmit only while the course isn't yet complete for the team members.

Unsubmitting involves the following:

1. **The instructor unsubmits** the submission and enters remarks. The module returns to the pending submission state, and the team unlocks. Team members receive a notification and an email. They don't see the earlier submission or comments.

1. **The instructor edits the team, if needed.** For example, the instructor removes a member who left.

1. **A team member uploads a new file.** Nothing is resubmitted automatically. The new file replaces the earlier one.

1. **An instructor evaluates the new submission.** The new evaluation replaces the earlier one, and Adobe Learning Manager doesn't keep the earlier evaluation.