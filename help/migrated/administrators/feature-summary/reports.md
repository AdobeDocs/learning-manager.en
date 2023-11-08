---
description: Learn about the Reports associated with Administrator role in Captivate Prime application.
jcr-language: en_us
title: Reports
contentowner: manochan
---


# Reports {#reports}

Captivate Prime&nbsp;Learning Programs&nbsp;are renamed to&nbsp;Learning Paths.&nbsp;This change happens immediately&nbsp;after the October 2021 release and&nbsp;the terminology of&nbsp;Learning Path&nbsp;is&nbsp;reflected for all roles.

Learn about the Reports associated with Administrator role in Captivate Prime application.

Adobe Captivate Prime enables you to create varied reports to track, monitor, and control learner activities. Learners activities are tracked and captured automatically into the database. Manager and Administrator reports are generated from the database.

## Overview {#overview}

Reports generation process is similar for both Administrator and Manager. Managers can view reports corresponding to their subordinates whereas Administrator can view all organization-wide reports.

Reports are aggregated in a dashboard. A report has to exist inside a dashboard. A&nbsp;**Default Dashboard**&nbsp;exists by default in the reports page. Any report added by you moves into this default dashboard. To add reports to individual dashboards, use the drop-down arrow and choose&nbsp;**Add Report**. For more information on creating dashboards, refer to Dashboards section on this page.

## Learning Summary dashboards {#dashboards}

See a summary report of all&nbsp;the&nbsp;learning activities in the platform. On this page, you can see the following summary information&nbsp;for the selected root user’s team and external profiles. Time&nbsp;range&nbsp;can also be selected:

* Learning Summary in form of Enrollments, Views, and Completions
* Top skills
* Compliance summary&nbsp;

![](assets/summary-charts.png)

If there are internal root level managers, they will be&nbsp;displayed&nbsp;one after another.&nbsp;

All external profiles will be listed after&nbsp;internal profiles&nbsp;(Internal root level users).

If an external profile has a manager, then&nbsp;the manager hierarchy will be displayed in the&nbsp;**Showing Data For**&nbsp;drop-down list.&nbsp;-&nbsp;User will be listed in manager&nbsp;hierarchy&nbsp;in all the details page (Learning&nbsp;summary,&nbsp;compliance,&nbsp;and skill status)

If not, then all&nbsp;individual user details will be displayed&nbsp;in the list.

To see more granular details of enrollments of various internal teams, click&nbsp;**Learning Summary Details**.

![](assets/learning-sunnarydetails.png)

When you click any enrollment, you can see the learners for each manager,&nbsp;and&nbsp;enrollment to which Learning Objects.&nbsp;You can also see the progression and completion details of each learner.&nbsp;

![](assets/learners-for-a-manager.png)

Click any team and export its report as a csv. An&nbsp;Admin can export the report for any of the User&nbsp;Group&nbsp;or individual user&nbsp;by selecting&nbsp;the&nbsp;User&nbsp;Group&nbsp;or individual user,&nbsp;and then export details from&nbsp;the Action drop-down&nbsp;list.

Also, you can see a bar chart view of skills that are in progress and have been&nbsp;achieved. You can add/remove skills that you want to feature in the graph.

![](assets/skill-status-stackedbarchart.png)

In the final visualization, you can check the compliance status of learners, and take appropriate action.

Also, an Admin can view individual training data in the Compliance Dashboard.

For instance, the Administrator has identified three trainings to track compliance. Captivate Prime provides the compliance snapshot for all three trainings at once.

Now an Admin can click on any training and quickly view the compliance for the selected training.

![](assets/compliance-dashboard.png)

You can also see the compliance status for each internal team.

Click the link&nbsp;**Compliance Status Details**&nbsp;on the bottom of the visualization.&nbsp;

You can see that, for a team, the number of learners in the team are violating or honoring the learning compliance.

![](assets/compliance-statusofateam.png)

## Share training with managers

Captivate Prime offers compliance dashboard to all Administrators and Managers.&nbsp;Managers find it&nbsp;very useful&nbsp;to track compliance of&nbsp;their team members for a particular training.&nbsp;At the same time, Administrators would like all Managers to add compliance trainings to their dashboard and track it.&nbsp;

In&nbsp;Captivate Prime, the&nbsp;**Share with Managers**&nbsp;workflow&nbsp;allows Administrators to share&nbsp;training&nbsp;with Managers,&nbsp;so that they&nbsp;can&nbsp;get added to&nbsp;a manager’s Compliance Dashboard.&nbsp;Thus,&nbsp;Managers do not need to take any&nbsp;action and can start tracking compliance&nbsp;immediately.&nbsp;

