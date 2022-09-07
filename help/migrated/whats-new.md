---
description: Learn about the new features and enhancements in Adobe Learning Manager
jcr-language: en_us
title: New features summary
contentowner: jayakarr
---


# New features summary {#new-features-summary}

Learn about the new features and enhancements in Adobe Learning Manager

## New features and enhancements

### Rebranding of Adobe Captivate Prime to Adobe Learning Manager

As has been previously communicated, Adobe Captivate Prime will be rebranded to Adobe Learning Manager with the various UI elements in the product reflecting the change.

### Out of the Box Integration with AEM Sites and Adobe Commerce

Adobe Learning Manager (ALM) integrates with Adobe Experience Manager (AEM) sites. This enables you to create your own website and responsive mobile interfaces for Adobe Learning Manager with minimum coding effort. With this integration, you can create customized learning experiences for your users.

For more information, see&nbsp; [**Adobe Learning Manager reference site (ALM reference site) package for AEM Sites**](adobe-learning-manager-integration-aem.md).

### Adobe Commerce Connector

Adobe Commerce is an extensible and scalable commerce enablement solution that enables you to build multi-channel commerce experiences for B2B and B2C customers on a single platform. Use the Adobe Commerce connector to connect your Adobe Learning Manager account with Adobe Commerce and realize ecommerce capabilities on the learning platform.

