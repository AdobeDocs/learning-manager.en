---
description: Learn more about how to export and review all trainings in your account, including content structure, learner engagement, and feedback insights.
jcr-language: en_us
title: Trainings Report in Adobe Learning Manager
---

# Training report

## Overview 

The Trainings Report provides a detailed inventory and performance analysis of all learning content within Adobe Learning Manager.  

The report tracks: 

* All Learning Object types (courses, certifications, learning paths) 
* Content structure hierarchies and relationships 
* Delivery formats and durations 
* Skill mappings  
* Learner engagement metrics and feedback scores 
* Content lifecycle status (published, retired) 
* Localization and language availability 
* Pricing information 

## Purpose and benefits 

* Gain visibility into the entire learning catalog structure, identifying content gaps, redundancies, or outdated materials. 
* Analyze feedback scores (L1-L3) and completion rates to determine which content delivers the highest learning impact. 
* Track expiration dates, training status, and skill mappings to maintain regulatory compliance. 
* Identify content requiring updates, retirement, or replacement based on publication dates and feedback metrics. 

## Use cases 

* A pharmaceutical company needs to demonstrate both the availability and effectiveness of its GxP compliance training to regulators. Filter the Trainings Report for all content with compliance-related catalog names, analyze completion rates and L2 assessment scores for these courses, and review expiration dates to ensure all compliance content remains current. 
* An IT department needs to streamline its technical training catalog while ensuring all critical skills remain covered. Export the Trainings Report with module-level information, analyze content overlap by comparing modules, skills, and formats, and identify low-engagement content (low completion rates, poor feedback scores) 
* The L&D team needs to evaluate whether structured learning paths deliver better outcomes than standalone courses. Compare completion rates between standalone courses and those embedded in learning paths, analyze feedback scores (L1-L3) for both delivery approaches, and review the structure of high-performing Learning Paths. 

## How to download the Trainings report 

1. Select **[!UICONTROL Reports]** and then select **[!UICONTROL Custom Reports]**. 
2. Select **[!UICONTROL Excel Reports]**. 
3. Select **[!UICONTROL Trainings Report]**. 
4. Select the following: 
    a. Selected trainings (Limit 10): Selects one or multiple trainings (up to 10) from any catalog 
    b. Trainings in the selected Catalogs (Limit 5) (catalog selection will be available up to five catalogs) 
    c. All trainings (all trainings in the account) 

5. In the **[!UICONTROL Advanced Options]** section, select either or both: 
    a. Include Course mappings with Learning Path/ Certification 
    b. Include Module Level information 

6. Select **[!UICONTROL Download]** to download the Trainings report as a CSV file. 

## What does the Trainings report contain