An Administrator can share a set of&nbsp;training courses&nbsp;with managers individually or&nbsp;with&nbsp;a group. This sharing can help a manager easily track the compliance of his/her&nbsp;team for the specified&nbsp;training.

The&nbsp;Administrator&nbsp;can "push" a default list of compliance&nbsp;training&nbsp;to be viewed in the manager's compliance dashboard.

### Share&nbsp; training

1. In&nbsp;**Reports > Learning Summary**, scroll down, and click the tab&nbsp;**Share with&nbsp;Managers**.&nbsp;

   ![](assets/share-with-managers.png)

1. To add&nbsp;training&nbsp;or multiple&nbsp;training, click&nbsp;**Share more**.&nbsp;  

1. In the&nbsp;**Share with Managers**&nbsp;dialog,&nbsp;choose the training(s) and the manager(s).

   ![](assets/select-training.png)

1. Click **Share**.

The training is now shared with the specified manager.

### View training

In the list of shared&nbsp;training, click&nbsp;**View**.&nbsp;You can view the training&nbsp;that&nbsp;is&nbsp;assigned to a manager or some managers.

### Withdraw&nbsp;training

1. To withdraw&nbsp;training&nbsp;from a manager, click&nbsp;**Withdraw**.  

1. Click&nbsp;**Proceed**. This withdraws&nbsp;previously&nbsp;shared training from the Manager’s compliance dashboard.

## User Activity dashboards {#useractivitydashboards}

See a summary of all user activity on the platform over time. Configure user groups and apply filters.

The user activity dashboard displays the activity of users in the account. The three&nbsp;reports&nbsp;that are listed are:

* **Registered Users: **This report provides information of the number of users registered in your account week over week. For accounts with Monthly Active Units licensing, the report shows the MAU units instead.

* **User Visits&nbsp;Report: **This report provides information&nbsp;about the number of users accessing the platform on a day to day basis. Monthly report is also available.

* **Learning Time Spent Report: **This report provides information about the Learning Time Spent in the platform on a day to day basis. Monthly report is also available.

## Registered Users {#registeredusers}

Captivate Prime records the number of users registered in the system every week. Administrators can view this report to understand the registered count of users on that day of the week. Registered count once stored for a week does not change. Hence historical registered count is not related to the current set of learners in the system.&nbsp;

This report provides information of the number of users registered in your account week over week.

For accounts with Monthly Active Units licensing, the report shows the MAU units instead.

![](assets/registered-usersreport.png)

***For Monthly Access Unit accounts:***

**Monthly Active Users report**

This report shows the count of learner active in the learning platform each month. User is considered active for the month if he/she performs any of the learning actions mentioned here. It is the same way Monthly Active Units are counted.

The monthly active count once counted and stored for a month, does not change. Hence the historical count displayed is not related to the current set of learners in the system.

## User Visits {#uservisits}

This report shows the total learners accessing the system in a day or month period. Browsing the learning platform without consuming any learning is also considered as 'accessing' the learning platform. This helps the Administrator understand the total set of users accessing the system. On the first of the month, captivate prime creates a record of total users accessing the platform for the previous month. It also captures the usergroup information for these users.

Only those usergroups configured by the Administrator are recorded. This allows the Administrators to apply filter on usergroups for historical monthly data as well. Note that incase usergroups configuration is modified and Captivate Prime has not recorded data for this usergroup in earlier months, then Captivate Prime cannot display the data for this newly configured usergroups for previous months.&nbsp;

This report contains users accessing the platform using all formats like web, mobile app, headless custom solutions, and so on. The device app usage graph specifically mentions only the users accessing the platform using Captivate Prime's device app. This helps Administrators identify the usage of mobile app in their account.&nbsp;

![](assets/user-visit-report.png)

## Learning Time Spent Report {#learningtimespentreport}

Here, you can see a dual-axis line charts that show total learning time spent for all learners across a 12-month period. The second axis represent the median time spent in learning for an individual.

The time spent for different Learning Objects, such as, Learning Programs and Certifications, is calculated for the following:

* Self-paced course with static and interactive content
* Activity courses with&nbsp;url.
* Weekend sessions with the weekend flag enabled.&nbsp;
* VC connect session where attendance is auto marked.
* The time spent for different Learning Objects, such as, Learning Programs and Certifications
* &nbsp;xAPI&nbsp;statements for an&nbsp;xAPI&nbsp;activity course.

You can further export the graph as an Excel spreadsheet.

A filter to choose User group configuration is provided which will help in viewing the data with respect to different user groups.

