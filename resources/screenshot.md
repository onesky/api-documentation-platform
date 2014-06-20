## Screenshot
- [Upload](#upload---upload-a-screenshot)
- [Grouping](#grouping---group-related-strings-of-same-screenshot)


### Upload - upload a screenshot

    POST https://platform.api.onesky.io/1/projects/:project_id/screenshots

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
        <td>screenshots</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Please refer to <a href="/reference/screenshot.md">screenshots</a></td>
    </tr>
</table>

**Response**

```
status 201 Created
```
[Back to top](#screenshot)


### Grouping - group related strings of same screenshot

    POST https://platform.api.onesky.io/1/projects/:project_id/screenshots/grouping

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
        <td>groupings</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Please refer to <a href="/reference/grouping.md">groupings</a></td>
    </tr>
</table>

**Response**

```
status 201 Created
```
[Back to top](#screenshot)
