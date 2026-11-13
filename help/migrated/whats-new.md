---
description: Learn about the new features and enhancements in the August 2026 release of Adobe Learning Manager
jcr-language: en_us
title: What's new in Adobe Learning Manager December 2026 release
exl-id: da46f186-3ff3-422a-af49-31c7405fd584
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
---

# What's new in Adobe Learning Manager (December 2026 release)

## Report Builder charts and dashboards

Adobe Learning Manager has added charts and dashboards to Report Builder, so administrators can visualize report data without leaving the product. You can create charts from the columns of a report, with aggregation and filtering available on each chart. Supported chart types:

- Big number

- Line chart

- Bar chart

- Pie chart

- Pivot table

A report dashboard holds charts built from one report. A custom dashboard combines charts from several reports, such as enrollment and user data, and supports up to 20 widgets. Charts that belong to a report are shared when you share the report. This helps administrators keep current report data in one view instead of rerunning reports. Charts display up to 10,000 data points, and pivot tables show up to 100 rows and 100 columns. If a chart exceeds a limit, apply filters to narrow the results. Dashboards can't be exported yet.

## Insights Agent reports in Report Builder

Administrators can now continue an Insights Agent answer in Report Builder. When Insights Agent answers a question, Report Builder maps the same query to its own fields in a parallel step. You open the resulting report, review it, edit it, and save it. From there you can use the same Report Builder capabilities as any other report, such as subscriptions.

If part of a question can't be expressed with Report Builder fields, the report lists that part as a gap. If the missing part is central to the question, the report isn't offered. Complex queries can produce reduced results, so review each report before you rely on it.

## Adobe Experience Manager Assets integration

Adobe Learning Manager now connects to Adobe Experience Manager Assets, so learning content and image assets comes from the same approved source as the rest of your brand's content. This removes the manual download-and-re-upload step between the team that manages assets in the DAM and the team that builds courses in ALM.

What it changes:

* **Approved assets, used directly.** Authors browse and select assets from Experience Manager Assets without leaving ALM, so courses use current, approved files rather than local copies that can drift out of date.
* **Updates carry through.** When an asset changes in the DAM, the update can flow into the courses using it automatically, keeping content consistent as assets are revised.
* **Access follows existing permissions.** Authors only see the assets they already have access to in Experience Manager Assets, so browsing in ALM respects the same permissions as the DAM itself.

The result is a single, governed path from asset to learner, with less manual work and fewer version mismatches.

## File submission enhancements

File submission modules now support team submissions, rubric-based evaluation, and a setting that controls whether instructors must approve submissions.

### Team submissions

Instructors can now create teams for file submissions. Each team submits one file for the whole team. The instructor evaluates the submission once, and the result applies to every member. Teams form in two ways: Instructors build them manually, or a scheduled process builds them before the instance start date, based on members per team or number of teams.

Instructors manage teams on a new **Teams management** page and review work on a team submissions page. They can unsubmit an approved submission to unlock a team, for example when a member leaves. A team holds up to 100 members. Learners can view their team, its members, and the evaluation result. Team modules can't be added or deleted after a course is published.

### Rubric-based assessments

Authors can now define a rubric, called an evaluation plan, for file submission modules. A rubric supports objective questions with scored options and subjective questions with written review. This makes evaluations consistent across learners. It applies to individual and team submissions.

Authors also control related settings:

- Whether learners view the rubric questions before they submit
- Whether scoring is one overall score or a score for each criterion

Each question can be required and can allow reviewer remarks. A rubric holds up to 100 questions, and authors enter questions separately for each locale. After a course is published, only question text can change.

### Instructor approval or automatic completion

Authors can now choose whether instructors must approve submissions in a file submission module, or whether completion is automatic. This is a separate setting from the evaluation plan.

## Model Context Protocol server for Learner Assistant

