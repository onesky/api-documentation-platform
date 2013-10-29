## In-context Translation
- [Get Key String Pairs](#get-key-string-pairs---get-the-key-string-mapping)
- [Translate](#translate---create-a-translation-for-a-key-in-a-specified-language)
- [Post Comment](#post-comment---create-a-comment-for-a-key)
- [Vote] (#vote---vote-a-translation)
- [Finalize] (#finalize---finalize-a-translation)
- [Approve] (#approve---approve-a-translation)


### Get Key String Pairs - get the key string mapping

    POST https://platform.api.onesky.io/1/in_context/project/:project_id/key_string_pairs

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
        <td>keys</td>
        <td>required</td>
        <td></td>
        <td>["key1", "key2", "key3"]</td>
        <td>Keys of the key string mapping to get</td>
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
status 200 OK
```
``` json
{
    "meta": {
        "status": 200
    },
    "data": {
        "value1": "OneSky",
        "value2": "hi",
        "value3": "world",
        ...
    }
}
```

[Back to top](#in-context-translation)

### Translate - create a translation for a key in a specified language

    POST https://platform.api.onesky.io/1/in_context/project/:project_id/translate

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

NONE

[Back to top](#in-context-translation)

### Post Comment - create a comment for a key

    POST https://platform.api.onesky.io/1/in_context/project/:project_id/comment

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
        <td>The content of the comment. Simply a text comment to the translation.</td>
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

NONE

[Back to top](#in-context-translation)

### Vote - vote a translation

    POST https://platform.api.onesky.io/1/in_context/translations/:translation_id/vote

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

NONE

**Response**

NONE

[Back to top](#in-context-translation)

### Finalize - finalize a translation

    POST https://platform.api.onesky.io/1/in_context/translations/:translation_id/finalize

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

NONE

**Response**

NONE

[Back to top](#in-context-translation)

### Approve - approve a translation

    POST https://platform.api.onesky.io/1/in_context/translations/:translation_id/approve

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

NONE

**Response**

NONE

[Back to top](#in-context-translation)
