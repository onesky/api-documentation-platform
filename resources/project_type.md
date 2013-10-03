## Project type
- [List](#list---list-all-project-types)


### List - list all project types

    GET https://platform.api.onesky.io/1/project-types

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
        "record_count": 10
    },
    "data": [
        {
            "code": "ios",
            "name": "iOS App"
        },
        {
            "code": "android",
            "name": "Android App"
        },
        {
            "code": "website",
            "name": "Website"
        },
        ...
    ]
}
```
[Back to top](#project-type)
