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
            "key": "question_001",
            "uploaded_at": "2013-10-07T15:27:10+0000",
            "uploaded_at_timestamp": 1381159630
        },
        {
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

    GET https://platform.api.onesky.io/1/projects/:project_id/items/show

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
        <td>item_key</td>
        <td>required</td>
        <td></td>
        <td><code>question_001</code></td>
        <td>Specify key of an item to show</td>
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
        "key": "question_001",
        "base_language": {
            "en": {
                "title": {
                    "string": "Which one is correct team name in National Basketball Association (NBA)?",
                    "description": "NBA basketball team name",
                    "length_limit": {
                        "absolute_char_count": 80,
                        "is_exceed_allowed": true
                    }
                },
                "answer1": {
                    "string": "New York Bulls",
                    "description": "New York Knicks, Chicago Bulls",
                    "length_limit": {
                        "relative_char_count": 2,
                        "is_exceed_allowed": false
                    }
                },
                "answer2": {
                    "string": "Los Angeles Kings",
                    "description": "Los Angeles Lakers, Sacramento Kings",
                    "length_limit": {
                        "relative_char_count": 2,
                        "is_exceed_allowed": false
                    }
                },
                "answer3": {
                    "string": "Golden State Warriros",
                    "description": "answer",
                    "length_limit": {
                        "relative_char_count": 2,
                        "is_exceed_allowed": false
                    }
                },
                "answer4": {
                    "string": "Huston Heat",
                    "description": "Huston Rocket, Miami Heat",
                    "length_limit": {
                        "relative_char_count": 2,
                        "is_exceed_allowed": false
                    }
                }
            }
        },
        "translations": {
            "zh-TW": {
                "title": "請選出正確的美國職業籃球聯賽球隊名稱",
                "answer1": "紐約公牛",
                "answer2": "洛杉磯帝王",
                "answer3": "金州勇士",
                "answer4": "休斯頓熱火"
            },
            "fr": {...},
            "de": {...},
            "jp": {...}
        },
        "attachments" : [
            {
                "name": "q001-answer1.jpg"
            },
            {
                "name": "q001-answer2.jpg"
            },
            ...
        ],
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
        <td>Specify strings in items. Format please refer to <a href="/reference/item_format.md">Items format</a></td>
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