|Column |Description |
|---|---|
|Catalog Name |The catalog(s) under which the training is listed. |
|Training ID |The ID of the course, certification, Learning Path, or Learning Path (Higher Level). |
|Training Unique ID |A unique, external-facing ID for the training. |
|Training Type |Type of training, Course, Certification, or Learning Path. |
|Training Name |The name or title of the training. |
|Embedded Path |The training's Learning Path. <br>This field shows Learning Paths that are embedded within another Learning Path.</br>| 
|Sub Trainings |Training courses linked to the training in question. <br>The column refers to the individual components or modules that are part of a larger training program, such as a Learning Path. </br> |
|Modules |Specific content modules within the training. <br><b>Note:</b> This column appears if you've selected the Include Module level information checkbox while generating the report. </br> |
|Format |The type of module, for example, Activity, Blended, Classroom, Self Paced, and Virtual Classroom. |
|Training or Module Duration (mins) |Total time required to complete the training or the modules, in minutes. It also indicates the overall course's time required when the module field is empty in the row (when module information is included).  Only modules that are part of the course are included for calculating total time required at a course level. Pre-work is not calculated. |
|Status of Training |The status of the training, Retired, Draft, Published, or Expired. |
|Skills |Skills linked to the training. |
|Author |Creator or owner of the training content. |
|Last Published Date (UTC TimeZone) |Last date and time the training was published. |
|Last Completed Date (UTC TimeZone) |Last date and time when the training was completed by any learner. |
|Instructors |Assigned instructors for instructor-led training. |
|Enrollment Count |The number of learner enrollments for the training. |
|Started Count |The number of learners who have started the training. |
|Completion Count |The number of learners who have completed the training successfully. |
|Avg L1 Score |The average L1 (learner satisfaction) feedback score. |
|Avg L2 Score |Average L2 (learning assessment) feedback score. |
|Avg L3 Score |Average L3 (manager feedback) score. |
|L1 Responses Received |The number of L1 feedback received. |
|L2 Responses Received |The number of L2 feedback received. |
|L3 Responses Received |The number of L3 feedback received. |
|Catalog Labels |The metadata labels assigned to the catalog for filtering and grouping. |
|Tags |The tags used for content categorization (beyond catalog labels). |
|Avg Star Rating |The average star rating received from learners. |
|Count of users providing Star rating |The number of users who submitted a star rating for the training. |
|Embedded Path ID |The ID of the embedded Learning Path, if applicable. |
|Training Language |The languages for which the courses have been developed. |
|Embedded Path Language |The language of the embedded Learning Path, if applicable. |
|Sub Training Language |The language of the sub-trainings, if it's a part of a Learning Path or certification. |
|Module Language |The language of the specific training modules. |
|Content Expiry Date (UTC TimeZone) |The date when the training content will expire. <br><b>Note:</b> This column appears if you've selected the Include Module level information checkbox while generating the report. </br> |
|Content Unique ID |The unique ID assigned to the content. <br><b>Note:</b> This column appears if you've selected the Include Module level information checkbox while generating the report.</br> |
|Price ($) |The price of the training if it's sold externally or internally. <br><b>Note:</b> This column appears in the report only if you've enabled the option Enable pricing for Courses/ Learning Paths/ Certifications when setting up the account. </br> <br>Also, the currency depends on the value you set when setting up the account.</br> |
|Gamification Enabled |Indicates if the training is eligible for gamification points. <br>The column indicates if gamification features are enabled for each instance of a course. For example, the values in the column are represented by `instance name`:0 or 1 (Default instance:0), which represents whether gamification is on or off. </br> |
|Auto Retirement Date (Enabled) |The date when the training auto-retires. This field must be enabled by the account administrator in Adobe Learning Manager settings page. If this option is enabled, then the author can set the date when the Learning Object retires automatically. |
|Completion Deadline (UTC TimeZone) |The date by which learners must complete the training. <br>The date and time by which learners must complete a course instance. For example, the values in the column will have date and time stamp against each course instance, such as NA, which means the default instance of the course does not have a completion deadline. If a course instance has a completion deadline, such as Default instance:NA,Course1, 2025:2025-03-31T21:59:59.000Z, it means that the Course1 instance has a completion deadline set by the course author.</br>|
|Role(s)/Product(s)/Recommendation(s) |Indicates if the learner has consumed a recommended training if the account is configured with the recommendation system. <br><b>Note:</b> This column is available only if you've upgraded to the new recommendation system. </br>|

## Additional considerations for Trainings report 

### Connector support 

You cannot download a training report using connectors. 

### How can I see the Sub Training ID column in the report? 

The downloaded training report does not contain the Sub Training ID column. However, you can use the Adobe Learning Manager APIs to generate a report that contains the column. Here's how to do it: 

1. Create a job. Use the POST /jobs endpoint to initiate the report generation process. 

    ```
    POST https://learningmanager.adobe.com/primeapi/v2/jobs
    ```

2. Provide the payload. Paste the relevant payload data into the request body to specify the report's parameters.

    ```
    { 
        "data": { 
            "type": "job", 
            "attributes": { 
                "description": "Download training data", 
                "jobType": "generateTrainingReport", 
                "payload":{ 
                    "courseId": "course:1171900,course:16444,course:1171899", 
                    "includeSubLOId": true 
                } 
            } 
    } 
    } 
    ```
 
    Ensure that includeSubLOId is passed as true in the payload to include the Sub Training ID column in the generated report. 

    Upon successful execution of the POST request, the report generation will begin. A unique Job ID will be assigned to track the progress. 

    The response is as follows: 

        
    ```
        { 
            "links": { 
                "self": "https://learningmanager.adobe.com/primeapi/v2/jobs" 
            }, 
            "data": { 
                "id": "43144", 
                "type": "job", 
                "attributes": { 
                    "dateCreated": "2025-05-27T04:23:30.000Z", 
                    "description": "Download training data", 
                    "jobType": "generateTrainingReport", 
                    "payload": { 
                        "includeSubLOId": true, 
                        "courseId": "course:1171900,course:16444,course:1171899" 
                    }, 
                    "status": { 
                        "code": "Submitted" 
                    } 
                } 
            } 
        } 

    ```

3. Use the GET /jobs/{id} endpoint, replacing {id} with the Job ID obtained from the previous step. 

    ```
    GET https://learningmanager.adobe.com/primeapi/v2/jobs/43144
    ``` 

