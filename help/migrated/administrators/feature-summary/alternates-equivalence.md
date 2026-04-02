---
title: Equivalents and alternates in Adobe Learning Manager
description: Deliver a frictionless learning experience and eliminate redundant training with Equivalents and Alternates in ALM. This new capability allows admins to configure one-way (alternates) or bidirectional (equivalents) rules, where completing one training automatically grants alternate completion for another
jcr-language: en-us
---

# Introduction

In many organizations, learners encounter training situations where different courses can legitimately satisfy the same requirement. For example, when should a new course replace an older one? When should a more comprehensive course stand in for a shorter one or when should a special substitute course be offered?

The Alternate Courses or Learning Path feature gives ALM a formal way to say:

"If the learner completed this training, treat them as having satisfied that related training requirement."

The feature works across courses and Learning Paths, ensures downstream requirements such as prerequisites and compliance rules are honored, and does this without forcing learners to sit through redundant content. It also keeps reporting accurate by recording what was completed directly versus what was satisfied via an alternate.

At the core, the feature introduces the concept of an alternate completion: a special completion state created automatically when a learner finishes a configured source training that counts towards another target trainings.

## Equivalents vs. alternates

Some training relationships are bidirectional, meaning each course can satisfy the other's requirement. This is effectively a scenario where two trainings are treated as mutually substitutable. In contrast, unidirectional relationships allow one training to satisfy the requirement for another, but not vice versa. ALM models both scenarios using the same underlying alternate completion mechanism.

- **Bidirectional relationship:** Completing either training satisfies the requirement for the other.
- **Unidirectional relationship:** Completing Training A satisfies Training B, but completing B does not satisfy A. This is common when a newer or more comprehensive version should count toward an older requirement, but not the reverse.

Alternates are most often used in **unidirectional** scenarios. For example, when a more comprehensive superset course covers everything in a simpler subset course. Completing the superset should satisfy the requirement for the subset, but not necessarily the other way around.

- A newer, expanded course that should count toward an older requirement.
- A course designed for a specific audience (for example, a regional or accessibility-adapted variant) that still fulfills the same requirement as the primary course.
- An enhanced new version of a course that the organization wants to count for an older requirement, but the older version should not count for the new requirement.

In Alternates, the relationship is normally **one-way**. If Course A is an alternate for Course B, completing A can satisfy B's requirement, but completing B does not necessarily satisfy A.

Both equivalents and alternates share the same underlying mechanism in ALM: when a configured source training is completed, ALM automatically produces an alternate completion for one or more target trainings.

## What problems does this solve?

Without Alternates and Equivalents, administrators and learners face several recurring issues:

- Learners are frequently asked to repeat courses that cover content they already completed in a different version or format.
- Updating compliance programs is simpler because admins can replace or restructure trainings without forcing learners who completed older versions to retake equivalent or superseded content.
- Prerequisite logic is rigid. If a path requires a particular course as a prerequisite, there is no clean way to recognize that another training is good enough.
- Reporting and audits are harder. There is no formal signal showing that a requirement was satisfied via an alternate completion and no straightforward way to trace the source of the credit.

The Equivalents and Alternates feature addresses these issues by:

- Preventing duplicate effort for learners when alternates are valid.
- Allowing admins to modify training structures (for example, swap a course inside a path) without breaking completions for learners who took the earlier version.
- Allowing prerequisites and compliance checks to respect both direct completions and alternate or equivalent completions.
- Recording clearly, in transcripts and reports, whether a training was completed directly or satisfied via an alternate relationship, along with which training served as the source.

## How the feature works conceptually

The feature is built on three main ideas: **relationships**, **alternate completion**, and **downstream behavior**.

### Relationships between trainings

Administrators define relationships between courses and Learning Paths. For each relationship, they choose a **source** and one or more **targets**. A single course might have up to 30 targets depending on how many earlier or related trainings it should satisfy.

For equivalents, admins can make the relationship **bidirectional** if they want both trainings to satisfy each other. For alternates, admins normally keep the direction one-way to reflect that only some substitutions are allowed.

