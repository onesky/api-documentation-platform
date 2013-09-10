# Feedback Resources
    POST feedback/:id

## Description
Update a feedback

## Requires authentication
- Details described [here](/README.md#authentication)

## Parameters
- `status`_(optional)_ - change feedback status ([reference](/reference/feedback/status.md))

## Example
**Request**

    POST https://api.platform.onesky.io/1/project/:project_id/feedback/:id

**Response**
```
status 200 OK
```