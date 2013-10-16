## Screenshots


**Parameters**

<table>
    <tr>
        <td><strong>Name</strong></td>
        <td><strong>Required?</strong></td>
        <td><strong>Sample</strong></td>
        <td><strong>Description</strong></td>
    </tr>
    <tr>
        <td>image</td>
        <td>required</td>
        <td></td>
        <td>Base64 encoded image data in Data URI scheme structure. Please reference to <a href="http://en.wikipedia.org/wiki/Data_URI_scheme" target="_blank">Data URI scheme</a> and <a href="http://en.wikipedia.org/wiki/Base64" target="_blank">Base64</a></td>
    </tr>
    <tr>
        <td>width</td>
        <td>required</td>
        <td><code>1261</code></td>
        <td>Width of screenshot (in pixel)</td>
    </tr>
    <tr>
        <td>height</td>
        <td>required</td>
        <td><code>1918</code></td>
        <td>Height of screenshot (in pixel)</td>
    </tr>
    <tr>
        <td>tags</td>
        <td>required</td>
        <td></td>
        <td>Translations bind to the screenshot. Please refer to <a href="#tags">tags</a></td>
    </tr>
</table>


**Sample**

``` json
{
    "screenshots": [
        {
            "image": <Base64 encoded image data>,
            "width": 1261,
            "height": 1918,
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
                    "y": 80,
                    "width": 150,
                    "height": 50
                },
                ...
            ]
        },
        {
            "image": <Base64 encoded image data>,
            "width": 1261,
            "height": 528,
            "tags": [
                {
                    "key": "common.footer.aboutus",
                    "x": 520,
                    "y": 60,
                    "width": 150,
                    "height": 50
                },
                {
                    "key": "common.footer.contactus",
                    "x": 520,
                    "y": 110,
                    "width": 150,
                    "height": 50
                },
                ...
            ]
        },
        ...
    ]
}
```


## Tags
Translations bind to a screenshot.


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
        <td>Key of the translation</td>
    </tr>
    <tr>
        <td>x</td>
        <td>required</td>
        <td></td>
        <td>X-axis of the translation component</td>
    </tr>
    <tr>
        <td>y</td>
        <td>required</td>
        <td></td>
        <td>Y-axis of the translation component</td>
    </tr>
    <tr>
        <td>width</td>
        <td>required</td>
        <td></td>
        <td>Width of the translation component</td>
    </tr>
    <tr>
        <td>height</td>
        <td>required</td>
        <td></td>
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
