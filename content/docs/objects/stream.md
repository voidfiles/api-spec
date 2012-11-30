## Stream

A customized view of the global stream that is streamed to the client instead of polling.

```js
{
    "endpoint": "https://stream-channel.app.net...",
    "filter": {
        "clauses": [
            {
                "field": "/data/entities/hashtags/*/name",
                "object_type": "post",
                "operator": "contains",
                "value": "rollout"
            }
        ],
        "id": "1",
        "match_policy": "include_any",
        "name": "Posts about rollouts"
    },
    "id": "1",
    "object_types": [
        "post"
    ],
    "type": "long_poll",
    "key": "rollout_stream"
}
```

### Stream Fields

<table>
    <thead>
        <tr>
            <th>Field</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>id</code></td>
            <td>string</td>
            <td>Primary identifier for a stream. This will be an integer, but it is always expressed as a string to avoid limitations with the way JavaScript integers are expressed.</td>
        </tr>
        <tr>
            <td><code>endpoint</code></td>
            <td>string</td>
            <td>The fully qualified URL the client should use to connect to this stream.</td>
        </tr>
        <tr>
            <td><code>filter</code></td>
            <td>object</td>
            <td>An optional filter to apply when generating the stream.</td>
        </tr>
        <tr>
            <td><code>object_types</code></td>
            <td>list</td>
            <td>A list of strings that specify the kinds of objects this stream is interested in. Must be one of <code>post</code>, <code>star</code>, <code>user_follow</code>.</td>
        </tr>
        <tr>
            <td><code>type</code></td>
            <td>string</td>
            <td>A string specifying the type of stream this is. This can affect the transport method of the endpoint url as well as characteristics of the stream (how many messages it can process, how long lived it is, etc). Currently, the only option is <code>long_poll</code>.</td>
        </tr>
        <tr>
            <td><code>key</code></td>
            <td>string</td>
            <td>An optional User assigned string that names this stream so it's easy to query for later. If a key is given, it must be unique for all streams created by a single token.</td>
        </tr>
    </tbody>
</table>