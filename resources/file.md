## File
- [List](#list---list-uploaded-files)
- [Upload](#upload---upload-a-file)
- [Download](#download---download-a-file)
- [Delete](#delete---delete-a-file)
- [Rename](#rename---rename-a-file)


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
            "format": "GNU_PO",
            "strings_count": 936,
            "status": "in-progress",
            "uploaded_at": 2013-10-07T15:27:10+0000,
            "uploaded_at_timestamp": 1381159630
        },
        {
            "file_name": "en.yml",
            "format": "YAML",
            "strings_count": 835,
            "status": "imported"
            "uploaded_at": 2013-10-05T12:36:52+0000,
            "uploaded_at_timestamp": 1380976612
        },
        ...
    ]
}
```
[Back to top](#file)


### Upload - upload a file
Add or update strings with uploaded file.

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
        <td>format</td>
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
        <td>is_deprecate</td>
        <td>optional</td>
        <td><code>false</code></td>
        <td></td>
        <td>Deprecate strings that does not exist in uploaded file if set to TRUE. Otherwise, keep those strings unchanged.</td>
    </tr>
</table>

**Response**

```
status 201 Created
```
[Back to top](#file)


### Download - download a file

    GET https://platform.api.onesky.io/1/projects/:project_id/files/download

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
        <td></td>
        <td>Name of the file to download</td>
    </tr>
</table>

**Response**

```
File
```
[Back to top](#file)


### Delete - delete a file

    DELETE https://platform.api.onesky.io/1/projects/:project_id/files/delete

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
        <td></td>
        <td>Name of the file to remove</td>
    </tr>
</table>

**Response**

```
status 200 OK
```
[Back to top](#file)


### Rename - rename a file

    POST https://platform.api.onesky.io/1/projects/:project_id/files/rename

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
        <td></td>
        <td>Name of the file to rename</td>
    </tr>
    <tr>
        <td>new_name</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>New name of the file</td>
    </tr>
</table>

**Response**

```
status 200 OK
```
[Back to top](#file)