The selected date and user group filter is applied to all the relevant graphs in the dashboard.&nbsp;

For **User Visits** and **Learning Time Spent** reports, the default data (when no user group is configured) shown will be for the entire account.

## Training Content dashboard {#trainingcontentdashboard}

The Training content dashboard offers insights into trainings available on the platform. You can view popular trainings or track all available trainings.&nbsp;

## Trainings Report {#trainingsreport}

This report provides information of the total trainings available in the platform (in published state) month over month. It gives an indication of the number of trainings offered over time.&nbsp;

![](assets/training-report.png)

## Active Trainings Report {#activetrainingsreport}

This report provides information of the trainings which are active over the selected time range. Active trainings are trainings which are enrolled, viewed in player, or completed in the given time.

For active trainings, data of all root user (with manager role) internal groups will be available for selection when no user group configuration is done. Apart from the root user user groups, you can configure 10 more user groups if needed.

![](assets/active-trainingsreport.png)

The data does not display as expected when **All Users** and** 12 months** filters are selected, but the data displays when you select **All internal user group.**

<table>
 <tbody>
  <tr>
   <td>
    <p>Reference</p></td>
   <td>
    <p>Metric</p></td>
   <td>
    <p>Description</p></td>
  </tr>
  <tr>
   <td>
    <p>1</p></td>
   <td>
    <p>Start Ratio (%)</p></td>
   <td>
    <p>Ratio of the number of learners who have started the course to the number of enrollments.</p></td>
  </tr>
  <tr>
   <td>
    <p>2</p></td>
   <td>
    <p>Completion Ratio (%)</p></td>
   <td>
    <p>Ratio of total users who have completed the course to the total users who have started the course.<br></p></td>
  </tr>
  <tr>
   <td>
    <p>3</p></td>
   <td>
    <p>Learner Feedback</p></td>
   <td>
    <p>Average of all L1 feedback responses received on a scale of 1 to 10 rounded to the nearest integer.<br></p></td>
  </tr>
  <tr>
   <td>
    <p>4</p></td>
   <td>
    <p>Manager Feedback</p></td>
   <td>
    <p>Average of all L3 feedback responses received on a scale of 1 to 5 rounded to the nearest integer<br></p></td>
  </tr>
 </tbody>
</table>

The training report has two additional columns:

1. Average star rating of a course.  
1. Number of learners who’ve rated the course.
1. Embedded Path&nbsp;
1. Embedded Path ID&nbsp;
1. Embedded Course ID

Start ratio, Completion ratio, Learner Feedback, and Manager Feedback are not affected by the filters applied. The filters affect only enrollment, views, and completions.

For both the reports (Training Content, User Activity), you can configure a maximum 10 user groups. It may take upto 24 hours for the processing to complete and make the newly configured filters available.

## Dashboard Reports {#dashboardreports}

A dashboard is a collection of reports. Reports can be grouped into a dashboard&nbsp;as per your choice.

## Sample Reports {#samplereports}

The **[!UICONTROL Sample Reports]** tab to show some indicative reports which are based on sample data points. Explore these reports to get an idea of different types of feature-rich reports that you can generate using your account data.

## Dashboard Reports {#DashboardReports-1}

To view all the boards that you created, click this board tab. From the **[!UICONTROL View Dashboard]** drop-down list, you can&nbsp;select the default board or a dashboard you created.

## Create a dashboard {#createadashboard}

1. To start creating your own boards, click&nbsp;Add Dashboard&nbsp;on the right side of the page.

   ![](assets/add-dashboards.png)

1. Provide the name and description of the dashboard.
1. If you want to share the dashboard with&nbsp;any Manager, choose them in&nbsp;**Share With**&nbsp;field. You can use any normal selection criteria for this operation.
1. Click&nbsp;****Save.****

You can view the recently created board in the **[!UICONTROL Dashboard Reports]** tab.

To add reports to your board, click the drop-down at the upper right corner of your board window and click&nbsp;**Add Report**. The report you create in this way is associated with your dashboard.

The reports that you create by clicking&nbsp;Add&nbsp;on the upper right corner of Reports&nbsp;page,&nbsp;are added to your default dashboard.

## Shared dashboards {#shareddashboards}

Shared boards are a collection of reports that have been shared with you by other users within your organization. Any reports that you add to a shared board are automatically shared with other users who have access to that board.

You can share the board&nbsp;by following two ways:

* By entering users in&nbsp;**Share With**&nbsp;field with whom dashboard is shared.
* Choose Edit Board in the drop-down list and enter user details for sharing the dashboard.

