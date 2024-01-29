---
description: Read this article to learn how to create and manage learning programs in Learning Manager
jcr-language: en_us
title: Learning Programs
contentowner: manochan
preview: true
---


# Learning Programs

Read this article to learn how to create and manage learning programs in Learning Manager

Learning programs are a set of uniquely designed courses meeting specific learner goals. Administrators create these learning programs for learners. You can view these learning programs as a learner.

## Create a learning program {#createalearningprogram}

Administrators can create learning programs. To create a learning program, follow the steps below:

1. Log in as Administrator. Click **[!UICONTROL Learning program]** on the left pane. Learning programs page appears with a list of existing learning programs if they are already created for your organization.
1. Click Add at the upper-right corner of the page. Add new learning program page appears.
1. Enter learning program name, overview, enter benefits of the program.
1. To create the learning programs in other locales, click Add New Language on top of the page. Select the languages that you need, and click Add. You may need to add all the learning program metadata in all the chosen languages. Else, the English information is displayed for other locales.  
1. Enter a unique Learning object Id for your learning program. The unique Id should contain only alphabets and numbers and no special characters. No two learning objects should have the same Id.
1. Choose the enrollment type as admin enroll or self enroll, as per your choice. Select the unenrollment option and course ordering options, and click Save. If you choose self enroll, the learners can enroll themselves to learning program.  

   Courses page appears to add courses to the learning programs. You can see Curriculum and Catalog tabs in it.   

   **Note** 

   All types of courses can be added to a Learning Program. These include classroom and virtual classroom courses, activity, self-paced, and blended courses. Manager nominated and manager approved courses do not appear during course selection in learning programs.

1. You have to add courses to learning program before publishing it. Click **[!UICONTROL Catalog]** tab to associate courses to the learning program. A list of all the available courses is displayed.  

1. Choose the courses you want to add to the learning program by hovering mouse pointer over any course card and by clicking it. If the course is not yet added to the learning program, you can view a + symbol at the middle of that course card.  

   To include more courses, repeat this step.  

   **Note** 

   View the list of all the added courses of your learning program in **[!UICONTROL Curriculum]** tab. Added label can be seen for the added courses, at the bottom of the course card in **[!UICONTROL Catalog]** tab.

1. Click **[!UICONTROL Back to programs]** on top of left pane, to view a list of all the learning programs. You can see your newly added learning program being listed there.
1. You can publish the learning program by clicking Overview in the left pane and choosing Actions>Publish. You can also publish the learning program through Courses and Instances view by clicking Publish at the upper-right corner of the page.

## Add learners to a learning program {#addlearnerstoalearningprogram}

