---
description: Learn about the new features and enhancements in the May 2025 release of Adobe Learning Manager
jcr-language: en_us
title: New features summary
---

# New features summary

The upcoming release of Adobe Learning Manager introduces a variety of new features and enhancements aimed at streamlining the platform and enhancing its capabilities.

Key updates include:

* The Group Success Dashboard, which allows for real-time tracking of team progress. 
* The ability to assign multiple custom roles to individual users.
* Improved tools for marking bulk learner enrollment, attendance, and completion.

Additional enhancements include better management of content expiration, expanded support for multiple languages in content, and new purchasing options for content.

## Group Success Dashboard

The Group Success Dashboard provides a more efficient and user-friendly way for admins and managers to monitor and track the progress of their teams' training activities.

Group Success Dashboard offers the following:

* Simplifies Learner Progress Tracking: The dashboard offers an alternative to the Excel-based learner transcript, allowing for easier and quicker access to information about learners' course enrollments and progress. 
* Facilitates Team Management: The dashboard is particularly useful for managers overseeing small teams, enabling them to frequently check their team members' learning progress on specific courses or learning paths.

Managers (or store managers) handling small teams (less than 50 people) can use the GSD to regularly check how their team is progressing with their courses. This is helpful for quick updates and making sure everyone is completing their training.
The Group Success Dashboard makes it easier to track learner progress. Instead of using Excel files, managers and admins can use the dashboard to quickly see course enrollments and progress.
Admins can create dashboards by giving them a name, selecting user groups, and choosing the courses or learning paths. The dashboards can be shared with other admins or managers.

## Custom role enhancements

Admins can now assign more than one custom role to a single user. This feature is especially helpful for large organizations, allowing roles to be reassigned to existing custom admin users when custom admins move to other teams or leave the organization.
Admins can create custom roles with specific permissions, like access to certain user catalogs or features. The new update allows one user to have multiple custom roles.
Custom roles have clear names in the user interface, so it's easier to know which role you're using. Custom admins can see their assigned roles in the profile section (top right corner) and switch between roles easily. 
 
Switch custom roles
To view and select any custom roles assigned to you, use the Switch custom role option.  
Select custom roles
Users receive email notifications when the custom roles are assigned to them. The emails now includes role names for better clarity.
Note: You can add up to 50 roles per user and 500 users per role.

## Learner bulk enrollment, attendance, and completion

Admins and instructors manually mark completions and attendance when they get attendance rosters after session completions. This requires a lot of redundant work to update names and mark completions for them. Now, this enhancement allows admins and instructors to update a CSV with email IDS of learners and directly upload it to the Adobe Learning Manager to mark enrollment, completions, and even mark attendance.

## Content expiry and unique code

Adobe Learning Manager now supports content expiry dates and unique codes to help manage content more effectively. These features are especially helpful for organizations that use multiple platforms and need to keep their training materials up to date and consistent.

* The expiry date helps authors keep track of outdated content that may need review or updates.
* The unique code makes it easier to link content between external systems and Adobe Learning Manager.

Authors can add a unique ID and set an expiration date when creating content. The unique ID must only include letters and numbers (no spaces) and must not be used for any other content. If a duplicate ID is entered, an error will appear. Authors can set these fields when creating a course.
The content will still be available after the expiry date, but the date acts as a reminder to review or update it. The expiry date and unique ID apply to all language versions of a content group, ensuring a consistent experience for all users, no matter the language. Authors can use the unique ID to quickly search for and find specific content, making it easier to manage and update training materials.
The unique code feature supports integration with content migration processes, allowing for seamless content transfer and management between systems.
The Training report now includes two new columns: Content Expiry Date (UTC TimeZone) and Content Unique ID, to track content expiry and content unique ID.

## New content languages

Adobe Learning Manager is known for supporting many languages, which makes it stand out from other learning platforms. With every milestone, Adobe Learning Manager expands its language offerings to better support a global and diverse user base. In this release, we're introducing new content languages, further enhancing our commitment to delivering inclusive and accessible learning experiences for all.

* Chinese-traditional Hong Kong (cn-HK)
* Norwegian Bokmal (nb-NO)
* Tamil (ta-IN)
* Telugu (te-IN)
* Kannada (kn-IN)
* Malayalam (ml-IN)

## Go1 content enhancements

Adobe Learning Manager introduces new purchasing models for Go1 content, providing more flexibility and options for acquiring content: Premium Essentials and Premium Essential Plus. Essentials offers cost-effective solutions for boosting employee engagement and includes content providers like Skillshub, Thomson Reuters, and Emtrain. Premium Essential Plus offers additional content from premium providers such as Blinkist, Pluralsight, Skillsoft, Traliant, and Coursera.
Select Content Marketplace in the Admin homepage to launch the marketplace to access learning content from various learning providers.

 
Purchase plans
There are also enhancements to ensure regular synchronization between the content hub and Adobe Learning Manager, with the new additions and updates automatically reflected in Adobe Learning Manager. The content is mapped to all supported languages, allowing Admins to easily filter content by language.
The content provider also handles the decommissioning of content, ensuring that no content is removed without prior notice.

## Login access report in FTP

The Login access report, along with other reports, helps admins build their reporting suite outside the platform by providing detailed information about user login and access times. This report can be used to create more informative dashboards and track user activity effectively.

The report is now available in the custom FTP along with existing reports, such as learner progress and course completion. This integration allows admins to access all necessary reports from a single source, facilitating better data management and analysis.

The report helps in automation by enabling the export of login and access data to the FTP, where it can be joined with other reports to create comprehensive dashboards. This feature is particularly useful for organizations that rely on automated processes for data analysis and reporting.

## User language preference update on login through SAML

Adobe Learning Manager is a multi-lingual platform where learners' language preferences are taken care of through various ways, like interface language, content language, and courses, along with its modules and instances, are also multi-lingual.

For users of the Adobe Learning Manager native platform, this enhancement addresses the need for just-in-time user provisioning. When users are creating accounts and logging in for the first time, this feature ensures that their language preferences are accurately captured and applied.

This feature ensures that users' language preferences are updated automatically when they log in through SAML. This helps in providing a personalized experience by displaying the interface in the user's preferred language.
When users log in through SAML, their language preference (Interface and Content language) is checked and updated based on the information provided during the login process. 

The feature integrates with the SAML login process to capture and update the user's language preference seamlessly. 

## Filter deleted users before purging

Purging users means permanently deleting their data from the system. This includes removing all records and information linked to the user, so nothing is left behind. Purging helps keep the system clean, saves storage space, and follows data retention rules.

The feature is designed to help admins manage and purge users who have been deleted for a certain period. This is particularly useful for maintaining data hygiene and ensuring that old, unused user data is removed from the system. 
Admins can filter users by the month they were deleted, making it easier to identify and purge users who were deleted in a specific timeframe.

