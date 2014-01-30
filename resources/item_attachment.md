## Item Attachment
Files attached to an item
- [List](#list---list-attachments-of-a-project)
- [Upload](#upload---upload-an-attachment)
- [Download](#download---download-an-attachment)
- [Delete](#delete---delete-an-attachment)
- [Attach](#attach---attach-to-an-item)


### List - list attachments of a project

    GET https://platform.api.onesky.io/1/projects/:project_id/item-attachments

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
        "record_count": 28
    },
    "data": [
        {
            "name": "q001-answer1.jpg",
            "uploaded_at": "2013-10-07T15:27:10+0000",
            "uploaded_at_timestamp": 1381159630
        },
        {
            "name": "q001-answer2.jpg",
            "uploaded_at": "2013-10-05T12:36:52+0000",
            "uploaded_at_timestamp": 1380976612
        },
        ...
    ]
}
```

[Back to top](#item-attachment)

### Upload - upload an attachment

    POST https://platform.api.onesky.io/1/projects/:project_id/item-attachments

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
        <td>File attached to an item</td>
    </tr>
    <tr>
        <td>item_key</td>
        <td>required</td>
        <td></td>
        <td><code>question_001</code></td>
        <td>Specify an item that file attach to</td>
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
        "status": 200
    },
    "data": {
        "name": "q001-answer1.jpg",
        "item_attached_to" :{
            "key": "question_001"
        },
        "uploaded_at": "2013-10-07T15:27:10+0000",
        "uploaded_at_timestamp": 1381159630
    }
}
```
Remark: Attachment name should be unique. If name of newly uploaded file is found, the previously uploaded file will be replaced.

[Back to top](#item-attachment)

### Download - download an attachment

    GET https://platform.api.onesky.io/1/projects/:project_id/item-attachments/download

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
        <td><code>q001-answer1.jpg</code></td>
        <td>Name of the attachment</td>
    </tr>
</table>

**Response**

```
status 200 OK
```
```
file
```

[Back to top](#item-attachment)

### Delete - delete an attachment

    Delete https://platform.api.onesky.io/1/projects/:project_id/item-attachments

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
        <td><code>q001-answer1.jpg</code></td>
        <td>Name of the attachment</td>
    </tr>
</table>

**Response**

```
status 200 OK
```

[Back to top](#item-attachment)

### Attach - attach to an item
Modify attachment to attach to another item within a project.

    POST https://platform.api.onesky.io/1/projects/:project_id/item-attachments/attach

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
        <td><code>q001-answer1.jpg</code></td>
        <td>Name of the attachment</td>
    </tr>
    <tr>
        <td>item_key</td>
        <td>required</td>
        <td></td>
        <td><code>question_001</code></td>
        <td>Specify an item to attach</td>
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
        "name": "q001-answer1.jpg",
        "item_attached_to" :{
            "key": "question_001"
        },
        "uploaded_at": "2013-10-07T15:27:10+0000",
        "uploaded_at_timestamp": 1381159630
    }
}
```

[Back to top](#item-attachment)
