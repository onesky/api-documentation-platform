## Project Group
- [Translate](#translate---create-a-translation-for-a-key-in-a-specified-language)
- [Post Comment](#comment---create-a-comment-for-a-key)
- [Add heart] (#add-heart---add-a-heart-to-a-translation)
- [Finalize] (#finalize---finalize-a-translation)
- [Approve] (#approve---approve-a-translation)


### Translate - create a translation for a key in a specified language

    GET https://platform.api.onesky.io/1/in-context/translate

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

## Post Comment - create  a comment for a key

    POST https://platform.api.onesky.io/1/in-context/comment

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

## Add heart - add a heart to a translation

    POST https://platform.api.onesky.io/1/in-context/add-heart

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
    }
}
```
[Back to top](#project-group)

## Finalize - finalize a translation

    POST https://platform.api.onesky.io/1/in-context/finalize

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
    }
}
```
[Back to top](#project-group)

## Approve - approve a translation

    POST https://platform.api.onesky.io/1/in-context/approve

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
    }
}
```
[Back to top](#project-group)
