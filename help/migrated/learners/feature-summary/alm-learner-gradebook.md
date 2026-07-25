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
* **After completing:** The gradebook shows all final module scores, your calculated aggregate course score, and a **Final grade** result in the header.

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
| ------------ | ------------------- |
| **Passed** | Module finished and score recorded |
| **In progress** | Module started but not yet finished |
| **Not started** | Module not yet opened |
| **Failed** | Module scored and the score did not meet the module's passing threshold |

## How your aggregate score is calculated

Your aggregate score is the sum of each scored module's weighted contribution:

(Score achieved ÷ Maximum score) × Weightage % = Module contribution

The **Contribution** column in the gradebook shows each module's contribution to your current aggregate. Modules marked **No weightage** are excluded from this calculation.

The scoring scale does not need to be the same across all modules. A module scored out of 100, and a module scored out of 10, both contribute correctly. The formula normalizes each one before applying the weightage.
