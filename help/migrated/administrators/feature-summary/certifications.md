---
description: Learn how to create certifications, enroll learners, and edit published certifications. 
jcr-language: en_us
title: Certifications
contentowner: manochan
---


# Certifications

Learn how to create certifications, enroll learners, and edit published certifications.

Certify your learners on a one time basis or on a recurring time frame using this feature. Only administrators can define the certifications for learners.

As an Admin, you can create a certification program either hosted internally or conducted by a 3rd party. In case of Internal certification, define the courses that a learner has to complete to get certified. Publish the program and then assign it to learners.

## Create a certification {#createacertification}

1. Click **[!UICONTROL Certification]** on the left pane.  
   A page appears with a list of all the draft, and published state of certifications.

1. View certifications in various modes:

   1. Click **[!UICONTROL draft]** tab to see all the certifications that are in draft state. You need to complete creating them.
   1. Click **[!UICONTROL Published]** to see all the certifications published  by you.
   1. Click **[!UICONTROL All]** to view the certifications in all states.
   1. Sort and view the list of certifications in ascending order, or descending order or based on the date you updated them.

1. Click **[!UICONTROL Add]**.

   A new certification page appears.

![](assets/add-new-certification.png)

*View the page to add a certification*

1. Add certificate name, and description.

<table>
 <tbody>
  <tr>
   <th>Field</th>
   <th>Description</th>
  </tr>
  <tr>
   <td>Days to complete</td>
   <td>The deadline for the certification. Enter a numeric value.</td>
  </tr>
  <tr>
   <td>Type</td>
   <td>
    <p>The type of certification:</p>
    <ul>
     <li><b>Recurring</b>- Choose this option if the certification needs to occur after every year, two years, or three years.</li>
     <li><b>Perpetual</b>- Choose this option if the certification needs to be a one time requirement.</li>
    </ul></td>
  </tr>
  <tr>
   <td>Reassignment</td>
   <td>Choose if you want the certificate to be reassigned based on completion date or on the basis on enrolment date.<br></td>
  </tr>
  <tr>
   <td>Validity (in months) <br></td>
   <td>Specify how long can the certification remain valid.</td>
  </tr>
  <tr>
   <td>Sequencing of Courses<br></td>
   <td>Decide if learners should take the courses in an ordered or unordered manner.<br></td>
  </tr>
  <tr>
   <td>Unenrollment<br></td>
   <td>Enable or disable the option to let learners unenroll themselves.</td>
  </tr>
  <tr>
   <td>Certification Issuer<br></td>
   <td>
    <p>Choose <b>Internal</b> if it belongs to your organization, or choose <b>External</b> for outside organization certifications.</p>
    <p>When you choose <b>External Certification</b>, you see two more options-</p>
    <ul>
     <li>Same as Approved Date<br></li>
     <li>Submitted by Learner<br></li>
    </ul>
    <p>Learners can specify the correct completion date for external certifications. In previous versions, the completion date was set by default by Prime, based on the date of Manager's approval date. Completion date provided by the learner should be greater than the certificate creation date<span>.</span></p></td>
  </tr>
  <tr>
   <td>Duration</td>
   <td>If you've chosen External Certification, then specify the duration in minutes.</td>
  </tr>
  <tr>
   <td>Tags</td>
   <td>Enter the tags that you want to associate with the certificate. Tags are helpful when you want to search for the certificate.</td>
  </tr>
  <tr>
   <td>Select Catalogs<br></td>
   <td>Choose the catalog where the certificate is a part of.</td>
  </tr>
 </tbody>
</table>

Choose the courses to be added to the certification from **[!UICONTROL Courses]** > **[!UICONTROL Catalog]** tab.

Hover the mouse on each course tile, click + to add them to the certification. Click **[!UICONTROL Preview]** to view the course as learner before adding it.

1. Click **[!UICONTROL Curriculum]** tab to view/verify the list of courses that you added.
1. Click **[!UICONTROL Publish]**.

## Course instance mapping for certifications {#courseinstancemappingforcertifications}

To map the course and instance for certifications:

1. Click Certifications from the left pane.
1. From the list of certifications, select View certification of the certification where you want to map the course and instance.
1. From the left pane, click Courses. The courses for the certification are displayed. Click Edit.
1. Hover over the course where you want to set the instance mapping, select Course Instance Mapping.
1. From the pop-up that appears, select the instance of the course that is to be delivered for the certification that you have chosen.
1. Click Save.

An admin can add class room and virtual class room type courses to a Learning Program. Whatever session the author has given during the creation of the course becomes the default instance. When admin adds courses to a learning program, by default it is mapped to the default instance of all the courses but admin can change the instance mapping. The number of courses added into a learning program is also visible in instances page as shown below.

## Enable full catalog control {#catalog}

Like granting full [catalog control for learning(s) or modules](shared-catalog-full-control.md), you can also enable full catalog control for certifications.

## Enroll or unenroll learners to the certification {#enrollorunenrolllearnerstothecertification}

For more information on enrolling learners and the steps to follow, see [Enrolling Learners](courses.md#main-pars_header_1058138132).

## Unenrollment for learners {#unenrollmentforlearners}

While creating certifications, Administrator has an option to select whether learners can unenroll themselves from the certification. If Administrator selects the option, then learner can unenroll themselves. 

![](assets/unenrollment.png)

*Choose to unenroll learners*

## Mark completion {#markcompletion}

Administrators can mark a Certification complete using the option available to them. To mark the completion of a certification, use the following steps.

1. Open **[!UICONTROL Certification]** > **[!UICONTROL Learners]**.

   The Learners page opens with the list of enrolled learners.

1. Select one/multiple/all learners to mark Certification completion using the checkbox available for each learner.
1. Click  **[!UICONTROL Action]** > **[!UICONTROL Mark completion.]**

   Note that if a certification has multiple courses, completion will be marked for all the courses.

## Mandatory courses for external certification {#mandatory}

In earlier releases of Learning Manager, course completion from learner in External certification was not mandatory to complete a Certificate.

You can now make courses mandatory by enabling the option **[!UICONTROL Set required courses as Mandatory for Certificate Completion]** in the Curriculum tab while editing the cerification.

## Editing a published Certification {#editingapublishedcertification}

A certification can be edited by an Administrator at a published state. At this state, the Administrator can edit all the sections of a certification and re-publish. 

To edit a published certification, click the certification card and click **[!UICONTROL Edit]** at the upper-right corner of the page. 

While editing the sections of a certification, if you have to move out of the page, you need to re-publish the certification. You get a dialog confirmation asking you to re-publish the certification.

## Subscription {#subscription}

An admin can fetch quiz score and learner status reports. They can set the report frequency, email subject, and recipients email id. Depending on the set frequency, the recipient will get an email with the report attached.

![](assets/report-subscription.jpeg)

*Set report frequency and other properties*
