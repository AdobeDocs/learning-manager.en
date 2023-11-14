---
description: This document contains basic troubleshooting tips to solve some of the typical problems that you may encounter while migrating data and content from existing LMS to Captivate Prime.
jcr-language: en_us
title: Troubleshooting Migration issues
contentowner: jayakarr
---


# Troubleshooting Migration issues

This document contains basic troubleshooting tips to solve some of the typical problems that you may encounter while migrating data and content from existing LMS to Captivate Prime.

## Generic migration issues {#genericmigrationissues}

### Unable to log in to FTP folder or content folder {#unabletologintoftpfolderorcontentfolder}

Ensure that your accounts have been created in the FTP and Box services. When you create a migration project, you request to set up these two services. As soon as you create the services, you receive emails from Exavault and Box to reset or set up the passwords. If you do not remember the passwords, you can reset them by visiting the Exavault and Box websites. 

### Jobs are not reflected even after clicking Refresh button {#jobsarenotreflectedevenafterclickingrefreshbutton}

* Ensure that the CSV files are uploaded to the correct folder in Exavault FTP. The path structure should be as follows:

`code Account>Project>Sprint location`

* Ensure that the file names of CSV files are as per the CSV specification names:

   * course.csv
   * course_instance.csv
   * course_module.csv
   * enrollment.csv
   * module.csv
   * module_version.csv
   * user_course_grade.csv 

### Failures are shown for jobs with error records {#failuresareshownforjobswitherrorrecords}

1. Download the error logs by clicking **Download error records** link
1. Correct the original CSVs based on the reported errors, and
1. Re-run the Sprint with the modified CSVs.

Best practice is to run modified CSVs in a new Sprint when the number of changes are less as compared to the total number of records.

### Unable to log in to Captivate Prime application even after stopping the Sprint migration {#unabletologintocaptivateprimeapplicationevenafterstoppingthesprintmigration}

It may take 10-15 mins to unlock an account once a Sprint run is stopped or completed. Try to access the application after 15 minutes.

### Some of the migration jobs display 'In Progress' status even after 'Stop' is triggered. {#someofthemigrationjobsdisplayinprogressstatusevenafterstopistriggered}

It may take 10-15 minutes to stop executing all the jobs once it is in 'In Progress' state. Please re-check the status after 10 mins. 

### Unable to create a Sprint as the button is disabled {#unabletocreateasprintasthebuttonisdisabled}

Ensure that the current Sprint is marked as complete, before creating a Sprint. Click **Mark Sprint Complete** at the top of the page to complete a Sprint migration. 

### Unable to mark a Migration Project as complete as the button is disabled {#unabletomarkamigrationprojectascompleteasthebuttonisdisabled}

Ensure that the current Sprint is marked as complete, before marking the migration project completion. Click **Mark Sprint Complete** at the top of the page to complete a Sprint migration. 

## CSV issues {#csvissues}

### module_version.csv file migration is failing and content is not migrated yet {#moduleversioncsvfilemigrationisfailingandcontentisnotmigratedyet}

Ensure that the content is available in Content folder (Box account under the specified migration project, sprint path). Also, ensure that you have selected the option **Yes **for **Will you be migrating content for this Sprint? **question in the Sprint creating page. 

If you forget to select **Yes**, and proceed further in this sprint, then you have to wait till you complete this sprint. Create another sprint and ensure to click **Yes. **

### enrollment.csv or user_course_grade.csv records fail with an error message 'Not a valid PrimeId' {#enrollmentcsvorusercoursegradecsvrecordsfailwithanerrormessagenotavalidprimeid}

Ensure that the email id provided as part of userId, assignedByUserID fields belong to valid Captivate Prime users. If not, please add the user, create a new Sprint with **Sync Users** option selected. In case  the user is not part of the organization, add the user as a deleted user in Prime by using Add users CSV specification. A sample CSV specification to add deleted users is provided below for your reference. 
[Users.csv](assets/users.zip)Refer to **CSV specifications and sample CSVs **section in [Migration manual](../integration-admin/feature-summary/migration-manual.md) to download complete set of CSV specifications and sample CSV files. 

### Courses appear blank or incorrect modules play for a migrated course {#coursesappearblankorincorrectmodulesplayforamigratedcourse}

Ensure that the **moduleOrderInCourse** key value for a Course starts with **0** and is in continuous order. The order in terms of  courseModuleType should be PRETEST, TESTOUT, CONTENT.

Also, make sure that two versions of Activity, Classroom, and VC are not linked with the existing Course.

### Receiving a message as 'Module is already linked with an existing course' {#receivingamessageasmoduleisalreadylinkedwithanexistingcourse}

Captivate Prime does not allow linking Activity/VC/Classroom module to more than one course. Ensure that the module is not linked with any other courses.

### All the courses show the latest version of Activity/VC/Classroom modules even though the courses are linked with different module versions {#allthecoursesshowthelatestversionofactivityvcclassroommoduleseventhoughthecoursesarelinkedwithdifferentmoduleversions}

Versioning of Activity, Classroom, and Virtual classroom modules is not supported in Captivate Prime. If you provide versions through moduleVersion.csv file, it updates the existing file instead of creating a new verison. 

### Desired duration does not appear for a migrated Activity/VC/Classroom module {#desireddurationdoesnotappearforamigratedactivityvcclassroommodule}

Desired duration is not a valid entry for Activity/VC/Classroom module.

### Hyperlink URL doesn’t open up in Captivate Prime {#hyperlinkurldoesntopenupincaptivateprime}

Ensure that that the provided links are pre-fixed with ‘http://' or 'https://'

### moduleVersion migration fails with ‘File not found’ errors {#moduleversionmigrationfailswithfilenotfounderrors}

Ensure that the referred file is present in the content folder and it is migrated successfully.

### moduleVersion migration fails with an error message as ‘An Internal Error has occurred - for Module : x and moduleVersion : y’ {#moduleversionmigrationfailswithanerrormessageasaninternalerrorhasoccurredformodulexandmoduleversiony}

Re-run the Sprint to resolve the issue.
