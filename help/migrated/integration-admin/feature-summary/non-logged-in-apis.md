---
description: Learn about the non-logged-in APIs to develop the headless interface. 
jcr-language: en_us
title: Non-logged-in APIs
---
# Non-logged-in APIs

Learn more about the Adobe Learning Manager APIs, which provide data for the headless or non-logged-in experience in this article.
Public Search API 

## Public Search API 

### Filter data using Public ES

The Public Search API allows you to get the filter data that can be used with the basic search API to filter the courses. This API provides all the filters that can be used in the search API.

**Sample curl**

Use the GET method to make the following request. Replace <Base_URL> with your base URL in the curl command below. You can find the <Base_URL> on the training data access connector page. 

```
curl --location '<Base_URL>/filterableData'
```

**Sample response**

```
{
    "terms": {
        "loSkillLevels": [
            "1"
        ],
        "catalogNames": [
            "Default Catalog"
        ],
"catalogLabelIds": [
            "0000_1111"
        ],
        "loType": [
            "course"
        ],
        "availability": [
            "waitlistAvailable",
            "seatAvailable"
        ],
        "loSkillNames": [
            "General"
        ],
        "tags": [
            "course_tag"
        ],
        "authors": [
            "author_1"        
]
    },
    "range": {
        "duration": [
            "0"
        ],
        "dateCreated": [
            "2024-06-13T04:32:17.000Z"
        ],
        "price": [
            "0.0"
        ],
        "sessionEndTime": [
            "2024-06-18T20:30:00.000Z"
        ],
        "averageRating": [
            "0.0"
        ],
        "sessionStartTime": [
            "2024-06-18T19:30:00.000Z"
        ],
        "publishDate": [
            "2024-06-13T04:32:51.000Z"
        ],
        "ratingsCount": [
            "0"
        ]
    },
    "term": {}
}
```

**Filter options**

| Options | Description |
| --- | --- |
| `loSkillLevels` | he proficiency level required for enrolling into the course. |
| `catalogNames` | List of available catalog names. |
| `loType` | Types of available learning objects. |
| `availability` | The seat availability and waitlist availability. |
| `loSkillNames` | The skill names added to the learning objects. |
| `tags` | The tags associated with the learning objects. |
| `authors` | The author's name of the learning objects |
| `duration` | The duration of the learning objects. |
| `dateCreated` | The date the learning object was created. |
| `sessionEndTime` | The time the session ended. |
| `averageRating` | The average star rating of the learning objects. |
| `sessionStartTime` | The time the session started. |
| `publishDate` | The published date of the learning object. |
| `ratingsCount` | The number of rating counts for the learning object.|

### Search API

The public Search API allows you to get basic search data using the provided data. 

**Sample Curl**

Use the POST method to make the following request. Replace <Base_URL> with your base URL in the curl command below. You can find the <Base_URL> on the training data access connector page. 

```
curl --location '<Base_URL>/search?size=1000' \
--header 'content-type: application/json' 

--data '{
   "query": "",
   
    "sort": {
        "name": "publishDate",
        "order": "desc"
    },
    "lang": [
        "en-US"
    ],
    "filters": {
        "terms": {
            "loType": [
                "course",
                "learningProgram",
                "certification"
            ],
            "availability": [
                "seatAvailable",
                "waitlistAvailable"
            ]
        },
        "term": {
            "enrollmentDeadlinePassed": "true"
        },
        "range": {
                "dateCreated": [
                    {
                        "gte": "2024-05-02T02:48:51.000Z"
                    }
                ],
            "sessionStartTime": [
                {
                   "gte": "2024-06-18T19:30:00.000Z"
                }
            ],
            "sessionEndTime": [
                {
                   "lte": "2024-06-20T09:30:00.000Z"     
                }
            ]
        }
    }
}'
```

**Sample response of the API call**

```
{
    "results": [
        {
            "loId": "course:11332313",
            "loType": "course",
            "tags": [
                "course_tag"
            ],
            "authors": [
                "author1",
                "author2"
            ],
            "status": "Published",
            "duration": 0,
            "publishDate": "2024-06-13T04:32:51.000Z",
            "dateCreated": "2024-06-13T04:32:17.000Z",
            "name": "vc coursse to check ",
            "averageRating": 0.0,
            "ratingsCount": 0,
            "loSkillNames": [
                "General"
            ],
            "loSkillLevels": [
                "1"
            ],
            "loInstances": [
                {
                    "id": "14346696",
                    "name": "Default Instance",
                    "status": "Active",
                    "price": 0.0
                }
            ],
            "catalogInfo": [
                {
                    "id": "37779",
                    "name": "Default Catalog"
                }
            ]
        }
    ],
    "request": {
        "query": "",
        "filters": {
            "terms": {
                "loType": [
                    "course",
                    "learningProgram",
                    "certification"
                ],
                "loSkillNames": [
                    "General"
                ],
                "deliveryType": [],
                "availability": [
                    "seatAvailable",
                    "waitlistAvailable"
                ]
            },
            "term": {
                "enrollmentDeadlinePassed": "true"
            },
            "range": {
                "dateCreated": [
                    {
                        "gte": "2024-05-02T02:48:51.000Z"
                    }
                ],
                "sessionStartTime": [
                    {
                        "gte": "2024-06-18T19:30:00.000Z"
                    }
                ],
                "sessionEndTime": [
                    {
                        "lte": "2024-06-20T09:30:00.000Z"
                    }
                ]
            }
        },
        "sort": {
            "name": "publishDate",
            "order": "desc"
        },
        "lang": [
            "en-US"
        ]
    },
    "self": "<Base_URL>/search?page=0&size=1000",
    "count": 1
}
```

**Sort options on the Search API**

You can select the following sorting options to be applied to the results.

| Options | Description|
| --- | --- |
| `duration` | The duration of the learning object. |
| `publishDate` | The published date of the learning object. |
| `dateCreated` | The date the learning object was created. |
| `name_en` | The name of the learning object. |
| `averageRating` | Average star rating provided by the learners. |
| `ratingsCount` | The number of rating counts for the learning object. |
| `relevance(default)` | The relevant data is based on the search keywords. |

### Get learning object data using Public search API

The Public ES Learning Object API lets you get the list of types and IDs of learning objects available on the headless interface. 

**Sample curl**

Use the GET method to make the following request. Replace <Base_URL> with your base URL in the curl command below. You can find the <Base_URL> on the training data access connector page. 

```
curl --location '<Base_URL>/learningObjectIds'
```

**Sample response for the API call**

```
{
    "loIds": [
        "course:1132800",
"certification:126009",
"learningProgram:104433"
    ]
}
```