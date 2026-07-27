---
description: Deliver one course to multiple audiences by controlling which modules each learner sees, and which are required, based on the user groups they belong to.
jcr-language: en_us
title: Adaptive Courses in Adobe Learning Manager
contentowner: mmanuel
---

# Adaptive courses in Adobe Learning Manager

Adaptive courses in Adobe Learning Manager let you deliver one course to multiple audiences by controlling which modules each learner sees, and which are required, based on the user groups they belong to.

Instead of building separate courses for each role, region, or compliance profile, a single adaptive course dynamically presents the right content to the right learner. 

## What problem adaptive courses solve

Organizations that train large, diverse workforces face a common challenge: data privacy, workplace ethics, and safety must reach learners with different roles, locations, or compliance obligations. 

That creates duplication: authors maintain multiple nearly identical courses, reporting is fragmented, and when core content changes every copy needs updating.

An adaptive course solves this by letting authors configure visibility and completion rules at the module level, tied to user groups. One course serves every audience simultaneously.

### Common scenarios

- A compliance course has a core module for all employees plus jurisdiction-specific addendum modules. Each learner sees only the addendums that apply to their location.
- A new-hire course shows different modules to employees, managers, and contractors. Each role sees only what's relevant to them.
- A safety course adds a new mandatory module mid-year. Admins trigger a refresh completion so all previously completed learners must do the new module to remain compliant.

### Real-world example

An organization rolls out a mandatory compliance course to its entire workforce. The course contains seven modules:

- Two modules apply to all employees.
- Two modules apply only to people managers.
- Two modules apply only to individual contributors in technical roles.
- One module applies only to senior directors and above.

## How module visibility and completion work

Each content module in an adaptive course has two settings:

**Visible to:** User groups that can see the module. Learners in these groups see the module in the course and can access it, but it doesn't count toward completion unless they are also in **Mandatory for**.

**Mandatory for:** User groups for which the module is required to complete the course. A module listed under **Mandatory for** is automatically visible to those groups; you don't need to add the same groups to both settings.

A module is in one of three states for any given learner at any point in time:

| State | How it's determined | Counts toward completion? |
|---|---|---|
| Mandatory | Learner is in a user group listed under **Mandatory for** | Yes - must be completed |
| Optional | Learner is in a group under **Visible to** but not **Mandatory for** | No - visible and accessible but not required |
| Hidden | Learner is not in any group under either setting | Not visible to the learner at all |

## Characteristics of an adaptive course

The defining characteristic of adaptive courses is that the course evaluates the learner's profile continuously, not just at enrollment.

When a learner's user group changes while they are enrolled:

- Modules no longer visible under their new user group disappear immediately.
- If a newly visible module is mandatory for their new user group, it is added to their completion requirement.
- If a previously mandatory module is no longer mandatory, it is removed from their completion requirement.
- Previously completed modules remain completed. A profile change does not reset work already done.

### Auto-unenrollment

If a user group change removes all a learner's mandatory modules, the learner is automatically unenrolled from the course.

### Auto-completion

If a user group change removes all remaining incomplete mandatory modules from an in-progress learner, the course completes automatically for that learner.

If a profile change results in new mandatory modules the learner hasn't completed, an administrator can trigger a refresh completion to roll back the existing completion and require the learner to complete the new modules.

## What adapts and what stays the same

Adaptive rules apply only to **content modules**. The following apply to all enrolled learners regardless of user group:

- **Pre-work modules:** Shown to all learners before the core content begins.
- **Test-out modules:** Available to all learners; completing a test-out completes the course regardless of content module status.
- **Prerequisites:** If a course has prerequisites configured, all learners must satisfy those prerequisites before enrolling, regardless of their user group. Prerequisites are not adaptive and cannot be scoped to specific user groups.

Job aids and resources attached to the course are also not adaptive. They are visible to all enrolled learners.

Skills, gamification points, and badges are awarded based on the learner's first course completion and are not affected by re-completions resulting from profile changes.

>[!NOTE]
>
>When an adaptive course is a part of a higher order LO that is externally shared, the adaptive course will be copied as a regular course in the child account.


## Feature availability

The adaptive course feature is controlled by a two-tier account-level flag. Contact your Adobe account team to enable this feature for your account.

Once the account flag is enabled:

- A **Completion and Visibility Rules** toggle becomes available when creating or editing a course.
- Enabling the toggle activates the adaptive configuration panel.

**Caution:** Enabling the adaptive feature flag is **irreversible**. Once enabled at the account level, it cannot be disabled.

## Catalog sharing

Adaptive courses can be added to catalogs within your account. When a catalog is shared externally to a peer account, adaptive courses are automatically excluded from the shared content.

