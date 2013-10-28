## In-context Translation
- [Translate](#translate---create-a-translation-for-a-key-in-a-specified-language)
- [Post Comment](#post-comment---create-a-comment-for-a-key)
- [Vote] (#vote---vote-a-translation)
- [Finalize] (#finalize---finalize-a-translation)
- [Approve] (#approve---approve-a-translation)


### Translate - create a translation for a key in a specified language

    POST https://platform.api.onesky.io/1/in-context/project/:project_id/translate

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
        <td>locale</td>
        <td>required</td>
        <td>en</td>
        <td>en-US</td>
        <td>The locale of the translation result</td>
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
    }
}
```

[Back to top](#-In-context-Translation)

## Post Comment - create a comment for a key

    POST https://platform.api.onesky.io/1/in-context/project/:project_id/comment

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
        <td>Key of the string to comment</td>
    </tr>
    <tr>
        <td>content</td>
        <td>required</td>
        <td></td>
        <td>This translation is true to the original</td>
        <td>The comment content</td>
    </tr>
    <tr>
        <td>locale</td>
        <td>required</td>
        <td>en</td>
        <td>en-US</td>
        <td>The locale of the comment</td>
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
    }
}
```
[Back to top](#-In-context-Translation)

## Vote - vote a translation

    POST https://platform.api.onesky.io/1/in-context/translations/:translation_id/vote

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
        <td>translation-id</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>The Id of the translation</td>
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
    }
}
```
[Back to top](#-In-context-Translation)

## Finalize - finalize a translation

    POST https://platform.api.onesky.io/1/in-context/translations/:translation_id/finalize

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
        <td>translation-id</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>The Id of the translation</td>
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
    }
}
```
[Back to top](#-In-context-Translation)

## Approve - approve a translation

    POST https://platform.api.onesky.io/1/in-context/translations/:translation_id/approve

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
        <td>translation-id</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>The Id of the translation</td>
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
    }
}
```
[Back to top](#-In-context-Translation)