ALM provides learning where learners are by offering MCP server for learners. Allowing learners to access ALM from anywhere including ChatGPT, Claude and custom agents. Easy configuration via Integration admin allows admins to have access to six core tools for learners. This includes two of the important Learner AI Assistant tools - Answer Agent and PLP.

- Search

- List enrollments

- Get learning object

- Get user profile

- Answer learning content question

- Personalized Learning Path

Administrators can edit each tool description, for example to add organization-specific examples. Clients read the authorization details from the server metadata, so setup needs only a client ID and client secret.

## Personalized learning path editing and branding strips

- Learners can now remove suggested topics or courses with a single click, in addition to the existing option to refine topic and course lists through chat.

- Administrators can now reposition the personalized learning paths strip on the learner home page through the Branding page.

## Virtual Coach: AI-powered role-play for skills practice

Adobe Learning Manager now offers Virtual Coach, an AI-powered role-play and coaching solution that lets learners practice realistic workplace conversations, such as sales objections, customer escalations, or performance reviews, before having them for real. Authors create scenarios from their own reference materials using templates or an AI assistant, and learners speak with an AI persona that adapts to their responses in real time. After each session, learners get instant scoring and coaching feedback on both knowledge and communication style, measured against criteria the author defined. Available in nine languages, Virtual Coach works as a standalone job aid or embedded within a course.

## Learning path citations in Learner Assistant

Learner Assistant answers now cite the learning path that contains a source course, along with the course itself. Learners open either the course overview or the learning path page from the citation. Answers drawn from a job aid include a download link. This helps learners find the training that answers their question.

## AI Assistant configurations

The Administrator Assistant offers two agents—Insights Agent and Knowledge Assistant— which can be configured individually. The Learner Assistant offers three agents—Knowledge Assistant, Answer Agent, and Learning Path Agent, which can be configured along with the catalog configuration.

## Webhooks for instructor edits to learning object instances

The learning object instance modification webhook now fires when an instructor edits a virtual classroom session, in addition to administrator and author changes. Changes such as session timings, venue, enrollment limit trigger it. Headless customers can then retrieve session details through the public API and pass updates on to learners.

## Multi-enrolled courses in the compliance widget

The compliance widget now lists every instance of a multi-enrollment course that a learner must complete. Each entry shows the instance name, and an instance without a deadline is hidden when another instance has one. The enrollments endpoint of the public API supports the same behavior through an optional parameter.

## Resend virtual classroom session invites

Administrators with course edit permission can now resend a session invite from the instance page. Select **Resend**, search for the learner, and send. The option is available for current and future virtual classroom sessions. For learners in multiple instances, the invite goes only to the selected instance. Learners who aren't enrolled in the session are skipped with a warning.

## Automatic attendance from Adobe Connect recording views

Adobe Learning Manager now marks attendance when a learner plays the recording of a missed virtual classroom session. A scheduled integration pulls viewer data from Adobe Connect and compares playback time with the completion criteria set for the account. Administrators set the schedule in the integration admin app. Skipping through a recording doesn't count, because only actual viewing time is used.

## Email Builder for courses and instances

Email Builder in Adobe Learning Manager lets administrators and authors create branded learner communication templates. In the December 2026 release of Learning Manager, the full Email Builder experience is available for course-level and instance-level emails. Authors can customize these emails while inheriting the layouts and formatting that administrators define.

With Email Builder, you can:

- Create reusable email layouts

- Apply organization branding

- Customize banners and signatures

- Define default fonts and colors

- Standardize communication across courses and learning programs

Administrators create account-wide email templates and layouts. Authors customize emails at the course and instance levels without rebuilding templates from scratch.

Banner and signature settings have moved. Earlier, these settings appeared on a separate **Settings** tab. That tab is removed, and **Banner** and **Signature** now appear in **Global Layout**.

### Email Builder hierarchy

Email Builder uses a hierarchy. Each level inherits from its parent level and allows local customization.

