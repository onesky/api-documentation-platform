# Feedback Block Resources
    GET feedbacks/:feedback_id/blocks

## Description
Returns a listing of feedback blocks in the platform.

## Requires authentication
- Details described [here](/README.md#authentication)

## Parameters
- `page` _(optional)_ - page number for pagination, default 1.
- `per_page` _(optional)_ - items to be returned per page, default 15.
- `status` _(optional)_ - filter the list by feedback block status

## Example
**Request**

    GET https://api.platform.onesky.io/1/feedbacks/:feedback_id/blocks

**Response**
``` json
{
    "feedback_blocks": [
        {
            "id":6789,
            "created_at":"2013-03-03T03:03:03+0000",
            "created_at_timestamp":1362301383,
            "category":"typo",
            "type":"string",
            "strings":"onesky is bad",
            "comment":"unacceptable typo mistake",
            "suggestion":"onesky is excellent",
            "status":"progress"
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
            "ridx":"2",
            "comment":"improper format",
            "suggestion":"shouldn't use underscore",
            "status":"new"
        }
    ]
}
```