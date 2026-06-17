---
jcr-language: en_us
title: Available datasets in Report Builder  
description: A reference guide to the data sets, fields, and derived fields available in Adobe Learning Manager Report Builder. 
contentowner: mmanuel
---

# Available datasets in Report Builder

Report Builder organizes all available columns into data sets, named groups of related fields. This article lists each data set, describes what it contains, and notes which data sets can be combined in a single report.

**Data sets in this release**

**Data set**

**What it contains**

**Key fields**

**User**

Learner profile data for active and deleted learners

Name, email, user ID, manager, active fields, status

**Transcript**

Enrollment and completion records

Enrollment date, completion date, progress %, status, score

**Learning Object**

Course, learning path, and certification metadata

LO name, LO ID, type, catalog, catalog label, status

**Learning Object Instance**

Instance-level details for courses with multiple instances

Instance name, instance ID, enrollment limit, deadline

**Catalog**

Catalog metadata and catalog label key-value pairs

Catalog name, catalog ID, label key, label value. **Catalog Label columns are customer-configured**. They appear only if your account has catalog labels set up. The label names and values you see will reflect your own configuration.

**User Group**

User group membership and hierarchy

User group name, user group ID, parent group, member count

**Module Session**

Session details for classroom, virtual classroom, and e-learning modules

Session ID, session name, instructor name(s), start time, end time, location

List of columns in datasets

Catalog

* Creation Date
* ID
* Name

Catalog Label

* Catalog
* ID
* Name
* Value

Custom field (Learning Object)

* Learning Object Completion %
* Learning Object Compliance %

Custom field (User)

* User Completion %
* User Compliance %

Learning Object

* Author Names
* Auto-retirement Date
* Completion Count
* Creation Date
* Duration (minutes)
* Enrollment Count
* Enrollment Type
* Format
* ID
* Instance Switch Enabled
* Last Completion Date
* Last Publication Date
* Multi Enrollment Enabled
* Name
* Pre-requisites Enforced
* Price
* Skill Credit
* Skill Level
* Skill Name
* Star Rating Average
* Star Rating Count
* Started Count
* Status
* Tags
* Type
* Unique ID

Learning Object Instance

* Completion Deadline
* Creation Date
* Enrollment Deadline
* ID
* Last Completion Date
* Learning Object ID
* Name
* Status
* Type
* Unenrollment Deadline

Module

* Access End Time
* Access Start Time
* Course ID
* Course Instance ID
* Duration (minutes)
* Ending Time
* Enrollment Count
* ID
* Instructor Names
* Location
* Location Information
* Location Region
* Location URL
* Module ID
* Name
* Seat Limit
* Starting Time
* Type
* Waitlist Limit

Transcript (Learning Object)

* Completion Date
* Completion Deadline
* Completion Source
* Completion Source - User ID
* Completion Source - User Name
* Enrollment Date
* Enrollment Source
* Enrollment State
* Learning Object ID
* Learning Object Name
* Learning Object Instance ID
* Overdue
* Parent Learning Object ID
* Passing Date
* Progress Percent
* Root Certification ID
* Starting Date
* Status
* Time Spent (minutes)
* User Highest Score
* User ID
* User Latest Score

Transcript (Module)

* Completion Date
* Course ID
* Module ID
* Module Name
* Passing Date
* Progress Percent
* Quiz Module Total Score
* Starting Date
* Status
* Time Spent (minutes)
* User Email
* User Highest Score
* User ID
* User Latest Score
* User Name

User

* Adobe ID
* Content Language
* Creation Date
* Deletion Date
* Direct Team Members Count
* Email
* ID
* Interface Language
* Is Admin
* Is Author
* Is Custom Role
* Is Instructor
* Is Integration Admin
* Is Learner
* Is Manager
* Is Root User
* Last Access Date
* Manager Email
* Manager ID
* Manager Name
* Manager Unique ID
* Name
* Roles
* Source
* Status
* Team Members Count
* Timezone
* Type
* Unique ID

User Group

* Creation Date
* ID
* Members Count
* Name
* Status

User Group (Active Field)

* Creation Date
* ID
* Members Count
* Name
* Status

User Group (Custom)

* Creation Date
* ID
* Members Count
* Name
* Status

User Group (Direct Team)

* Creation Date
* ID
* Members Count
* Name
* Owner Email
* Owner ID
* Owner Name
* Owner Unique ID
* Status

User Group (Inbuilt)

* Creation Date
* ID
* Members Count
* Name
* Status

