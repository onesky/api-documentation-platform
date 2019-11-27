## Import Task
- [List](#list---list-import-tasks)
- [Show](#show---show-an-import-task)


### List - list import tasks

    GET https://platform.api.onesky.io/1/projects/:project_id/import-tasks

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
    <tr>
        <td>status</td>
        <td>optional</td>
        <td><code>all</code></td>
        <td><code>in-progress</code></td>
        <td>
            Filter to show only import tasks of specific status with one of the followings:
            <ul>
                <li><code>all</code> - All tasks</li>
                <li><code>completed</code> - Tasks imported successfully</li>
                <li><code>in-progress</code> - Tasks are being handling or waiting for others to finish</li>
                <li><code>failed</code> - Tasks failed while processing</li>
            </ul>
        </td>
    </tr>
</table>

**Response**

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
Remark:
- `status` can be either `completed`, `in-progress` or `failed`.
- Response may vary according to the way used to import strings. More response sample [here](/reference/import_tasks_response_samples.md#list---list-import-tasks).
- Import history is accessible up to one year.

[Back to top](#import-task)

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
Remark:
- `status` can be either `completed`, `in-progress` or `failed`.
- Response may vary according to the way used to import strings. More response sample [here](/reference/import_tasks_response_samples.md#show---show-an-import-task).
- Import history is accessible up to one year.

[Back to top](#import-task)
