---
description: Learn about the new features and enhancements in the August 2026 release of Adobe Learning Manager
jcr-language: en_us
title: What's new in Adobe Learning Manager August 2026 release
exl-id: da46f186-3ff3-422a-af49-31c7405fd584
---
# What's new in the August 2026 release of Adobe Learning Manager

## Gradebook

A gradebook in Adobe Learning Manager adds weighted scoring to courses, allowing authors to assign a contribution percentage to each scored module and set a minimum aggregate score for course completion. Learners can track their grades throughout the course, and administrators can view final scores and download relevant transcripts. 

### What gradebook does 

A gradebook-enabled course calculates each learner's final score by combining individual module scores according to the weightage percentage assigned to each module. This provides a precise, weighted measure of performance rather than a simple sum of scores or a pass/fail marker based on completion alone. 

Gradebook supports two completion models: 

* **Required modules only**: the course completes when all mandatory modules are finished. Gradebook scores are still calculated and visible, but the aggregate score does not contribute to passing criteria. 

* **Required modules plus aggregate score**: the learner must both complete all required modules and achieve an aggregate score at or above the minimum passing threshold. Both conditions must be met to achieve a passing grade. 

### How course scores are calculated 

For each scorable module, the contribution to the course aggregate score is: 

(Score achieved ÷ Maximum score) × Weightage % = Module contribution 

The aggregate course score is the sum of all module contributions. Weightage percentages across all scorable modules must add up to exactly 100. The gradebook configuration cannot be saved until this condition is met. 

The aggregate course score is the sum of all module contributions. Weightage percentages across all scorable modules must add up to exactly 100. The gradebook configuration cannot be saved until this condition is met. 

The scoring scale does not need to be consistent across modules. A classroom session scored out of 100, and a SCORM module scored out of 10 can coexist in the same gradebook. The formula normalizes each contribution before applying the weightage. 

**Scorable and non-scorable modules** 

Only modules that produce a score are eligible for weightage. Scorable module types include: 

* SCORM, AICC, and xAPI content with scoring enabled
* Captivate content packages
* Native quizzes in Adobe Learning Manager
* Classroom and virtual classroom sessions where the instructor or admin enters a score
* Activity modules scored by an instructor or admin 

Non-scorable module types, PDF files, video files, audio files, PowerPoint presentations, Word documents, Excel files, and HTML content, cannot be assigned a weightage percentage and do not contribute to the aggregate score. These modules may still be required for course completion. When the Include modules that don't contribute to final grade option is enabled, they appear in the gradebook without a weightage value.

View [Gradebook for Authors](/help/migrated/authors/feature-summary/alm-author-gradebook.md) for more information.

## Hierarchical content folders

The Content Library now supports up to three levels of private folder hierarchy. Administrators create the folder structure and control which custom roles can access which Level 1 folders. Access cascades automatically to all subfolders within a Level 1 folder.

Authors can copy and move content between folders, filter the Content Library by folder, and browse the hierarchy when adding modules to a course.

Key capabilities:

* Up to three levels of nesting (maximum 25 subfolders per parent)
* Role-based access assigned at Level 1 only
* Content can appear in multiple folders without duplication
* Public folder and private folder structure are mutually exclusive
* Browse folders experience when selecting modules in course authoring