These relationships are stored at the training level, not at the learner level. Once configured and enabled, they apply to all current and future completions of the source training, subject to account-level settings such as whether retroactive completion is enabled.

### Alternate completion

When a learner completes a source training, ALM examines all configured alternate or equivalent relationships and, for each relevant target training, creates an **alternate completion record**. This record is distinct from a normal completion:

- It marks the target training for the learner but keeps track that it was completed via alternates or equivalents rather than directly.
- It records which source training was used to satisfy the target.
- It is stored in a dedicated structure so reporting can distinguish between direct and alternate completions.

Learners will see alternate completion even if they're not enrolled. The Learner Transcript (LT) report includes only records of trainings that the learner has enrolled in.

### Learner app experience for alternate and equivalent completions

Alternate and equivalent completions are surfaced distinctly in the learner app so learners can clearly understand how a training requirement was satisfied, while maintaining consistency with transcripts and reports.

For the learner who is logged in, an additional filter is available under Catalogs:

- Completed via Alternate (Alternate Completions)

## LO card behavior

### Alternate completion status

When a learner completes a training via an alternate or equivalent relationship, the Learning Object (LO) card displays a distinct status such as **Completed via Alternate**.  
This visual distinction helps learners differentiate between direct completions and completions granted through configured relationships.

Alternate completion can still trigger notifications for target LOs in catalogs where the learner cannot see.

Alternate completion/incompletion notifications may not appear the same way on the mobile immersive app as elsewhere.

### Completion method indicator

The LO card includes a completion method indicator (for example, a label or icon) to show that the completion was achieved through an **Alternate**.  
If an alternate completion is later revoked due to changes such as retroactive incompletion or deletion of the source training, the LO card updates to reflect **Alternate (Revoked)**.

### Transparency and audit details

Learners can open the LO card to view additional details, including:

- The source course or learning path that granted the alternate completion
- The completion date associated with the source training

This ensures transparency and supports audit and compliance reviews.

## Filtering and views

### Completion method filter

The learner app provides a filter that allows learners to distinguish between:

- Completed  
- Completed via alternate (This filters only alternate completions.)
- When you select Completed and Completed via alternate, you'll be able to see all completions

This enables learners to quickly understand how their learning requirements were fulfilled.

### Transcript and progress views

The completion method filter is available in learner-facing views such as:

- Learner transcripts
- Progress and completion tracking sections

These views clearly indicate which trainings were completed directly and which were satisfied through alternates or equivalents.

### Reporting alignment

The filtering logic in the learner app aligns with the **Completion Method** column used in reports.  
This ensures consistency between what learners see in the UI and what administrators see in exports and compliance reports.

## Configure equivalent courses (complete each other)

Use this workflow to define courses that are **equal in value**, where completing either course should automatically complete the other.

1. Launch ALM and navigate to courses.
2. Select a course to configure.
3. Navigate to the **Alternates** section.
4. Search for and select one or more related courses.
5. For each selected course, enable **Completes each other**.
6. Save the configuration.

**Result**

- ALMm records a **bi-directional equivalence relationship**.
- Either course can act as a completion source for the other.

## Configure alternate courses (superset → subset)

Use this workflow when one course is a **superset** of another and should satisfy completion for the simpler or subset course.

1. Launch ALM and navigate to courses.
2. Select the **superset (primary)** course.
3. Go to the **Alternates** section.
4. Select one or more **alternate (subset)** courses.
5. Leave the relationship as **alternate** (do not enable completes each other).
6. Save the configuration.

**Result**

- Completion flows **one-way** from the source course to the alternate.
- Reverse completion is not applied.

## Apply completion logic after source course completion

Automatically evaluate and apply alternate or equivalent completion once a learner completes a configured source course. ALM:

1. Detects completion of a **source course**.
2. Evaluates configured relationships:
   - Equivalent relationships
   - Alternate relationships
3. For each related course:
   - Marks the course as completed if conditions are met
4. Creates a completion record with method **Alternate**.

**Key system rules**

- Alternate completion:
  - Satisfies prerequisites
  - Allows progress in learning paths and certifications
