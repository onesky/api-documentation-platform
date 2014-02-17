## Import Task
- [Show](#show---show-an-import-task)


### Show - show an import task

    GET https://platform.api.onesky.io/1/projects/:project_id/import-tasks/:import_id

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

NONE

**Response**

``` json
{
    "meta": {
        "status": 200
    },
    "data": {
        "id": 176,
        "file": {
            "name": "string.po",
            "format": "GNU_PO",
            "locale": {
                "code": "en-US",
                "english_name": "English (United States)",
                "local_name": "English (United States)",
                "locale": "en",
                "region" : "US"
            }
        },
        "string_count": 236,
        "word_count": 1260,
        "status": "in-progress",
        "created_at": "2013-10-07T15:27:10+0000",
        "created_at_timestamp": 1381159630
    }
}
```
Remark: `status` can be either `completed`, `in-progress` or `failed`.

[Back to top](#import-task)
