## Delete a Stream

Delete a <a href="../objects/stream.md">Stream</a>. The Stream must belong to the current User. It returns the deleted Stream on success.

*Remember, access tokens can not be passed in a HTTP body for ```DELETE``` requests. Please refer to the [authentication documentation](/appdotnet/api-spec/blob/master/auth.md#authenticated-api-requests).*

> This endpoint is currently migrated by the ```response_envelope``` migration. Please refer to the [Migrations documentation](/appdotnet/api-spec/blob/master/migrations.md#current-migrations) for more info.

### URL
> https://alpha-api.app.net/stream/0/streams/[stream_id]

### Data

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Required?</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>stream_id</code></td>
            <td>Required</td>
            <td>string</td>
            <td>The stream id</td>
        </tr>
    </tbody>
</table>

### Example

> DELETE https://alpha-api.app.net/stream/0/streams/1
```js
{
    "data": {
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
        "type": "long_poll"
    },
    "meta": {
        "code": 200
    }
}
```