---
description: Learn how to access, download, and interpret the Feedback Report in Adobe Learning Manager. Understand report columns, question types, manager and learner responses, and how feedback insights support training evaluation and continuous improvement.
jcr-language: en_us
title: Feedback Report in Adobe Learning Manager
---

# Feedback report

## Overview 

The Feedback report in Adobe Learning Manager collects both Level 1 (learner feedback) and Level 3 (manager feedback) after learners complete the learning objects. This report presents a structured overview of both subjective and objective responses from learners and their managers.  

The report tracks learner details such as name, email, feedback form name, version, and language, and captures responses to administrator-defined questions. It also records the learner's selection for each question (for example, Strongly Agree, Agree, or Disagree). 

## Purpose and benefits 

* Provides actionable insights to improve the course quality and overall learning effectiveness. 
* Refine navigation, pacing, and delivery methods based on direct user feedback. 

## Use cases 

* **Identify content issues quickly**: Administrators can spot low ratings or repeated negative comments and update the learning objects without waiting for support tickets or escalations. 
* **Measure training effectiveness**: Teams can compare learner feedback across multiple courses or versions to understand which learning objects are performing well and which may need to rework. 
* **Track learner engagement with feedback forms**: Administrators can see how many learners are answering or skipping questions, helping them refine feedback forms to improve response quality and completion rates. 

## How to download the Feedback report 

1. Log in to Adobe Learning Manager as an administrator. 
2. Select **[!UICONTROL Reports]** from the left navigation menu. 
    ![](assets/select-report.png)
    _The Administrator homepage shows the Reports option highlighted for downloading reports_

3. Select **[!UICONTROL Custom Reports]** within Reports and then select **[!UICONTROL Excel Reports]**.
4. Select **[!UICONTROL Feedback Report]**. 
    ![](assets/select-feedback-report.png)
    _Custom Reports section shows the option to select Feedback Report to access learner and manager feedback data_

5. Select **[!UICONTROL All Trainings]** or **[!UICONTROL Selected Trainings]**, and the date range. If you select the second option, you can add up to a maximum of 10 courses or Learning Paths and generate their feedback report. Additionally, you can generate the report for up to one year. 
    ![](assets/feedback-report.png)
   _Configure the Feedback Report by selecting the training scope, setting the date range, and choosing the translation option before downloading_
 
6. Select the language to translate the L1 feedback to. Objective questions and their responses are translated into the selected language when that language version is explicitly defined. Only the subjective questions that are explicitly defined in the selected language appear in the report.  Responses to subjective questions would be in the original response language. 
7. Select **[!UICONTROL Download]** to download the report. 

## What does the Feedback report contain 

The following are the default columns in the Account-level report: 

| Column| Description|
|----|----|
| Type of Feedback| Indicates whether the feedback is from the learner (L1) or the manager (L3)|
| User Name| Name of the learner who completed the training|
| User Email| Email address of the learner|
| Training Id| A system-generated unique identifier assigned to each Learning Object (course, certification, or learning path)|
| Training Name| Name of the learning item for which feedback is submitted|
| Training Instance| Instance name of the training (for multi-instance courses)|
| Training Type| Type of training (Course, Certification, Learning Path)|
| Type of Feedback Form| Type/category of the feedback form used (for example, Blended Courses, Self Paced Courses, and Classroom courses)|
| Feedback Form Name| Name of the feedback form|
| Feedback Version| Version number of the feedback form|
| Current Manager| Name of the learner's manager|
| Current Manager Email| Email address of the learner's manager|
| Date of Completion| The date when the learner completed the training|
| Date of Feedback| The date when the learner submitted the feedback|
| L1 Feedback Original Language| The language in which the learner originally submitted the L1 feedback|

The following columns appear in the Account-level report based on the four types of questions added to the feedback form: 

| Column | Description|
|---|---|
| Course Effectiveness| The predefined course-effectiveness question displayed in the form|
| Course Effectiveness Answer| The learner's response to the course-effectiveness question|
| NPS Question 1| First Net Promoter Score question|
| NPS Range 1| Rating scale used (e.g., 0 to 10)|
| NPS Answer 1| Learner's rating for NPS Question 1|
| Likert Question 1| First Likert-scale question|
| Likert Answer 1| Response to Likert Question 1|
| Text Question 1| First open-ended/text question in the form|
| Text Answer 1| Learner's response to Text Question 1|
| L3 Likert Scale Question 1| Measures the learner's post-training performance using a rating scale|
| L3 Likert Scale Response 1| Manager's response to this Likert-scale question|
| L3 Free Text Question 1| Free-text question added to the L3 feedback form for managers; can be configured as optional or mandatory|
| L3 Free Text Response 1| The manager's response to that free-text question|

>[!NOTE]
>
>The Account-level report also includes any active fields configured for learners.  

The following columns appear in the Learning Object level report: 

| Column| Description|
|---|---|
| Learner| Name of the learner|
| Email| Learner's email address|
| Feedback Form Name| Name of the feedback form|
| Feedback Version| Version number of the feedback form|
| Learner Language| Language selected by the learner|


