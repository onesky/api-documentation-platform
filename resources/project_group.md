## Project Group
- [List](#list---retrieve-all-project-groups)
- [Show](#show---retrieve-details-of-a-project-group)
- [Create](#create---create-a-new-project-group)
- [Delete](#delete---remove-a-project-group)
- [Languages](#languages---list-enabled-languages-of-a-project-group)


### List - retrieve all project groups

    GET https://platform.api.onesky.io/1/project-groups

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
        "record_count": 65,
        "page_count": 3,
        "next_page": "http://platform.api.onesky.io/1/project-groups?per_page=25&page=3", *
        "prev_page": "http://platform.api.onesky.io/1/project-groups?per_page=25&page=1", *
        "first_page": "http://platform.api.onesky.io/1/project-groups?per_page=25&page=1", *
        "last_page": "http://platform.api.onesky.io/1/project-groups?per_page=25&page=3" *
    },
    "data": [
        {
            "id": 365,
            "name": "Travel Magazine"
        },
        {
            "id": 366,
            "name": "Fashion Magazine"
        },
        ...
    ]
}
```

\* Assume `page = 2` and `per_page = 25`

\* Note that `next_page`, `prev_page`, `first_page` and `last_page` can be `null`

[Back to top](#project-group)


### Show - retrieve details of a project group

    GET https://platform.api.onesky.io/1/project-groups/:project_group_id

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
        "id": 365,
        "name": "Travel Magazine",
        "base_language": {
            "code": "en-US",
            "english_name": "English (United States)",
            "local_name": "English (United States)",
            "locale": "en",
            "region" : "US"
        },
        "enabled_language_count": 3,
        "project_count": 6
    }
}
```
[Back to top](#project-group)


### Create - create a new project group

    POST https://platform.api.onesky.io/1/project-groups

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
        <td>name</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Name of the project group</td>
    </tr>
    <tr>
        <td>locale</td>
        <td>optional</td>
        <td><code>en</code></td>
        <td><code>zh-TW</code></td>
        <td>Locale code of the project group base language. Please refer to <a href="/resources/locales.md">GET locales</a></td>
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
[Back to top](#project-group)


### Delete - remove a project group

    DELETE https://platform.api.onesky.io/1/project-groups/:project_group_id

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

NONE

**Response**

```
status 200 OK
```
[Back to top](#project-group)


### Languages - list enabled languages of a project group

    GET https://platform.api.onesky.io/1/project-groups/:project_group_id/languages

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
        "record_count": 3
    },
    "data": [
        {
            "code": "en-US",
            "english_name": "English (United States)",
            "local_name": "English (United States)",
            "locale": "en",
            "region" : "US",
            "is_base_language": true
        },
        {
            "code": "ja-JP",
            "english_name": "Japanese",
            "local_name": "日本語",
            "locale": "ja",
            "region" : "JP",
            "is_base_language": false
        },
        {
            "code": "ko-KR",
            "english_name": "Korean",
            "local_name": "한국어",
            "locale": "ko",
            "region" : "KR",
            "is_base_language": false
        },
        ...
    ]
}
```
[Back to top](#project-group)
