## Item
- [List](#list---list-items)
- [Show](#show---show-an-item)
- [Create](#create---create-items)


### List - list items

    GET https://platform.api.onesky.io/1/projects/:project_id/items

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
        "record_count": 36
    },
    "data": [
        {
            "item_id": 1,
            "key": "question_001",
            "uploaded_at": "2013-10-07T15:27:10+0000",
            "uploaded_at_timestamp": 1381159630
        },
        {
            "item_id": 2,
            "key": "question_002",
            "uploaded_at": "2013-10-05T12:36:52+0000",
            "uploaded_at_timestamp": 1380976612
        },
        ...
    ]
}
```

[Back to top](#item)

### Show - show an item

    GET https://platform.api.onesky.io/1/projects/:project_id/items/:item_id

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
        "id": 1,
        "key": "question_001",
        "content": {
            "question_001": {
                "title": "Which name is correct team name in National Basketball Association (NBA)?",
                "answer1": "New York Bulls",
                "answer2": "Los Angeles Kings",
                "answer3": "Golden State Warriros",
                "answer4": "Huston Heat"
            }
        },
        "uploaded_at": "2013-10-07T15:27:10+0000",
        "uploaded_at_timestamp": 1381159630
    }
}
```

[Back to top](#item)

### Create - create items
Add or update strings as items.

    POST https://platform.api.onesky.io/1/projects/:project_id/items

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
        <td>items</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Specify strings in items. Format please refer to <a href="/references/item_format.md">Items format</a></td>
    </tr>
    <tr>
        <td>locale</td>
        <td>optional</td>
        <td>[base language]</td>
        <td><code>zh-TW</code></td>
        <td>Specify the input language. If locale is different from base language, the strings will add to translation strings. Please refer to <a href="/resources/locale.md">GET locales</a></td>
    </tr>
</table>

**Response**

```
status 201 Created
```
``` json
{
    "meta": {
        "status": 201
    },
    "data": {
        "language": {
            "code": "en-US",
            "english_name": "English (United States)",
            "local_name": "English (United States)",
            "locale": "en",
            "region" : "US"
        },
        "import": {
            "id": 154,
            "created_at": "2013-10-07T15:27:10+0000",
            "created_at_timestamp": 1381159630
        }
    }
}
```
Remark: After request made successfully, string import process will be performed in background. Please check the import status via [Import Task](/resources/import_task.md#show---show-an-import-task) endpoint by using the `import.id` provided.

[Back to top](#item)
