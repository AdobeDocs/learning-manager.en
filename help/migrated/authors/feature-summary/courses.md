---
description: To learn how to create courses, certifications, and learning programs in Learning Manager, read this article.
jcr-language: en_us
title: Creating, modifying, and publishing courses
contentowner: manochan
exl-id: c5257796-0afa-4021-bd17-d3f1e9a86948
---
# Creating, modify, and publish courses

To learn how to create courses, certifications, and learning programs in Learning Manager, read this article.

Authors can create learning objects such as courses, certifications, and learning plans. Learners can consume these learning objects, while administrators can track learners' progress.

## Courses in Learning Manager {#coursesincaptivateprime}

Adobe Learning Manager enables authors to create courses using one or more modules related to virtual training, self-paced training, classroom training, and activities. Administrators can further use these courses to create course instances, enroll learners, assign badges, and enable feedback for these courses. They can also create learning programs, learning plans, and certifications using these courses.

Authors can use e-learning content that is created using any eLearning tool. Other supported course formats include video files, PDF, doc, docx, PPT, and PPTX.

## Create a course - Basic workflow {#createacoursebasicworkflow}

To create a course, follow the steps below:

1. Log in to Adobe Learning Manager as an Author, as only authors have the rights to create courses. Now, on the Getting Started page, click **[!UICONTROL Create Courses]**.
1. On the **Course Overview** page, enter the name of the course. Now, enter a short description for this course, which is displayed on the course card. This description must not be more than 140 characters. Then enter the detailed overview for the course, which is displayed on the Course Details page. The description must not exceed 1500 characters.

   As an author, you can see the description of the modules while adding the module to a course.

1. To make your course available in other languages, click Add New Language from the upper-left corner of the page. Select the language or languages in which you want to make your course available. Click **[!UICONTROL Save]**. For more information, see [Add content for different languages](/help/migrated/authors/feature-summary/content-library.md).
1. **Modify course settings**-

   1. On the Course Settings page, choose a skill for the course. From the Skill drop-down list, choose the required skill. Then, from the Level drop-down list, choose the required level.
   1. Choose the course skills, level, and set the credits for the skill. Add more skills, if required.
   1. From the **Enrollment Type** drop-down list, choose the type of enrollment.

   The following are the types of enrollments:

   * **Manager nominated:** Only managers can nominate these courses. A learner cannot enroll to these types of courses.
   * **Manager approved:** Managers approve these courses. Learners can sign up for these courses, but they are not enrolled directly to these types of courses without Manager's approval. A notification request is sent to Managers when learners sign up for these types of courses. Upon Manager approval, these courses are listed as enrolled for learners.
   * **Self-enrolled:** Learners can directly enroll themselves to these types of courses.

1. To save the changes, click **[!UICONTROL Save]**. To publish the course, click **[!UICONTROL Publish]**.

## Create a course - Advanced workflow {#createacourseadvancedworkflow}

