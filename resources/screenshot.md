## Screenshot
- [Upload](#upload---upload-a-screenshot)


### Upload - upload a screenshot

    POST https://platform.api.onesky.io/1/projects/:project_id/screenshots

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
        <td>screenshot</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Base64 encoded image data in Data URI scheme structure. Please reference to <a href="http://en.wikipedia.org/wiki/Data_URI_scheme" target="_blank">Data URI scheme</a> and <a href="http://en.wikipedia.org/wiki/Base64" target="_blank">Base64</a></td>
    </tr>
    <tr>
        <td>width</td>
        <td>required</td>
        <td></td>
        <td><code>1261</code></td>
        <td>Width of screenshot (in pixel)</td>
    </tr>
    <tr>
        <td>height</td>
        <td>required</td>
        <td></td>
        <td><code>1918</code></td>
        <td>Height of screenshot (in pixel)</td>
    </tr>
    <tr>
        <td>tags</td>
        <td>required</td>
        <td></td>
        <td></td>
        <td>Translations bind to the screenshot. Please refer to <a href="/reference/tag.md">tags</a></td>
    </tr>
</table>

**Response**

```
status 200 OK
```
[Back to top](#screenshot)
