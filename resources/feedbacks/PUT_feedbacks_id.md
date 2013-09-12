# Feedback Resources
    PUT feedbacks/:id

## Description
Update a feedback

## Requires authentication
- Details described [here](/README.md#authentication)

## Parameters
- `status` _(optional)_ - change feedback status ([reference](/reference/feedbacks/status.md))

## Example
**Request**

    PUT https://api.platform.onesky.io/1/feedbacks/:id

**Response**
```
status 200 OK
```