- Alternate completion does **not** award:
  - Skills
  - Badges
  - Gamification credits

## Record completion in Learning Transcript

Ensure alternate and equivalent completions are clearly distinguishable from direct completions for audit and reporting. ALM:

1. Updates the **Learner Transcript (LT)**.
2. Sets:
   - Completion status = Completed
   - Completion method = **Alternate**
3. Sets completion date equal to the **source course completion date**.

## Enable retroactive completion (optional)

Apply alternate or equivalent completion benefits to learners who completed source courses **before** the relationships were configured.

1. Open **Account-level settings** from Administrator home > Settings > General.
2. Enable **Retroactive completion**.
3. Save the configuration.

ALM:

1. Scans historical learner completions.
2. Applies alternate or equivalent completion where applicable.
3. Updates learner transcripts automatically.

## Enable retroactive incompletion (irreversible)

Revoke previously applied alternate or equivalent completions when relationships are removed or corrected.

1. Open **Account-level settings**.
2. Enable **Retroactive incompletion**.
3. Modify or remove alternate/equivalent relationships.

ALM:

1. Identifies impacted alternate completions.
2. Revokes previously applied alternate or equivalent completions.
3. Updates transcript entries to **Alternate (Revoked)**.

## Retroactive completion and incompletion behavior

ALM supports retroactive completion and retroactive incompletion to ensure that alternate and equivalent relationships remain accurate over time, even when relationships are created, modified, or removed after learners have already completed training.

### Retroactive completion

#### Definition

When retroactive completion is enabled, learners who completed a source course in the past automatically receive an alternate completion for the target course if an equivalent or alternate relationship is created later.  
This ensures that historical learning is honored without requiring learners to retake training.

#### How it works

1. An administrator enables retroactive completion at the account level.
2. The administrator defines an equivalent or alternate relationship between a source and target training.
3. The system scans historical completion records for the source training.
4. Eligible learners are granted alternate completion for the target training.
5. These records appear as **Completed via Alternate** in learner transcripts and reports.

### Retroactive incompletion

#### Definition

When retroactive incompletion is enabled, alternate completions are revoked if the underlying equivalent or alternate relationship is removed or if the source training is deleted.  
This ensures the system reflects the current and valid training relationships.

### #How it works

1. An administrator enables retroactive incompletion at the account level.
2. The administrator removes an alternate or equivalent relationship or deletes the source training.
3. The system identifies learners who received alternate completion through the affected relationship.
4. The corresponding alternate completion records are revoked.
5. Revoked records are marked as **Alternate (Revoked)** in transcripts and reports for audit visibility.

### Impact on prerequisites

Alternate completions—including those granted retroactively—are treated as valid completions when evaluating prerequisites.  
If a learner has **Completed via Alternate**, they are allowed to proceed with courses that require the target training.

If an alternate completion is later revoked through retroactive incompletion, the learner may lose eligibility for courses that depend on that prerequisite.

### Impact on learning paths and certifications

Alternate completions contribute toward completion of learning paths and certifications.  
Learners can advance or complete these programs when required trainings are satisfied via alternate or equivalent relationships.

If an alternate completion is revoked, affected learning paths or certifications may lose progress or completion status until the requirement is met through a valid completion.

### Learner experience

Learners see updated completion statuses on LO cards and in transcripts, such as:

- **Completed via Alternate**

When an alternate completion is revoked, no label is shown on the learner UI. In reports and transcripts, completion methods appear as:

- Alternate
- Alternate (Revoked)
- Direct

Prerequisite checks, learning path progress, and certification status update dynamically based on the current completion state.

Ordered LOs unlock dynamically based on alternate completion.

Skills, badges, gamification points, or feedback will not be awarded to learners upon alternate completion of targets. 

### Reporting and audit

All retroactive changes are reflected in the Learning Transcript (LT) report. After the source is deleted, the Learner Transcript can still show a source training ID next to **Alternate Revoked**. Reports clearly distinguish between direct completions, alternate completions, and revoked alternate completions to support compliance, support investigations, and audits.

The Enrollment Report leaves the Completion Source field as blank in the case of direct completion while the Learner Transcript shows the email and type for the same.

