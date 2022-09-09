---
description: Learn how to download learner transcript based on users, learning objects, or skills in Learning Manager.
jcr-language: en_us
title: Learner transcripts
---


# Learner transcripts {#learner-transcripts}

Learning Manager Learning Programs are renamed to Learning Paths. This change happens immediately after the October 2021 release and the terminology of Learning Path is reflected for all roles.

Learn how to download learner transcript based on users, learning objects, or skills in Learning Manager.

Adobe Learning Manager enables the Managers of an organization to generate the transcripts associated with learners. 

## Generate learner transcripts {#generatelearnertranscripts}

1. To generate learner transcripts, click **Reports** on the left pane in Manager login.
1. Click **My Reports** tab on the page.  
1. Click **Learner Transcripts** link. 

   ![](assets/learner-transcripts.png)

1. A Learner transcripts dialog appears. Choose the date range for which you need the transcript generated.

   >[!NOTE]
   >
   >By default, from start date is the learner's registration date and the to date is always the current date. You can modify only the start date from when you need the data.

1. Choose the learners names from the Select Learners field, and click **Generate.**

You can choose single learner or groups of learners. To add more than one learner, click Add More Learners.

Transcripts are generated and downloaded to your computer as .xls files. Each .xls excel file has seven sheets, the details of which are mentioned below: 

## Download Learner Transcript based on timezone {#lt-timezone}

Like an Administrator, a Manager can also choose the columns to export. In addition, a Manager can download the Learner Transcript based on the timezone that he/she had selected in the profile settings. 

If the Manager enables this option, the timezone is picked from the one set in the profile settings page, shown below.

>[!NOTE]
>
>For a new Manager, the Timezone checkbox is disabled.

![](assets/image030.png) 

## Learner Transcript file content {#learnertranscriptfilecontent}

A typical learner transcript file consists of six excel sheets in a single file. The learner transcript sheets gives an overall insight into data including the number of learners involved per course, their skills, the competion percentage based on course or learner, and a compliance dashboard. The following are the dashboards available in learner transcripts:

**Learner Transcript**

In the learner transcript excel sheet, along with profile details about the learner, a learning object wise consumption details are provided such as enrollment date, started date, grade achieved, quiz score obtained and so on. If courses are part of any learning program, they are listed separtely apart from individual course consumption details. 

**1 - Learning Activity Dashboard**

In this LO-specific dashboard, you can view the number of learners for each course, learning program, or certification. You can view the progress sheet for learners for a particular learning object. This sheet displays data like the number of learners who have completed the course or learning program, learners in progress, and learners' due dates.

The users' progress for the specific course is calculated based on the Input Fields where you specify the due date and progress percentage thresholds. For example, if you specify 7 days and 70% as the values in your Input field, the course progress for courses due in 7 days, and for courses that have more than 70% progress are displayed. You can also change the time period in this sheet, where the modified data is automatically displayed in this dashboard.

**2 - Learning Activity Dashboard**

This learning dashboard will display data for a specific user. From this dashboard, you can see the courses, learning programs, or certifications that a particular user has enrolled in. The table also displays data on which learning objects the user has completed, the learning objects in progress, and upcoming due dates for the user.

The users' progress for each course is calculated based on the inputs that you specify. That is, the due date and progress percentage values. For example, if you specify 7 days and 70% as the values in your Input field, the user's progress for different courses that are due in 7 days, and for courses that have more than 70% progress are displayed.

**Skill**

In the skills sheet, skill name, skill level, required credits, earned credits, completion percentage and other profile details are provided. A sample snapshot of skills excel sheet is provided below for reference.

**Skill Dashboard**

In this dashboard, you can see whether your organization is equipped on various skills. For a specific skill you can check the number of users in an organization who are supposed to have this skill vs the number who actually have the skill. This dashboard also specifies the users who might need to refresh their skills. This value is calculated based on the input that you enter in the Input field. For example, if you enter 50 days as your input, the dashboard provides data on users who might need their skills refreshed after 50 days.

This skill dashboard is more user specific. You can filter a specific user or several users and view their skill level as a dashboard. This sheet can help managers and administrators track how skilled each learner is as compared to how skilled they are expected to be. The Skill dashboard also throws light on the learners who need to refresh their skills. The learners refresh list is calculated based on the number of days that you enter in the Input Field.

**Compliance Dashboard**

The Compliance Dashboard has two parts - compliance report per user and compliance report per training. For the user-based report, you can use the Compliance Dashboard to track users who have upcoming due dates for important compliance initiatives. For the training-based report, you can filter by learning program or certification.

For both the compliance reports, filter by the due date to view the appropriate data.
