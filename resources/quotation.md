## Quotation
- [Show](#show---retrieve-a-quotation)


### Show - retrieve a quotation

    GET https://platform.api.onesky.io/1/projects/:project_id/quotations

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
        "string_count": 2013,
        "word_count": 639,
        "specialization": "general",
        "translation_only": {
            "per_word_cost": "0.01",
            "total_cost": "20.13",
            "estimated_return_datetime": "2013-01-01T23:00:00+0000",
            "estimated_return_timestamp": 13453435132,
            "estimated_seconds_from_now": 1234567
        },
        "translation_and_review": {
            "per_word_cost": "0.02",
            "total_cost": "40.26",
            "estimated_return_datetime": "2013-01-02T23:00:00+0000",
            "estimated_return_timestamp": 1357167600,
            "estimated_seconds_from_now": 2345678
        },
        "review_only": {
            "per_word_cost": "0.005",
            "total_cost": "10.07",
            "estimated_return_datetime": "2013-01-01T23:00:00+0000",
            "estimated_return_timestamp": 13453435132,
            "estimated_seconds_from_now": 1234567
        }
    }
}
```
[Back to top](#order)