1. Log in to Adobe Learning Manager as an Author, as only authors have the rights to create courses. Now, on the Getting Started page, click **[!UICONTROL Create Courses]**.
1. On the **Course Overview** page, enter the name of the course. Now, enter a short description for this course, which is displayed on the course card. This description must not be more than 140 characters. Then enter the detailed overview for the course, which is displayed on the Course Details page. The description must not exceed 1500 characters.
1. To make your course available in other languages, click Add New Language from the upper-left corner of the page. Select the language or languages in which you want to make your course available. Click **[!UICONTROL Save]**. For more information, see [Add content for different languages](/help/migrated/authors/feature-summary/content-library.md).
1. **Modify course settings**-

   1. On the Course Settings page, choose a skill for the course. From the Skill drop-down list, choose the required skill. Then, from the Level drop-down list, choose the required level.
   1. Choose the course skills, level, and set the credits for the skill. Add more skills, if required.
   1. Add the custom compliance labels to the course, if required. See [Add compliance labels to course/learning path/certification](/help/migrated/authors/feature-summary/courses.md#add-compliance-labels-to-courselearning-pathcertification). 
   1. From the **Enrollment Type** drop-down list, choose the type of enrollment.

   The following are the types of enrollments:

   * **Manager nominated:** Only managers can nominate these courses. A learner cannot enroll to these types of courses.
   * **Manager approved:** Managers approve these courses. Learners can sign up for these courses, but they are not enrolled directly to these types of courses without Manager's approval. A notification request is sent to Managers when learners sign up for these types of courses. Upon Manager approval, these courses are listed as enrolled for learners.
   * **Self-enrolled:** Learners can directly enroll themselves to these types of courses.

1. Choose if you want to set a price for your course or make it free. If you want to make the course paid, choose the option **[!UICONTROL Paid]**, and specify a price. The price then appears on the Course card and the Course overview page for a learner.

   NOTE: This is only enabled when Adobe Commerce connector is configured.

1. If you want to provide the ability for learners to unenroll themselves from your course, enable the check-box **Learners can unenroll themselves**.

1. **Instance Configuration**

   If you enable this option, learners who are in the state, In Progress,  can visit other instances and enroll there. A learner can then retain the progress of the previous instance.

   After publishing the course, if you come back to the Settings page, the option is no longer editable.

   You can enable the option for the following course types:

   * Self-paced
   * Classroom
   * Activity
   * Blended

   Note: While duplicating a course, if you had enabled the option Instance Configuration in the source course, the option remains disabled in the destination course.

   **Instance Switch isn't supported for**:

   * Paid courses
   * Manager-nominated enrollment-type courses.

   Instance switch configuration will not be propagated to peer accounts if shared through the catalog, the option remains disabled in the destination course.

1. **Multiple enrollments**

   Using this, you can enroll learners in more than one course instance at one or different periods.

   Enable the toggle **Multiple Enrollment** to switch between various course enrollments of a learner. If you've enabled Instance Switch, you cannot use Multiple Enrollment.

1. Select the pre-requisite courses that must be completed before taking up your course. Click the Courses field and choose from the list of courses.
1. Enable the **Enable** **Prerequisites** check-box if you want the pre-requisite courses to me made mandatory.
1. Add keywords as tags related to your course. These tags help the learners to locate your course easily during search. All these tags are automatically added based on the modules that we have added. If you have other tags that you want to add to this course, you can go ahead and enter it.
1. Add keywords as tags related to your course. These tags help the learners to locate your course easily during search. All these tags are automatically added based on the modules that we have added. If you have other tags that you want to add to this course, you can go ahead and enter it.
1. In the Auto Retire field, select a date when the course retires. The Administrator must enable the Auto Retire option first.
1. To save the changes, click **[!UICONTROL Save]**. To publish the course, click **[!UICONTROL Publish]**.

### Add compliance labels to course/learning path/certification {#add-custom-compliance-label}

To add the compliance labels to courses, follow these steps:

1. In the author app, go to **[!UICONTROL Courses]**/**[!UICONTROL Learning Paths]**/**[!UICONTROL Certifications]** and select **[!UICONTROL Add]**.
1. Type the name and other details such as description, skills, etc.
1. In the **[!UICONTROL Custom compliance]** text box, type and select the compliance label.
 
   ![](assets/add-compliance-label.png)
   _Add custom compliance_

   >[!IMPORTANT]
   >
   >Make sure to set a deadline for the course when you're adding Custom Compliance

1. Save and publish the course/learning path/certification. 
Now the course/learning path/certification is considered as compliance type. Admins can add this course to the compliance dashboard and share it with managers to track the progress

>[!NOTE]
>
>Authors can also add the compliance labels to an existing course/learning path/certification by editing them. 

## Gamification points

You can allocate gamification points at the course and course instance levels. With this, you can award points to different courses or instances. Learners are incentivized to take specific courses or prefer a particular course instance over others.

1. At the course instance level, select **[!UICONTROL Gamification Points]**.

![gamification points](assets/select-gamification-points-new.png)

*Set points for gamification*

1. Select **[!UICONTROL Edit]**.
1. If you select Use course level settings, the following options display: 

   * **[!UICONTROL On completion]**: Select this toggle if you want the learner to get 100 points when they complete a course.
   * **More rules**

     * **[!UICONTROL Early completion]**: If you select this, the first 30 learners are awarded 100 points when they complete a course.
     * **[!UICONTROL Timely completion]**: If you select this, learners are awarded 100 points if they complete a course within 999 days.

1. If you select **[!UICONTROL Use custom settings]**, the following options display:

   * **[!UICONTROL On completion]**: Select this toggle if you want the learner to get 100 points when they complete a course.
   * **More rules**

      * **[!UICONTROL Early completion]**: If you select this, you can determine how many learners will be awarded specified points.
      * **[!UICONTROL Timely completion]**: If you select this, you can determine the number of points learners will be awarded if they complete a course within a specified time.

   ![gamification points](assets/gamification-custom-settings.png)

   *Set early and timely completion*

1. Select **[!UICONTROL Save]**.

## Aggregate learning resources

An author can decide if they want to aggregate the learning resources at the Learning Plan level or let them remain at an individual course level.

As an author, select **[!UICONTROL Learning Path]** > **[!UICONTROL Settings]**. Click **[!UICONTROL Edit]**.

In the **[!UICONTROL Resources]** section, the checkbox, Show constituent course resources aggregated at Learning Path level, when enabled displays whether resources present at course level would be shown on Learning Path level.

>[!NOTE]
>
>On the Settings page of a Learning Path, an Admin can also enable this option, which displays resources present at the course level that would be shown on the Learning Path level.

## Scheduling Assistant

Manage conflicts in booking instructors and classrooms. If you want to know at what time and date any instructor is available before assigning him to the course, use the Scheduling Assistant.

While creating a course, for a VC or CR course, click Scheduling Assistant.

![Select Scheduling Assistant](assets/scheduling-assistant.png)

*Launch scheduling assistant*

The Scheduling Assistant window launches.

![Scheduling Assistant screen](assets/scheduling-assistant-window.png)

*The Scheduling Assistant dialog*

On the Scheduling Assistant, you can:

* Search instructors by their names.
* Search instructors by their skills.

### Search instructors by their names

On the Instructor field, type the name of the instructor or search for a partial instructor name. A list of instructors appear, from which you can choose an instructor.

![Search instructors by name](assets/search-instructor.png)

*Search for instructors*

Multiple instructors can be selected but only one instructor can be assigned at a time. The selected time will be highlighted in the time conflict window. Near the instructor, a cross icon appears, which you click to remove the instructor.

![Select multiple instructors](assets/busy-times.png)

*Search for multiple instructors*

### Search instructors by skills

Search for an instructor with single or multiple skills. The search uses the AND operator.

Skills can be searched by partial or complete skill name only, not by skill level.

On the Assistant, enter the name of the instructor, location, and seat limit.

Also, you can search skill, which would be displayed after clicking on the filter icon present on the right side of Instructor search box. The screenshot below displays the button.

![Enter skills for instructor](assets/scheduling-assistant-instructor-skill.png)

*Search for instructors by skills*

### User group filter

Select the filter in the Instructor field. There is a **[!UICONTROL User Group]** filter an Author or Custom Author can find the right instructor by using the values in the User Group.

If both filters are applied, a list of instructors displays who belong to the user group and has the selected skills.

This applies to Scheduling Assistant on the Courses or Instances page.

![scheduling assistant](assets/scheduling-assistant-2.png)

*Filter by User Groups*

### Instance page

You can also access the Scheduling Assistant from the Instance page, as shown below.

The Scheduling Assistant is also available on the Instance page as well for admins, and custom admin/author. 

![Scheduling Assistant from the Instance page](assets/instances-scheduling.png)

*Schedule instructors from Instances page*

### Search for a location

You can search for a location by specifying both the classroom name and the location region name on both the module and the Scheduling Assistant pages.

## Rich Text Formatting

While creating a Course, Learning Program, Certification, or Job Aid, Authors can input different types of content such as text, image, or apply various text formatting options.

When creating a course, you can see the Rich Text Editor in the Course Overview field. You can format your content, add images, add hyperlinks, and so on.

![](assets/rich-text-editor-author.png)

*Launch the Rich Text Editor*

Similarly, you can use the Rich Text Editor to modify the description when creating a:

**Learning Program**

![](assets/lp-rte-new.png)

*Use Rich Text Editor for a Learning Program*

**Certification**

![](assets/cert-rte-new.png)

*Use Rich Text Editor for a Certification*

**Job Aid**

![](assets/job-aid-rte-new.png)

*Use Rich Text Editor for a Job Aid*

In addition, you can use the Rich Text Editor for other languages. 

## Rich text description support for headless user Interface

### Why is CSS required?

Rich text is composed of HTML markup. Rendering the markup as-is would result in default styling applied by the browser. This often doesn't go well with the style guidelines of the company. A CSS is required to meet the guidelines.

### Default style

The attached CSS stylesheet contains the styling that is applied by Learning Manager. The styling is tweaked considering majority of the usecases. Download the attached CSS file and import it to your webapp according to your conventions and build system. The CSS classes defined are namespaced under ql-editor class and they don't interfere with your existing styles.

### Customize styles

The default styling may not meet everyone's needs. The customisations can be done by overiding CSS supplied. All the styling is wrapped under ql-editor as descendant selectors. The following classes are used:

* Indenting: **li.ql-indent-$number**. $number varies from 1-9
* size: **ql-size-small**, **ql-size-large**, **ql-size-huge**

* alignment: **ql-align-center**, **ql-align-justify**, **ql-align-right**

* color: **ql-color-$color**. $color = white, red, orange, yellow, green, blue, purple
* background: **ql-bg-$color**. $color = black, red, orange, yellow, green, blue, purple
* html tags: p, ol, ul, pre, blockquote, h1, h2, h3, h4, h5, h6

[CSS file to be used for customization.](assets/ql-headless.css)

### API CHANGES TO ENABLE RENDERING RICH TEXT OVERVIEWS

When customers build a headless interface, they have a need to display the learning objects in that custom user interface they are developing. For doing this, one would typically use the [GET /learningObjects](https://learningmanagereu.adobe.com/docs/primeapi/v2/#!/learning_object/get_learningObjects) API that is exposed. Now that Learning Manager supports capturing "rich text" for the overview field, the data model of Learning Objects in the API responses also exposes the same. See the field named "richTextOverview" in the fragment of the model in the API response below. Also note that the field exposed earlier ("overview") remains unchanged for backward compatibility.

```
{ 
 "data": [ 
 { 
 "id": "string", 
 "type": "string", 
 "attributes": { 
 … 
 "localizedMetadata": [ 
 { 
 "description": "string", 
 "locale": "string", 
 "name": "string", 
 "overview": "string", 
 "richTextOverview": "string" 
 } 
 ], 
 … 
 }, 
 "relationships": { 
 … 
 } 
 } 
 } 
 ] 
} 

```

Customers who are already using the overview field remain unaffected in their headless interface will see just plain text as before. If customers want to take advantage of the rich text overview, they will have to create richly formatted overviews for their learning objects in the Author UI and after that Learning Manager will start returning the rich text overview as well, in addition to the plain text (as before) in the API response model.

However, to render this rich text in their UI, the customer will need to include a CSS. This is explained in detail in the following sections.

## Allow multiple attempts {#allowmultipleattempts}

Once the admin has enabled multi attempts, as an author you can configure multi attempts for an interactive e-learning module at a course or module level.

![](assets/allow-multipe-attempts.png)

*Configure multi attempts for an interactive e-learning module*

<table>
 <tbody>
  <tr>
   <td>
    <p><b>Option</b></p></td>
   <td>
    <p><b>Description</b></p></td>
  </tr>
  <tr>
   <td>
    <p>Set Attempts at</p></td>
   <td>
    <p>You can set the number of attempts for a module to infinite or provide a definite limit.<span style="font-size: 0.8125rem;">The attempt information will be shown to the learner once it is enabled. The learner can choose to reattempt the module by clicking on the 'Reattempt' button.</span></p></td>
  </tr>
  <tr>
   <td>
    <p>Stop new attempt once module is completed or passed</p></td>
   <td>
    <p>To configure when to stop learners from selecting the new attempt option, enable the check-box "Stop new attempt once module is completed or passed". The 'Reattempt' option will be removed from the learner view once they successfully complete the module.</p></td>
  </tr>
  <tr>
   <td>
    <p>Lock module between attempts 0:0:1 Format: Days/Hours/Minutes</p></td>
   <td>
    <p>You can lock modules for a specific time between attempts, by enabling the check-box "<b>Lock module between attempts 0:0:1 Format: Days/Hours/Minutes</b>". When a module is locked, the learner cannot visit the module until the lock time provided elapses. </p>
    <p>ou can define the end criteria of an attempt by selecting the '<b>Player close</b>' or '<b>Completion</b>' check-boxes.</p></td>
  </tr>
  <tr>
   <td>
    <p>Player Close</p></td>
   <td>
    <p>Every module launch is treated as a new attempt if the criteria is selected as '<b>Player Close</b>'. A learner is prompted with module lock details and attempt details on closing the player.</p></td>
  </tr>
  <tr>
   <td>
    <p>Completion</p></td>
   <td>
    <p>If the end of an attempt is based on <b>Completion</b>, then it will be calculated based on the content success criteria. Learners are not allowed to re-attempt the module until the content sends the completion information. Module lock and attempt details are communicated to the learner once an attempt ends.</p></td>
  </tr>
  <tr>
   <td>
    <p>Set time limit to complete module</p></td>
   <td>
    <p>Authors can set a time limit to complete a module by the enabling the check-box, "<b>Set time limit to complete module</b>".</p>
    <p>Every player launch is considered as a new attempt and the learner is prompted with the time details during launch.</p>
    <p><b>Note:</b><span style="font-size: 0.8125rem;">The attempt will end automatically once the time elapses. Closing the player as well will end the current attempt.</span></p></td>
  </tr>
  <tr>
   <td>
    <p>Multi attempts at Module level</p></td>
   <td>
    <p>Selecting an attempt at 'Module level' from the 'Set Attempt at' drop-down list allows you to configure the options at individual module level.</p></td>
  </tr>
 </tbody>
</table>

## Course modules {#coursemodules}

### Add modules {#addmodules}

You can now add Content, Prework, and Testout modules. **Content** modules are the main modules that make up the course. **Prework** modules include some basic information, which can help learners get ready for the course. These modules are not mandatory for the learners to complete. **Testout** modules help learners skip the content and take the test if they are already aware of the content and want to take the test to fulfill the compliance requirement.

To add a content module, perform the steps below:

1. Click **[!UICONTROL Add Modules]**. You can see four options to add modules. The first option is to add Self Paced Modules. These are the modules that you create and add to the module library in Adobe Learning Manager. These second option is to set up the Virtual Classroom. The third one is to set up a Classroom Module, and the fourth is Activity Module.

   ![](assets/select-module-type.png)

   *Add a module for a course*

   **Self Paced Module:** In this mode, you can start and complete a course module at your own pace. You can set your own schedule.

   After you click the option, you can see the list of self-paced modules that have been already added to your module library. Here you can either scroll through the list and select the ones you want to add, or you can search for the modules by typing the module's name in the search field or the module tags.

   After you have selected the modules, click **[!UICONTROL Add]**. These modules now appear under the Content section.

   You can also rearrange the modules. Drag any module and move it up or down and arrange the modules in a proper sequence.

   **Virtual Classroom Module:** In this mode, learners can attend live online lectures, facilitated by a trained instructor. Enter the title, description, and set the duration of the session. You can also specify the conference url and the instructors to conduct the session. To save the changes, click **[!UICONTROL Done]**.

   ![](assets/1st-image.png)

   *Add a VC module*

   When creating a course using the Virtual Classroom configuration dialog box, set the **Conferencing System** to the Teams connection that you created. Select whether you want a meeting organizer for the event.

   If you select **Yes** for a meeting organizer, you must enter the name of the organizer. Type the name and select the organizer.

   **Lobby bypassing**

   * If you select **Yes**, any learner can join the meeting.
   * If you select **No**, a request is sent to the organizer to allow or prevent the learner from joining the meeting.

   **Note:** A learner must be available on Microsoft Teams. However, the learner can join Learning Manager as a guest.

   **Classroom Module:** In this mode, learners attend in-person lectures, facilitated by a trained instructor. Enter the title, description, and set the duration of the session. You can also specify the location of the class and the instructors to conduct the session. To save the changes, click **[!UICONTROL Done]**.

   ![](assets/classroom-module.png)

   *Add a classroom module*

   When creating a course, in the Virtual Classroom configuration dialog box, set the conferencing system to the Microsoft Teams connection that you created. Select whether you want a meeting organizer for the event.

   If you select Yes for a meeting organizer, you must enter the name of the organizer. Type the name of the organizer and select the organizer.

   **Lobby bypassing**

   * If you select Yes, any learner can join the meeting.
   * If you select No, a request is sent to the organizer to allow or prevent the learner from joining the meeting.

   **Note:** If a learner wants to join Microsoft Teams as guest, he/she must enter the email. The email must be present in Learning Manager.

   **Activity Module:** In this mode, learners must complete a set of activities, such as, workshops, exercises, questionnaire, and other learning activities. Enter the title, description, and the external url for reference. To save the changes, click **[!UICONTROL Done]**.

   ![](assets/activity-module.png)

   *Add an activity module*

   You can specify the duration while adding an activity module in a course for activity type File Submission and xAPI-based modules. 

1. Similarly, add modules for Prework and Testout modes.
1. Choose the sequencing type for modules as Ordered or Unordered based on your preference.

   If you choose **Ordered**, the modules appear in the same sequence as you created them. If you choose **Unordered**, the modules are not sequenced. Learners can complete the modules in any order.

1. From the Mandatory Modules drop-down list, choose the number of modules that the learner must take to complete the course.
1. Add a cover image and the banner image for the course. The catalogs are created by the administrator. For more information, see [Catalogs](/help/migrated/administrators/feature-summary/catalogs.md).

   **Note:** The recommended dimensions are:

   * **Cover image:** 300 px x 300 px
   * **Banner image:** 1600 px x 140 px

1. On the top-right corner of the page, click **[!UICONTROL Save]**.

#### Add HTML link in the Activity Module

Authors can add HTML links in the activity module and set the completion criteria. To add an HTML link and set a completion criteria, follow these steps:

1. In the author app, select **[!UICONTROL Create Courses]** on the home page.
1. In the **[!UICONTROL Course Catalog]** screen, select **[!UICONTROL Add]**.
1. Type the name and description of the course.
1. In the **[!UICONTROL Module]** option, select **[!UICONTROL Add Module]** > **[!UICONTROL Activity Module]**.
1. In the **[!UICONTROL Activity Module]** prompt, type the name and description.
1. Select the **[!UICONTROL Type]** as **[!UICONTROL External URL]**.
1. Select any of the following options from the **[!UICONTROL Completion Criteria]** option.
   * **[!UICONTROL Learner marks complete]**: The learner has the option to mark the course as complete in the Fluidic Player.
   * **[!UICONTROL On Launching content]**: The course will automatically be marked as complete, when the learner launches it.
 
   ![](assets/completion-criteria-activity-module.png)
   _Completion criteria_

1. Select **[!UICONTROL Add]** and publish the course.

## Checklist {#create-checklist}

Evaluation is an important aspect of any LMS. Online assessments are one of the top ways of evaluating a learner's understanding of a topic. But often, it's necessary to evaluate a person's understanding while she's/he's on the job by observing him/her carry out the necessary tasks.

Consider store employees or warehouse workers undergoing evaluation for the tasks they are supposed to carry out on a day to day basis. It could be the steps carried out to repair a coffee machine or the steps involved in packing a material. Instructors can evaluate employees for such tasks based on a checklist and evaluate them as Pass or Fail in the evaluation activity.

### Create a checklist {#createachecklist}

Only an Author can create a checklist. A checklist is a type of Activity module. While setting up an Activity module, you, an Author, can select an Activity as **Checklist**, as shown below: 

![](assets/checklist-option.png)

*Create a checklist*

Once you choose the option **Checklist**, you see a few additional options.

**Checklist Type:** Choose any option, **Yes/No** or **1-5**. If you choose Yes/No, the checklist will contain questions that can only be answered with Yes or No. If you choose 1-5, you can see a Likert checklist, where you can grade a question on a five-point scale.

**Pass Criteria:**

<table>
 <tbody>
  <tr>
   <td>
    <p>If you had chosen <b>Yes/No</b>, then...</p></td>
   <td>
    <p>If you had chosen <b>1-5</b>, then...</p></td>
  </tr>
  <tr>
   <td>
    <p>Set the pass criteria as the number of responses as Yes. For example, if you enter 3, then the learner passes the course, if he/she receives at least three <b>Yes </b>responses, when evaluated by an Instructor.</p></td>
   <td>
    <p>Set the pass criteria as a threshold of any number between 1-5. For example, if you enter 2 and 4, then the learner passes the course, if he/she attains at least <b>two </b>evaluations that have score greater than or equal to <b>four</b>.</p></td>
  </tr>
 </tbody>
</table>

Choose an instructor or instructors who will evaluate the learner.

Also, if you have anything to comment or a note, you can add that in the **Note to instructor** text field.

Now, add the checklist questions. Click **[!UICONTROL Add]**. You can only add up to 150 questions.

![](assets/add-checklist-questions.png)

*Add checklist questions*

To add more questions, click **[!UICONTROL Add more]**.

Save the changes, add the module, and publish the course.

### Add skills {#addskills}

On this page, enter the following details:

1. Choose the course skills, level, and set the credits for the skill. Add more skills, if required.

   ![](assets/course-skills.png)

   *Add skills for a course*

1. Choose the type of enrollment. The following are the options:

   * **Manager nominated:** Only managers can nominate these courses. A learner cannot enroll to these types of courses.
   * **Manager approved:** Managers approve these courses. Learners can sign up for these courses, but they are not enrolled directly to these types of courses without Manager's approval. A notification request is sent to Managers when learners sign up for these types of courses. Upon Manager approval, these courses are listed as enrolled for learners.
   * **Self-enrolled:** Learners can directly enroll themselves to these types of courses.

1. If you want to provide the ability for learners to unenroll themselves from your course, enable the check-box **Learners can unenroll themselves**.
1. Select the pre-requisite courses that must be completed before taking up your course. Click the Courses field and choose from the list of courses.

   ![](assets/prerequisite-courses.png)

   *Add pre-requisite courses*

1. Enable the **Prerequisites** check-box if you want the pre-requisite courses to me made mandatory.
1. Add keywords as tags related to your course. These tags help the learners to locate your course easily during search. All these tags are automatically added based on the modules that we have added. If you have other tags that you want to add to this course, you can go ahead and enter it.
1. Add the profiles of your target audience for this course by clicking the text area and choosing the profiles from the suggestions.
1. Add resource files for your course as extra material. Drag your materials such as text, or video, or audio files.
1. Now this course will be available for these learners having these profiles as a recommended course. You can also attach additional resources for your learners in this section. Learners will be able to download these files for later reference. Once you are done with all these changes, go ahead and click **[!UICONTROL Save]** on the top-right corner. This will save your course as a draft. Your course is saved as draft, by default.

## Assign instructors for modules {#assigninstructorsformodules}

1. After you create modules for your course, you can assign instructors to the modules. From the Author dashboard, click **[!UICONTROL Course Catalog]**.
1. Click the course whose module you want to assign instructors to.
1. From the **Add Modules** section, click the module to which you want to assign an instructor.
1. In the **Instructor** field, specify the user name of the user to who you want to assign the instructor role.

   ![](assets/instructor-field.png)

   *Assign an instructor role to a user*

1. To republish the course with the updates, click **[!UICONTROL Republish]**.

## Observation checklist

A Checklist module can now be reviewed by managers in addition to instructors. People managers, as well as non-hierarchical managers, such as store managers or location managers, can review and complete the checklist. 

Course authors can add people managers as well as non-hierarchical managers (if applicable) as reviewers by selecting these role options in the "Reviewers" section while setting up a Checklist module. This can be done at a course instance level.

![Checklist for managers](assets/manager-checklist.png)

*Add reviewers in an activity module*

Selecting the "**[!UICONTROL +Managers]**" option will automatically enable a learner's manager in the organization hierarchy to review the checklist. You don't need to search and add manager names individually. 

If your account administrator has set up non-hierarchical manager roles (such as location managers or site managers) by using the Active Fields option, those manager roles will be available for you to select and enable them to review the checklist.

You don't need to search and add manager names individually. When learners enroll in the checklist course, it will automatically send a notification to their managers/store managers for review along with any selected Instructor. This workflow makes it simple for authors to not mention individual managers' names.

In the sample screenshot provided above, selecting the "**[!UICONTROL +Store Managers]**" option will automatically enable the non-hierarchial manager aligned to the learner to review the checklist. Note that "store" here will be replaced by the active field defined by the administrator.

Updates to the checklist module also include notifications to instructors and managers when a learner is enrolled in a course that has a checklist module in it. The reviewer gets a notification in the Learning Manager notification center as well as in the instructor/manager dashboard that checklist action is due.

<!--![View notification for enrollment](assets/checklist-notification.png)-->

The reviewer will be able to view information about all pending checklist review items from the Checklists menu as well as the Notifications menu when they log in as an instructor/manager.

![Cert approvals](assets/pending-task-managers.png)

*Approvals for certification*

After clicking Review Checklist, the reviewer can complete the evaluation.

![Review pending checklist review items](assets/evaluation-checklist.png)

*Review pending checklist review items*

Reporting can be downloaded on checklists, which include detailed information on learner evaluation, reviewer name, role, and e-mail.

The Checklist Report csv has the new and updated fields:

* Reviewer Name instead of Instructor Name
* Reviewer Email instead of Instructor Email
* Reviewer Role- Possible values are Manager, Store/Location Manager, Instructor

## Preview a course {#previewacourse}

Once the course is created and saved as a draft, you can preview the course as a learner, and then publish it to make it available in the course catalog.

To preview the course, click **[!UICONTROL Preview as learner]**.

![Preview a course as learner](assets/preview-as-a-learner.png)

*Preview a course as learner*

This opens the course **Overview** page for you where you can see the modules, their order, and other details related to the course.

![](assets/overview-page.png)

*View modules and other related details*

To see how the learners can experience this course, click each of these modules to start playing it. This starts playing the course in the Fluidic Player.

## Publish a course {#publishacourse}

After previewing the course as a learner, you can publish the course, so that it becomes available for learners to consume. Note that the course is still in a draft mode.

A typical course life cycle looks as follows:

* **Draft** - When an author completes creating a course and saving it. At this state, course is not available yet for learners.
* **Published** - When an author completes publishing a course. At this state, the course is available for learners to enroll. You can also edit a course at this state.
* **Retired** - After publishing a course, an author can move it to a retired state if the author doesn't want the course to appear in course catalog for learners.
* **Deleted** - A course under deleted state is when it is removed completely from the Adobe Learning Manager application. Only authors can delete courses when they are in Draft or Retired states. 

![](assets/typical-course-lifecycle.png)

*Workflow of a course lifecycle*

To publish the course that you had created, click **[!UICONTROL Publish]** on the top-right corner of the page.

![](assets/publish-a-course.png)

*Publish a course*

On the confirmation pop-up message that appears, click **[!UICONTROL OK]**.

The course is now available in the course catalog.

## View a course {#viewacourse}

You can view a list of all available courses as an author. To view all the courses in Learning Manager account, click Course Catalog. To view all your authored courses in Learning Manager, click **[!UICONTROL My Courses]**.

On the course card, hover on the options, and click **[!UICONTROL View Course]**.

![](assets/view-a-course.png)

*View a course*

The course information window displays. The course is in a read-only mode. To modify the course, click **[!UICONTROL Edit]**.

## Retire a course {#retireacourse}

If you retire a course, you cannot enroll new learners to the course. Learners who are already enrolled can take the course.

To retire a course, on the course card, hover on the options, and click Retire Course.

![](assets/retiring-course.png)

*Retire a course*

On the confirmation pop-up that appears, click **[!UICONTROL Yes]**.

## Duplicate a course {#duplicateacourse}

You can create a copy of the course and then modify the course. If you want to back up your course, you can duplicate the course.

## Search for courses {#searchforcourses}

Adobe Learning Manager makes it easier for you to find the courses of your choice quickly. You can search for your courses in the following ways:

**Search field:** Click the search bar on the upper-right corner of the **Course Catalog** page. Type the course name or any keywords associated with your courses. You can also search using tags that are added during course creation. Tags are searchable inside Search Courses field, which means the tags are displayed in search field as you type.

![](assets/search-field.png)

*Search for courses*

**Filter list of courses:** You can filter the courses by state such as All, Published, Draft, and Retired. Based on your choice, you can view the filtered list of courses and select the required courses.

As an author, you can also sort the courses to better locate your required course. Click **[!UICONTROL Sort by]** and choose alphabetical ascending order, alphabetical descending order, course created date, course updated date, and effectiveness of courses.

![](assets/filter-list-of-courses.png)

*Filter list of courses*

## Enroll learners in a course {#enrolllearnersinacourse}

To enroll learners to the courses, or to allow managers to nominate learners for the courses, you must switch to the Administrator mode, as only administrators have the rights to enroll learners for the courses.

To switch to the Admin mode,

1. Click your profile picture and then select Administrator.
1. In the Admin mode, click **[!UICONTROL Courses]** on the left pane. On this page, you can see all the courses created by all the authors in your Learning Manager account.
1. To enroll the learners, hover over the course card, and you can see the option **Enroll Learners**. Click this option.

   ![](assets/enroll-learners.png)

   *Enroll learners to a course*

1. On the Enroll Learners dialog box, on the top-right corner you an see that the option **Default Instance** is selected. As soon as a course is created by an author, a default instance of the course is created. 

   ![](assets/default-instance.png)

   *View default instance of a course*

1. Start typing the name of a learner in the Include Learners field and choose a learner. You can also add user groups here. If you want to enroll all the learners in your Learning Manager account, start typing all. You can also enroll learners in a team.

   ![](assets/include-learners.png)

   *Add learhers to a course*

1. If you want to exclude any learner from the course., enter the name of the learner in the **Exclude Learners** field.
1. After you have enrolled the learners, click **[!UICONTROL Proceed]**. On the Enroll Learners dialog box, you can view the summary of the enrollment.

   ![](assets/summary-of-enrollment.png)

   *View course enrollment summary*

1. To enroll all learners in the course, click **[!UICONTROL Enroll]**. These learners are now successfully enrolled for this course. The learners get a notification to go ahead and take the course. To enroll more learners, repeat the enrollment procedure.

## Changes to the Course Instance page for Connect VC modules {#connect-vc}

While retrieving a Connect course, you can create two types of rooms:

* Dynamic
* Persistent

A persistent url is always fixed. But for users who do not have Connect and their own meeting room, then they must use a dynamic meeting room at runtime. People can then join their meeting.

![](assets/dynamic-room-options.png)

*Dynamic meeting room options*

You can now change the url of the persistent room on the **Course Instance** page.

<!--| ![](assets/persistentroomdropdown.png) | ![](assets/courseinstancepage-persistentroom.png) |
|---|---|-->

## Unenroll learners from a course {#unenrolllearnersfromacourse}

While creating a course, an author can enable the option **Learners can unenroll themselves**, so that learners who are taking the course can unroll from the course.

An Administrator can also unenroll learners from the course.

![](assets/unenroll-learners.png)

*Unenroll learners from a course*

For more information see [Unenrolling learners](/help/migrated/administrators/feature-summary/courses.md).

## Add course modules for Captivate and Presenter {#addcoursemodulesforcaptivateandpresenter}

You can also publish the course modules to Learning Manager from Adobe Captivate and Adobe Presenter software using the Publish menu.

1. In Captivate, click **[!UICONTROL Publish]** > **[!UICONTROL Publish to Learning Manager]**.
1. Provide the sub-domain name or email id and click **[!UICONTROL Submit]**. If you have multiple accounts, you are prompted to choose the account.
1. Log in with Adobe credentials. If you do not have an Adobe id, click **[!UICONTROL Create Account]**. After authorization, you are directed to module publishing page.
1. Provide all the basic information about the module and click Publish.

You can see the published module on the Learning Manager modules page. For more information, see [Publish project to Adobe Learning Manager](https://helpx.adobe.com/captivate/classic/publish-project-to-captivate-prime.html).

## Course effectiveness {#courseeffectiveness}

Course effectiveness score helps the authors to evaluate the courses which are not working as per learners needs and modify them accordingly. Course effectiveness is evaluated to understand the usefulness of a course to the learner. It is a combination of results from learner feedback on the course content. The course quiz results for a learner and the manager's feedback evaluating a learner based on learning from the course.

In **My Courses**, an author can view the course effectiveness rating on the course thumbnails as shown in the below snapshot. You can see the rating for this course as 100.

<!--![](assets/course-rating.png)-->

The course effectiveness rating value is arrived considering L1, L2 & L3 feedback values. To view the breakup of each feedback, click the course effectiveness value. A pop-up menu appears as shown below.

![](assets/how-course-effectivenessiscalculated.png)

*Calculation of course effectiveness*

In this sample snapshot, 1 out 1 user received all the three types of feedback, hence the score is 100/100. From this table, you can understand the missing feedback to improve overall effectiveness. To view how course effectiveness is calculated, click the down-arrow at the lower-right corner of the pop-up menu.

<!--![](assets/how-course-effectivenessiscalculated1.png)-->

As per the pie-chart shown above, more weightage is given to L3 feedback from manager.

## Certifications and Learning Programs {#certificationsandlearningprograms}

Both Author and Admin can create certifications and learning programs for learners from the Author app. From the home page, click either Certifications, or Learning Programs to create the respective learning objects.

To know how to create and manage certifications and learning programs, see  [Certifications](/help/migrated/administrators/feature-summary/certifications.md) and  [Learning Programs](/help/migrated/administrators/feature-summary/learning-programs.md).

## Mandatory courses for external certification {#mandatorycoursesforexternalcertification}

In earlier releases of Learning Manager, course completion from learner in External certification was not mandatory to complete a Certificate.

You can now make courses mandatory by enabling the option **Set required courses as Mandatory for Certificate Completion** in the Curriculum tab.

![](assets/set-required-coursesasmandatory.png)

*Set mandatory courses to complete a certificate*

When courses are set as mandatory:

* The submission page of the Manager lists the learners only after the learners complete the courses.
* The learner can only upload a file after completing the course.

## Frequently Asked Questions {#frequentlyaskedquestions}

+++How to remove "seek manager nomination" for a course?

Perform the following steps:

1. Log into Learning Manager as an Author.
1. Open the course.
1. On the left pane, click **[!UICONTROL Settings]** > **[!UICONTROL Edit]**.
1. On the **Enrollment Type** drop-down list, change the enrollment type from **Manager Nominated** to **Manager Approved** or **Self Enrolled**.

1. Once you have changed the type of enrollment, republish the course.

+++

+++How to combine courses?

You can combine courses via a Learning Program.

1. Log in to Learning Manager as an Administrator.
1. On the left pane, click **[!UICONTROL Learning Programs]**.
1. To add a Learning Program, click **[!UICONTROL Add]**.
1. Enter the details of the Learning Program and to save the Learning Program, click **[!UICONTROL Save]**.
1. After creating the Learning Program, click **[!UICONTROL Catalog]**.
1. On a course card, click **[!UICONTROL Add]**, as shown below. Repeat the process for as many courses that you want to add to the Learning Program.

![](assets/add-catalog.png)

Once you have added all the courses required in the Learning Program, click **[!UICONTROL Publish]**.

In a Learning program, you can only add self-enrolled courses and not Manager Nominated or Manager Approved courses. This is a default behavior in Learning Manager.

+++

+++How to make sure that all learners cannot see all courses?

You can achieve this via catalogs.. A default catalog contains all courses added to Learning Manager by default.

You must disable the default catalog and create custom catalogs.

1. Log in to Learning Manager as an Administrator.
1. On the left pane, click **[!UICONTROL Catalogs]**.
1. Create a Catalog by clicking **[!UICONTROL Create]**. Enter the details and click **[!UICONTROL Save]**.

1. On the newly created Catalog options, you can select different types of learning that you can add, for example, Learning Program, certification, or course.
1. In the Learning Program section, click **[!UICONTROL Add Content]**.
1. On the left pane, click **[!UICONTROL Share Internally]** or **[!UICONTROL Share Externally]** depending on the audience that you want to target.

1. To add a user group, click **[!UICONTROL Add User Groups]**.
1. On the Catalogs page, disable the **D[!UICONTROL efault Catalog]**, and enable the catalog that you have created.

![](assets/enable-custom-catalog.png)

+++

+++How to re-enroll in a completed course?

A course completion cannot be reverted. A learner **cannot be re-enrolled** to a completed course.

+++

+++How can learners view course even after they have completed it?

A learner can view a course after completion by clicking the Revisit button in the course.

Perform the steps below:

1. Login as a learner.
1. Open the course that you have completed.
1. Click **[!UICONTROL Revisit]**.

+++

+++How to add resource file in the course?

While creating a course, you can add video, audio, pdf, or text files to the course that are relevant to the course so that the learner can access additional training material.

![](assets/add-resources.png)

+++

+++How to set multiple attempts on module?

**Pre-requisite:** The Administrator must enable the option **Multiple Attempts** in **Settings > General** in the Admin app.

As an Author, on the Course overview page, enable the option **Allow multiple attempts**.

For more information, see the [section on multiple attempts](courses.md#Allowmultipleattempts).

+++

+++Can you download the content that has been uploaded on Adobe Learning Manager to modify the content?

No, the content uploaded on Learning Manager is a published zip file and is not the source file. Therefore, even if the content is downloaded, the content cannot be edited in an authoring tool. You would require a source file to edit the content.

+++