| **Level**         | **What it provides**                                                                                                | **Who customizes it** |
|-------------------|---------------------------------------------------------------------------------------------------------------------|-----------------------|
| Account layout    | Branding, fonts, colors, and header and footer structure                                                            | Administrators        |
| Account template  | Global email styling, common messaging components, and shared branding                                              | Administrators        |
| Course template   | Course-specific emails, such as enrollment messages, course reminders, completion emails, and session notifications | Authors               |
| Instance template | The highest level of customization, such as cohort-specific, session-specific, or regional messages                 | Authors               |

All courses can inherit from account templates. Course emails inherit the organization's layout and allow content customization.

### Layout inheritance

A template links to the nearest available layout. An instance-level template links to an instance-level layout if one exists. If none exists, the template links to the nearest parent layout. You can view which level a layout comes from.

When a template is linked to a layout:

- Branding flows into the template automatically.

- Authors update only the content.

- The layout reduces duplication across messages.

You can unlink a template from its layout. After you unlink a template:

- The template keeps its existing design.

- Future layout updates don't affect the template.

- The template becomes independently editable.

Layout inheritance depends on the parent layouts that are available. When both levels exist, instance-level emails override course-level templates.

### Administrator and author workflow

Administrators create an account layout, create an account template, and publish the branding. Authors then inherit the layout, customize the course email, save the template, and publish the course. Authors use instance-level templates when cohorts need different messages, which they manage through course instances.

### Availability of Email Builder for course and instance emails

If Email Builder is already enabled for your account, you receive the new changes automatically and don't need to take any action. Existing email functionality continues to operate independently of Email Builder migration activities.

## Custom learner attributes in Learning Tools Interoperability

Adobe Learning Manager now reads custom learner attributes through the optional Names and Role Provisioning Services endpoint of Learning Tools Interoperability. It also reads them from the launch request. Attributes such as country or city are stored in groupable profile fields. Launch parameters need a required prefix so that Adobe Learning Manager recognizes them. Some learning systems, such as Moodle, don't support this endpoint.

## Discussion board instructor notifications

Headless customers can now send instructors and cohort managers a digest of discussion board activity. Using the API, you add subscribers to a board. They receive new posts, comments, and replies in a single email, at an interval you set. Likes and dislikes aren't included. The feature is turned on through the API.

## Relevance ranking in admin catalog search

Catalog search in the admin view now ranks results by relevance, using the same search service as learner and admin search elsewhere. An exact match, such as a catalog name with a specific date, appears first, followed by partial matches. The suggestion list while typing follows the same order.

## Session cancellation sync from Adobe Workfront

Sessions canceled in Adobe Workfront carry over to Adobe Learning Manager through the Migration process, with no manual steps. Migration adds an optional **State** column that accepts Active or Cancelled. A blank value leaves the session unchanged. A cancellation made through Migration behaves like one made in the Learning Manager interface. Learners, instructors, administrators, authors, and managers receive the same cancellation emails.

Two behaviors apply to canceled sessions:

- Migration doesn't apply detail changes to a canceled session, and it returns a validation error for those rows.

- Setting the state to Active reactivates the session, and you can then update its details or cancel it again.

Session updates continue to work as before.

## Character limit for first names

Adobe Learning Manager now accepts first names of up to 255 characters, up from 63. This applies to users added in the interface, through CSV import, and in self-registration, so user syncs from other systems no longer fail on long names.

Adobe Learning Manager supports longer first names so that you can bring users with long names into your account without trimming them. This is especially helpful when you migrate users from an external system or automate user creation.

Beginning with the December 2026 release, the first name field accepts up to 255 characters. Earlier releases accepted a maximum of 63 characters.

>[!NOTE]
>
>The limit applies to all users in your account, regardless of their role. Existing users and their names aren't affected by this change.

You can enter long names when you add or edit users in the following ways:

- Add a single user in the admin interface

- Edit an existing user

- Import users with a CSV file

- Register users through self-registration

- Add external users

Long names can be wider than the space available in some parts of the interface. To keep the layout readable, Adobe Learning Manager shortens long names in compact areas, such as:

