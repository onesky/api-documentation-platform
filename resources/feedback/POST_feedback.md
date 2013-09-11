# Feedback Resources
    POST feedback

## Description
Create a feedback

## Requires authentication
- Details described [here](/README.md#authentication)

## Parameters
- `url` _(required)_ - url of the webpage
- `locale` _(required)_ - translated string language
- `screenshot` _(required)_ - base64 encoded image content
- `user_type` _(required)_ - submitter user type, `user`, `employee` or `proofreader`
- `project` -(optional)_ - the project belongs to
- `email` _(optional)_ -  user email to reply
- `comment` _(optional)_ - comment on feedback

## Example
**Request**

    POST https://api.platform.onesky.io/1/feedback

**Response**
```
status 201 Created
```