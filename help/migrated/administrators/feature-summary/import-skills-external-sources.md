---
jcr-language: en_us
title: Import skills from external sources
description: Import Skills from content providers, such as LinkedIn and Go1, by using the respective connectors.  The imported skills will be added to the admin defined skills in Learning Manager and will be available to Authors during the course creation workflow.
contentowner: saghosh
exl-id: 3bcd8fc6-16e4-4f66-a5c6-15b3d606f0c2
---
# Import skills from external sources

Import Skills from content providers, such as LinkedIn and Go1, by using the respective connectors. This enhancement is a part of the goal towards Learning Manager's ability to integrate with external Skills Clouds and Talent Management Systems. The imported skills will be added to the admin defined skills in Learning Manager and will be available to Authors during the course creation workflow. Enhancements have also been made to the skill search functionality across the platform to provide a better search experience when the account has an extensive number of skills.  

## Configure skill import

Follow the steps in the procedure to enable skill import in the account.

1. In the Admin app, select **Settings** on the left pane.
1. Select **General**.
1. In the **Skills import** section, select **Enable**. If enabled, you can choose an external source to import skills. Once enabled, for all subsequent imports of learning resources, the skills will be imported into skills repository for newly imported items. The skills for existing learning resources can be imported to the skills repository one time and to execute this initial run please contact your CSM.
1. Select a content provider from the the dropdown.

As an Admin, you can only import skills from one skill source.

### Default skill level

The default skill level is one and Credit is 10 after the skills are migrated. Later admin can change the credit.

You cannot edit the name of the skill, description and add levels to external skills. You can, however, add domain, badges, and edit credits.

### Default course skills and credits

After you import skills, they are added to the learning resources imported from the source which was selected as skill source. For example, if your skill source was LinkedIn Learning, all learning resources imported from LinkedIn Learning will have the skills provided by it. When imported into learning resources, each learning resource gives a default of 10 credits.

#### Reporting

The column **Source** with values- Internal, LinkedIn Learning, Go1, which indicates the source of skill import.

The recently added skills will be at top.

Om the Course setting page, the column **Assigned by** containing values, Internal, and Content Provider.


## Integration Admin workflow

The Integration Admin uploads the CSVs (skill, skill-level, and course) and then migrates the courses into the account. For example, after the Admin selects LinkedIn Learning, the Integration Admin can schedule an activity where both skills and levels are imported to Adobe Learning Manager.

## Export the skills

As an Administrator, 

1. Select **Skills** on the left pane.
1. Select the source for any skill. You can view the courses, job aids, enrolled learners, and instructors of the course.

### Edit a skill

Select a skill. In the **Edit a Skill** pop-up, you cannot edit the name and description of the skill. You can, however, add skill domains and a badge for the skill.
