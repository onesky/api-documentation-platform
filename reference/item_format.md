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
        <td>string_key</td>
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
        <td>[no limit]</td>
        <td>Set the length limit for translator</td>
    </tr>
    <tr>
        <td>length_limit - type</td>
        <td>(required if length_limit provided)</td>
        <td></td>
        <td>
            <ul>
                <li>
                    <code>absolute</code>
                    <br>
                    Absolute number of characters limited for translation
                </li>
                <li>
                    <code>relative</code>
                    <br>
                    Number of characters limited is calculated according to string length. For example, length limit value <code>2</code> with string length <code>10</code>, formula will be <code>10 x 2</code>. That is <code>20</code> characters.
                </li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>length_limit - value</td>
        <td>(required if length_limit provided)</td>
        <td></td>
        <td>Value either used as absolute characters limited or to calculate the limitation</td>
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
        "<string_key>": {
            "string": "<string to be translated>",
            "description" "<string description>",
            "length_limit": {
                "type": "[absolute, relative]",
                "value": "<value of length limit>",
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
                "type": "absolute",
                "value": 80,
                "is_exceed_allowed": true
            }
        },
        "answer1": {
            "string": "New York Bulls",
            "description": "New York Knicks, Chicago Bulls",
            "length_limit": {
                "type": "relative",
                "value": 1,
                "is_exceed_allowed": false
            }
        },
        "answer2": {
            "string": "Los Angeles Kings",
            "description": "Los Angeles Lakers, Sacramento Kings",
            "length_limit": {
                "type": "relative",
                "value": 1,
                "is_exceed_allowed": false
            }
        },
        "answer3": {
            "string": "Golden State Warriros",
            "description": "This is the answer",
            "length_limit": {
                "type": "relative",
                "value": 1,
                "is_exceed_allowed": false
            }
        },
        "answer4": {
            "string": "Huston Heat",
            "description": "Huston Rocket, Miami Heat",
            "length_limit": {
                "type": "relative",
                "value": 1,
                "is_exceed_allowed": false
            }
        }
    },
    "question_002": {
        "title": {
            "string": "Albert Einstein was born in which country?",
            "description": "Albery Einstein"
            "length_limit": {
                "type": "absolute",
                "value": 70,
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
