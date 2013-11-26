## Translation
- [List](#list---list-translations)
- [Export](#export---export-translations-into-files)


### List - list translations

    GET https://platform.api.onesky.io/1/projects/:project_id/translations

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
    "data": [
        {
            "locale": {
                "code": "en-US",
                "english_name": "English (United States)",
                "local_name": "English (United States)",
                "locale": "en",
                "region" : "US"
            },
            "progress": "100%",
            "word_count": 2549
        },
        {
            "locale": {
                "code": "ja-JP",
                "english_name": "Japanese",
                "local_name": "日本語",
                "locale": "ja",
                "region" : "JP"
            },
            "progress": "100%",
            "word_count": 3956
        },
        ...
    ]
}
```
[Back to top](#translation)


### Export - export translations into files
This action will create files from translations with specified locales and format. When translation file is ready, this action will simply response with the file.

You can add a header `If-Modified-Since` with the modified time of your downloaded copy of translation file.

Exmaple: `If-Modified-Since: 2013-10-07T15:27:10+0000`

Remark: This endpoint may have 5 minutes delay approximately. That means new translation will be updated to the file in 5 minutes.

    POST https://platform.api.onesky.io/1/projects/:project_id/translations/export

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
        <td>locale</td>
        <td>required</td>
        <td></td>
        <td><code>"zh-TW"</code></td>
        <td>Specify languages of translations to export. Please refer to <a href="/resources/locale.md">GET locales</a></td>
    </tr>
    <tr>
        <td>format</td>
        <td>required</td>
        <td></td>
        <td><code>IOS_STRINGS</code></td>
        <td>Specify the output format. Please refer to <a href="/reference/format.md">format list</a></td>
    </tr>
</table>

**Response**

When translation file is not ready. If the file is not processing, this will trigger the action to create file.
```
status 202 Accepted
```
***

When translation file is ready.
```
file
```
***

When your copy of translation file is up-to-date.
```
status 304 not modified
```

[Back to top](#translation)