For more information, see [**Adobe Commerce connector**](integration-admin/feature-summary/connectors.md#adobe-commerce).

### Training Data Access connector

The Training Data Access connector enables your AEM Sites-based custom-made user interface to retrieve and render training information to learners and helps easy and faster search.

For more information, see [**Training Data connector**](integration-admin/feature-summary/connectors.md#connector_trgmetadata).

## Other enhancements

### Optional skill points in a course

Authors will now be provided with an option to set maximum credits for a particular skills level in a course. Authors can either use the new checkbox to select maximum credits for a specific skill level, or manually enter the credits.

### Notifications for reply on a social post

In Social Learning, a Learner now gets an email notification for every reply on their community post.

### Search for external users

As an Administrators, search for external profiles in the External Users page. In the search bar, enter the profile name of the user. At a time, five matching profiles appear.

### Export feedback

The generateFeedbackReport API produces a feedback report that contains six new fields. They are&nbsp;

* L1 feedback question #1
* L1 feedback response #1
* L1 feedback question #2
* L1 feedback response #2
* L3 feedback question
* L3 feedback response

### Instructor comments in exported reports

An instructor's comments can now be included as a new column in the exported Excel.

### Extension of character limits

In this release, we have extended the limit to the number of characters in the Title field of a&nbsp;Course, Certificate, and Learning Path to 255.

### Alert message when a message is deleted

An alert message appears when authors try to&nbsp;republish courses/Learning Paths/certifications when the content is modified (added/deleted).

### New column with the comments in excel

As an instructor, you can mark the attendance, provide scores, add and edit comments for a Learner.&nbsp; You can also capture this information as a PDF report once the attendee list is confirmed for any upcoming and past sessions.

The easy-to-print pdf displays information as a table with the Learner' name, Email, attendance status, marks scored, and comments.

There are two types of reports that can be exported:

* Export Learner List (PDF): This report displays the list of all the Learner's information to capture attendance, marks, and comments manually in a physical classroom session. To export this list, click **Actions** > **Export Learner List (PDF)**.
* Export Attendance Report (PDF): This is a newly added report that displays the list of all the Learner's information with the attendance, marks and comments filled out. To export this list, click **Actions** > **Export Attendance Report (PDF)**.

The Comments column is a new addition to add or edit any observations on Learner's attendance and scoring. It appears as the last column in the end of the exported report.

An Instructor can add comments for a Learner, only after marking attendance for the completed module. By default, the Comments field is disabled.

To add a comment for a Learner, click **Actions** > **Edit Scores & Comments**. This enables the Comments field.

### Share Monthly Active User (MAU) licenses

If you are using the MAU licensing model with ALM, you can share licenses in your peer accounts. This enables more flexibility and better utilization of licenses across partner organizations.

To share the seats,

1. On the Peer Accounts page, click **Add**.
1. Enable the checkbox **Share Seats**.
1. Enter the number of seats that you want to share.&nbsp;This field is optional. If you do not enter the number of seats, then all seats are shared.

After you share the seats, the details are listed on the report.

### Support for Multi-manager

In ALM, a learner can now manage multiple user groups. This is made possible by using Active Fields, where an Active Field can now store multiple values.

There is a new checkbox, **Learner-Configurable**, which, when unchecked, the active field will be hidden from the learner on the profile page.

For example, in a retail setup, a store supervisor may manage more than one retail store. In previous versions of ALM, assigning a supervisor to multiple stores was not possible. In this release, a user can be assigned multiple active fields.

The [Manager dashboard](managers/feature-summary/manager-dashboard.md#multi-manager-dashboard) also reflects the changes.

### Recommendation based on areas of interest

In this release of ALM, an Administrator can switch between single and multiple Areas of Interest recommendation strips for a learner.

In the previous release, there used to be only one strip that displayed all your recommendations.

There will be at most five such strips with each strip representing a particular area of interest.

The recommendations are based on a combination of rule-based logic and ML-based recommendation logic.

On the **Administrator app > Branding** page, the Administrator can toggle between the interest widgets that will ultimately appear on the learner's page.

### Marketo Engage enhancements

This release of ALM adds two new events to be exported to Marketo.

* **Update User Metadata:** Metadata of existing users, for example, name, profile, etc., will be updated.
* **Update User Activity:** Updates last login and social activity timestamp.

### Preview a module

An Administrator can mark any module inside a course for preview. Learners can preview the course before deciding to purchase the course.

A new setting has been introduced in this release. In the **Admin app > Settings > General**, enable **Module Preview**.

An Author, while creating a course, can mark a module as preview able.&nbsp;

The Learner Preview checkbox enables the modules to be marked for preview.

### Connectors

Marketo and Adobe Commerce connectors are not supported in FedRamp instances (CoSo).

### Feedback report

When an Administrator downloads the Feedback Report from Reports - Custom Reports, the report does not show the feedback for subjective questions. To get the subjective feedback responses, the admin must go to the course and export responses from Export Feedback Scores.

### Nomenclature changes

The CSV has three new columns:

* Skill level
* Social
* Social Learning

However, the title inside the social page does not change with nomenclature.

### Learner-related changes

On a training card, a Learner can see the price of the course, if the price has been set by the Author or the Administrator. The learner can then filter training according to the price range.

If the learner wants to buy a course, they select **Buy Now**. They are redirected to Adobe Commerce and when they complete the purchase, they can then take the course.

## API changes and enhancements

### Enhancement of Public APIs

This release significantly enhances all the public learner APIs to support entity caching.&nbsp;

Entity caching is a technique to store recently read or written entity instance in memory, which minimizes database access and improves the application performance.

ALM learner APIs now use enhanced caching techniques, and therefore, are more performant. This also means that the response times of the GET APIs are less than what used to be.&nbsp;

Customers use the learners APIs to create custom headless interfaces. These APIs typically fetch a lot of learner-related data, such as, enrollment, available courses, and so on.

Entity caching helps when there are concurrent and bulk calls to the learner APIs. This technique also manages load balancing and makes the APIs more scalable.

### E-Commerce

**API models Changes:** 

* Get user include account

  * Additional boolean flag "enableEcommerce", takes value from DB column  
  * lastSyncedDateCreatedForMagento  
  * headlessLmsBaseUrl  

* learningObject- price  
* enrollment - purchasedPrice  

**API Changes:** 

* Get /learningObjects (Learner):

  * price range filter
  * price filter for free and paid  

* search - same as /learningObjects  
* Additional apis for ecommerce:

  * GET /maxPrice  
  * POST /ecommerce/purhcaseInitiated  
  * /ecommerce/purhcaseCompleted

### Multi-valued active fields

For multi-valued active fields, the **fields** property can store values of type integer or string. For example,

```
"fields":{
  "office": [ "store1", "store2", "store3" ] 
}
```

If fields is a single valued active field, then:

```
"fields":{
  "location": "london"** 
}
```

### Feedback reports

The L1 feedback report that contains six new fields. They are:

* L1 feedback question #1
* L1 feedback response #1
* L1 feedback question #2
* L1 feedback response #2
* L3 feedback question
* L3 feedback response

### API nomenclature changes

The terminologies of Skill levels and Social Learning are added and the changes are displayed on the Learning overview page, Social widget, and the Social learning page. The changes also reflect in the mobile immersive pages.

### Buy courses in mobile immersive

>[!NOTE]
>
>Only applicable to mobile immersive app, not the native mobile app.


After an author adds a price to a course, in the mobile immersive app, a learner can see the price on the cards on the Homepage, Catalog Page, and the search result pages. The learner can purchase a course and after the learner purchases the course, a Start button appears on the course overview page.

### Group users

This update provides an ability to group users based on multi value active fields. This will not impact existing users and can continue to use single value active field.

### Support for multi-value active fields&nbsp;

This update introduces the following changes:&nbsp;

* Support of multi value active fields for User API.&nbsp;
* The User Group API supports GET /user-groups corresponding to the multi-valued active fields.&nbsp;
* Jobs API User report should have multi value active fields.
* Add/edit the managed stores of a user.&nbsp;
* List all managed stores of a user.&nbsp;
* Remove office/store from a specified manage list.

### ECommerce API changes&nbsp;

This update includes the changes below for the responses of the following APIs:

**Account**

* enableEcommerce
* lastSyncedDateCreatedForMagento  
* headlessLmsBaseUrl

**learningObject**

* price

**enrollment**

* PurchasedPrice

### Filter prices

The GET /learningObjects API for learners adds two new filter parameters:

* priceRange to return courses that satisfy a specified price range.&nbsp;
* priceFilter for free and paid courses.

### Recommendation API changes

The Recommendation API now includes a new filter. The filter.rectype property has a new filter multi_skill_interest.

You must invoke the recommendation API with filter.recType=multi_skill_interest per strip to get all strips data. Within each strip, you can paginate using the next link. The maximum strip size is 5.

For example,&nbsp;&nbsp;

GET /recommendations?filter.loTypes=course&filter.recType=multi_skill_interest &strip=1&page[limit]=10

### Preview content in player

The learningObjects/{id}&nbsp; API contains the following changes:

* account - Additional boolean flag "enableModulePreview", takes value from 'account_setting_extended.enable_preview'  
* learningObject - Additional boolean flag "hasPreview", takes value from course.has_preview, certification.has_preview, learning_plan.has_preview
* learningObjectResourse - Additional boolean flag "previewEnabled", takes value from 'course_module.is_preview'&nbsp;
* resource - contentZipUrl, location and contentStructureInfoUrl will come in api response if 'account_setting_extended.enable_preview' is true and module is preview able regardless of enrollment.

### Information about mandatory modules

With the help loResourceCompletionCount&nbsp; API, you can build a workflow with minimum completion criteria by defining the number of modules to be completed.

### Mark User Notification in bulk

The primeapi API now enables you to mark User Notifications as read in bulk.&nbsp;

`primeapi/v2/users/<user>/userNotificationsMarkRead`

### Changes in learningObjects and Search APIs

A new filter skillLevel is added to the APIs. The values are 1,2, or 3.

### Social boards filtered by skills

You can retrieve a list of social boards that are attached to specified skills.

Example request URL:

[https://examplre.com/primeapi/v2/boards?page[offset]=0&page[limit]=10&sort=name&filter.board.skills=SKILLA](https://examplre.com/primeapi/v2/boards?page%5boffset%5d=0&page%5blimit%5d=10&sort=name&filter.board.skills=SKILLA)

### Zoom/BlueJeans login

Licensed users and existing accounts will get start url so that they can join the meeting directly. There is no impact on guest users. They continue to fill registration form and then log in.

### ID format change for loResourceGrades

In this update, we have changed the format of the ID for the loResourceGrades API by removing the uuids. The ID remains as unique ID.

### Other enhancements

* You can search for a course with the help of these additional filters:

   * effectiveModifiedDate
   * dateCreated
   * DateUpdated

* The"effectiveModifiedDate" property displays the loModifedDate.modifiedDate value.
* An instructor gets notified in both the Mobile and Immersive apps when an activity module is submitted. The instructor then can check and act accordingly.
* In the mobile immersive app, if you click Skills in the Overview pages, you are taken to the catalog page with that skill filter checked.
* The learningObject relationship has been removed from the LoSkill API.
* Removed the following from the migrations csvs:

   * course.csv - courseCreationDate
   * certification.csv - certificationCreationDate
   * learning_program.csv - dateAdded

* An Administrator can now search for all external users or partner accounts.

&nbsp;

## Release Notes {#releasenotes}

For information regarding current and previous releases of Learning Manager web app and device app, see the&nbsp; [***Release notes***](release-note/release-notes.md).

## Bug fixes {#bugfixes}

To see the bugs that are fixed in this update, refer to the&nbsp; [***Bugs fixed***](release-note/release-notes.md#bug-fixes-alm)&nbsp;list.

## Known issues {#knownissues}

* In an AEM website, a flexible Learning Program always appears as a fixed Learning Program. This is as designed since a flexible Learning Program is not supported in AEM.
* Unable to retake a course with multiple attempts&nbsp;if you have failed the course.
* If the value of a multi-valued active field contains a delimiter, for example, comma, the value gets separated as two distinct values, and the user will be present in both the user groups.
* In the Learner app, redirection from the calendar widget does not always occur as expected. Instead of the user getting navigated to an instance, they are unable to do so.

## System Requirements {#systemrequirements}

[Learning Manager system requirements](system-requirements.md)

## Previous releases of Learning Manager {#previousreleasesofcaptivateprime}

* [Learning Manager | January 2022 release](whats-new-jan-2022.md)
* [Learning Manager | October 2021 release](whats-new-october-2021.md)
* [Learning Manager | August 2021 release](whats-new-august-2021.md)
* [Learning Manager | February 2021 release](whats-new-february-2021.md)
* [Learning Manager | December 2020 release](whats-new-december-2020.md)

## Have a question or an idea? {#haveaquestionoranidea}

<table> 
 <tbody>
  <tr> 
   <td><img src="assets/ask-the-community.svg"></td> 
   <td><p>If you have a question to ask or an idea to share, come and participate in the&nbsp;<a href="https://community.adobe.com/t5/captivate-prime/bd-p/captivate-prime?page=1&amp;sort=latest_replies&amp;filter=all" disablelinktracking="false"><strong><em>Adobe Learning Manager Community</em></strong></a>. We would love to hear from you and address your queries.<br></p></td> 
  </tr> 
 </tbody>
</table>

## More like this

* [Adobe Learning Manager product guide](https://www.adobe.com/products/captivateprime.html)
* [Adobe Learning Manager playlist](https://www.youtube.com/playlist?list=PLq21ukQtk0URntzGmTxsx7Qt8z9b9Elth)
* [Organize your training in Adobe Learning Manager | Ashwini Jaisim](https://elearning.adobe.com/2020/07/organize-your-trainings-in-adobe-captivate-prime/)
* [Add your Adobe Learning Manager Account URL to your Adobe Connect Central Account Summary Page](https://elearning.adobe.com/2019/10/add-adobe-captivate-prime-account-url-adobe-connect-central-account-summary-page/)
