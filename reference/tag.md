## Tags
Translations bind to a screenshot.

**Parameters**

<table>
    <tr>
        <td><strong>Name</strong></td>
        <td><strong>Required?</strong></td>
        <td><strong>Description</strong></td>
    </tr>
    <tr>
        <td>key</td>
        <td>required</td>
        <td>Key of the translation</td>
    </tr>
    <tr>
        <td>x</td>
        <td>required</td>
        <td>X-axis of the translation component</td>
    </tr>
    <tr>
        <td>y</td>
        <td>required</td>
        <td>Y-axis of the translation component</td>
    </tr>
    <tr>
        <td>width</td>
        <td>required</td>
        <td>Width of the translation component</td>
    </tr>
    <tr>
        <td>height</td>
        <td>required</td>
        <td>Height of the translation component</td>
    </tr>
</table>

**Sample**

``` json
{
    "tags": [
        {
            "key": "common.nav.product.smartphone",
            "x": 460,
            "y": 30,
            "width": 150,
            "height": 50
        },
        {
            "key": "common.nav.product.television",
            "x": 460,
            "y": 180,
            "width": 150,
            "height": 50
        },
        ...
    ]
}
```
