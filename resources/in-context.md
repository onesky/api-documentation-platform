## Project Group
- [Translate](#translate---translate-a-string-by-key)
- [List Translations](#translate---translate-a-string-by-key)
- [List Comment](#list---list-all-comment-for-a-string)
- [Post Comment](#list---list-all-comment-for-a-string)



### Translate - create a translation for a key in a specified language

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
        <td>key</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Key of the string to translate</td>
    </tr>
    <tr>
        <td>translation</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>The translation of the string which specified by key</td>
    </tr>
    <tr>
        <td>language-code</td>
        <td>required</td>
        <td></td>
        <td>en-US</td>
        <td>The language code of the translation result</td>
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
    }
}
```

[Back to top](#project-group)

### List Translations- retrieve all project groups

    GET https://platform.api.onesky.io/1/in-context/comments

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
        <td>key</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Set page number to retrieve. (min: 1)</td>
    </tr>
    <tr>
        <td>language-code</td>
        <td>required</td>
        <td></td>
        <td>en-US</td>
        <td>The language code of the translation result</td>
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
        <td><code>10</code></td>
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
        "record_count": 2
    },
    "data": [
        {
            "id": 365,
            "content": "Travel Magazine",
            "name": "Anthony"
        },
        {
            "id": 366,
            "content": "Fashion Magazine",
            "name": "Anthony"
        }
    ]
}
```
[Back to top](#project-group)

### List Comments- retrieve all project groups

    GET https://platform.api.onesky.io/1/in-context/comments

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
        <td>key</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Set page number to retrieve. (min: 1)</td>
    </tr>
    <tr>
        <td>language-code</td>
        <td>required</td>
        <td></td>
        <td>en-US</td>
        <td>The language code of the translation result</td>
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
        <td><code>10</code></td>
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
        "record_count": 2
    },
    "data": [
        {
            "id": 365,
            "content": "Travel Magazine",
            "name": "Anthony"
        },
        {
            "id": 366,
            "content": "Fashion Magazine",
            "name": "Anthony"
        }
    ]
}
```
[Back to top](#project-group)

## Post Comment- retrieve all project groups

    POST https://platform.api.onesky.io/1/in-context/comments

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
        <td>key</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Set page number to retrieve. (min: 1)</td>
    </tr>
    <tr>
        <td>content</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>The comment to the string</td>
    </tr>
    <tr>
        <td>language-code</td>
        <td>required</td>
        <td></td>
        <td>en-US</td>
        <td>The language code of the translation result</td>
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
    }
}
```
[Back to top](#project-group)
