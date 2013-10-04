## String
- [List](#list---list-all-strings)


### List - list all strings

    GET https://platform.api.onesky.io/1/projects/:project_id/strings

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
        "record_count": 1746
    },
    "data": [
        {
            "id": 10353,
            "key": "message.order.create.success",
            "description": "dialog message shown after order created",
            "word_count": 12,
            "char_count": 46,
            "status": "normal"
        },
        {
            "id": 10352,
            "key": "message.order.create.fail",
            "description": "dialog message shown after order created",
            "word_count": 16,
            "char_count": 58,
            "status": "hidden"
        },
        ...
    ]
}
```
[Back to top](#string)
