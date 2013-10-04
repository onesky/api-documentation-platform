## File
- [List](#list---list-uploaded-files)
- [Upload](#upload---upload-a-file)
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
        <td><strong>Description</strong></td>
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
        "record_count": 16
    },
    "data": [
        {
            "id": 639,
            "file_name": "strings.po",
            "version": 2,
            "strings_count": 936,
            "status": "in-progress"
        },
        {
            "id": 638,
            "file_name": "strings.po",
            "version": 1,
            "strings_count": 910,
            "status": "imported"
        },
        {
            "id": 637,
            "file_name": "en.yml",
            "version": 1,
            "strings_count": 835,
            "status": "imported"
        },
        ...
    ]
}
```
[Back to top](#file)


### Upload - upload a file

    POST https://platform.api.onesky.io/1/projects/:project_id/files

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

<table>
    <tr>
        <td><strong>Name</strong></td>
        <td><strong>Required?</strong></td>
        <td><strong>Default</strong></td>
        <td><strong>Description</strong></td>
    </tr>
    <tr>
        <td>file</td>
        <td>required</td>
        <td></td>
        <td>File contains strings to translate</td>
    </tr>
    <tr>
        <td>file_type</td>
        <td>required</td>
        <td></td>
        <td>
            Specify the file type
            <br>
            File type can be one of the following:
            <ul>
                <li>IOS_STRINGS</li>
                <li>GNU_PO</li>
                <li>ANDROID_XML</li>
                <li>ANDROID_JSON</li>
                <li>JAVA_PROPERTIES</li>
                <li>RUBY_YML</li>
                <li>RUBY_YAML</li>
                <li>FLASH_XML</li>
                <li>GNU_POT</li>
                <li>RRC</li>
                <li>RESX</li>
                <li>RESJSON</li>
                <li>HIERARCHICAL_JSON</li>
                <li>PHP</li>
                <li>PHP_VARIABLES</li>
                <li>HTML</li>
                <li>RESW</li>
                <li>YML</li>
                <li>YAML</li>
                <li>ADEMPIERE_XML</li>
                <li>QT_TS_XML</li>
                <li>TMX</li>
                <li>L10N</li>
                <li>INI</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>version</td>
        <td>optional</td>
        <td>[current version]</td>
        <td>Specify the target version of the project</td>
    </tr>
    <tr>
        <td>locale</td>
        <td>optional</td>
        <td>[base language]</td>
        <td>Specify the locale of the strings. If locale is different from base language, the strings will add to translation strings.</td>
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
        "id": 737,
        "file_name": "strings.po",
        "version": 1,
        "status": "in-progress"
    }
}
```
[Back to top](#file)


### Delete - delete a file

    DELETE https://platform.api.onesky.io/1/projects/:project_id/files/:file_id

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

NONE

**Response**

```
status 200 OK
```
[Back to top](#file)


### Rename - rename a file

    POST https://platform.api.onesky.io/1/projects/:project_id/files/:file_id

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

<table>
    <tr>
        <td><strong>Name</strong></td>
        <td><strong>Required?</strong></td>
        <td><strong>Default</strong></td>
        <td><strong>Description</strong></td>
    </tr>
    <tr>
        <td>name</td>
        <td>required</td>
        <td></td>
        <td>New name of the file</td>
    </tr>
</table>

**Response**

```
status 200 OK
```
[Back to top](#file)
