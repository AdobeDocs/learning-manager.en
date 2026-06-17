---
jcr-language: en_us
title: Report Builder - Frequently asked questions
description: Get answers to frequently asked questions about Adobe Learning Manager Report Builder.
contentowner: mmanuel
---

# Report Builder - Frequently asked questions


**What is the difference between a template and a report?**

Templates are pre-built report configurations provided by Adobe Learning Manager. They're designed for common use cases, ready to download immediately, and read-only. You can't edit them. Reports are your own saved configurations. You create them by building from scratch or by duplicating a template and editing the copy. Reports appear in your **Reports** tab; templates appear in the **Templates** tab.

**Can I edit a template directly?**

No. Templates are read-only. To customize a template, select **Duplicate** to create an editable copy. Your changes are saved as a new report in the **Reports** tab and don't affect the original template.

Duplicate rows appear when a field in the data has a one-to-many relationship with the main record. Common causes include sessions with multiple instructors (one row per instructor per session) and learning objects with multiple authors. To resolve this, add the field that has multiple values, such as **Instructor Names** or **Author Name**, as a column.

**Why does row order change between two downloads of the same report?**

Report generation uses a distributed query system. Without explicit sorting, row order depends on which query node returns results first, which can differ between runs. Apply at least one sort to your report to ensure consistent output across downloads.

**Why are dates shown in UTC?**

Report Builder returns date values in UTC in this release. Your account's configured time zone will be applied to date fields in a future release. When analyzing date-based data, factor in the UTC offset relevant to your account's primary time zone.

**How long does it take for new enrollment or completion data to appear?**

Report Builder pulls from Adobe Learning Manager's database, which has a maximum latency of approximately 15 minutes from when an event occurs in the system. If you've just recorded an enrollment or completion and it doesn't appear in your report, wait at least 15 minutes and download again.

**Is there a limit on rows or columns in a report?**

Reports are limited to approximately 1 million rows. There's no limit on the number of columns in this release. If your report requires more than 1 million rows, apply filters to narrow the scope.

**Can I pull Report Builder data through an API or automation?**

Automated API access to Report Builder reports is planned for a future release. In the current release, reports are downloaded manually through the Report Builder UI or received on a scheduled basis via the subscription feature.
