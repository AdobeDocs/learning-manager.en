---
description: Learn about the new features and enhancements, including API and webhooks changes, in the April 2026 release of Adobe Learning Manager
jcr-language: en_us
title: What's new in Adobe Learning Manager August 2026 release
exl-id: da46f186-3ff3-422a-af49-31c7405fd584
---
# What's new in the August 2026 release of Adobe Learning Manager

>[!WARNING]
>
>The features described in this article are available as part of the beta release. Adobe Learning Manager beta features are provided for evaluation purposes and may be modified, limited, or removed before the general availability release. Feature names, behavior, and configuration options are subject to change without notice.


## Adaptive courses

Adaptive courses let you deliver personalized training by controlling which modules each learner sees, and which are required, based on the user groups they belong to. A single course dynamically presents the right content to the right person automatically.

Authors configure each module with **Optional** and **Mandatory** for user group rules. Learners in different user groups can complete entirely different sets of modules and still complete the same course. Seat limits for classroom and virtual classroom sessions are now enforced at the module level, so a learner can be enrolled in a course while waitlisted on a specific session only. For more information, see [Gradebook for Authors](/help/migrated/authors/feature-summary/adaptive-course-author.md)

Key capabilities:

* Module-level visibility and completion rules per user group
* OR-merge logic: if any group makes a module mandatory, it is mandatory for that learner
* Module-level waitlisting for classroom and virtual classroom sessions
* Refresh completion triggered when a learner's profile changes
* Supported in learning paths and certifications with documented limitations for recurring certifications

Learn more about adaptive courses.

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

For more information, see [Gradebook for Authors](/help/migrated/authors/feature-summary/alm-author-gradebook.md)

## Hierarchical content folders

The Content Library now supports up to three levels of private folder hierarchy. Administrators create the folder structure and control which custom roles can access which Level 1 folders. Access cascades automatically to all subfolders within a Level 1 folder.

Authors can copy and move content between folders, filter the Content Library by folder, and browse the hierarchy when adding modules to a course.

Key capabilities:

* Up to three levels of nesting (maximum 25 subfolders per parent)
* Role-based access assigned at Level 1 only
* Content can appear in multiple folders without duplication
* Public folder and private folder structure are mutually exclusive
* Browse folders experience when selecting modules in course authoring

Learn more about content folder hierarchy.

## Component-based email template builder

Organizations can now create enterprise-grade, branded email notifications in Adobe Learning Manager using a modern WYSIWYG component editor. Administrators can build a global layout once, with a reusable header, footer, and brand elements, and apply it across all email templates at the account level. Individual templates can then be customized at the course or instance level, inheriting the parent layout by default and overriding it only when needed.

Key capabilities:

* WYSIWYG editor with a library of reusable components (text, image, button, divider, header, footer)
* Variable support: insert dynamic fields such as learner name, course name, and due date
* Linked and unlinked template hierarchy: changes to a linked template propagate to all child templates; unlinked templates are editable independently
* Multi-language template support
* Preview and test-send before publishing
* Backward compatibility: existing email templates continue to work

For more information, see [Component-based email builder](/help/migrated/administrators/feature-summary/email-builder.md)

## External learning support

Learners can now submit off-platform training, like certifications, workshops, conferences, and external courses, for manager approval directly from their learner dashboard. Approved submissions appear in the Learner Transcript.

Key capabilities:

* Configurable submission form with standard and custom fields
* Manager review and approval workflow with comment support
* Approved submissions appear in Learner Transcript with full metadata
* Admin can configure mandatory fields including custom fields
* New columns in Admin and Learner Transcripts: External Learning Name, Completion Comment, custom field columns
* API support: five new learner-scoped endpoints for creating, retrieving, and updating submissions

## AI features

### AI Assistant for learners

The AI Assistant for learners now supports four new capabilities in addition to answering questions from assigned learning content:

