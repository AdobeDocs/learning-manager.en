---
description: Learn how Content Composer handles course updates in Adobe Learning Manager- how republishing creates a new module version, and how ALM authors update existing courses to use the latest version.
jcr-language: en_us
title: Module versioning in Adobe Learning Manager
---

# Module versioning in Adobe Learning Manager

Source material changes over time - a policy is revised, a SOP gets a new version, a pitch deck is updated. Content Composer and ALM handle a refresh as a version change, not an in-place edit, so previously published courses keep working while you update the underlying module.

When you republish, Adobe Learning Manager uploads the existing module as a new version in the Content Library, incrementing the module's version number by one.

1. In Content Composer, update the source files and regenerate the affected lessons (see Update a course when source material changes), then republish.

2. Publishing the update doesn't overwrite the existing module - it adds a new version alongside it in the ALM Content Library.

3. An ALM Author needs to explicitly update each ALM course that uses the module to point to the new version; existing courses keep referencing the version they were built with until an ALM Author makes that change.

4. Learners who already completed the course under the previous version keep their existing completion record. The new version applies to learners enrolled after the ALM course is updated.

Review the regenerated lessons in Content Composer before republishing. Regeneration can adjust previously edited text, images, or quiz questions in the affected lessons.
