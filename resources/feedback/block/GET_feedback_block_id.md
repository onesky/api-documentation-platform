# Feedback Block Resources
    GET feedback/:feedback_id/block

## Description
Returns the feedback block's attributes.

## Requires authentication
- Details described [here](/README.md#authentication)

## Parameters
None

## Example
**Request**

    GET https://api.platform.onesky.io/1/feedback/:feedback_id/block/:id

**Response**
``` json
{
    "feedback_block": {
        "id":"6789",
        "created_at":"2013-03-04T04:04:04+0000",
        "created_at_timestamp":1365066244,
        "category":"typo",
        "type":"string",
        "strings":"onesky is bad",
        "comment":"unacceptable typo mistake",
        "suggestion":"onesky is excellent"
        "status":"process"
    }
}
```