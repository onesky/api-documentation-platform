# OneSky Platform API

OneSky Platform API provides programmatic access to OneSky's platform management.

## Resources

#### Feedback Resources
- `GET`  [feedback](/resources/feedback.md#list-of-feedbacks)
- `GET`  [feedback/:id](/resources/feedback.md#feedback)
- `POST` [feedback](/resources/feedback.md#create-feedback)
- `POST` [feedback/:id](/resources/feedback.md#update-feedback)

#### Feedback Block Resources
- `GET`  [feedback/block](/resources/feedback_block.md#list-of-feedback-blocks)
- `GET`  [feedback/block/:id](/resources/feedback_block.md#feedback-blocks)
- `POST` [feedback/block](/resources/feedback_block.md#create-feedback-blocks)
- `POST` [feedback/block/:id](/resources/feedback_block.md#update-feedback-blocks)

## Authentication

All of the request require you to do authentication. Please refer [Authenticaion](/reference/authentication.md) page.

## Sorting

Sorting of list request. Please refer [Sorting](/reference/sorting.md) page.

## Pagination

Pagination of list request. Please refer [Pagination](/reference/pagination.md) page.

## Request
We accept request data in JSON format. Please specify request header with `content-type: application/json` and encode the data in JSON format.

SSL is applied to protect all request data. Make sure you are using https to initiate request.

## Response
Successful request will response with either `200` or `201` status code togehter with response data if there is. When there is a new record created, `201 Created` will be used. Otherwise, `200 OK` will apply.

Failure request will response with an error status code together with an error message:
`{'code': 400, 'message': 'Your request cannot be processed'}`

Currently, we only support JSON data format in response.
