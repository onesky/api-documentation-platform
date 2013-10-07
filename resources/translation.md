## Translation
- [List](#list---list-translations)
- [Show export](#show---show-export-information-of-a-translation)
- [Export](#export---export-translations-into-files)
- [Download](#download---download-exported-translations)


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


### Show export - show export information of a translation

    GET https://platform.api.onesky.io/1/projects/:project_id/translations/export

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
        <td><code>zh-TW</code></td>
        <td>Specify language of translations. Please refer to <a href="/resources/locale.md">GET locales</a></td>
    </tr>
</table>

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
        "locale": {
            "code": "en-US",
            "english_name": "English (United States)",
            "local_name": "English (United States)",
            "locale": "en",
            "region" : "US"
        },
        "progress": "100%",
        "word_count": 2549,
        "formats" :[
            {
                "type": "IOS_STRINGS",
                "exported_at": "2013-10-07T15:26:32+0000",
                "exported_at_timestamp": 1381159592,
                "status": "up-to-date"
            },
            {
                "type": "ANDROID_XML",
                "exported_at": "2013-09-25T13:01:56+0000",
                "exported_at_timestamp": 1380114116,
                "status": "out-dated"
            },
            ...
        ]
    }
}
```
[Back to top](#translation)


### Export - export translations into files
This action will create files from translations with specified locales and format. Please check the status before downloading the files.

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
        <td>locales</td>
        <td>required</td>
        <td></td>
        <td><code>["en", "zh-TW", "de-DE"]</code></td>
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

```
status 200 OK
```
[Back to top](#translation)


### Download - download exported translations

    GET https://platform.api.onesky.io/1/projects/:project_id/translations/download

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
        <td>locales</td>
        <td>required</td>
        <td></td>
        <td><code>["en", "zh-TW", "de-DE"]</code></td>
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

```
File
```
[Back to top](#translation)