* **Course summaries**: use the / command to select a catalog item and generate a summary without opening the course
* **Learning Object comparison**: select up to two learning objects using the / command and ask the assistant to compare them
* **Adobe Experience League answers**: the assistant now sources answers to how-to questions from Adobe Learning Manager help documentation
* **Third-party content queries**: Go1 and LinkedIn Learning catalog content can be queried (metadata only; English only; ingestion takes 1–2 hours after catalog is added)

For more information, see [AI Assistant for learners](/help/migrated/learners/feature-summary/learner-ai-assistant.md).

### Learning Path agent

Learners can now have a guided conversation with the AI Assistant to generate a custom, sequenced learning path based on their goals, background, and available time. The learning path is created automatically and the learner is enrolled.

Key capabilities:

* Multi-turn conversation guides the learner through topic selection, course review, and path confirmation
* Up to five suggested learning topics per conversation
* Course selection from assigned catalogs
* Maximum of 10 personalized learning paths visible on the learner home page
* Completed paths can be shared with colleagues

For more information, see [AI Assistant for learners](/help/migrated/learners/feature-summary/learning-path-agent.md).

### Insights Agent

The Insights Agent helps administrators analyze learning data through natural language queries. Ask questions about enrollment trends, completion rates, learner engagement, and skill gaps. The agent generates reports and visualizations in response.

For more information, see [Insights Agent](/help/migrated/administrators/feature-summary/insights-agent.md)

### Gen AI credits

Adobe Learning Manager integrates AI-powered features managed through a credit-based system linked to Agent Orchestrator licenses. This system requires administrators to activate features, set credit limits, and monitor usage via the Billing page. Linking the Adobe Learning Manager account to an Adobe Admin Console organization with an active Agent Orchestrator license is essential for enabling Gen AI features.

