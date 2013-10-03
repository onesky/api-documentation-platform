## Project Group
- [List project groups](#list---retireve-all-project-groups)
- [Show project group](#show---retireve-details-of-a-project-group)
- [Update project group](#update---update-details-of-a-project-group)
- [Delete project group](#delete---remove-a-project-group)


### List - retrieve all project groups

    GET https://platform.api.onesky.io/1/project-groups

**Authentication**

- Required. Details described [here](/README.md#authentication)

**Parameters**

<table>
    <tr>
        <td></td>
        <td>Required?</td>
        <td>Default</td>
        <td>Description</td>
    </tr>
    <tr>
        <td>page</td>
        <td>optional</td>
        <td>1</td>
        <td>set page number to retrieve</td>
    </tr>
    <tr>
        <td>per_page</td>
        <td>optional</td>
        <td>50</td>
        <td>set how many groups to retrieve for each time</td>
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
        "records_count": 2
    },
    "data": [
        {
            "id": 365
            "name": "Travel Magazine"
        },
        {
            "id": 366
            "name": "Fashion Magazine"
        }
    ]
}
```


### Show - retrieve details of a project group

    GET https://platform.api.onesky.io/1/project-groups/:project_group_id

**Authentication**

- Required. Details described [here](/README.md#authentication)

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
        "id": 365,
        "name": "Travel Magazine",
        "base_language": {
            "code": "en-US",
            "english_name": "English (United States)",
            "local_name": "English (United States)",
            "locale": "en",
            "region" : "US"
        },
        "enabled_languages_count": 3,
        "projects_count": 6
    }
}
```


### Create - create a new project group

    POST https://platform.api.onesky.io/1/project-groups

**Authentication**

- Required. Details described [here](/README.md#authentication)

**Parameters**

<table>
    <tr>
        <td></td>
        <td>Required?</td>
        <td>Default</td>
        <td>Description</td>
    </tr>
    <tr>
        <td>name</td>
        <td>required</td>
        <td></td>
        <td>name of the project group</td>
    </tr>
    <tr>
        <td>locale</td>
        <td>optional</td>
        <td>`en-US`</td>
        <td>base language of the project group. Please refer to [GET locales](/endpoints/locale/GET_locales.md)</td>
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
        "id": 8465,
        "name": "ABC Publications",
        "base_language": {
            "code": "en-US",
            "english_name": "English (United States)",
            "local_name": "English (United States)",
            "locale": "en",
            "region" : "US"
        }
    }
}
```


### Rename - update name of a project group

    PUT https://platform.api.onesky.io/1/project-groups/:project_group_id/rename

**Authentication**

- Required. Details described [here](/README.md#authentication)

**Parameters**

<table>
    <tr>
        <td></td>
        <td>Required?</td>
        <td>Default</td>
        <td>Description</td>
    </tr>
    <tr>
        <td>name</td>
        <td>required</td>
        <td></td>
        <td>new name of the project group</td>
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
    "data": {}
}
```


### Delete - remove a project group

    DELETE https://platform.api.onesky.io/1/project-groups/:project_group_id

**Authentication**

- Required. Details described [here](/README.md#authentication)

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
    "data": {}
}
```
