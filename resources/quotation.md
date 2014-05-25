## Quotation
- [Show](#show---make-a-quotation)


### Show - make a quotation

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
        <td><code>['string.po']</code></td>
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
        <td><code>false</code></td>
        <td>Include not translated phrases to translate</td>
    </tr>
    <tr>
        <td>is_including_not_approved</td>
        <td>optional</td>
        <td><code>true</code></td>
        <td><code>false</code></td>
        <td>Include not approved phrases to translate</td>
    </tr>
    <tr>
        <td>is_including_outdated</td>
        <td>optional</td>
        <td><code>true</code></td>
        <td><code>false</code></td>
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
        "is_including_not_translated": true,
        "is_including_not_approved": true,
        "is_including_outdated": false,
        "specialization": "general",
        "translation_only": {
            "string_count": 2013,
            "word_count": 639,
            "per_word_cost": "0.01",
            "total_cost": "20.13",
            "will_complete_at": "2013-01-01T23:00:00+0000",
            "will_complete_at_timestamp": 13453435132,
            "seconds_to_complete": 1234567,
            "preferred_translator" : {
                "will_complete_at": "2013-01-05T23:00:00+0000",
                "will_complete_at_timestamp": 1357426800,
                "seconds_to_complete": 2342342
            }
        },
        "translation_and_review": {
            "string_count": 2013,
            "word_count": 639,
            "per_word_cost": "0.02",
            "total_cost": "40.26",
            "will_complete_at": "2013-01-02T23:00:00+0000",
            "will_complete_at_timestamp": 1357167600,
            "seconds_to_complete": 2345678,
            "preferred_translator" : {
                "will_complete_at": "2013-01-06T23:00:00+0000",
                "will_complete_at_timestamp": 1357513200,
                "seconds_to_complete": 3456789
            }
        },
        "review_only": {
            "string_count": 2013,
            "word_count": 639,
            "per_word_cost": "0.005",
            "total_cost": "10.07",
            "will_complete_at": "2013-01-01T23:00:00+0000",
            "will_complete_at_timestamp": 13453435132,
            "seconds_to_complete": 1234567,
            "preferred_translator" : {
                "will_complete_at": "2013-01-05T23:00:00+0000",
                "will_complete_at_timestamp": 1357426800,
                "seconds_to_complete": 2342342
            }
        }
    }
}
```
[Back to top](#quotation)