- Table cells

- Dropdown list items

- Search results

To view the full name, hover over the shortened name.

### Add a user with a long name

If a user's name is longer than 63 characters, you can now add the user to your account without shortening the name. The first name field accepts up to 255 characters.

### Add a single user

1.  Log in to Adobe Learning Manager as an administrator.

2.  In the navigation pane, select **Users**.

3.  Select **Add** \> **Single User**.

4.  In the **Name** field, type the full name. The field accepts up to 255 characters.

5.  Type the remaining required details, such as the unique identifier and email address.

6.  Select **Save**.

The user is added to your account with the full name. In compact views, the name appears shortened. Hover over the name to view it in full.

### Import users that have long names

If you add users in bulk, you can include long names in your CSV file. The first name column accepts up to 255 characters.

1.  Prepare your user CSV file. Ensure that each first name is 255 characters or fewer.

2.  Log in to Adobe Learning Manager as an administrator.

3.  Import the CSV file by using the **Upload a CSV** option.

Review the import results to confirm that all users were added.

## Badge information for courses and learning paths

When authors add courses or learning paths, a window now lists existing courses and learning paths with badge information. The badges show the name, type (course or learning path), publication status, and course format, such as self-paced, virtual, classroom, or blended.

## Non-logged-in enhancements

Adobe Learning Manager has long let anonymous visitors browse catalogs and course overviews, but playing any content required a login. For customer-education academies, this gate appears when a prospect finds a relevant course and wants to evaluate it, so each gated play can cost a lead.

Non-logged-in enhancements in this release remove that barrier in a controlled way. Administrators choose which catalogs are public, and authors choose which courses and modules anyone can play without an account. Learning Manager also publishes crawlable, AI-readable pages so academies can be found through search engines and AI assistants like Claude and ChatGPT. Anonymous usage is metered per visitor and reported separately from logged-in usage.

## Retire a course without making a learning path inaccessible

A retired course or nested learning path is removed from the higher-level learning object, which stays open for new enrollments. Retiring a course no longer makes the learning path inaccessible.

## Non-logged-in page URL for self-registration profiles

Self-registration profiles let external users, such as partners or members of multiple organizations, create their own Adobe Learning Manager accounts. Each profile can now have its own shareable non-logged-in menu URL, built in Experience Builder.

When users select **Sign up** from a page reached through that URL, they're added to the profile the URL belongs to. This keeps users from different organizations, such as separate agencies or partner companies, in separate profiles.

## Store last access dates for learning path enrollments

Adobe Learning Manager now lets you attach custom metadata, such as a last access date, to a learning path enrollment. You set and read it through the API, which helps you track time-bound access to the learning paths you assign.

Course enrollments already support a last access date through the API, which controls how long a learner can access the course. Learning path enrollments now offer a generic metadata field, so you can store a last access date or any other value you want to track.

## Export Report Builder reports with the Job API

This release of Adobe Learning Manager adds a new Job API job type, generateCustomReport. Pass a report ID to automatically export any report you created in Report Builder.

Combined with the new L2 quiz dataset in Report Builder, you can now:

- Export question-level (L2) quiz data across multiple courses and modules in a single report, rather than running generateQuizReport once per course.

- Automate recurring exports, such as a daily incremental export to your data warehouse or business intelligence tool.

Existing job types, including generateQuizReport, are unchanged.

## Column heading changes in downloaded reports

Report Builder now includes the dataset name in default column headings of downloaded reports, so Name from the Learning Object dataset appears as "Learning Object - Name" instead of "Name." For aggregated columns, the heading also includes the function, such as "Count of Learning Object - ID." If you enter a custom name in a column's Alias field, that alias is used as the heading and stays unchanged. After the upgrade, existing reports without custom aliases show the updated headings, while report data, filters, and schedules aren't affected. If your scripts, spreadsheets, business intelligence dashboards, or integrations reference columns by heading, update them to the new names, or set a custom alias to keep a specific heading.

## Live Hub

