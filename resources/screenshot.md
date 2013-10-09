## Screenshot
- [List](#list---list-project-screenshots)
- [Show](#show---show-a-screendshot-details)
- [Upload](#upload---upload-a-screenshot)
- [Delete](#delete---remove-a-screenshot)


### List - list project screenshots

    GET https://platform.api.onesky.io/1/projects/:project_id/screenshots

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

<table>
    <tr>
        <td><strong>Name</strong></td>
        <td><strong>Required?</strong></td>
        <td><strong>Default</strong></td>
        <td><strong>Sample</strong></td>
        <td><strong>Description</strong></td>
    </tr>
    <tr>
        <td>page</td>
        <td>optional</td>
        <td><code>1</code></td>
        <td></td>
        <td>Set page number to retrieve. (min: 1)</td>
    </tr>
    <tr>
        <td>per_page</td>
        <td>optional</td>
        <td><code>50</code></td>
        <td></td>
        <td>Set how many groups to retrieve for each time. (max: 100, min: 1)</td>
    </tr>
</table>

**Response**

```
status 200 OK
```
``` json
{
    "meta": {
        "status": 200,
        "record_count": 12
    },
    "data": [
        {
            "id": 295,
            "filename": "landing_page_02.png",
            "path": "/images/screenshots",
            "created_at": "2013-09-26T10:32:57+0000",
            "created_at_timestamp": 1380191577
        },
        {
            "id": 294,
            "filename": "landing_page_01.png",
            "path": "/images/screenshots",
            "created_at": "2013-09-26T10:30:27+0000",
            "created_at_timestamp": 1380191427
        },
        ...
    ]
}
```
[Back to top](#screenshot)


### Show - show a screenshot details

    GET https://platform.api.onesky.io/1/projects/:project_id/screenshots/:screenshot_id

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

NONE

**Response**

```
status 200 OK
```
``` json
{
    "meta": {
        "status": 200
    },
    "data": {
        "id": 294,
        "filename": "landing_page_01.png",
        "path": "/images/screenshots",
        "image": "<Base64 encoded image data>",
        "width": 1261,
        "height": 1918,
        "tags_count": 35,
        "created_at": "2013-09-26T10:30:27+0000",
        "created_at_timestamp": 1380191427,
    }
}
```
[Back to top](#screenshot)


### Upload - upload a screenshot

    POST https://platform.api.onesky.io/1/projects/:project_id/screenshots

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

<table>
    <tr>
        <td><strong>Name</strong></td>
        <td><strong>Required?</strong></td>
        <td><strong>Default</strong></td>
        <td><strong>Sample</strong></td>
        <td><strong>Description</strong></td>
    </tr>
    <tr>
        <td>screenshot</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Base64 encoded image data in Data URI scheme structure. Please reference to <a href="http://en.wikipedia.org/wiki/Data_URI_scheme">Data URI scheme</a> and <a href="http://en.wikipedia.org/wiki/Base64">Base64</a></td>
    </tr>
    <tr>
        <td>width</td>
        <td>required</td>
        <td></td>
        <td><code>1261</code></td>
        <td>Width of screenshot (in pixel)</td>
    </tr>
    <tr>
        <td>height</td>
        <td>required</td>
        <td></td>
        <td><code>1918</code></td>
        <td>Height of screenshot (in pixel)</td>
    </tr>
    <tr>
        <td>tags</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Translations bind to the screenshot. Please refer to [tags](/reference/tag.md)</td>
    </tr>
</table>

**Response**

```
status 200 OK
```
[Back to top](#screenshot)


- [Delete](#delete---remove-a-screenshot)
### Delete - remove a screenshot

    DELETE https://platform.api.onesky.io/1/projects/:project_id/screenshots/:screenshot_id

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

NONE

**Response**

```
status 200 OK
```
[Back to top](#screenshot)
