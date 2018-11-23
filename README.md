# OneSky Platform API

OneSky Platform API provides programmatic access to OneSky's platform management.

## The new API

This is new Platform API and is not compatible with the [Classic API](http://developer.oneskyapp.com/api). This new API covers most of the endpoints of classic API with numerous of new endpoints added and will continue to be actively developed going forward.

## Authentication

All of the endpoints require you to authenticate. You will have to find your own API key and API secret. First login to [OneSky](http://www.oneskyapp.com) and find the [API key](http://support.oneskyapp.com/hc/en-us/articles/206887797-How-to-find-your-API-keys-).

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
        <td>Your own API public key</td>
    </tr>
    <tr>
        <td><code>timestamp</code></td>
        <td>integer</td>
        <td>Current unix timestamp (GMT+0) in <a href="http://www.epochconverter.com/">seconds</a></td>
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
For more authentication error troubleshooting, please see this [article](https://support.oneskyapp.com/hc/en-us/articles/222464588-I-received-an-authentication-error-when-using-the-API).

## Resources

**Project**
- [**Project Group**](/resources/project_group.md) 
    -   LIST all project groups
    -   SHOW project group details
    -   CREATE a new project group
    -   DELETE a project group
    -   list enabled LANGUAGES 
- [**Project**](/resources/project.md) 
    - LIST projects of a project group
    - SHOW project details
    - CREATE a new project
    - UPDATE a project
    - DELETE a project
    - list LANGUAGES of a project 
- [**Project Type**](/resources/project_type.md)
    - LIST all project types

**String**
- [**File**](/resources/file.md) 
    - LIST uploaded files
    - UPLOAD a file 
    - DELETE a file
- [**Translation**](/resources/translation.md) 
    - EXPORT translations in files
    - export translations in MULTILINGUAL files
    - export translations of APP STORE Description
    - GET translation status
- [**Import Task**](/resources/import_task.md) 
    - LIST import tasks
    - SHOW import task
- [**Screenshot**](/resources/screenshot.md)
    - UPLOAD screenshots

**Order**
- [**Quotation**](/resources/quotation.md)
    - SHOW a quotation
- [**Order**](/resources/order.md) 
    - LIST all orders 
    - SHOW order details
    - CREATE an order

**Language**
- [**Locale**](/resources/locale.md) 
    - LIST all locales

## Wrappers
**PHP**
- [api-library-php5](https://github.com/onesky/api-library-php5) - OneSky

**PHP Symphony**
- [OneSkyBundle](https://github.com/OpenClassrooms/OneSkyBundle) - OpenClassrooms

**Python**
- [onesky-python](https://github.com/Jana-Mobile/onesky-python) - danob-jana

**Ruby**
- [onesky-ruby](https://github.com/onesky/onesky-ruby) - OneSky

**Rails**
- [onesky-rails](https://github.com/onesky/onesky-rails) - OneSky

**Grunt**
- [grunt-onesky-import](https://github.com/howardhenry/grunt-onesky-import) - howardhenry
- [grunt-onesky-export](https://github.com/howardhenry/grunt-onesky-export) - howardhenry

**Node.js**
- [nodejs-onesky-utils](https://github.com/brainly/nodejs-onesky-utils) - Brainly

**Go**
- [onesky-go](https://github.com/SebastianCzoch/onesky-go) - Sebastian Czoch

**C#**
- [OneSky.CSharp](https://github.com/QuadRatNewBy/OneSky.CSharp) - QuadRatNewBy

**.NET**
- [Sirius.OneSky](https://github.com/siriusch/Sirius.OneSky) - siriusch

**Elixir**
- [onesky.ex](https://github.com/ahtung/onesky.ex) - Ahtung
