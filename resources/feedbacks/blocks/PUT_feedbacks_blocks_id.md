# Feedback Block Resources
    PUT feedbacks/:feedback_id/blocks/:id

## Description
Update a feedback block

## Requires authentication
- Details described [here](/README.md#authentication)

## Parameters
- `status`_(optional)_ - change feedback block status ([reference](/reference/feedbacks/blocks/status.md))
- `translated_string` _(optional) - translated string id in platform to associated with

## Example
**Request**

    PUT https://api.platform.onesky.io/1/feedbacks/:feedback_id/blocks/:id

**Response**
```
status 200 OK
```