---
jcr-language: en_us
title: Import skills from external sources
description: Import Skills from content providers, such as LinkedIn and Go1, by using the respective connectors.  The imported skills will be added to the admin defined skills in Learning Manager and will be available to Authors during the course creation workflow.
contentowner: saghosh
---

# Import skills from external sources

Import Skills from content providers, such as LinkedIn and Go1, by using the respective connectors. This enhancement is a part of the goal towards Learning Manager's ability to integrate with external Skills Clouds and Talent Management Systems. The imported skills will be added to the admin defined skills in Learning Manager and will be available to Authors during the course creation workflow. Enhancements have also been made to the skill search functionality across the platform to provide a better search experience when the account has an extensive number of skills.  

## Configure skill import

Follow the steps in the procedure to enable skill import in the account.

1. In the Admin app, select **Settings** on the left pane.
1. Select **General**.
1. In the **Skills import** section, select **Enable**. If enabled, you can choose an external source to import **Skills**. The skills for existing learning resources will be imported to the Skills repository one time during the initial run. For all subsequent imports of learning resources, the Skills will be imported into Skills repository only for newly imported items. 
1. Select a content provider from the the dropdown.

## Integration Admin workflow

The Integration Admin uploads the CSVs (skill, skill-level, and course) and then migrates the courses into the account. For example, after the Admin selects LinkedIn Learning, the Integration Admin can schedule an activity where both skills and levels are imported to Adobe Learning Manager.

## Export the skills

As an Administrator, 

1. Select **Skills** on the left pane.
1. Select the source for any skill. You can view the courses, job aids, enrolled learners, and instructors of the course.

### Edit a skill

Select a skill. In the **Edit a Skill** pop-up, you cannot edit the name and description of the skill. You can, however, add skill domains and a badge for the skill.