For more information, see [Gen AI credits](/help/migrated/administrators/feature-summary/billing-management.md#genaicredits)

## Channels

Channels provide a centralized way to organize, publish, and discover video content from web and Confluence pages. Administrators can create and manage channels by connecting supported web pages or Confluence pages, configure channel settings, control visibility, and synchronize content from the source. Learners can browse available channels, subscribe to channels of interest, and watch curated video content from a single location.  

Learn more about Channels.

## Report Builder

Report Builder gives administrators a flexible, self-service reporting tool that goes beyond the fixed report types available elsewhere in Adobe Learning Manager. Rather than being limited to predefined report structures, administrators can join fields from multiple datasets, like User, User Groups, Courses and Learning Paths, Modules, Transcript, Catalogs, and more — into a single custom report tailored to their organization's specific data needs.

Reports are created once and saved for repeated use. There is no need to rebuild filters, re-apply groupings, or rejoin datasets on every download. Saved reports can be downloaded on demand, shared with other administrators, or set up with a subscription so that recipients receive updated reports automatically at a regular interval.

Learn more about Report Builder.

## Custom role changes

Custom administrators can now be granted expanded user management capabilities through the Advanced permission level under Users in a custom role definition.

Two access levels are available:

| Access level | What the custom administrator can do |
|---|---|
| **Read only** | View all custom roles, import logs, and deleted users; download the custom roles report |
| **Full control** | All read-only capabilities plus: create, edit, delete, and assign custom roles; import users via CSV; purge deleted users |

Learn more about Custom role changes. For more information, see [What the Advanced user permission unlocks](/help/migrated/administrators/feature-summary/custom-role.md#whatadvanceduserpermissionunlocks)


## LTI deep linking

Integration administrators can now enable LTI Deep Linking for LTI tool configurations, allowing course authors to browse and embed Adobe Learning Manager courses directly from an external LMS without manually copying course URLs.

Once enabled, authors see a **Select content** button in the external LMS activity configuration. They can browse approved catalogs, select courses, and confirm the selection — with all fields populated automatically.

For more information, see [LTI deep links](/help/migrated/integration-admin/feature-summary/lti-deep-links.md).

## Classroom locations

Classroom Locations now support a structured **four-field location format**, including Country, State/Province/Region, City, and Location Name, making it easier to manage and organize training locations across regions. The update includes a one-time migration from the legacy single-field format and adds multilingual support for the **Location Name** and **Room Information** fields, enabling localized classroom details for learners.

For more information, see [Classroom locations](/help/migrated/administrators/feature-summary/classroom.md).

## Reporting changes in the release

Learn more about the [reporting changes in the August 2026 release of Adobe Learning Manager](/help/migrated/reporting-changes-august-2026.md).

## API changes in the release

Learn more about the [API changes in the August 2026 release of Adobe Learning Manager](/help/migrated/api-changes-august-2026.md).

## Other enhancements in the release

| Enhancement | Description |
|---|---|
| **MQA: Latest vs. Highest score** | For modules with multiple attempts, authors can now choose whether the Latest or Highest attempt score is recorded in the Learner Transcript and used in gradebook calculations. Latest was the existing default and remains so when the setting is not configured. For more information, see [Gradebook for Authors](/help/migrated/authors/feature-summary/alm-author-gradebook.md#configurescoresettingsmultipleattempts).
| **Content preview in Content Library** | Authors can now preview uploaded content files directly in the Content Library before adding them to courses. For more information, see [Preview Content Library](/help/migrated/authors/feature-summary/content-library.md#previewcontentlibrary).  |
| **Incremental user report** | A new API-based user report returns only users created or modified since the last request, reducing data transfer for large accounts using automated user sync workflows. |
| **Player performance improvements** | The fluidic course player has been optimized for faster load times and smoother transitions between modules. |
| **11 new languages in fluidic player** | The fluidic player now supports 11 additional languages, including right-to-left (RTL) script support. For more information, see [Fluidic Player](/help/migrated/learners/feature-summary/fluidic-player.md).|
| **Impact warning before retiring courses/LPs** | Administrators now see a warning listing all active enrollments and dependent learning paths before a course or learning path can be retired. |
| **CR/VC Module: Expected Duration** | Authors can now set an expected duration for classroom and virtual classroom modules, separate from the scheduled session time. This value appears in reports and learner-facing course information. |
| **LTI module migration** | Existing LTI 1.1 modules can now be migrated to LTI 1.3 using the migration tool. For more information, see [LTI migration of modules](/help/migrated/integration-admin/feature-summary/migration-manual.md). |
| **Confirmation before editing acquired courses** | Administrators in peer accounts now see a confirmation dialog before editing a course acquired through catalog sharing, preventing unintended changes to shared content. |
| **Session URL with instance ID** | Session launch URLs for Microsoft Teams, Adobe Connect, and Zoom sessions now include the instance ID, ensuring learners are routed to the correct session when multiple instances exist. |
| **Warning for large-audience announcements** | When sending an ad-hoc announcement email to more than a configurable threshold of recipients, administrators now see a volume warning before sending. |
| **Email templates: Account URL for external learners** | Email notification templates can now include a separate account URL specifically for external learners, routing them to the correct login experience. |
| **Email Builder: Rich Text Editor Support** | Email Templates in Adobe Learning Manager now support rich text formatting, attachments, and custom automations. For more information, see [Email Builder](/help/migrated/administrators/feature-summary/email-builder.md). |
| **Email Builder: Preview feature** | You can check your composed email to see how it would look at the recipient's end by using the Preview option. For more information, see [Email Builder](/help/migrated/administrators/feature-summary/email-builder.md). |
| **Webhook timestamp standardization** | All date and time fields within the `data` object of webhook payloads now have seconds set to `00`, providing minute-level precision consistent with Learner Transcript reports. |
| **Connect enhancements** | Azure Data Lake Storage (ADLS) connector updates; persistent room name support for recurring virtual classroom sessions; recording-view-based attendance tracking. |


## System requirements

View [Adobe Learning Manager system requirements](/help/migrated/system-requirements.md).

## Release notes

Check out the [release notes](/help/migrated/release-note/release-notes.md) for latest release updates. 

## Previous releases of Adobe Learning Manager

* [Adobe Learning Manager April 2026 release](/help/migrated/whats-new-april-2026.md)
* [Adobe Learning Manager October 2025 release](/help/migrated/whats-new-october-2025.md)