A manager can only view the reports of their team members from a shared dashboard.

## Downloads {#downloads}

The exported sheet of dashboard reports provides detailed information instead of report summary. The downloaded report follows the format of a Learner Transcript.

## Create reports {#report}

1. Click Reports on the left pane. Report summary page appears.

   By default, at least three sample reports appear in the sample board tab. You can only view the sample reports to get an idea as to how you could create and customize them.&nbsp;

1. On the top-right corner of the page, click **Add**.
1. In the **Add Report** dialog box, in the Type drop-down list, you can choose either one of the pre-defined reports or you can select **Custom**. If you select a pre-defined report, you can see that the form is pre-populated. You can further make changes to some of the fields and click **Save**. This adds the report to your default dashboard.

   ![](assets/create-report.png)

   In **Report Type**, you can choose a pre-defined set of reports or choose custom values. You can view the following reports as part of a pre-defined set of reports:

   * Skills assigned and achieved
   * Course enrolled and completed
   * Effectiveness of courses
   * Learning programs enrolled and completed
   * Learning time spent per course
   * Learning time spent per quarter
   * Certification completion

1. Choose the **Y-axis** for your report from the drop-down options. For some of the selected criteria, you can choose one or multiple states from the States options. For example, for a course enrollment statistics primary criterion, the states can be completed, incomplete, and enrolled. Primary range data is represented in the form of bar graphs in the report.

   ![](assets/axes-for-reports.png)

1. Choose the secondary **Y-axis** criteria/range for your report from the drop-down options. For example, for a learning program enrollment option, choose one or multiple states from the States drop-down. Secondary range data is represented in the form of line graphs.
1. Choose the appropriate X**-axis** criteria for your report from the drop-down options. If x-axis is chosen as date, then an option to group your x-axis criterion by day, month, quarter, and the year is available.
1. In the Time Span section, choose the appropriate option from the drop-down. The available options are:

   * Last one month
   * Quarter
   * Year
   * QTD (last 90 days)
   * YTD (last 365 days)
   * Date range. Provide values in the **From** and **To** date fields.

   ![](assets/time-filter-for-report.png)

1. **Filters section**

   Filters appear in Add report dialog at the bottom based on types of reports you have chosen. Some of the prominent filters are mentioned below.

   * **Manager:** You can choose any one of the managers based on hierarchy. For some managers, there can be subordinate managers and multiple employees reporting to each subordinate manager.
   * **Profile:** Choose the designation of your employee. It would help in viewing reports of employees based on their profile/designation. For example, computer scientist, engineer.
   * **User Group:** Choose the user group based on which you want to filter the reports. Captivate Prime fetches the user groups defined for your account from Users feature.
   * **Content:** You can filter your report based on any course by choosing them from the drop-down.

   Expand this section and choose the required filters.

   ![](assets/choose-filters.png)

1. Click&nbsp;**Save**&nbsp;to complete creating a report.&nbsp;

   ![](assets/sample-report.png)

## Edit a report {#editareport}

On the report, click the drop-down arrow, and choose the option **Edit Report**.

![](assets/edit-a-report-1.png)

Make the required changes to the report. To save the changes, click **Save**.

## Move a report to a dashboard {#moveareporttoadashboard}

Choose this option to move the current report to an existing dashboard. To move the report, click the option **Move to Dashboard**.

![](assets/move-a-report.png)

Choose the dashboard where you want the report to move to and click **Move**.

## Create a copy of a report {#createacopyofareport}

To create a copy of the report, choose the option **Create a Copy**.

![](assets/copy-a-report.png)

Choose the dashboard where you want to copy the report to. To start copying, click **Copy**.

## Delete a report {#deleteareport}

To delete a report, choose the option **Delete Report**. After you delete the report, you cannot restore the report. The process is irreversible. Proceed with caution when deleting a report.

![](assets/delete-a-report.png)

## Download a report {#downloadareport}

To download the report, choose the option **Download Report**.

![](assets/download-a-report.png)

## Resize a report {#resizeareport}

You can resize your reports in 1×1 (medium) and 1×2 (large) sizes. This gives you a better real estate to view your reports. Also, you can easily pan and zoom these reports.

## Filters {#filters}

Filters appear in **[!UICONTROL Add]** report dialog at the bottom based on types of reports you have chosen. Some of the prominent filters are mentioned below.&nbsp;

** Manager**&nbsp;You can choose any one of the managers based on hierarchy. For some managers, there can be subordinate managers and multiple employees reporting to each subordinate manager.

