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
            "created_at": "2013-10-07T15:27:10+0000",
            "created_at_timestamp": 1381159630
        },
        {
            "key": "question_002",
            "created_at": "2013-10-05T12:36:52+0000",
            "created_at_timestamp": 1380976612
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
                        "type": "absolute",
                        "value": 80,
                        "is_exceed_allowed": true
                    }
                },
                "answer1": {
                    "string": "New York Bulls",
                    "description": "New York Knicks, Chicago Bulls",
                    "length_limit": {
                        "type": "relative",
                        "value": 2,
                        "is_exceed_allowed": false
                    }
                },
                "answer2": {
                    "string": "Los Angeles Kings",
                    "description": "Los Angeles Lakers, Sacramento Kings",
                    "length_limit": {
                        "type": "relative",
                        "value": 2,
                        "is_exceed_allowed": false
                    }
                },
                "answer3": {
                    "string": "Golden State Warriros",
                    "description": "answer",
                    "length_limit": {
                        "type": "relative",
                        "value": 2,
                        "is_exceed_allowed": false
                    }
                },
                "answer4": {
                    "string": "Huston Heat",
                    "description": "Huston Rocket, Miami Heat",
                    "length_limit": {
                        "type": "relative",
                        "value": 2,
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
        "created_at": "2013-10-07T15:27:10+0000",
        "created_at_timestamp": 1381159630
    }
}
```

[Back to top](#item)

### Create - create items
Add or update (re-create) strings of base language as items.

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
        <td>is_keeping_all_strings</td>
        <td>optional</td>
        <td><code>true</code></td>
        <td></td>
        <td>Whether to deprecate strings within an previously created item that cannot be found in the re-creation of the item. For example, <code>item1</code> (already created) contains <code>string1</code> and <code>string2</code>. Re-create <code>item1</code> with <code>string2</code> and set <code>is_keeping_all_strings</code> to <code>false</code>. <code>string1</code> will be deprecated.</td>
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
        "import": {
            "id": 154,
            "created_at": "2013-10-07T15:27:10+0000",
            "created_at_timestamp": 1381159630
        }
    }
}
```
Remark: `import.id` is to retrieve the import status and there will be a new action to do so. We are working on it and will be available in the near future. Watch this repo to stay notice of any update.

[Back to top](#item)