4. Upon successful execution of the GET request, an S3 URL is provided. Copy and paste this URL into your browser to download the generated training report. 

    ```
    { 
        "links": { 
            "self": "https://learningmanager.adobe.com/primeapi/v2/jobs/43144" 
        }, 
        "data": { 
            "id": "43129", 
            "type": "job", 
            "attributes": { 
                "dateCompleted": "2025-05-26T16:58:31.000Z", 
                "dateCreated": "2025-05-26T16:57:58.000Z", 
                "description": "Download training data", 
                "jobType": "generateTrainingReport", 
                "payload": { 
                    "includeSubLOId": true, 
                    "courseId": "course:1171900,course:16444,course:1171899" 
                }, 
                "status": { 
                    "code": "Completed", 
                    "data": { 
                        "s3Url": "https://acapgeneratedreports-stg1.s3.amazonaws.com/1010/TrainingReport2400515127248713323.csv?response-content-disposition=attachment%3B%20filename%3D%22TrainingReport2400515127248713323.csv%22&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20250526T165831Z&X-Amz-SignedHeaders=host&X-Amz-Credential=AKIAXJMB2V5WNGSXKY7H%2F20250526%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Expires=604800&X-Amz-Signature=f431afc46ff1c1d4084ab603ddfaec7de6ae0a82744ccf398a2f4fc8a01ebd10" 
                    } 
                } 
            } 
        } 
    } 
    ```
 

The downloaded report will contain the column Sub Training ID. 

### Check Learning Objects stats for a user group 

The downloaded training report does not contain the stats for Learning Objects for a user group. However, you can use the Adobe Learning Manager APIs to generate the stats. Here's how to do it: 

1. Get the user group IDs using the /userGroups endpoint. 
    
    ```
    GET https://learningmanager.adobe.com/primeapi/v2/userGroups?page[offset]=0&page[limit]=10&sort=name&filter.states=Active 
    ```

2. Create a job. Use the POST /jobs endpoint to initiate the stats generation process. 

    ```
    POST https://learningmanager.adobe.com/primeapi/v2/jobs 
    ```

3. Provide the payload. Specify the relevant user groups in the request body to specify the required parameters.   

    ```
    { 
        "data": { 
            "type": "job", 
            "attributes": { 
                "description": "Sample description", 
                "jobType": "generateTrainingStatsReport", 
                "payload":{ 
                    "userGroups": "17039,17038" 
                } 
            } 
    } 
    } 
    ```
 

    Upon successful execution of the POST request, you will see the following response: 

    ```
        { 
            "links": { 
                "self": "https://learningmanager.adobe.com/primeapi/v2/jobs" 
            }, 
            "data": { 
                "id": "43145", 
                "type": "job", 
                "attributes": { 
                    "dateCreated": "2025-05-27T04:55:37.000Z", 
                    "description": "Sample description", 
                    "jobType": "generateTrainingStatsReport", 
                    "payload": { 
                        "userGroups": "17039,17038" 
                    }, 
                    "status": { 
                        "code": "Submitted" 
                    } 
                } 
            } 
        } 
    ```

4. Use the GET /jobs/{id} endpoint, replacing {id} with the Job ID obtained from the previous step.   

    ```
    GET https://learningmanager.adobe.com/primeapi/v2/jobs/43145 
    ```

5. Upon successful execution of the GET request, an S3 URL is provided (see the response at the end of the step). Copy and paste this URL into your browser to download the following Learning Object stats for users in a user group: 

    * completedCourses 
    * incompleteCourses 
    * completedCertification 
    * incompleteCertification 
    * completedLearningProgram 
    * incompleteLearningProgram 

```
{ 
    "links": { 
        "self": "https://learningmanager.adobe.com/primeapi/v2/jobs/43145" 
    }, 
    "data": { 
        "id": "43145", 
        "type": "job", 
        "attributes": { 
            "dateCompleted": "2025-05-27T04:55:46.000Z", 
            "dateCreated": "2025-05-27T04:55:37.000Z", 
            "description": "Sample description", 
            "jobType": "generateTrainingStatsReport", 
            "payload": { 
                "userGroups": "17039,17038" 
            }, 
            "status": { 
                "code": "Completed", 
                "data": { 
                    "s3Url": "https://cp-s3-stage1-us-east-1-jobs.s3.amazonaws.com/1010/users_2025-05-27T04%3A55%3A43.839Z.csv?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20250527T045546Z&X-Amz-SignedHeaders=host&X-Amz-Credential=AKIAXJMB2V5WNGSXKY7H%2F20250527%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Expires=604800&X-Amz-Signature=68abf51a5538d148e94a19e209a6592ef4e68d193a5a564ddf312dcab90b75f6" 
                } 
            } 
        } 
    } 
} 
```
 

 

