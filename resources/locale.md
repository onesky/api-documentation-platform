## Locale
- [List](#list---list-all-locales)


### List - list all locales

    GET https://platform.api.onesky.io/1/locales

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
        "status": 200,
        "record_count": 102
    },
    "data": [
        {
            "code": "en-US",
            "english_name": "English (United States)",
            "local_name": "English (United States)",
            "locale": "en",
            "region" : "US"
        },
        {
            "code": "ja-JP",
            "english_name": "Japanese",
            "local_name": "日本語",
            "locale": "ja",
            "region" : "JP"
        },
        {
            "code": "ko-KR",
            "english_name": "Korean",
            "local_name": "한국어",
            "locale": "ko",
            "region" : "KR"
        },
        ...
    ]
}
```
[Back to top](#locale)