For more information on enrolling learners and the steps to follow, see  [Enrolling Learners.](courses.md#main-pars_header_1058138132)

## Enable full catalog control for learning programs {#catalog}

Like granting full [catalog control for learning(s) or modules](shared-catalog-full-control.md), you can also enable full catalog control for learning programs.

## Reset course

An Administrator can reset the progress of a course inside a Learning Program.

From a Learning Program, the Administrator can reset the progress of the course.

To reset a course, Admin must select a course from Courses dropdown.

Then from the **[!UICONTROL Actions]** drop-down list, click **[!UICONTROL Reset Course]**.

Learners can now launch the modules of the selected courses from the start.

**Note: Only failed and incomplete modules of the course will be reset.**

## Create multiple instances of learning programs {#createmultipleinstancesoflearningprograms}

You can create multiple instances of a course or learning program.

1. Click Learning Programs from the left pane.
1. Click the learning program name in the courses/learning programs list of thumbnails.
1. Click Instances from the left pane.
1. Click Add New Instance on the right corner of the upper-right corner of the course information.
1. A new instance of the learning program is displayed.
1. Click the edit icons (as shown with red arrow in the snapshot) on the new instance to modify the course/learning program values such as deadline, instance name, feedback, and badge. After making the changes, click the tick mark adjacent to modified value to save the changes. Click X mark to cancel the changes.

An admin can add class room and virtual class room type courses to a Learning Program. Whatever session the author has given during the creation of the course becomes the default instance. When admin adds courses to a learning program, by default it is mapped to the default instance of all the courses but admin can change the instance mapping. The number of courses added into a learning program is also visible in instances page as shown below.

**Change instance mapping**

To change instance mapping, click on the course count in the Instance page. A course instance mapping box appears with a list of instances. You can now select instance mapping.

![](assets/change-instance-mapping.jpeg) 

## Create Flexible Learning Programs {#flexible}

Using Flexible Learning programs, learners can take trainings that are not restricted to what the default instance offers. An Admin creates different Instances to accommodate the learners' needs. This type of learning program is typically a classroom or VC session. To ensure that all learners are presented with the opportunity to attend, an Admin may create more than one Instance of a Course session to accommodate different time zones.

An Admin can also map an instance of a Learning program to an instance of a course that the Learner selects.

**Workflow**

1. Create a few courses with multiple instances.
1. Create a Learning Program and add some courses.
1. Create instances of the Learning Program.
1. Enroll the Learners.

## Subscription {#subscription}

An admin can fetch quiz score and learner status reports. They can set the report frequency, email subject, and recipients email id. Depending on the set frequency, the recipient will get an email with the report attached.

![](assets/report-subscription.jpeg) 

## View quiz scores {#viewquizscores}

1. Click any learning program tile
1. Click Quiz Score on the left pane.

You can view the quiz scores of any particular learning program based on user name or based on each question. Choose By User or By Question tabs accordingly.

Quiz scores appear for one course at a time. Change the course name from the drop-down to view the quiz scores for other courses. You can also export quiz scores of each course.

Choose the instance type from the drop-down list to view the scores based on each instance of the learning program.

## View L1 and L3 feedback {#viewl1andl3feedback}

As an admin, you can enable L1 and L3 feedback for a Learning Program. The L1 feedback given by the learner will be visible under the L1 feedback tab and the L3 feedback given by the manager will be seen under the L3 feedback tab.

## Unenrollment for learners {#unenrollmentforlearners}

While creating learning programs, Administrator has an option to select whether learners can unenroll themselves from the learning programs. If Administrator selects the option, then learner can unenroll themselves. 

![](assets/unenrollment.png) 

## Mark completion {#markcompletion}

Administrators can mark a Learning Program as complete using the option available to them. To mark the completion of Learning Program, use the following steps.

1. Open the **[!UICONTROL Learning Program]**.
1. Open the **[!UICONTROL Learners]** page from the menu on your left.

   The **[!UICONTROL Learners]** page opens with the list of enrolled learners.

1. Select one/multiple/all learners to mark LP completion using the checkbox available for each learner.
1. Click **[!UICONTROL Users]** > **[!UICONTROL Action]** > **[!UICONTROL Mark completion]**.

   If the LP has multiple courses, all the courses will be marked complete.

## Ordering of courses in learning program {#orderingofcoursesinlearningprogram}

Administrators can set the order in which learners shall take up the courses in learning program. After creating a learning program you can update this order of courses at any point in time. 

To update the order of courses in a learning program,

1. Click the learning program card of your choice and click **[!UICONTROL Courses]** on the left pane.

1. A list of course cards associated with the learning program is displayed. Click **[!UICONTROL Edit]** at the upper-right corner of the page. 
1. You can change the order of the list by clicking and dragging each course card to the appropriate position. 
1. Click **[!UICONTROL Republish]**.

## Editing a published learning program {#editingapublishedlearningprogram}

A learning program can be edited by an Administrator at a published state. At this state, the Administrator can edit all the sections of a learning program and re-publish. 

To edit a published learning program, click the learning program card and click **[!UICONTROL Edit]** at the upper-right corner of the page. 

While editing the sections of a learning program, if you have to move out of the page, you need to re-publish the learning program. You get a dialog confirmation asking you to re-publish the learning program. 
