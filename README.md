# OneSky Platform API

OneSky Platform API provides programmatic access to OneSky's platform management.

## Resources

- [**Project Group**](/resources/project_group.md)
- [**Project**](/resources/project.md)
- [**File**](/resources/file.md)
- [**Translation**](/resources/translation.md)
- [**Screenshot**](/resources/screenshot.md)
- [**Feedback**](/resources/feedback.md)
- [**Locale**](/resources/locale.md)
- [**Project type**](/resources/project_type.md)

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
```
{
  'meta': {
    'status': 400,
    'message': 'Your request cannot be processed'
  },
  'data': {}
}
```

Currently, we only support JSON data format in response.
