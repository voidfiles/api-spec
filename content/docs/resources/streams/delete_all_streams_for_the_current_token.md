## Delete all of the current user's Streams

Delete all <a href="../objects/stream.md">Streams</a> for the current token. It returns the deleted Streams on success.

*Remember, access tokens can not be passed in a HTTP body for ```DELETE``` requests. Please refer to the [authentication documentation](/appdotnet/api-spec/blob/master/auth.md#authenticated-api-requests).*

> This endpoint is currently migrated by the ```response_envelope``` migration. Please refer to the [Migrations documentation](/appdotnet/api-spec/blob/master/migrations.md#current-migrations) for more info.

### URL
> https://alpha-api.app.net/stream/0/streams

### Data

None.

### Example

> DELETE https://alpha-api.app.net/stream/0/streams
```js
{
    "data": [
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
            "type": "long_poll"
        },
        ...
    ],
    "meta": {
        "code": 200,
        "max_id": "2",
        "min_id": "1",
        "more": false
    }
}
```