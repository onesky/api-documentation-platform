## Project
- [List](#list---list-projects-of-a-project-group)
- [Show](#show---retrieve-details-of-a-project)
- [Create](#create---create-a-new-project)
- [Update](#update---update-project)
- [Delete](#delete---remove-project)
- [Languages](#languages---list-languages-of-a-project)


### List - list projects of a project group

    GET https://platform.api.onesky.io/1/project-groups/:project_group_id/projects

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
        "record_count": 2
    },
    "data": [
        {
            "id": 6968,
            "name": "Company website"
        },
        {
            "id": 6969,
            "name": "Company blog"
        }
    ]
}
```
[Back to top](#project)


### Show - retrieve details of a project

    GET https://platform.api.onesky.io/1/projects/:project_id

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
        "id": 6968,
        "name": "Website",
        "description": "Words from company website.",
        "project_type": {
        	"code": "website",
        	"name": "Website"
        },
        "string_count": 1385,
        "word_count": 2956
    }
}
```
[Back to top](#project)


### Create - create a new project

    POST https://platform.api.onesky.io/1/project-groups/:project_group_id/projects

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
        <td>project_type</td>
        <td>required</td>
        <td></td>
        <td><code>website</code></td>
        <td>Please refer to <a href="/resources/project_type.md">GET project_type</a></td>
    </tr>
    <tr>
        <td>name</td>
        <td>optional</td>
        <td></td>
        <td></td>
        <td>Project name</td>
    </tr>
    <tr>
        <td>description</td>
        <td>optional</td>
        <td></td>
        <td></td>
        <td>Project description</td>
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
        "id": 10476,
        "project_type": {
        	"code": "website",
        	"name": "Website"
        },
        "name": "Website",
        "description": "Words from company website"
    }
}
```
[Back to top](#project)


### Update - update project

    PUT https://platform.api.onesky.io/1/projects/:project_id

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
        <td>optional</td>
        <td></td>
        <td></td>
        <td>New project name</td>
    </tr>
    <tr>
        <td>description</td>
        <td>optional</td>
        <td></td>
        <td></td>
        <td>New project description</td>
    </tr>
</table>

**Response**

```
status 200 OK
```
[Back to top](#project)


### Delete - remove project

    DELETE https://platform.api.onesky.io/1/projects/:project_id

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

NONE

**Response**

```
status 200 OK
```
[Back to top](#project)


### Languages - list languages of a project

    GET https://platform.api.onesky.io/1/projects/:project_id/languages

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
            "region": "US",
            "custom_locale" : "en-Custom",
            "is_base_language": true,
            "is_ready_to_publish": true,
            "translation_progress": "100%"
        },
        {
            "code": "ja-JP",
            "english_name": "Japanese",
            "local_name": "日本語",
            "locale": "ja",
            "region": "JP",
            "custom_locale" : "jp-Custom",
            "is_base_language": false,
            "is_ready_to_publish": true,
            "translation_progress": "98%"
        },
        {
            "code": "ko-KR",
            "english_name": "Korean",
            "local_name": "한국어",
            "locale": "ko",
            "region": "KR",
            "custom_locale" : null,
            "is_base_language": false,
            "is_ready_to_publish": true,
            "translation_progress": "56%"
        },
        ...
    ]
}
```
[Back to top](#project)
