## Groups


**Parameters**

<table>
    <tr>
        <td><strong>Name</strong></td>
        <td><strong>Required?</strong></td>
        <td><strong>Sample</strong></td>
        <td><strong>Description</strong></td>
    </tr>
    <tr>
        <td>name</td>
        <td>required</td>
        <td><code>index</code></td>
        <td>Name of the group. Suggest to use the same naming methodology of screenshot</td>
    </tr>
    <tr>
        <td>phrases</td>
        <td>required</td>
        <td></td>
        <td>Phrases belong to the group. Please refer to <a href="#phrases">phrases</a></td>
    </tr>
</table>


**Sample**
``` json
{
    "groupings": [
        {
            "name": "landing_page",
            "phrases": [
                {
                    "key": "landing_page.title.header",
                    "file": "string.po"
                },
                {
                    "key": "landing_page.title.header",
                    "file": "string.po"
                },
                ...
            ]
        },
        {
            "name": "dashboard",
            "phrases": [
                {
                    "key": "dashboard.header",
                    "file": "dashboard.yml"
                },
                {
                    "key": "dashboard.menu.profile",
                    "file": "dashboard.yml"
                },
                {
                    "key": "dashboard.menu.settings",
                    "file": "dashboard.yml"
                },
                ...
            ]
        },
        ...
    ]
}
```


## Phrases

**Parameters**

<table>
    <tr>
        <td><strong>Name</strong></td>
        <td><strong>Required?</strong></td>
        <td><strong>Sample</strong></td>
        <td><strong>Description</strong></td>
    </tr>
    <tr>
        <td>key</td>
        <td>required</td>
        <td></td>
        <td>Key of the phrase</td>
    </tr>
    <tr>
        <td>file</td>
        <td>optional</td>
        <td><code>en.yml</code></td>
        <td>Name of the string file</td>
    </tr>
</table>


**Sample**
``` json
{
    "phrases": [
        {
            "key": "nav.header",
            "file": "common.yml"
        },
        {
            "key": "dashboard.menu.profile",
            "file": "menu.yml"
        },
        {
            "key": "dashboard.menu.settings"
        },
        ...
    ]
}
```