Also, Enrollment Report and Learner Transcript can show different completion dates for the same alternate completion. This is because of different date rules and is not a data mismatch.

When a target is removed from the source (or the source itself is deleted), the Enrollment Report may not display the same **Alternate or Alternate (Revoked)** status as shown in the Learner Transcript.

Even when **Equivalence** and **Alternates** are disabled, historical entries in the **Content Audit** or **Enrollment** rows may still display activity related to alternates.

The completion date may precede the enrollment date when a Learning Object (LO) is completed via an alternate path **before** the learner actually enrolls. Since alternate completions can occur regardless of learner status (**Enrolled**, **Not Enrolled**, or **In Progress**), learners may complete the LO first and only enroll in the target course later.

## Webhooks for equivalents and alternates

ALM provides dedicated webhook events for equivalent and alternate completions to support automation, integrations, and synchronization with external systems.

These events allow external consumers to reliably distinguish between direct completions and completions granted through alternate or equivalent relationships.

### Overview

When a learner completes a course via an alternate or equivalent relationship, ALM triggers a webhook event that is separate from the standard course completion webhook.  
This ensures that integrations can respond differently to alternate completions where required.

Webhook events are also triggered when retroactive completion or retroactive incompletion occurs, covering historical updates as well as relationship changes.

### Webhook event behavior

- A distinct webhook event is triggered when a learner receives **Completed via Alternate** status for a target course.
- The event is generated when the learner completes a configured source course that satisfies the target through an equivalent or alternate relationship.
- This webhook is not triggered for direct course completions.
- When retroactive completion or retroactive incompletion is enabled, webhook events are emitted for each affected learner and target course.

### Webhook payload details

The alternate completion webhook payload includes the following key attributes:

- **Learner ID**  
Identifies the learner who received the alternate completion.
- **Source course**  
The course or learning path that the learner completed directly.
- **Target course**  
The course that is marked as completed via the alternate or equivalent relationship.
- **Completion method**  
Indicates that the completion method is **alternate**.
- **Completion date**  
Derived from the completion date of the source course.
- **Relationship type**  
Specifies whether the relationship is **equivalent** or **alternate**.

For retroactive incompletion scenarios, webhook events indicate that an existing alternate completion has been revoked.

### Integration considerations

External systems can use these webhook events to:

- Update learner records
- Synchronize completion status
- Trigger notifications or downstream workflows
- Maintain audit trails for compliance purposes

Webhook consumers should explicitly differentiate between **direct** and **alternate** completions.

Alternate completions do not grant skills, badges, gamification rewards, and feedback should be handled accordingly in downstream systems.  


## Impact of retiring and deleting source training in equivalents and alternates

The lifecycle state of a source training (retired or deleted) directly affects how alternate and equivalent completions are maintained for learners. ALM handles these scenarios differently to preserve historical accuracy while ensuring current relationships remain valid.

### Retire source training

#### Definition

Retiring a course makes it unavailable for new enrollments while keeping it in the system for historical reference, reporting, and audit purposes.

#### Impact

- Existing alternate completions granted through the retired source course remain valid.
- Learners who previously completed the source course continue to hold alternate completion for the target course.
- No new alternate completions are generated from the retired course, since it cannot be completed by new learners.
- Learner transcripts and reports continue to display **Completed via alternate** for affected learners.

### Delete source training

#### Definition

Deleting a course removes it entirely from the system, including its completion records and configured relationships.

#### Impact

- If a source training is deleted or targets are revoked (or via ALP retrigger), the status may change to Alternate (Revoked). Retiring an LO does not trigger this status.
- If retroactive incompletion is enabled, all alternate completions granted through the deleted source course are revoked.
- Learner transcripts and reports update to show **Alternate (Revoked)** for audit and compliance visibility.
- Learners may lose progress or completion status in learning paths, certifications, or prerequisites that depended on the revoked alternate completion.
- No further alternate completions can be granted from the deleted course.

### Workflow

