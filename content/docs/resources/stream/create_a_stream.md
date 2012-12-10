## Create a Stream

Create a <a href="../objects/stream.md">Stream</a> for the current token.

Send a JSON document that matches the  <a href="../objects/stream.md">stream schema</a> with an HTTP header of ```Content-Type: application/json```. Currently, the only keys we use from your JSON will be ```object_types```, ```type``` and ```filter_id```. If you don't want to specify a filter, omit ```filter_id```.

> This endpoint is currently migrated by the ```response_envelope``` migration. Please refer to the [Migrations documentation](/appdotnet/api-spec/blob/master/migrations.md#current-migrations) for more info.

### URL
> https://alpha-api.app.net/stream/0/streams

### Data

A JSON object representing the stream to create. See <a href="../objects/stream.md">the stream object</a> for more information. Specify ```filter_id``` instead of ```filter``` if you want to filter this stream. (Omit the ```id``` and ```endpoint``` parameters).</td>

### Example

> POST https://alpha-api.app.net/stream/0/streams
> 
> Content-Type: application/json
> 
> DATA {"object_types": ["post"], "type": "long_poll", "id": "1", "filter_id": "1", "key": "rollout_stream"}
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
        "type": "long_poll",
        "key": "rollout_stream"
    },
    "meta": {
        "code": 200
    }
}
```