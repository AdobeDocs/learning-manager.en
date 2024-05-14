---
jcr-language: en_us
title: API Deprecations in Adobe Learning Manager
description: As the APIs in Adobe Learning Manager evolve, APIs are periodically reorganized or upgraded. When APIs evolve, the old API is deprecated and eventually removed. This page contains information you need to know when migrating from deprecated API versions to newer and more stable API versions.
contentowner: saghosh
exl-id: 0fe9a3cb-9114-42d6-81ae-1a4f28c984fa
---
# API deprecations and changes in Adobe Learning Manager

## API deprecations in the March 2024 release of Adobe Learning Manager

<!-- ### Changes in Rate Limits

With the next release of Adobe Learning Manager, we're restructuring API rate limits for new accounts. For existing accounts, only the Admin APIs will be rate-limited. After 90 days (about 3 months), we will restructure rate limits for all APIs, but existing accounts will be whitelisted according to current usage. Existing accounts need to revisit their learner API usage. 

For new accounts, if they want to increase the rate limits, they must contact the Customer Success team of ALM. 

#### Which APIs will be rate limited 

For new accounts, all Admin, Learner, and Search APIs will have rate limits and burst enforced.  

The API burst rate or burst limit refers to the maximum number of requests allowed to be made to an API in a short burst within a limited timeframe. 

The following table lists the rate and burst limits for the APIs.

<table>
    <tr>
        <th>API</th>
        <th>Number of requests-RPM</th>
        <th>Number of requests-Burst</th>
    </tr>
    <tr>
        <td>Admin</td>
        <td>5</td>
        <td>5</td>
    </tr>
    <tr>
        <td>Learner</td>
        <td>20</td>
        <td>5</td>
    </tr>
    <tr>
        <td>Search</td>
        <td>50</td>
        <td>5</td>
    </tr>
</table>
-->

### Changes to offset limits 

Due to a high number of records being retrieved by the offset value and slowing down overall performance, we're enforcing a limit of **500** records. In the next release, for both Admin and Learner, the **GET Users** API will return a maximum of **500** records. 

If you need more records to be fetched, use the **GET Jobs** API.  

The change in offset limits applies to all new customers. For existing customers, the 90-day rule applies.

### Exclude paths 

At present, Learning Manager APIs follow a graph data structure, which allows you to fetch data by traversing the API model through includes. Even though you could traverse an API up to seven levels, fetching the data using a single API call is computationally expensive. 

We recommend that all existing and new customers make small calls multiple times instead of one large call. This approach will prevent unwanted data from being loaded in the call. 

We want to enforce these restrictions on new accounts and maintain a whitelist of existing accounts.

#### What paths are deprecated

The following paths are deprecated:

* /learningObjects
    * Deprecated paths:
        * enrollment.loInstance.loResources.resources
        * instances.loResources.resources 
    * New paths:
        * enrollment.loInstance.loResources
        * instances.loResources 

* /learningObjects/{id} 
    * Deprecated path: 
        * enrollment.instances.subLoInstances.learningObject 
    * New path: 
        * enrollment.instances.subLoInstances 

* /enrollments 
    * Deprecated path:  
        * loInstance.learningObject.enrollment 
    * New path: 
        * loInstance.learningObject 

* /learningObjects/{id} 
    * Deprecated path: 
        * instance.subLoInstances.learningObject.enrollment.loResourceGrades 
    * New path: 
        * instance.subLoInstances 

### Instance summary count changes 

Currently, in the LO summary endpoint, you fetch the number of all possible instances. For example, for a course, you can view the number of enrollments and waitlists in the response for **GET /learningObjects/{loId}/instances/{loInstanceId}/summary**. You can then view the completionCount and enrollmentCount in the response. If the course is a VC or classroom, you can also view its seat limit and waitlist limit. 

The process of retrieving the completion and enrollment counts is computationally expensive, therefore the calculation is done on a request basis. If the data is not present in the cache, the data is reloaded, which is computationally intensive. If there are many users enrolling in a course, the counts will be large, and effectively impacts CPU performance. 

In the next release of Adobe Learning Manager, in the LO Instance summary endpoint, the completionCount, enrollmentCount, seatLimit, and waitlistCount are cached. The cached information persists till there are changes in enrollments or unenrollments. For counts exceeding 1000 enrollments, we'll assume the estimated counts, and invalidate the results for all existing and new accounts.

>[!NOTE]
>
>For counts, such as, completionCount, enrollmentCount, seatLimit, and waitlistCount exceeding1000, it's advisable to interpret them as estimates rather than precise figures, as these will be retrieved from cache.

### Sort by name 

In the next release of Adobe Learning Manager, name and –name are deprecated in the sort field of the following APIs:

* GET /userGroups/{userGroupId}/users 
* GET /users 

>[!NOTE]
>
>For all existing and new accounts, sort by name and –name will be deprecated. 


## API deprecations in the November 2023 release of Adobe Learning Manager

### Override flag

In the November 2023 release of Adobe Learning Manager, we have discontinued the override flag from the APIs. The override flag is not a part of the public API specification and is intended for backend testing. The flag is now discontinued for Learner APIs. However, the flag is still valid for Admin APIs.  

The reason we're deprecating the flag for the Learner APIs is because the override flag was fetching a large amount of data via the Learner APIs.  

Going forward, the following Learner API will stop working because it has the override flag.

_/primeapi/v2/users?page[offset]=0&page[limit]=10&sort=id&override=TRUE_

### API Changes for Skill based new recommendations

Adobe Learning Manager improves the recommendations for Customer and Partner-enabled accounts. This improvement in the recommendation algorithm with the change in the ranking algorithm for course, learning path, and certification provides a better user experience in content discovery.  

The algorithm will no longer allow peer-based recommendations. The change will not affect the existing users, but the Industry Aligned option will continue to exist. For the Custom option, Adobe Learning Manager will no longer allow custom peer-based selection.  

The peer group now becomes an account, and learners will see a string that shows the trending topics in the group. All recommendations are explainable. For example, if you are viewing something on a subject, the card on the strip will display the reason for the course. 

### Changes In Notifications Announcement Report

In earlier releases of Adobe Learning Manager, the Notification Announcement report didn't have any filters. Adobe Learning Manager downloaded all notifications in the account. 

In the November 2023 release, we've added a date filter, using which you can download the notifications within a specified period.  You can, however, download the report for the last six months only.

### Deprecation of high offset values in GET /users endpoint

To improve system performance and manage resource utilization more effectively, Adobe has deprecated high offset values in the GET /users endpoint for both **ADMIN** and **LEARNER** scopes. We recommend using the **Jobs API** to retrieve the records with an offset value.