Live Hub is now generally available for Ultimate customers and remains in beta for Prime customers.

## Multilingual support for closed captions in Live Hub

Closed captions in Live Hub have been enhanced to support additional languages. Instructors can now select the caption language in **Room settings** based on the language spoken during the session.

Captions are generated automatically in the selected language and displayed in a dedicated panel that updates continuously as the instructor speaks. All participants view captions in the language selected by the instructor.

This enhancement improves accessibility for participants across different languages and helps them follow live sessions more effectively.

## Localized Live Hub interface and recording player

The Live Hub interface now displays in the language selected for the Learning Manager user interface. Labels and headings throughout the session, including chat, attendees, polls, breakout rooms, and settings, appear in the user's chosen language. Live Hub supports the same 18 interface languages as Learning Manager, including English. The recording player is also localized, so elements such as polls display in the course language. For example, a recording of a German course displays the player interface in German.

This gives global participants a consistent experience across the platform and in session recordings.

## Live Hub sessions up to 5,000 attendees

Live Hub now supports large-scale sessions with up to 5,000 attendees, allowing organizations to conduct large training sessions. Authors can choose 5000 capacity sessions when adding a Virtual Classroom module to a course. Live Hub automatically configures the room based on the audience size and applies specific interaction restrictions. In large sessions, camera access, screen sharing, and whiteboard functionality are limited to instructors, while breakout rooms are unavailable. Simultaneous large volume of chat messages, reactions, and questions are delivered in staggered batches. Other interactions and capabilities, including polls, quizzes, recording, and attendance tracking, continue to function as they do in regular sessions.

This allows organizations to run large trainings within the same platform, with a room that can be set to the expected audience size.

## Channels

Channels are now generally available for all customers.

## Group enrollment windows and seat reservation

Group enrollment reservation and waitlist management give Authors finer control over who can enroll in Classroom and Virtual Classroom courses. Authors can allocate seats to specific user groups and set separate enrollment open dates for those groups and for all other learners. They can also turn on automatic waitlist promotion with a cut-off date, so a freed seat goes to the next eligible learner. Reserving all seats restricts a course to the selected groups.

## Support for multiple Zoom connections

Adobe Learning Manager now supports multiple Zoom connections within a single account, allowing organizations to manage virtual classroom sessions across different Zoom accounts.

Integration Admins can configure multiple Zoom connections and assign them to specific roles or user groups. When creating or editing a course session, authors can select from the Zoom connections available to them, with each session using one connection.

This enhancement provides greater flexibility for organizations that use multiple Zoom accounts, particularly for:

- **Department-specific training**: Manage separate Zoom accounts for different departments or teams within the same Learning Manager account.

- **Partner and external training**: Assign dedicated Zoom connections to specific partners or user groups to support their training sessions.

- **Controlled access**: Restrict the availability of Zoom connections based on roles or user groups, ensuring authors can select only the connections assigned to them.

- **Simplified connection management**: Enable integration admins to centrally manage multiple Zoom connections without affecting existing sessions.

## Safe Exam Browser integration for quizzes

Adobe Learning Manager now integrates with Safe Exam Browser for native quizzes, providing a secure, controlled environment for conducting assessments. Administrators can enable the integration at the account level and upload a Safe Exam Browser configuration file (.seb) to define the assessment restrictions. Authors can then choose which individual quizzes require Safe Exam Browser.

When learners attempt a quiz that requires Safe Exam Browser, they are prompted to launch the browser. This blocks access to other browsers and applications for the duration of the assessment as per the admin-defined restrictions. Learners who don't have it installed are prompted to download it.

**Where it helps:**

- **Certification assessments:** Conduct quizzes where restricting access to external resources is important.
- **Compliance training:** Support controlled assessments for mandatory training and regulatory requirements.
- **High-stakes evaluations:** Reduce opportunities to access unauthorized applications or resources during important assessments.
- **Flexible assessment management:** Allow Authors to require Safe Exam Browser only for quizzes that need additional restrictions.

