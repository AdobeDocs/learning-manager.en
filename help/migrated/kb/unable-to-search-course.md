---
jcr-language: en_us
title: Unable to search a course in Learning Manager
description: A learner is unable to search a course in Learning Manager.
contentowner: nluke
---


# Unable to search a course in Learning Manager

## Issue

A learner is unable to search a course in Learning Manager.

## Scenario 1: Enrollment is through a higher Learning Object

### Summary

There are scenarios, where, a learner searches a course and the course is not listed. But if the learner has enrolled for a Learning Program/Certification, then the learner is able to view the course inside the Learning Object.

### Why does this happen?

In Learning Manager, when a learner is enrolled through a Learning Program/Certification, the enrollment for that course is through the Learning Program/Certification.

Therefore, the learner is not able to search for the stand-alone Courses under **My Learning**.

However, the learner cannot view the courses inside the Learning Program/Certification.

## Scenario 2: Learner does not have access to the Catalog that contains the Course.

### Summary

A learner is unable to search courses in the Catalog or the Learning Dashboard.

### Why does this happen?

This issue occurs if:

* The learner is not a part of the Catalog that contains the course **OR**
* The course is not a part of the Catalog that the Learner has access to.

### Resolution

1. Log in as administrator.   

1. Click **Catalog** and browse to the catalog that contains the course. 
1. Click **Share Internally** or **Content** (depending upon the scenario mentioned above).

   ![](assets/cp-share-internally.png)

   *Share the catalog internally*

1. Review the scenarios below:

   * Learner is not part of the catalog

     To share the catalog, click **Add**, and add the user group that the user is a part of. Click **Save**.

     ![](assets/cp-add-user-group.png)

     *Add the user group*

   * Course is not a part of the Catalog

     In the Content section, click **Add Content,** and select the course that you need to add to the catalog.

     ![](assets/cp-add-content.png)

     *Add content to the course*
