# Feedback Block Resources
    PUT feedback/:feedback_id/block/:id

## Description
Update a feedback block

## Requires authentication
- Details described [here](/README.md#authentication)

## Parameters
- `status`_(optional)_ - change feedback block status ([reference](/reference/feedback/block/status.md))
- `translated_string` _(optional) - translated string id in platform to associated with

## Example
**Request**

    PUT https://api.platform.onesky.io/1/feedback/:feedback_id/block/:id

**Response**
```
status 200 OK
```