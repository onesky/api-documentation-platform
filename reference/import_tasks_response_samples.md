## Response samples of import tasks
- [List](#list---list-import-tasks)
- [Show](#show---show-an-import-task)

### List - list import tasks

**Import by files**
``` json
{
    "meta": {
        "status": 200
    },
    "data": [
        {
            "id": 177,
            "file": {
                "name": "string2.po"
            },
            "status": "in-progress",
            "created_at": "2013-10-07T15:25:00+0000",
            "created_at_timestamp": 1381159500
        },
        {
            "id": 176,
            "file": {
                "name": "string.po"
            },
            "status": "in-progress",
            "created_at": "2013-10-07T15:27:10+0000",
            "created_at_timestamp": 1381159630
        }
    ]
}
```

**Import by phrase collections**
``` json
{
    "meta": {
        "status": 200
    },
    "data": [
        {
            "id": 266,
            "collection_count": 5,
            "status": "in-progress",
            "created_at": "2013-10-07T15:25:00+0000",
            "created_at_timestamp": 1381159500
        },
        {
            "id": 265,
            "collection_count": 3,
            "status": "in-progress",
            "created_at": "2013-10-07T15:27:10+0000",
            "created_at_timestamp": 1381159630
        }
    ]
}
```

#### Show - show an import task

**Import by files**
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

**Import by phrase collections**
``` json
{
    "meta": {
        "status": 200
    },
    "data": {
        "id": 265,
        "collection_count": 3,
        "status": "in-progress",
        "created_at": "2013-10-07T15:27:10+0000",
        "created_at_timestamp": 1381159630
    }
}
```