1. An administrator retires or deletes the source course using the admin interface.
2. The system evaluates all alternate and equivalent completions derived from the source course.
3. Completion status is updated based on the course state:
    - **Retired:** Existing alternate completions remain unchanged.
    - **Deleted:** Alternate completions are revoked if retroactive incompletion is enabled.
4. Learner transcripts and reports reflect the updated status to support compliance and audit requirements.

## No chaining of relationships

ALM does not support chaining of alternate or equivalent relationships. Alternate completions are granted only for directly configured relationships and do not cascade across multiple levels of courses.

### Concept: no chaining of relationships

#### Definition

Chaining refers to allowing alternate or equivalent relationships to propagate across multiple courses.  
For example, if Course A is an alternate for Course B, and Course B is an alternate for Course C, chaining would imply that completing Course A grants completion for Course C.

#### Policy

Chaining is not supported.  
Alternate and equivalent relationships are evaluated only at a single level. Completing a source course grants alternate completion only to its immediate target course or courses, not to any downstream targets.

### Workflow

#### Relationship setup

An administrator defines alternate or equivalent relationships between courses, such as:

- Course A → Course B
- Course B → Course C

#### Completion event

A learner completes Course A directly.

#### System action

- The system grants alternate completion for Course B, if the A → B relationship is defined.
- The system does not grant alternate completion for Course C, even if a B → C relationship exists.

#### Direct completion requirement

To receive alternate completion for Course C, the learner must:

- Directly complete Course B, or
- Complete a course that is explicitly configured as a direct alternate or equivalent for Course C.

## Implications

### No indirect benefits

Learners cannot receive completion credit for courses further down a relationship chain unless each course (or its direct alternate) is completed.  
This ensures that learning requirements are met explicitly and predictably.

### Simplified audit and reporting

Reports and learner transcripts display alternate completions only for direct relationships.  
This avoids complex, multi-hop audit trails and ensures clarity when reviewing how a completion was granted.

## Catalog sharing with peer accounts: relationships not shared

Catalog sharing allows learning objects (LOs) to be shared across peer accounts, but alternate and equivalent relationships are managed independently within each account and are not shared.

### Concept: catalog sharing and relationships

#### Catalog sharing

Accounts can share catalogs with peer accounts to provide access to courses, learning paths, and other learning objects across accounts.

#### Relationships not shared

Alternate, equivalent, and alternate-completion relationships configured in the source account are not shared or replicated when a catalog is shared.  
Each account maintains and evaluates its own relationships independently.

### Workflow

#### Catalog sharing

An administrator in **Account A** shares a catalog containing learning objects with **Account B**.

#### Relationship configuration

Account A may have alternate or equivalent relationships defined among the learning objects in the shared catalog.

#### Peer account access

Account B receives access to the shared learning objects but does not inherit any alternate or equivalent relationships configured in Account A.

#### Independent management

If Account B requires similar alternate or equivalent behavior, an administrator in Account B must manually configure the relationships within that account.

### Implications

#### No automatic relationship propagation

Alternate and equivalent relationships are not automatically available in peer accounts through catalog sharing.

#### Manual setup required

Each peer account is responsible for defining and managing its own relationships for shared learning objects.

#### Consistency considerations

Completion behavior, prerequisite satisfaction, and reporting may differ across accounts unless relationships are intentionally aligned through manual configuration.

## Downstream behavior

Once an alternate completion exists for a target training, ALM uses it in downstream checks:

- If the target training is a **prerequisite** for other trainings, the learner becomes eligible for those trainings as if they had completed the target.
- If the target is a **mandatory course in a learning path**, the path's completion logic can treat the learner as having completed that part and proceed to mark the path complete when other conditions are met.
- Compliance and other dashboards such as Group Success Dashboard that rely on whether a training requirement is met can include learners who only have alternate completions.

The system distinguishes between actual completion and alternate completion so that:

- If the learner later takes the target training directly and completes it, this direct completion can override the need for the alternate completion.
- If the relationship between source and target is removed or changed, ALM can remove or adjust the alternate completions without touching genuine completions, provided retroactive incompletions are enabled for the account.

Alternate completions are designed not to interfere with actual learner activity on the target training. They act as an overlay that can be revised if the relationships change.
