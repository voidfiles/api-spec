## Stream Marker

Stream markers allows a User's position in a stream of Posts to be synced between multiple App.net clients. Then when you go from the browser to your phone, you're stream is right where you left off. The current stream marker will be included in the [response envelope]() from any stream that returns Posts.

### Example Stream Marker

If a Stream Marker hasn't yet been set, you will receive the following format:
```js
{
    "name": "global",
}
```

A marker that has been set will look like this:
```js
{
    "id": "1234",
    "name": "global",
    "percentage": 0,
    "updated_at": "2012-11-09T23:35:38Z",
    "version": "NWoZK3kTsExUV00Ywo1G5jlUKKs"
}
```

### Stream Marker fields

<table>
    <tr>
        <th>Field</th>
        <th>Type</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><code>id</code></td>
        <td>string</td>
        <td>The Post id of the Post at the top of the stream when this Stream's position was last synced.</td>
    </tr>
    <tr>
        <td><code>name</code></td>
        <td>string</td>
        <td>The name of the Stream this marker is for.</td>
    </tr>
    <tr>
        <td><code>percentage</code></td>
        <td>integer</td>
        <td>An optional field that indicate what percentage this post has been scrolled in the stream. It defaults to 0. This allows for very precise stream syncing but since different clients render Posts with different heights it won't be consistent across different clients.</td>
    </tr>
    <tr>
        <td><code>updated_at</code></td>
        <td>string</td>
        <td>The time this marker was last updated in <a href='http://en.wikipedia.org/wiki/ISO_8601'>ISO 8601</a> format.</td>
    </tr>
    <tr>
        <td><code>version</code></td>
        <td>string</td>
        <td>A unique identifier updated every time this Stream Marker is updated.</td>
    </tr>
</table>