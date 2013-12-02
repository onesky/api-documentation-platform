## Feedback
- [List](#list---list-all-feedbacks)
- [Show](#show---show-details-of-a-feedback)
- [Create](#create---create-a-feedback)


### List - list all feedbacks
Returns a listing of feedbacks in the platform.

    GET https://platform.api.onesky.io/1/feedbacks

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

<table>
    <tr>
        <td><strong>Name</strong></td>
        <td><strong>Required?</strong></td>
        <td><strong>Default</strong></td>
        <td><strong>Sample</strong></td>
        <td><strong>Description</strong></td>
    </tr>
    <tr>
        <td>page</td>
        <td>optional</td>
        <td><code>1</code></td>
        <td></td>
        <td>Set page number to retrieve. (min: 1)</td>
    </tr>
    <tr>
        <td>per_page</td>
        <td>optional</td>
        <td><code>50</code></td>
        <td></td>
        <td>Set how many groups to retrieve for each time. (max: 100, min: 1)</td>
    </tr>
    <tr>
        <td>project</td>
        <td>optional</td>
        <td></td>
        <td></td>
        <td>Filter the list by project which the feedback belongs to.</td>
    </tr>
    <tr>
        <td>locale</td>
        <td>optional</td>
        <td><code>en</code></td>
        <td><code>zh-TW</code></td>
        <td>Filter the list by locale. Please refer to <a href="/resources/locales.md">GET locales</a></td>
    </tr>
</table>

**Response**

```
status 200 OK
```
``` json
{
    "feedbacks": [
        {
            "id":123,
            "created_at":"2013-03-03T03:03:03+0000",
            "created_at_timestamp":1328475945,
            "url":"http://www.oneskyapp.com",
            "language":{
                "code": "ja_JP",
                "english_name": "Japanese",
                "local_name": "日本語",
                "locale": "ja",
                "region" : "JP"
            },
            "screenshot_url":"<screenshot url>",
            "submitter":{
                "user_type":"employee",
                "email":"contact@oneskyapp.com"
            },
            "comment":"onesky is good",
            "status":"process",
            "blocks": [
                {
                    "id":6789,
                    "created_at":"2013-03-04T04:04:04+0000",
                    "created_at_timestamp":1365066244,
                    "category":"typo",
                    "type":"string",
                    "strings":"onesky is bad",
                    "comment":"unacceptable typo mistake",
                    "suggestion":"onesky is excellent",
                    "status":"process",
                    "translated_string":{
                        "id":12308,
                        "string":"onesky is bad"
                    }
                },
                {
                    "id":7890,
                    "created_at":"2013-03-03T03:03:03+0000",
                    "created_at_timestamp":1362301383,
                    "category":"format",
                    "type":"non-textual",
                    "index":2,
                    "comment":"improper format",
                    "suggestion":"shouldn't use underscore",
                    "status":"new"
                },
                ...
            ]
        },
        {
            "id":456,
            "created_at":"2013-03-04T04:04:04+0000",
            "created_at_timestamp":1365066244,
            "url":"http://www.oneskyapp.com",
            "language":{
                "code": "zh_CN",
                "english_name": "Chinese Simplified",
                "local_name": "简体中文",
                "locale": "zh",
                "region" : "CN"
            },
            "screenshot_url":"<screenshot url>",
            "submitter":{
                "user_type":"proofreader",
                "email":"contact@oneskyapp.com"
            },
            "comment":"I love onesky",
            "status":"finish",
            "blocks": [
                {
                    "id":345,
                    "created_at":"2013-03-04T04:04:04+0000",
                    "created_at_timestamp":1365066244,
                    "category":"translate",
                    "type":"string",
                    "strings":"The best translation site",
                    "comment":"wrong translation",
                    "suggestion":"The best translate platform",
                    "status":"finish",
                    "translated_string":{
                        "id":2390,
                        "string":"The best translation site"
                    }
                },
                ...
            ]
        },
        ...
    ]
}
```
[Back to top](#feedback)


### Show - show details of a feedback
Returns the feedback's attributes.

    GET https://platform.api.onesky.io/1/feedbacks/:id

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

NONE

**Response**

```
status 200 OK
```
``` json
{
    "feedback": {
        "id":123,
        "created_at":"2013-03-03T03:03:03+0000",
        "created_at_timestamp":1328475945,
        "url":"http://www.oneskyapp.com",
        "language":{
            "code": "ja_JP",
            "english_name": "Japanese",
            "local_name": "日本語",
            "locale": "ja",
            "region" : "JP"
        },
        "screenshot_url":"<screenshot url>",
        "submitter":{
            "user_type":"employee",
            "email":"contact@oneskyapp.com"
        },
        "comment":"onesky is good",
        "status":"process",
        "blocks": [
            {
                "id":6789,
                "created_at":"2013-03-04T04:04:04+0000",
                "created_at_timestamp":1365066244,
                "category":"typo",
                "type":"string",
                "strings":"onesky is bad",
                "comment":"unacceptable typo mistake",
                "suggestion":"onesky is excellent",
                "status":"process",
                "translated_string":{
                    "id":12308,
                    "string":"onesky is great"
                }
            },
            {
                "id":7890,
                "created_at":"2013-03-03T03:03:03+0000",
                "created_at_timestamp":1362301383,
                "category":"format",
                "type":"non-textual",
                "index":2,
                "comment":"improper format",
                "suggestion":"shouldn't use underscore",
                "status":"new"
            },
            ...
        ]
    }
}
```
[Back to top](#feedback)


### Create - create a feedback
Returns the feedback's attributes.

    POST https://platform.api.onesky.io/1/feedbacks

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

<table>
    <tr>
        <td><strong>Name</strong></td>
        <td><strong>Required?</strong></td>
        <td><strong>Default</strong></td>
        <td><strong>Sample</strong></td>
        <td><strong>Description</strong></td>
    </tr>
    <tr>
        <td>url</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>url of the webpage</td>
    </tr>
    <tr>
        <td>locale</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Translated string language. Please refer to <a href="/resources/locales.md">GET locales</a></td>
    </tr>
    <tr>
        <td>screenshot</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>base64 encoded image content</td>
    </tr>
    <tr>
        <td>user_type</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Submitter user type, <code>user</code>, <code>employee</code> or <code>proofreader</code></td>
    </tr>
    <tr>
        <td>project</td>
        <td>optional</td>
        <td></td>
        <td></td>
        <td>The project that the feedback belongs to.</td>
    </tr>
    <tr>
        <td>email</td>
        <td>optional</td>
        <td></td>
        <td></td>
        <td>User email to reply.</td>
    </tr>
    <tr>
        <td>comment</td>
        <td>optional</td>
        <td></td>
        <td></td>
        <td>Comment on feedback</td>
    </tr>
    <tr>
        <td>blocks</td>
        <td>optional</td>
        <td></td>
        <td></td>
        <td>Blocks array to create</td>
    </tr>
</table>

**Response**

```
status 201 OK
```
[Back to top](#feedback)
