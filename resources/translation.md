## Translation
- [Export](#export---export-translations-in-files)
- [Export Multilingual File](#export-multilingual-file---export-translations-in-multilingual-files)
- [App Description](#app-description---export-translations-of-app-store-description-in-json)
- [Status](#status---translations-status)


### Export - export translations in files
This action will create files from translations with specified locale. When translation file is ready, this action will simply response with the file.

    GET https://platform.api.onesky.io/1/projects/:project_id/translations

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

Name | Required? | Default | Sample | Description
---- | --------- | ------- | ------ | -----------
locale | required | | `zh-TW` | Specify language of translations to export. Please refer to [GET locales](/resources/locale.md).
source_file_name | required | | `string.po` | Specify the name of the source file.
export_file_name | optional | *`string_zh-TW.po` | `zh-TW.po` | Specify the name of export file that is the file to be returned.

*Assume `locale = "zh-TW"` and `source_file_name = "string.po"`

**Response**

When translation file is not ready. If the file is not processing, this will trigger the action to create file.
```
status 202 Accepted
```

When no string is ready in the file.
```
status 204 No content
```

When translation file is ready.
```
file
```
[Back to top](#translation)

### Export Multilingual File - Export Translations in Multilingual Files
This action will create files from translations of specified file. When translation file is ready, this action will simply response with the file. Currently supported format is `I18NEXT_MULTILINGUAL_JSON`.

    GET https://platform.api.onesky.io/1/projects/:project_id/translations/multilingual

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

Name | Required? | Default | Sample | Description
---- | --------- | ------- | ------ | -----------
source_file_name | required | | `app.json` | Specify the name of the source file.
export_file_name | optional | \*`app.json` | `string.json` | Specify the name of export file that is the file to be returned.
file_format | optional | | `I18NEXT_MULTILINGUAL_JSON` | Specify export file format, if different from source file format.<br />**Recommend only convert from** `I18NEXT_HIERARCHICAL_JSON`**.**

*Assume `source_file_name = "app.json"`

**Response**

When translation file is not ready. If the file is not processing, this will trigger the action to create file.
```
status 202 Accepted
```

When no string is ready in the file.
```
status 204 No content
```

When translation file is ready.
```
file
```
[Back to top](#translation)


### App Description - export translations of App Store Description in JSON
This action is available for project of App Store Description and will export translations with specified locale in JSON format.

    GET https://platform.api.onesky.io/1/projects/:project_id/translations/app-descriptions

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

Name | Required? | Default | Sample | Description
---- | --------- | ------- | ------ | -----------
locale | required | | `zh-TW` | Specify language of translations to export. Please refer to [GET locales](/resources/locale.md).

**Response**
```
status 200 OK
```
``` json
{
    "meta": {
        "status": 200,
        "language": {
            "code": "en-US",
            "english_name": "English (United States)",
            "local_name": "English (United States)",
            "locale": "en",
            "region" : "US"
        }
    },
    "data": {
        "APP_NAME": "My App Name",
        "TITLE": "App title",
        "DESCRIPTION": "App description",
        "APP_KEYWORD": {
            "popular app": "popular app"
        },
        "APP_IAP_NAME": {
            "iap_product1": "Product 1",
            "iap_product2": "Product 2"
        },
        "APP_IAP_DESCRIPTION": {
            "iap_product1": "Product 1 description",
            "iap_product2": "Product 2 description"
        }
    }
}
```
[Back to top](#translation)


### Status - translations status
Return the progress of the translation of a speicfic file.

    GET https://platform.api.onesky.io/1/projects/:project_id/translations/status

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

Name | Required? | Default | Sample | Description
---- | --------- | ------- | ------ | -----------
file_name | required | | `string.po` | Specify the name of the source file to be translated.
locale | required | | `zh-TW` | Specify language of translation. Please refer to [GET locales](/resources/locale.md).

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
        "file_name": "string.po",
        "locale": {
            "code": "ja-JP",
            "english_name": "Japanese",
            "local_name": "日本語",
            "locale": "ja",
            "region" : "JP"
        },
        "progress": "92%",
        "string_count": 1359,
        "word_count": 3956
    }
}
```
[Back to top](#translation)