## Accessibility fixes in Live Hub

Accessibility fixes in Live Hub improve the experience for users of assistive technologies and keyboard navigation.

- **Screen readers**: Controls and content are now announced correctly with NVDA, JAWS, VoiceOver, and TalkBack.
- **Keyboard navigation**: Every interactive element is reachable in a logical tab order with a visible focus indicator, focus no longer gets trapped, and a skip-navigation link is available.
- **Closed captions**: Live sessions show real-time captions, recordings support caption upload and toggling, and the caption toggle can be operated from the keyboard.
- **Color contrast**: Text and UI components now meet the required contrast ratios, and a high-contrast theme is available.
- **Zoom and reflow**: Content and functionality are preserved at 200% browser zoom, and Live Hub works with screen magnifiers.

## API changes in the December 2026 release

### Bookmark API ordering and retired content handling

Learners can bookmark trainings to revisit later, but the bookmark APIs returned them in no set order, so headless integrations couldn't show recent saves first. Bookmarks to retired learning objects also stayed in the list and led to "Page not found" errors.

This update fixes both:

- Bookmarks are now returned newest first.

- Bookmarks to retired learning objects are no longer returned.

No new endpoints, parameters, or response attributes are added, so existing integrations keep working without changes.

### APIs for discussion board instructor notifications

This release includes new APIs that support discussion board instructor notifications. Use them to subscribe instructors and cohort managers to discussion boards and to control which activity appears in their digest emails.

### API support for multi-enrolled instances in the Learner app

The enrollments API now supports multi-enrolled instances in the Learner app. Add the optional includeMultiInstanceEnrollments=true parameter to GET /enrollments to include them. The default is false, so existing integrations, including headless implementations, keep working unchanged.

### Last access date for learning path enrollment

You can now store custom metadata, such as a last access date, on a learning path enrollment and set and read it through the API. This helps you track time-bound access to the learning paths you assign.

- Set the metadata on an existing enrollment or when you enroll a learner, using an admin token.

- Read it with an admin or learner token.

The metadata is for your own tracking. It doesn't control access and isn't applied to the courses in the path.

### Job API job type for Report Builder exports

The Job API has a new job type, generateCustomReport, that exports any saved Report Builder report when you pass its report ID. With the new L2 quiz dataset, you can export question-level quiz data across multiple courses in one report and automate recurring exports.

Existing job types, including generateQuizReport, are unchanged.

### APIs for the Zoom connector

Use these APIs to view and manage Zoom connectors in Adobe Learning Manager. Use them to retrieve existing Zoom connections, save Zoom credentials, create or update connections, and manage access permissions for user groups and custom roles.

#### API sequence

Use the APIs in this sequence:

| **Step** | **API**                             | **Purpose**                                                       | **Authentication**        |
|------------------------------------|---------------------------------------------------------------|---------------------------------------------------------------------------------------------|-----------------------------------------------------|
| 1        | POST /ctr/authcred/uuid/20012       | Save the Zoom credentials.                                        | Integration Admin session |
| 2        | POST /ctr/app/esconnect             | Create a Zoom connection or update an existing one.               | Integration Admin session |
| 3        | PUT /ctr/xtsa/{connectionId}/access | Set the user groups and custom roles that can use the connection. | Integration Admin session |

#### Authentication and permissions

These APIs are session based. Call them as an Integration Admin who is logged in to Adobe Learning Manager. They don't use an API key or an OAuth token. Each request needs the following headers:

- x-acap-caller-role: ROLE_INTEGRATIONADMIN

- x-csrf-token: The session-bound token that is embedded in the Integration Admin page HTML as csrfToken.

- Cookie: The session cookies of the logged-in admin.

>[!NOTE]
>
>The clientSecret is sensitive. The view call GET /ctr/app/connection/{id}/object/10002 returns it in clear text. Rotate the secret if it is exposed, and don't share session cookies, CSRF tokens, or credentials.
