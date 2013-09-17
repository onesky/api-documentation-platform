# Feedback Resources
    GET feedbacks/:id

## Description
Returns the feedback's attributes.

## Requires authentication
- Details described [here](/README.md#authentication)

## Parameters
None

## Example
**Request**

    GET https://api.platform.onesky.io/1/feedbacks/:id

**Response**
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
                "index":"2",
                "comment":"improper format",
                "suggestion":"shouldn't use underscore",
                "status":"new"
            }
        ]
    }
}
```