>[!NOTE]
>
>When a Learning Path or certification containing an adaptive course is shared externally, the receiving account sees the Learning Path or certification in their catalog, but the adaptive course within it does not appear. The Learning Object is not excluded entirely; only the adaptive course component is removed from the shared version. Authors in the receiving account should be aware that the shared Learning Object may have fewer modules than the source version.

>[!NOTE]
>
>When an adaptive course is configured as a prerequisite of another course, and that parent course is shared to a receiving account via catalog sharing, the adaptive prerequisite course is not shared to the receiving account. This applies whether the prerequisite is set directly on the course or through a higher-order Learning Object such as a Learning Path or certification.
>
>In the receiving account, the parent course is available but the adaptive prerequisite is absent. Learners in the receiving account are not affected by the missing prerequisite because the prerequisite dependency is not enforced for content that arrives through catalog sharing without its prerequisites present.
>
>Do not configure adaptive courses as prerequisites for content you intend to share externally.

## Supported configurations

| Configuration | Supported? |
| --- | --- |
| Adaptive course in a regular Learning Path | Yes (see note below) |
| Adaptive course in a flex Learning Path | Yes |
| Adaptive course in an adaptive Learning Path | No |
| Adaptive course in a certification | Yes (not recommended for recurring certifications) |
| Multi-enrollment | No |
| Instance switching | Yes |
| Catalog sharing (cross-account) | No |
| Visibility rules on pre-work or test-out modules | No |
| Visibility rules on core content modules | Yes |

>[!NOTE]
>
>When an adaptive course is included in an **ordered** Learning Path, learners who have no visible modules in the adaptive course, because their user group does not match any module's visibility rules, cannot complete that course. In an ordered Learning Path, this blocks all subsequent items from becoming accessible. To avoid this, ensure that every learner enrolled in the Learning Path belongs to at least one user group that has visibility to at least one module in any adaptive course in the path. 

Additionally, do not embed a Learning Path that contains an adaptive course inside a higher-order (nested) Learning Path. In this configuration, if a learner has no visible or mandatory modules in the adaptive course, the embedded player may become unresponsive, preventing navigation through the remaining content. This behavior is being addressed in a future release.

>[!NOTE]
>
>When a learner is auto\-unenrolled from an adaptive course inside a **regular** Learning Path, because a user group change removed all their visible modules, the parent Learning Path remains in an enrolled state. The Learning Path does not auto\-unenroll. The learner will see the Learning Path as enrolled in their transcript even though the adaptive course within it is no longer accessible. If your use case requires the parent Learning Path to also unenroll when the adaptive course does, consider using an **adaptive Learning Path** instead of a regular Learning Path to contain the adaptive course.

## Enable adaptive courses for your account

Turn on adaptive learning so authors can create courses that show different modules to different learners based on user group membership.

## Before you enable

- **Permanent:** Once enabled, Adaptive Learning cannot be turned off for the account.
- **Affects both courses and Learning Paths simultaneously:** The same flag that enables adaptive courses also enables adaptive Learning Paths.
- **Existing courses are unchanged:** Only newly created courses can be made adaptive. No existing regular course is converted automatically.
- **Authors see the option immediately:** As soon as you save, the adaptive course type appears in the authoring workflow.
- **Two-tier provisioning:** If your account has been provisioned for adaptive learning, you see the option enabled and locked. It cannot be changed from the UI. If the account has not been provisioned, the setting is not visible at all. Contact Adobe to request provisioning.

## Enable adaptive courses

1. Sign in to Adobe Learning Manager as an administrator.
2. Select **Settings** in the left navigation pane.
3. Select **General**.
4. Navigate to the section **Visibility and completion rules**. If adaptive learning has been enabled for your organization, the option will appear as locked, as shown:

![](assets/image_0001.png)

Adaptive learning is now active for your account. Authors can create adaptive courses and adaptive Learning Paths immediately.

## What changes after enabling

After enabling adaptive learning:

- Authors see a **Content visibility and completion rules** option when creating a course, in addition to the existing regular course type.
- Each content module in an adaptive course can be configured with **Optional** and **Mandatory** rules for user groups.
- Learners enrolled in an adaptive course see only the modules their user groups make visible.
- All existing regular courses remain unchanged.

## Troubleshooting

- **The Visibility and completion rules section is not visible in Settings:** The feature must be provisioned at the backend before the toggle appears. Contact your Adobe account representative or Adobe Support to request access.
- **The toggle is already enabled and appears locked:** Adaptive learning was enabled when your account was provisioned. No action is needed. Authors can already create adaptive courses.