User Group (Team)

* Creation Date
* ID
* Members Count
* Description
* Name
* Owner Email
* Owner ID
* Owner Name
* Owner Status
* Owner Unique ID
* Status

**How datasets join together**

Not every pair of datasets can be combined in a single report. Data sets must share a logical relationship in Adobe Learning Manager's data model to be joinable. When you add your first column, Report Builder filters the remaining data sets to show only compatible ones. If a data set appears greyed out, it can't be directly joined with the columns you've already selected.

It means that dataset cannot be joined with the columns you've already selected. This is a hard constraint in the data model. The two datasets don't share a compatible join path.

A common example is the **Compliance %** derived field. When Compliance % is selected, the **Transcript**, **Module Transcript**, and **LO Instance** data sets are disabled. Compliance % is calculated at the user or user group level against learning objects and catalogs. It's intended to be used alongside **User**, **User Group**, **Learning Object**, and **Catalog** columns and filters only.

To use a disabled data set, deselect the columns that are causing the conflict, then add the data set you need.

The join relationships below are drawn from the Report Builder data model. Understanding them helps you plan which data sets to combine before building a report.

**Hub data sets**

Two data sets act as central hubs. Most other data sets connect through them:

* **Enrollment** (enrollment data set), the primary fact table. It connects directly to **User** (the learner who enrolled), **Learning Object** (what they enrolled in), and through the learning object to **Module Session**, **Catalog**, **Catalog Label**, and **LO Instance**.
* **Module Transcript** (moduleTranscript data set) — the module-level progress fact table. It connects to **User** and to **Module Session**, which in turn links to **Learning Object**.

Most reports that combine learner, course, and completion data are built through one of these two hubs.

**Join paths by use case**

**To combine these data sets**

**The join path**

**User** + **Enrollment**

Enrollment → User (via learner ID)

**Enrollment** + **Learning Object**

Enrollment → Learning Object (via LO ID)

**Learning Object** + **Catalog**

Learning Object → LO Catalog → Catalog

**Learning Object** + **Catalog Label**

Learning Object → LO Catalog Labels

**Learning Object** + **LO Instance**

LO Instance → Learning Object

**Module Session** + **Learning Object**

Module Session → Learning Object (via session course)

**Module Session** + **User** (instructor)

Module Session → User (via instructor alias FK)

**User** + **User Group**

User Group Membership → User + User Group

**Learning Object** + **User** (author)

LO Author → User (via author alias FK)

**User** + **Active Fields**

User Active Fields → User (via user ID)

**Aliased relationships**

Some fields in the data model join to the **User** entity via a named role rather than a direct learner ID. These are aliased foreign keys. They point to the same user table but represent a different role:

* **Instructor**: Module Session joins to User as the session's instructor
* **Author**: LO Author joins to User as the learning object's author
* **Manager**: User joins to itself to represent the learner's manager
* **Completed by**: Enrollment and Module Transcript each carry a separate "completed by" user reference

This is why a single report can show both a learner's name and their instructor's name. They both come from the User entity via different join paths.

**User group data set types**

The **User Group** category contains several distinct data set views, each covering a different type of group:

**Data set**

**Group type**

**User Group** (userGroup)

All user groups. Use this as the primary user group data set

**Active Field User Group** (active_field_user_group)

Groups based on active field values (e.g. region, department)

**Team User Group** (team_user_group)

Manager-hierarchy-based groups

**Custom User Group** (custom_user_group)

Manually configured custom groups

**Inbuilt User Group** (inbuilt_user_group)

System-defined groups

The view-based user group data sets (**Active Field**, **Team**, **Custom**, **Inbuilt**) don't have direct foreign key relationships in the schema, they're SQL views. This means they have looser join constraints than the core **User Group** data set. Use the core **User Group** data set when joining user group data with enrollment or transcript data for the most reliable results.

**Derived fields**

Derived fields are pre-calculated columns computed by Report Builder. They're listed separately from standard columns in the column picker.

**Derived field**

**What it calculates**

**Required data sets**

**Compliance %**

Percentage of required learners who completed compliance-tagged courses

User Group, Learning Object, Transcript

**Completion %**

Completions divided by enrollments × 100

Transcript or Learning Object

**Enrolled User Count**

Total enrolled learners for a learning object

Learning Object

**Completion Count**

Total completions for a learning object

Learning Object

**Start Count**

Learners who have started but not completed

Learning Object

**Member Count**

Number of users in a user group

User Group
