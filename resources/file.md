## File
- [List](#list---list-uploaded-files)
- [Upload](#upload---upload-a-file)
- [Delete](#delete---delete-a-file)
- [Import status](#import-status---show-status-of-an-import-task)


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
            "file_name": "strings.po",
            "string_count": 236,
            "word_count": 1260,
            "import_status": "in-progress",
            "uploaded_at": "2013-10-07T15:27:10+0000",
            "uploaded_at_timestamp": 1381159630
        },
        {
            "file_name": "en.yml",
            "string_count": 335,
            "word_count": 1982,
            "import_status": "completed",
            "uploaded_at": "2013-10-05T12:36:52+0000",
            "uploaded_at_timestamp": 1380976612
        },
        ...
    ]
}
```
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
        "import_id": 154
    }
}
```
Remark: After string file uploaded, string import process will be performed in background. Please check the import status via [Import status](#import-status---show-status-of-an-import-task) endpoint by using the `import_id` provided.

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
[Back to top](#file)


### Import status - show status of an import task

    GET https://platform.api.onesky.io/1/projects/:project_id/files/import-status/:import_id

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
        "file_name": "en.yml",
        "string_count": 236,
        "word_count": 1260,
        "import_status": "in-progress",
        "imported_at": "2013-10-07T15:27:10+0000",
        "imported_at_timestamp": 1381159630
    }
}
```
Remark: `import_status` can be either `completed` or `in-progress`.

[Back to top](#file)
