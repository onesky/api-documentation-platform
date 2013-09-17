# Feedback Resources
    GET feedbacks

## Description
Returns a listing of feedbacks in the platform.

## Requires authentication
- Details described [here](/README.md#authentication)

## Parameters
- `page` _(optional)_ - page number for pagination, default 1.
- `per_page` _(optional)_ - items to be returned per page, default 15.
- `project` _(optional)_ - filter the list by project which the feedback belongs to
- `locale` _(optional)_ - filter the list by locale

## Example
**Request**

    GET https://api.platform.onesky.io/1/feedbacks

**Response**
``` json
{
    "feedbacks": [
        {
            "id":"123",
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
                    "index":"2",
                    "comment":"improper format",
                    "suggestion":"shouldn't use underscore",
                    "status":"new"
                }
            ]
        },
        {
            "id":"456",
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
                }
            ]
        }
    ]
}
```
