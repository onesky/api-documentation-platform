# Feedback Resources
    GET feedback/:id

## Description
Returns the feedback's attributes.

## Requires authentication
- Details described [here](/README.md#authentication)

## Parameters
None

## Example
**Request**

    GET https://api.platform.onesky.io/1/feedback/:id

**Response**
``` json
{
    "feedback": {
        "id":"123",
        "created_at":"2013-03-03T03:03:03+0000",
        "created_at_timestamp":1328475945,
        "url":"http://www.oneskyapp.com",
        "locale":"ja_JP",
        "screenshot_url":"<screen shot url>",
        "submitter_user_type":"employee",
        "submitter_email":"contact@oneskyapp.com",
        "comment":"onesky is good",
        "status":"process",
        "blocks": [
            {"id":"1"},
            {"id":"2"}
        ]
    }
}
```