**Profile**&nbsp;Choose the designation of your employee.&nbsp;It&nbsp;would help in viewing reports of employees based on their profile/designation. For example, computer scientist, engineer.

**User Group&nbsp;**Choose the user group based on which you want to filter the reports. Captivate Prime fetches the user groups defined for your account from Users feature.&nbsp;

**Course**&nbsp;You can filter your report based on any course by choosing them from the drop-down.

![](assets/sample-report-admin.png)

Above the legend for the graph, you can view a zoom box. Move cursor over it, click, and drag the crossbar over any part of the zoom box graph area, to zoom in.

You can view the secondary y-axis values in the form of a line across the graph bars. For example, in the above sample, you can see the values for Effectiveness in gray line across the graph.

## User group reports {#user-group-reporting}

Track how user groups such as departments, external partners, and roles are performing in comparison with other user groups or against other learning objectives.

### User groups {#usergroups}

To generate reports based on user groups, choose **User Group **in the x-axis from the list of drop-down options as shown in the screenshot below.&nbsp;

![](assets/user-group-reports.png)

To choose a user group, type the name of the group. You can see the suggested groups that are displayed according to the string you enter. Once you see a list of groups, choose the required user group.

You can also choose multiple user groups with the help of type-ahead search.

Once you save and generate this report, if you selected multiple user groups, the report is generated with all the user groups represented in bar graph next to each other in x-axis.&nbsp;

This user group report enables you to compare the performance of one department/division/role against the other to evaluate their learning achievements.&nbsp;

### Custom user groups/user attributes {#customusergroupsuserattributes}

You can also create customized user groups using Add users/user groups feature in Captivate Prime. After creating the user groups you can generate reports for those customized user groups with the help of a list of attributes like location, branch.&nbsp;

In x-axis, choose the user attribute option and select the attribute from the **select **drop-down next to it. To create a customized user group report based on these attributes, you also have to choose the appropriate user group in the filter.&nbsp;

## Types of reports {#typesofreports}

Adobe Captivate Prime supports four major types of reports such as completion, time spent, skills, and effectiveness. You can use the&nbsp;following report types to generate reports of 300+ variations:

* Course delivery statistics for learners
* Effectiveness of courses report
* Learner skill-based report
* Learning program enrollment statistics for learners
* Learning time spent by learners
* Learner count
* Certification completion

## Viewing reports {#viewingreports}

On the Reports page, you can view all the reports. You can minimize each report by clicking minus (-) icon at the upper right corner of each report. Click (+) icon to view your report again.

## Quick view with different dates {#quickviewwithdifferentdates}

You can change the date range/value for any report and view quickly for a different date without modifying and saving the report. Click the edit icon (as shown with an arrow in the snapshot below) next to the date range, such as QTD, last one year. To confirm the change, choose the new value from the pop-up menu and click tick mark. You can cancel the change by clicking X mark.

The date values that you use to view the report are temporary. This view of the report is not downloaded when you choose the download option. This view is only temporary view.

![](assets/learner-count-report.png)

## Quick view with different managers {#quickviewwithdifferentmanagers}

If there are multiple managers reporting to you, you can view the reports quickly for each manager. To display unique report for each manager, choose the manager name from the drop-down list.

The manager values that you use to view the report are temporary. This view of report is not downloaded when you choose the download option. This view is only temporary view.

## View course reports {#viewcoursereports}

You can view the reports specific to each course by following the below steps:

1. Click&nbsp;**View course reports**&nbsp;link in My Dashboards tab on the Reports page.  
   A pop-up dialog appears.&nbsp;A text input field appears where you can enter the required course and suggested &nbsp;course names appear in the drop-down list. Choose the course from the list shown.

   ![](assets/view-course-report-300x117.png)

1. Select the course of your choice from the drop-down list and click Show.
1. You are redirected to the Quiz score results page of the selected course to view the course-specific report.

**Edit/Move to board/Create a Copy/Delete/Resize report**

To view drop-down options as Edit/Move to Dashboard/Create a copy/Delete/Resize, click the drop-down arrow at the upper-right corner of each report.

![](assets/edit-options-dashboard-300x126.png)

**Edit **To&nbsp;go back to initial values while modifying data, click Reset. Click Save after modifying the values.

**Move to Dashboard**&nbsp;You can move the current report to another dashboard, which is chosen from the list of dashboards.

**Create a Copy**&nbsp;You can&nbsp;copy the report to same or another dashboard, which is chosen from the list of dashboards.

**Delete**&nbsp;Click Delete to remove the report. A warning/confirmation message appears before you can delete the report.

**Resize**&nbsp;You can resize your reports in 1×1(medium) and 2×2(large) sizes.

