# OneSky Platform API

OneSky Platform API provides programmatic access to OneSky's platform management.

## The new API

This is new Platform API and is not compatible with the [Classic API](http://developer.oneskyapp.com/api). This new API covers most of the endpoints of classic API with numerous of new endpoints added and will continue to be actively developed going forward.

## Resources

- [**Project Group**](/resources/project_group.md)
- [**Project**](/resources/project.md)
- [**File**](/resources/file.md)
- [**Translation**](/resources/translation.md)
- [**Import Task**](/resources/import_task.md)
- [**Quotation**](/resources/quotation.md)
- [**Order**](/resources/order.md)
- [**Screenshot**](/resources/screenshot.md)
- [**Locale**](/resources/locale.md)
- [**Project type**](/resources/project_type.md)
- [**Item**](/resources/item.md)

## Authentication

All of the endpoints require you to authenticate. You will have to find your own API key and API secret. First login to [oneskyapp](http://www.oneksyapp.com) and find the API key and secret in **Site Settings** under **API Keys & Usage**.

#### Parameters
<table>
    <tr>
        <td><strong>Name</strong></td>
        <td><strong>Type</strong></td>
        <td><strong>Description</strong></td>
    </tr>
    <tr>
        <td><code>api_key</code></td>
        <td>string</td>
        <td>Your own API key</td>
    </tr>
    <tr>
        <td><code>timestamp</code></td>
        <td>integer</td>
        <td>Current unix timestamp</td>
    </tr>
    <tr>
        <td><code>dev_hash</code></td>
        <td>string</td>
        <td>
            Calculate with <code>timestamp</code> and <code>api_secret</code>
            <br>
            Formula: <code>md5(concatenate(&lt;timestamp&gt;, &lt;api_secret&gt;))</code>
        </td>
    </tr>
</table>

## Request
We accept request data in JSON format. Please specify request header with `content-type: application/json` and encode the data in JSON format.

SSL is applied to protect all request data. Make sure you are using https to initiate request.

## Response

Response body will be in JSON format with 2 objects.
- `meta` contains the metadata of the response and additional information such as status code, total record count, paginations, etc...
- `data` contains the data from your request such as project information, file information, etc...

Currently, we only support JSON data format in response.

#### Success
Successful request will response with `2xx` status code together with response body if there is. Details of response body is shown at the bottom of each endpoints.

#### Failure
Failure request will response with an error status code together with an error message.

Example:
```
status 400 bad request
```
```json
{
  "meta": {
    "status": 400,
    "message": "Your request cannot be processed"
  },
  "data": {}
}
```