View [Hierarchical content folders](/help/migrated/administrators/feature-summary/settings/advanced-settings.md#content-folder) for more information on admin-level functionalities. View [Hierarchical content folders](/help/migrated/authors/feature-summary/content-library.md#add-content-to-a-folder) for more information on author- level functionalities.

If you are migrating your learning content from another platform into Adobe Learning Manager and want to preserve your existing folder organization, you can use CSV files to create a hierarchical folder structure and associate your content files with the appropriate folders. Learn more about migration in [Migrate content folder hierarchy](/help/migrated/integration-admin/feature-summary/migration-manual.md#migratecontentfolderhierarchy)

## Live Hub (Beta)

Live Hub is an AI-powered virtual training experience within Adobe Learning Manager that helps organizations deliver engaging and impactful live learning. With intelligent features such as AI-powered polls, breakout room orchestration, persistent learning spaces, and AI-powered assistance, Live Hub supercharges Instructor productivity while reducing the complexity of session delivery.

Key highlights:

* Elevate live learning with a native Adobe Learning Manager experience that improves instructional quality and learner outcomes.
* Give your Instructors an AI-powered co-facilitator that drives engagement through intelligent polls, Q&A support, and breakout room insights.
* Help your learners get more from every session with AI-generated summaries and session recordings searchable by topics.
* Measure what matters with engagement analytics that go beyond attendance to reveal real learning participation.
* Assist your Authors to use the AI-powered Instructor Finder to match the right Instructor by skills, availability, preferred times, time zone, and current utilization.

View [Getting started with Live hub](./getting-started-with-live-hub/getting-started-live-hub.md) for more information.

## Adobe Learning Manager Content Composer (Beta)

Adobe Learning Manager now includes Content Composer, an AI-native course authoring tool that takes you from a plain-language prompt to a structured, publish-ready course in minutes.

Key features:

* Conversational AI guides authors through training goals, source material, and learning objectives to generate a complete course brief and outline.
* Document-grounded generation restricts AI output to your uploaded files, which is essential for compliance, regulatory, and procedure-based training.
* Full course generation in a single pass, such as lessons, topics, text, images, knowledge checks, and graded quizzes.
* Visual theme system with light and dark mode, font controls, header and footer support, and JSON export for advanced customisation.
* Configurable completion criteria, success criteria, quiz settings, and SCORM version before publishing.
* and more.

View [Adobe Learning Manager Content Composer](/help/migrated/authors/feature-summary/content-composer/content-composer-help.md) for more information.


## Component-based email template builder

Organizations can now create enterprise-grade, branded email notifications in Adobe Learning Manager using a modern WYSIWYG component editor. Administrators can build a global layout once, with a reusable header, footer, and brand elements, and apply it across all email templates at the account level. Individual templates can then be customized at the course or instance level, inheriting the parent layout by default and overriding it only when needed.

Key capabilities:

* WYSIWYG editor with a library of reusable components (text, image, button, divider, header, footer)
* Variable support: insert dynamic fields such as learner name, course name, and due date
* Linked and unlinked template hierarchy: changes to a linked template propagate to all child templates; unlinked templates are editable independently
* Multi-language template support
* Preview and test-send before publishing
* Backward compatibility: existing email templates continue to work

View [Component-based email builder](/help/migrated/administrators/feature-summary/email-builder.md) for more information.

## External learning support

Learners can now submit off-platform training, like certifications, workshops, conferences, and external courses, for manager approval directly from their learner dashboard. Approved submissions appear in the Learner Transcript.

Key capabilities:

* Configurable submission form with standard and custom fields
* Manager review and approval workflow with comment support
* Approved submissions appear in Learner Transcript with full metadata
* Admin can configure mandatory fields including custom fields
* New columns in Admin and Learner Transcripts: External Learning Name, Completion Comment, custom field columns
* API support: five new learner-scoped endpoints for creating, retrieving, and updating submissions

For more information at the admin-level, view [External learning support](/help/migrated/administrators/feature-summary/settings/basic-settings.md). For more information at the manager-level, view [External learning support](/help/migrated/managers/feature-summary/review-external-learning-requests.md). For more information at the learner-level, view [External learning support](/help/migrated/learners/feature-summary/submit-external-learning.md).

## AI features

### AI Assistant for learners

The AI Assistant for learners now supports four new capabilities in addition to answering questions from assigned learning content:

* **Course summaries**: use the / command to select a catalog item and generate a summary without opening the course
* **Learning Object comparison**: select up to two learning objects using the / command and ask the assistant to compare them
* **Adobe Experience League answers**: the assistant now sources answers to how-to questions from Adobe Learning Manager help documentation
* **Third-party content queries**: Go1 and LinkedIn Learning catalog content can be queried (metadata only; English only; ingestion takes 1–2 hours after catalog is added)

View [AI Assistant for learners](/help/migrated/learners/feature-summary/learner-ai-assistant.md) for more information.

### Learning Path agent

Learners can now have a guided conversation with the AI Assistant to generate a custom, sequenced learning path based on their goals, background, and available time. The learning path is created automatically and the learner is enrolled.

Key capabilities:

* Multi-turn conversation guides the learner through topic selection, course review, and path confirmation
* Up to five suggested learning topics per conversation
* Course selection from assigned catalogs
* Maximum of 10 personalized learning paths visible on the learner home page
* Completed paths can be shared with colleagues

View [Learning path agent](/help/migrated/learners/feature-summary/learning-path-agent.md) for more information.

### Insights Agent

The Insights Agent helps administrators analyze learning data through natural language queries. Ask questions about enrollment trends, completion rates, learner engagement, and skill gaps. The agent generates reports and visualizations in response.

View [Insights Agent](/help/migrated/administrators/feature-summary/insights-agent.md) for more information.

<!--
### Gen AI credits

Adobe Learning Manager integrates AI-powered features managed through a credit-based system linked to Agent Orchestrator licenses. This system requires administrators to activate features, set credit limits, and monitor usage via the Billing page. Linking the Adobe Learning Manager account to an Adobe Admin Console organization with an active Agent Orchestrator license is essential for enabling Gen AI features.

View [Gen AI credits](/help/migrated/administrators/feature-summary/billing-management.md#genaicredits) for more information.
-->

## Channels (Beta)

Channels provide a centralized way to organize, publish, and discover video content from web and Confluence pages. Administrators can create and manage channels by connecting supported web pages or Confluence pages, configure channel settings, control visibility, and synchronize content from the source. Learners can browse available channels, subscribe to channels of interest, and watch curated video content from a single location.  

View [Create Channels](/help/migrated/administrators/feature-summary/create-channels.md) for more information.

## Report Builder

Report Builder gives administrators a flexible, self-service reporting tool that goes beyond the fixed report types available elsewhere in Adobe Learning Manager. Rather than being limited to predefined report structures, administrators can join fields from multiple datasets, like User, User Groups, Courses and Learning Paths, Modules, Transcript, Catalogs, and more — into a single custom report tailored to their organization's specific data needs.

Reports are created once and saved for repeated use. There is no need to rebuild filters, re-apply groupings, or rejoin datasets on every download. Saved reports can be downloaded on demand, shared with other administrators, or set up with a subscription so that recipients receive updated reports automatically at a regular interval.

View [Report Builder](/help/migrated/administrators/feature-summary/alm-report-builder.md) for more information.

## Custom role changes

Custom administrators can now be granted expanded user management capabilities through the Advanced permission level under Users in a custom role definition.

Two access levels are available:

| Access level | What the custom administrator can do |
|---|---|
| **Read only** | View all custom roles, import logs, and deleted users; download the custom roles report |
| **Full control** | All read-only capabilities plus: create, edit, delete, and assign custom roles; import users via CSV; purge deleted users |

### Limitations

**Manually created roles only**: The expanded custom role administration capabilities apply only to roles created through the Adobe Learning Manager administrtor interface. Roles imported via CSV upload are not supported.

Learn more about Custom role changes. For more information, view [What the Advanced user permission unlocks](/help/migrated/administrators/feature-summary/custom-role.md#whatadvanceduserpermissionunlocks)

## LTI deep linking

Integration administrators can now enable LTI Deep Linking for LTI tool configurations, allowing course authors to browse and embed Adobe Learning Manager courses directly from an external LMS without manually copying course URLs.

Once enabled, authors see a **Select content** button in the external LMS activity configuration. They can browse approved catalogs, select courses, and confirm the selection — with all fields populated automatically.

View [LTI deep links](/help/migrated/integration-admin/feature-summary/lti-deep-links.md) for more information.

## Classroom Locations

Classroom Locations now support a structured **four-field location format**, including Country, State/Province/Region, City, and Location Name, making it easier to manage and organize training locations across regions. The update includes a one-time migration from the legacy single-field format and adds multilingual support for the **Location Name** and **Location Information** fields, enabling localized classroom details for Learners.

View [Classroom Locations](/help/migrated/administrators/feature-summary/classroom.md) for more information.

## Reporting changes in the release

View [reporting changes in the August 2026 release of Adobe Learning Manager](/help/migrated/reporting-changes-august-2026.md) for more information.

## API changes in the release

View [API changes in the August 2026 release of Adobe Learning Manager](/help/migrated/api-changes-august-2026.md) for more information.

## Other enhancements in the release

| Enhancement | Description |
|---|---|
| **MQA: Latest vs. Highest score** | For modules with multiple attempts, authors can now choose whether the Latest or Highest attempt score is recorded in the Learner Transcript and used in gradebook calculations. Latest was the existing default and remains so when the setting is not configured. For more information, view [Gradebook for Authors](/help/migrated/authors/feature-summary/alm-author-gradebook.md#configurescoresettingsmultipleattempts). |
| **Content preview in Content Library** | Authors can now preview uploaded content files directly in the Content Library before adding them to courses. For more information, view [Preview Content Library](/help/migrated/authors/feature-summary/content-library.md#previewcontentlibrary).  |
| **Incremental user report** | A new API-based user report returns only users created or modified since the last request, reducing data transfer for large accounts using automated user sync workflows. For more information, view [Incremental User Report](/help/migrated/incremental-user-report.md). |
| **11 new languages in fluidic player** | The fluidic player now supports 11 additional languages, including right-to-left (RTL) script support. For more information, view [Fluidic Player](/help/migrated/learners/feature-summary/fluidic-player.md).|
| **LTI module migration** | Existing LTI 1.1 modules can now be migrated to LTI 1.3 using the migration tool. For more information, view [LTI migration of modules](/help/migrated/integration-admin/feature-summary/migration-manual.md#migrationofltimodules). |
| **Email Builder: Rich Text Editor Support** | Email Templates in Adobe Learning Manager now support rich text formatting, attachments, and custom automations. For more information, view [Email Builder](/help/migrated/administrators/feature-summary/email-builder.md). |
| **Email Builder: Preview feature** | You can check your composed email to see how it would look at the recipient's end by using the Preview option. For more information, view [Email Builder](/help/migrated/administrators/feature-summary/email-builder.md). |
| **Webhook timestamp standardization** | All date and time fields within the `data` object of webhook payloads now have seconds set to `00`, providing minute-level precision consistent with Learner Transcript reports. |
| **Connect enhancements** | Azure Data Lake Storage (ADLS) connector updates; persistent room name support for recurring virtual classroom sessions; recording-view-based attendance tracking. |
| **Player performance improvements** | The fluidic course player has been optimized for faster load times and smoother transitions between modules. |
| **Impact warning before retiring courses/LPs** | Author/Admin will see a warning list of dependent LOs before a course or learning path can be retired. Notifies author that a constituent LO has been retired. Admins receive if they authored the LO but do not have the Author role.|
| **CR/VC Module: Expected Duration** | Authors can now set an expected duration for classroom and virtual classroom modules, separate from the scheduled session time. This value appears in reports and learner-facing course information. |
| **Confirmation before editing acquired courses** | Administrators in peer accounts now see a confirmation dialog before editing a course acquired through catalog sharing, preventing unintended changes to shared content. |
| **Session URL with instance ID** | Session launch URLs for Microsoft Teams, Adobe Connect, and Zoom sessions now include the instance ID, ensuring learners are routed to the correct session when multiple instances exist. |
| **Warning for large-audience announcements** | When sending an ad-hoc announcement email to more than a configurable threshold of recipients, administrators now see a volume warning before sending. |
| **Email templates: Account URL for external learners** | Email notification templates can now include a separate account URL specifically for external learners, routing them to the correct login experience. |
| **AEM Sites** | There is only one **Edit** button now in **Your Profile** > Your areas of interest section to edit your preferences for Products and Roles and Skills. This is part of native learning manager as well. |
| **AEM Sites** | Earlier, there used to be two **Edit** buttons, but now the **Edit** button is a consolidated  button to modify your preferences for Products and Roles and Skills. |
| **Time Zone** | A new search box has been added just below the Time Zone field in the Profile Settings of the logged in user. The search box can be used to search directly for a time zone instead of scrolling through the entire list of available time zones. If you would like to change the existing time zone, you select a new time zone and select Save. The new time zone is saved. The Save button appears only when you select a time zone. |

## System requirements

View [Adobe Learning Manager system requirements](/help/migrated/system-requirements.md) for more information.

## Release notes

Check out the [release notes](/help/migrated/release-note/release-notes.md) for latest release updates. 

## Previous releases of Adobe Learning Manager

* [Adobe Learning Manager April 2026 release](/help/migrated/whats-new-april-2026.md)
* [Adobe Learning Manager October 2025 release](/help/migrated/whats-new-october-2025.md)
