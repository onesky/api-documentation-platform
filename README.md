# OneSky Platform API

OneSky Platform API provides programmatic access to OneSky's platform management.

## Endpoints

#### Feedback Resources
- `GET`  [feedbacks](/resources/feedbacks/GET_feedbacks.md)
- `GET`  [feedbacks/:id](/resources/feedbacks/GET_feedbacks_id.md)
- `POST`  [feedbacks](/resources/feedbacks/POST_feedbacks.md)

## Authentication

All of the endpoints require you to do authentication. You will have to find your own API key and API secret. First login to [oneskyapp](http://www.oneksyapp.com) and find the API key and secret in **Site Settings** under **API Keys & Usage**.

#### Parameters
- string `api_key`
  > Your own API key

- int `timestamp`
  > Current unix timestamp

- string `dev_hash`
  > Calculate with `api_secret` and `timestamp`
  >
  > Formula: `md5(concatenate(<timestamp>, <api_secret>))`

## Request
We accept request data in JSON format. Please specify request header with `content-type: application/json` and encode the data in JSON format.

SSL is applied to protect all request data. Make sure you are using https to initiate request.

## Response
Successful request will response with either `200` or `201` status code togehter with response data if there is. When there is a new record created, `201 Created` will be used. Otherwise, `200 OK` will apply.

Failure request will response with an error status code together with an error message:
`{'code': 400, 'message': 'Your request cannot be processed'}`

Currently, we only support JSON data format in response.