## Generate and view reports for peer account {#generateandviewreportsforpeeraccount}

As an administrator, apart from generating reports for your account, you can also generate and view reports for peer accounts that you have set.

When you have established a peer account with another user, you can view the reports for that peer account from the **[!UICONTROL Reports]** page. When you create a report, you find the **[!UICONTROL Select Account]** field. From the drop-down list, that lists all the peer account with which you are associated, select the account for which you want to view the shared reports.

While creating a peer account, if the&nbsp;Share Catalog&nbsp;option had not been selected, you cannot view that peer account in this list.

![](assets/acc1-jpg.png)

1. Select the x-axis and y-axis for this report, and select the date for this report.
1. Notice the filters field, the Shared Catalogs button is auto-enabled. It is mandatory. If Shared Catalog is not enabled, it implies that you cannot generate or view reports for the peer account.
1. From the drop-down list below Shared Catalog, select the shared catalog for which you want to view the report.
1. Click Save.

   ![](assets/acc2.png)

1. After you click Save, you can view the graphical representation of your reports in your default dashboard. From this dashboard, you can further filter the report by the manager for the specific peer account.
1. If there are any changes to the catalog from your side, the changes are immediately reflected in the reports and dashboard generated by the peer. However, when the peer modifies the catalog, the changes do not appear in your dashboard automatically.&nbsp;
1. If you want your dashboard to be updated automatically, your peer must send a new peer request to you.

   Managers cannot view peer reports.

## Email subscriptions {#emailsubscriptions}

You can get your favorite reports in an email by subscribing to them.

In **[!UICONTROL Reports]** page, click the  **[!UICONTROL Subscription]**&nbsp;tab. Reports subscription page appears.

To select the report name from the drop-down list, start typing the report name in the&nbsp;Reports&nbsp;field. Choose the frequency of email from the drop-down. You can add the subject of the email and provide an alternate email id.

You can Edit and Delete subscriptions.

## Excel Reports {#excelreports}

The **[!UICONTROL Excel Reports]** tab allows you to export reports in XLS file format.

The following are the report types available for download.

* Course Reports
* Learner Transcripts
* Announcements Report
* Job Aids Report
* Content Audit Trail
* User Audit Trail
* Login/ Access Report
* Gamification Transcripts

## Learner transcripts {#learnertranscripts}

The Learner Transcripts in Excel reports displays the columns Credits Required and Credits Earned in decimal numbers.

## Course Reports {#coursereports}

As an administrator, you can download reports for courses. Follow these steps:

1. Open **[!UICONTROL Reports > Excel Reports > Course Reports]**.
1. The **[!UICONTROL Course Report]** dialogue appears. Select the course you want to fetch the report of and click **[!UICONTROL Show]**.

   ![](assets/course-reports.png)

1. You are redirected to the course page. You can export quiz score by user and by question&nbsp;based on each enrollment by choosing the specific enrollment type.
1. Select **[!UICONTROL Export Quiz Score]** to export the report. A **[!UICONTROL Generating Report Request]** dialogue box appears. Click **[!UICONTROL OK]** to confirm.

   ![](assets/generating-reportrequest.png)

   Exported quiz score report will contain the score details for every attempt if the multi attempt option is configured for the module.

## Learner Transcripts {#LearnerTranscripts-1}

Adobe Captivate Prime enables the administrators of an organization to generate the transcripts associated with learners. The Learner Transcript report carries the following:

1. Learner Transcript: Learning Activity Dashboard
1. Skill:&nbsp;Skill Dashboard
1. Compliance Dashboard

`The Learner Transcripts in Excel reports displays the columns Credits Required and Credits Earned in decimal numbers.`

For information on generating Learner Transcript reports and more information, see [Learner Transcripts.](learner-transcripts.md)

## Announcements Reports {#announcementsreports}

As an administrator, you can generate a report of all the announcements that you send. The report has details regarding:

* Announcement type
* Announcement name
* Announcement date
* State of the announcement
* Learner name

To download a report, follow any one of these steps:

1. Open&nbsp;**Reports **> **Excel Reports** > **Announcements Report**. The&nbsp;**Generating Report Request**&nbsp;dialogue box opens. Click&nbsp;Ok.
1. Announcements > Actions > Export Report.

   ![](assets/announcements.png)

1. You can extract a report for a specific announcement by clicking&nbsp;Export Report&nbsp;under the settings icon.

   ![](assets/announcements-specific-report.png)

## Job Aids Report {#jobaidsreport}

