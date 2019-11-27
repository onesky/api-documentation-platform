## File
- [List](#list---list-uploaded-files)
- [Upload](#upload---upload-a-file)
- [Delete](#delete---delete-a-file)


### List - list uploaded files

    GET https://platform.api.onesky.io/1/projects/:project_id/files

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
        "record_count": 16
    },
    "data": [
        {
            "name": "strings.po",
            "string_count": 236,
            "last_import": {
                "id": 123,
                "status": "in-progress"
            },
            "uploaded_at": "2013-10-07T15:27:10+0000",
            "uploaded_at_timestamp": 1381159630
        },
        {
            "name": "en.yml",
            "string_count": 335,
            "last_import": {
                "id": 109,
                "status": "completed"
            },
            "uploaded_at": "2013-10-05T12:36:52+0000",
            "uploaded_at_timestamp": 1380976612
        },
        {
            "name": "Manually input",
            "string_count": 285,
        },
        ...
    ]
}
```
Remark:
- `status` can be either `completed`, `in-progress` or `failed`.
- Manual input strings will display as a separate file with no `last_import`, `uploaded_at` and `uploaded_at_timestamp`.
- Import history is accessible up to one year. For files imported longer than one year ago, `id`  will display as `0` and `status` will display as `completed`.

[Back to top](#file)

### Upload - upload a file
Add or update strings by file.

    POST https://platform.api.onesky.io/1/projects/:project_id/files

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
        <td>file</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>File contains strings to translate</td>
    </tr>
    <tr>
        <td>file_format</td>
        <td>required</td>
        <td></td>
        <td><code>IOS_STRINGS</code></td>
        <td>Specify the input format. Please refer to <a href="/reference/format.md">format list</a></td>
    </tr>
    <tr>
        <td>locale</td>
        <td>optional</td>
        <td>[base language]</td>
        <td><code>zh-TW</code></td>
        <td>Specify the input language. If locale is different from base language, the strings will add to translation strings. Please refer to <a href="/resources/locale.md">GET locales</a></td>
    </tr>
    <tr>
        <td>is_keeping_all_strings</td>
        <td>optional</td>
        <td><code>true</code></td>
        <td></td>
        <td>For strings that cannot be found in newly uploaded file with same file name, keep those strings unchange if set to <code>true</code>. Deprecate those strings if set to <code>false</code>. Notice that different files will not interfere each other in the same project. For example, with setting <code>is_keeping_all_strings</code> to <code>false</code>, uploading <code>en2.po</code> will not deprecate strings of previously uploaded file, <code>en.po</code>.</td>
    </tr>
    <tr>
        <td>is_allow_translation_same_as_original</td>
        <td>optional</td>
        <td><code>false</code></td>
        <td></td>
        <td>This setting applies to translation upload, skip importing translations that are the same as source text if set to <code>false</code>. Keeping the translations that are the same as source text if set to <code>true</code>.</td>
    </tr>
</table>

**Request**

Since this endpoint required to upload file, please use `Content-Type: multipart/form-data` for the request and submit the request like a form data.

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
        "name": "string.po",
        "format": "GNU_PO",
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
Remark: After string file uploaded, string import process will be performed in background. Please check the import status via [Import Task](/resources/import_task.md#show---show-an-import-task) endpoint by using the `import.id` provided.

[Back to top](#file)


### Delete - delete a file

    DELETE https://platform.api.onesky.io/1/projects/:project_id/files

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
        <td>file_name</td>
        <td>required</td>
        <td></td>
        <td><code>string.po</code></td>
        <td>Specify name of file to delete.</td>
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
        "name": "string.po"
    }
}
```
[Back to top](#file)
