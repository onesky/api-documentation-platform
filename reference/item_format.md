## Item format
**Parameters**

<table>
    <tr>
        <td><strong>Name</strong></td>
        <td><strong>Required?</strong></td>
        <td><strong>Default</strong></td>
        <td><strong>Description</strong></td>
    </tr>
    <tr>
        <td>item_key</td>
        <td>required</td>
        <td></td>
        <td>Unique key to item</td>
    </tr>
    <tr>
        <td>content_key</td>
        <td>required</td>
        <td></td>
        <td>Unique key to string within an item</td>
    </tr>
    <tr>
        <td>string</td>
        <td>required</td>
        <td></td>
        <td>String to be translated</td>
    </tr>
    <tr>
        <td>description</td>
        <td>optional</td>
        <td></td>
        <td>Description of string</td>
    </tr>
    <tr>
        <td>length_limit</td>
        <td>optional</td>
        <td></td>
        <td>Set the length limit for translator</td>
    </tr>
    <tr>
        <td>length_limit - absolute_char_count</td>
        <td>(either this or relative_char_count if length_limit provided)</td>
        <td></td>
        <td>Absolute number of characters limit for translation</td>
    </tr>
    <tr>
        <td>length_limit - relative_char_count</td>
        <td>(either this or absolute_char_count if length_limit provided)</td>
        <td></td>
        <td>Length limit is calculated according to string length. For example, relative_characters <code>2</code> with string length <code>10</code>, length limit is <code>10 x 2</code>. That is <code>20</code> characters.</td>
    </tr>
    <tr>
        <td>length_limit - is_exceed_allowed</td>
        <td>optional</td>
        <td>true</td>
        <td>Whether allow translation exceeding the length limit a little</td>
    </tr>
</table>

**Structure**

``` json
{
    "<item_key>": {
        "<content_key>": {
            "string": "<string to be translated>",
            "description" "<string description>",
            "length_limit": {
                "absolute_char_count": "<absolute characters count>",
                "relative_char_count": "<relative characters count>",
                "is_exceed_allowed": "<whether allow translation exceeding the length limit a little>"
            }
        }
    }
}
```

**Sample**

``` json
{
    "question_001": {
        "title": {
            "string": "Which one is correct team name in National Basketball Association (NBA)?",
            "description": "NBA basketball team name",
            "length_limit": {
                "absolute_char_count": 80,
                "is_exceed_allowed": true
            }
        },
        "answer1": {
            "string": "New York Bulls",
            "description": "New York Knicks, Chicago Bulls",
            "length_limit": {
                "relative_char_count": 1,
                "is_exceed_allowed": false
            }
        },
        "answer2": {
            "string": "Los Angeles Kings",
            "description": "Los Angeles Lakers, Sacramento Kings",
            "length_limit": {
                "relative_char_count": 1,
                "is_exceed_allowed": false
            }
        },
        "answer3": {
            "string": "Golden State Warriros",
            "description": "This is the answer",
            "length_limit": {
                "relative_char_count": 1,
                "is_exceed_allowed": false
            }
        },
        "answer4": {
            "string": "Huston Heat",
            "description": "Huston Rocket, Miami Heat",
            "length_limit": {
                "relative_char_count": 1,
                "is_exceed_allowed": false
            }
        }
    },
    "question_002": {
        "title": {
            "string": "Albert Einstein was born in which country?",
            "description": "Albery Einstein"
            "length_limit": {
                "absolute_char_count": 70,
                "is_exceed_allowed": true
            }
        },
        "answer1": {
            "string": "France"
        },
        "answer2": {
            "string": "Germany",
            "description": "answer"
        },
        "answer3": {
            "string": "Italy"
        },
        "answer4": {
            "string": "England"
        }
    }
}
```