Job Aids are training content that a Learner can access without having to enroll for any specific learning object like a Course or Learning Program. Administrators can extract and download Job Aids report.

The extracted report includes information about the following:

* Name
* Type of Job Aid
* State of Job Aid (published or withdrawn)
* Enrollment date
* Date of completion
* Download date
* Learner name&nbsp;
* Manager name
* Created by

&nbsp;

To download a report, do one of the following:

* Open  **[!UICONTROL Reports > Excel Reports > Job Aid Reports]**. The **[!UICONTROL Generating Report Request]** dialogue box appears. Click **[!UICONTROL Ok]**.

* Open **[!UICONTROL Job Aid > Actions > Export Report]**.

![](assets/job-aids.png)

* You can also extract a report for a specific Job Aid by clicking **[!UICONTROL Export Report]** under the settings icon.

![](assets/job-aid-specific-download.png)

## Content audit trail reports {#contentaudittrailreports}

Use the **[!UICONTROL Content Audit Trail]** report generator to generate a report of all the changes and edits made to a course during its life in the system. The generated report has the following information fetched.

* Object id
* Object name
* Object type
* Modification type
* Description
* Referenced object ID  
* Referenced object name  
* Modified by user name  

* Modified by user ID  
* Modified date (UTC Timezone)

Information regarding metadata is not fetched in the generated report.

To generate a Course trail audit report, follow these steps.

1. Select **[!UICONTROL Report > Excel reports> Course Audit Trail]**. The **[!UICONTROL Content Audit Trail]** dialog box appears.

   ![](assets/course-audit-trial.png)

1. Select the course, learning program and certification that you want to download the report of. If not specified, all reports are downloaded by default.
1. Select a date range for the report and click **[!UICONTROL Generate.]**
1. The report is generated and you are notified that the content audit report is ready. You can download the report.

## User audit trail reports {#useraudittrailreports}

User audit trail captures the life cycle of users, user groups,&nbsp;and self-registration profiles. User addition, deletion, change in Manager, are all captured. Creation and deletion of self-registration profiles are recorded. You can also pause and resume self-registration.

You can Add, Enable, Disable, Pause, or Resume for External profiles while you can Add, Delete, Pause, or Resume for self-registration. CSV uploads are also captured.

1. Select  **[!UICONTROL Report > Excel report > User Trail]**. The&nbsp;User Audit Trail&nbsp;dialog box appears.
1. The User Audit Trail dialog box appears. Select the date range from the pop-up menu. You can either choose to generate report for last one week, last one month, or select custom date.

   ![](assets/user-audit-trail.png)

1. Click **[!UICONTROL Generate]** to generate the report.

There are two filters on the **User Audit Trail Report** dialog.

**Date rage filter:&nbsp;**Choose the date range for which you want to generate the report. There are three options:

* Last One week  
* Last One Month  
* Custom date

Select Learners filter:&nbsp; Search for a user or a user group.

The exported report will contain data of the users who meet both the search criteria specified.

![](assets/user-audit-trail.png)

## Gamification reports {#gamification}

Administrators can download gamification transcript in CSV format. You can either download the report for&nbsp;individual&nbsp;user or user groups. User name, user email, User's UUID, total user points scored,&nbsp; breakup of points collected, name of groups the user plays in, name of the manager, and active field values are all fetched in the report. Administrators can use this report to evaluate and understand user rankings at the organization level or for a specific group.

1. Select&nbsp;Report > Excel report > Gamification report.

   ![](assets/gamification.png)

1. The Gamification Transcripts dialog box appears. Select learners using their Name, Profile, User Groups, Email Id, or UUID.

   ![](assets/gamification-transcriptsdialog.png)

1. Click  **[!UICONTROL Generate]**&nbsp;to generate the report.

   After you generate the report of a learner, you must be able to export the current and achieved-level information&nbsp;for all the users (internal, external, or deleted) in the account. You can also check the dates for the levels achieved by a learner:

   * Bronze Achieved Date
   * Silver Achieved Date
   * Gold Achieved Date
   * Platinum Achieved Date

   These columns contain the dates on which the level was achieved at the very first time. The column **Current Level** displays the current level of the learner.&nbsp;

   When the Admin resets the gamification, all points of the learner get reset accordingly.

## Enrollment and Unenrollment report {#enrollmentandunenrollmentreport}

Administrators and managers can extract a report of the learners who have been enrolled&nbsp;and unenrolled. As an administrator, you can see any of the learner, administrator, or manager who has been enrolled or unenrolled from an instance of a course, learning program or certification and export the report. While, as a Manager, you can only fetch a report of your team members.&nbsp;As a manger, you are not able to see the deleted learners or your&nbsp;own name in the manager application as an enrolled or an unenrolled learner.

