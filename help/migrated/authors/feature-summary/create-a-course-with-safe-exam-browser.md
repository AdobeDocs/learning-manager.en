---
title: Create a course with a Safe Exam Browser
description: Create a quiz with Safe Exam Browser mode and add it to a course as a self-paced module in Adobe Learning Manager to provide a restricted assessment environment.
---

# Create a course with a Safe Exam Browser

Authors can add quizzes to courses that require Safe Exam Browser to provide a secure, restricted assessment environment. Safe Exam Browser applies only to individual native Adobe Learning Manager quizzes and does not restrict access to other modules in the course.

Before adding the quiz to a course, ensure that Safe Exam Browser is enabled for the quiz. If the course includes other delivery types, such as virtual classroom modules, those modules continue to function independently of the Safe Exam Browser requirement. 

This article explains how to add a Safe Exam Browser-enabled quiz to a course and configure its settings for the course.

## Create a quiz with Safe Exam Browser mode

Safe Exam Browser mode determines whether Learners should use Safe Exam Browser to take the quiz. The option appears only after an Administrator enables Safe Exam Browser integration for the account. View **Enable Safe Exam browser** for more information.

To create a quiz with Safe Exam Browser mode:

1. Login to the ALM as an Author.
1. Select **Create Content**.

   The **Content Library** page appears.

1. Select **Add** > **Quiz**.

   The **Create Quiz** page opens.

1. Enter a name for the quiz in the **Name** field.
1. (Optional) Enter a description for the quiz in the Description field.
1. Select **Add quiz question** and add the **Passing Criteria**.
1. Enable **Safe Exam Browser mode**. The **Allow author to customize while Course creation** option appears.

   ![Safe Exam Browser mode setting on the Create Quiz page](assets/quiz-safe-exam-browser-mode-setting.png "Safe Exam Browser mode setting on the Create Quiz page")

1. (Optional) Enable **Allow author to customize while Course creation**.

   The Safe Exam Browser option appears when you configure the course code.

   >[!NOTE]
   >
   > If the Administrator enables this option, you can enable or disable the Safe Exam Browser (SEB) requirement for a course quiz module. If the Administrator disables this option, SEB becomes mandatory for the quiz, and you cannot change this requirement.

1. Select **Publish**.

## Add a Safe Exam Browser-enabled quiz to a course

Add the quiz as a self-paced module to require Safe Exam Browser for that assessment. Before you begin, ensure that the quiz is published with Safe Exam Browser enabled. View Enable afe Exam Browser for more information.

To add the quiz to a course:

1. Select **Create course** and enter the course name and description.
1. Select **Add Modules** from the **Modules** page.

   The Modules pop up appears.

1. Select **Self-paced learning**. The **Self Paced Module** dialog box opens.

   ![Self Paced Module dialog box listing available quiz modules](assets/self-paced-module-dialog-quiz-selection.png "Self Paced Module dialog box listing available quiz modules")

1. Select the checkbox next to the Safe Exam Browser quiz that you created.
1. Select **Add**. The quiz is added to the course as a self-paced module.
1. (Optional) To add another delivery type to the course, select **Add More Delivery Types** and configure the required module.
1. Select **Save** > **Publish**.

   The course now includes an assessment that requires Learners to use Safe Exam Browser.
