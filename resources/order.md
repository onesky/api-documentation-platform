## Order
- [List](#list---retrieve-all-orders)
- [Show](#show---retrieve-details-of-an-order)
- [Create](#create---create-a-new-order)


### List - retrieve all orders

    GET https://platform.api.onesky.io/1/projects/:project_id/orders

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
        "record_count": 26
    },
    "data": [
        {
            "id": 123,
            "amount": "358.00",
            "ordered_at": "2013-08-15T08:12:40+0000",
            "ordered_at_timestamp":13283746583
        },
        {
            "id": 122,
            "amount": "1593.50",
            "ordered_at": "2013-08-15T08:12:40+0000",
            "ordered_at_timestamp":13283746583
        },
        ...
    ]
}
```
[Back to top](#order)


### Show - retrieve details of an order

    GET https://platform.api.onesky.io/1/projects/:project_id/orders/:order_id

**Authentication**

Required. Details described [here](/README.md#authentication)

**Parameters**

NONE

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
        "id": 123,
        "amount": "695.00",
        "files": [
            {
                "name": "string.po"
            },
            {
                "name": "string2.po"
            },
            ...
        ],
        "from_language": {
            "code": "en-US",
            "english_name": "English (United States)",
            "local_name": "English (United States)",
            "locale": "en",
            "region" : "US"
        },
        "tasks": [
            {
                "status": "completed",
                "to_language": {
                    "code": "ko-KR",
                    "english_name": "Korean",
                    "local_name": "한국어",
                    "locale": "ko",
                    "region" : "KR"
                },
                "translator":{
                    "name": "Jinny O."
                },
                "completed_at": "2013-08-17T13:05:20+0000",
                "completed_at_timestamp": 1376744720
            },
            ...
        ],
        "order_type": "translate-only",
        "is_including_not_translated": true,
        "is_including_not_approved": false,
        "is_including_outdated": true,
        "tone": "formal",
        "specialization": "general",
        "note": "Message to translator",
        "ordered_at": "2013-08-15T08:12:40+0000",
        "ordered_at_timestamp":13283746583
    }
}
```
Remark: `status` can be either `completed` or `in-progress`.

[Back to top](#order)


### Create - create a new order

    POST https://platform.api.onesky.io/1/projects/:project_id/orders

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
        <td>files</td>
        <td>required</td>
        <td></td>
        <td><code>['string.po', 'string2.po']</code></td>
        <td>Files to be translated in the order</td>
    </tr>
    <tr>
        <td>to_locale</td>
        <td>required</td>
        <td></td>
        <td><code>zh-TW</code></td>
        <td>Target language to tranlate. Please refer to <a href="/resources/locales.md">GET locales</a></td>
    </tr>
    <tr>
        <td>order_type</td>
        <td>optional</td>
        <td><code>translate-only</code></td>
        <td><code>review-only</code></td>
        <td>
            Specify type of order.
            <br>
            Types:
            <ul>
                <li><code>translate-only</code> - perform translations only</li>
                <li><code>review-only</code> - review translations only</li>
                <li><code>translate-review</code> - perform translations and review afterwards</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>is_including_not_translated</td>
        <td>optional</td>
        <td><code>true</code></td>
        <td></td>
        <td>Include not translated phrases to translate</td>
    </tr>
    <tr>
        <td>is_including_not_approved</td>
        <td>optional</td>
        <td><code>true</code></td>
        <td></td>
        <td>Include not approved phrases to translate</td>
    </tr>
    <tr>
        <td>is_including_outdated</td>
        <td>optional</td>
        <td><code>true</code></td>
        <td></td>
        <td>Include outdated phrases to translate that is updated since last order.</td>
    </tr>
    <tr>
        <td>translator_type</td>
        <td>optional</td>
        <td><code>preferred</code></td>
        <td><code>fastest</code></td>
        <td>
            Specify type of translator used in translation.
            <br>
            Types:
            <ul>
                <li><code>preferred</code> - select translator who helped translated your projects previously for consistency</li>
                <li><code>fastest</code> - select translator who has fewest jobs and is able to pick up your job faster</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>tone</td>
        <td>optional</td>
        <td><code>not-specified</code></td>
        <td><code>formal</code></td>
        <td>
            Specify the tone used in translation.
            <br>
            Currently supported:
            <ul>
                <li><code>not-specified</code> - no preference</li>
                <li><code>formal</code> - translate in formal tone</li>
                <li><code>informal</code> - translate in informal tone</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>specialization</td>
        <td>optional</td>
        <td><code>general</code></td>
        <td><code>game</code></td>
        <td>
            Specify specialization in order to translate phrases in a specific area.
            <br>
            Currently supported:
            <ul>
                <li><code>general</code> - genreal translations</li>
                <li><code>game</code> - translations of game</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>note</td>
        <td>optional</td>
        <td></td>
        <td></td>
        <td>Note to translator.</td>
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
        "id": 372,
        "amount": "50.00",
        "files": [
            {
                "name": "string.po"
            },
            {
                "name": "string2.po"
            },
            ...
        ],
        "from_language": {
            "code": "en-US",
            "english_name": "English (United States)",
            "local_name": "English (United States)",
            "locale": "en",
            "region" : "US"
        },
        "to_language": {
            "code": "ja-JP",
            "english_name": "Japanese",
            "local_name": "日本語",
            "locale": "ja",
            "region" : "JP"
        },
        "string_count": 835,
        "word_count": 3056,
        "ordered_at": "2013-08-15T08:12:40+0000",
        "ordered_at_timestamp":13283746583,
    }
}
```
[Back to top](#order)