To download a report, follow these steps: Open the  **[!UICONTROL Course/ Learning program/ Certification > Learners > Action > Export report.]**

![](assets/unenrollment.png)

## Feedback Report {#feedback-report}

As an Administrator, you can now fetch both Learner feedback (L1) and Manager feedback (L3) for selected trainings for a specified period.&nbsp;

You can export the data from the UI or through&nbsp;PowerBI&nbsp;connector&nbsp;for more in-depth analysis.

L1&nbsp;and&nbsp;L3 feedback reports&nbsp;provide an option to download a consolidated feedback report for the L1&nbsp;and&nbsp;L3 responses for selected trainings for a&nbsp;**one-year&nbsp;**range or for up to 10 Selected trainings for any date range.

Sign in as an Administrator, click&nbsp;**Reports > Custom Reports**, and in the list of reports, click&nbsp;**Feedback Report**.

![](assets/download-feedbackreport.png)

Clicking on download after selecting the filters,&nbsp;you&nbsp;will receive a notification to download the report in CSV format.

The downloaded report will have details such as Training name and type, Instance name, Learner name and email, Type of Feedback: L1 or L3, Dates of the&nbsp;feedback&nbsp;submitted for new data.&nbsp;

For existing data prior to this feature implementation the LO completion date will be displayed, LO Completion date, L1&nbsp;Feedback&nbsp;question Self-Paced actual text and Class Room Text in different columns, L1&nbsp;Feedback&nbsp;respective responses, Manager name and email, L3&nbsp;feedback&nbsp;value and submitted date, Active Fields.

You can also export the data from the UI or&nbsp;to Power BI, which supports all trainings for any date range for more in-depth analysis

## Trainings Report {#training-report}

Captivate Prime supports&nbsp;Training Report which allows Administrators to download training details and its associated metadata like author, published date, skills, Catalog labels etc.&nbsp;

On the Admin app, click&nbsp;**Reports > Custom Reports > Excel Reports > Trainings Report**.&nbsp;

You can download reports&nbsp;for the following:

* Selected trainings (Limit 10) - Selects one or multiple trainings (up to 10) from any catalog
* Trainings in the selected Catalogs (Limit 5) - (catalog selection will be available up to five catalogs)
* All trainings - (all trainings in the account)

![](assets/download-trainingreport.png)

In the&nbsp;Advanced Options&nbsp;section,&nbsp;the following options are available:

* Include Course mappings with Learning Program / Certification
* Include Module Level information

After selecting the filters and clicking&nbsp;Download, you&nbsp;will receive a notification to download the report in CSV format.&nbsp;

The report will have the following fields:

*Catalog Name, Training Type, Training Id,&nbsp;Training&nbsp;unique id, Training Name, Sub Trainings, Modules, Training or Module Duration, Format, Status of Training, Skills, Author, Last Published Date, Last completed Date, Instructors Enrollment Count,&nbsp;Started&nbsp;count, Completion count, Avg L1 score, Avg L2 score, Avg L3 score, L1 responses received, L2 responses received, L3 responses received, Catalog labels & Tags.*

![](assets/more-options.png)

## Session Summary Report

The Session Summary Report&nbsp;contains all sessions planned for a learner within a specified date.

This allows the&nbsp;Administrator to export all the Virtual and Classroom session details falling under the given date range. The Admin can also export the session report with respect to&nbsp;specific&nbsp;trainings&nbsp;or&nbsp;Instructors.&nbsp;

This will also help the Administrator&nbsp; to understand the sessions planned on a monthly basis and identify instructors' schedule and&nbsp;already&nbsp;delivered sessions.

As an Administrator, click&nbsp;**Custom Reports > Session Summary Report**.

In the dialog box that follows, choose the date range, and either the training or instructor for a summary.

![](assets/session-summary-report.png)

The downloaded csv contains the following fields:

* Start date and time
* End date and time

* Module Name&nbsp;
* Session Duration (in minutes)
* Seat count
* Location
* Instance Name&nbsp;

* Course Name
* Course Id
* Instructor Name
* Instructor Email&nbsp;
* Enrollment Count

* Session Type
* Waitlist Limit
* Waitlist count&nbsp;
* Waitlist user emails

## Frequently Asked Questions {#frequentlyaskedquestions}

**1.&nbsp;How to share a custom dashboard with a manager?**

When creating a dashboard, enter the name and description. To share with managers, enter the manager's name in the **Share With** field.

![](assets/share-dashboard-manager.png)

