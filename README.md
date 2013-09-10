# OneSky Platform API

OneSky Platform API provides programmatic access to OneSky's platform management.

## Resources

#### Feedback Resources
- `GET`  [feedback]()
- `GET`  [feedback/:id]()
- `POST` [feedback]()
- `POST` [feedback/:id]()

#### Feedback Block Resources
- `GET`  [feedback/block]()
- `GET`  [feedback/block/:id]()
- `POST` [feedback/block]()
- `POST` [feedback/block/:id]()

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
