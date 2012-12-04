## List User interactions with me

List all the [Interactions](../objects/interactions.md) other users have had with me. *Note: you can only request this list for the current user.*

> This endpoint is currently migrated by the ```response_envelope``` migration. Please refer to the [Migrations documentation](/appdotnet/api-spec/blob/master/migrations.md#current-migrations) for more info.

### URL
> https://alpha-api.app.net/stream/0/users/me/interactions

### Parameters

None.

### Example

> GET https://alpha-api.app.net/stream/0/users/me/interactions
```js
{
    "data": [
        {
            "action": "repost",
            "objects": [
                {
                    "id": "1",
                    ...
                }
            ],
            "users": [
                {
                    "id": "2",
                    ...
                },
                {
                    "id": "1",
                    ...
                },
            ]
        },
        {
            "action": "follow",
            "objects": [
                {
                    "id": "1",
                    ...
                }
            ],
            "users": [
                {
                    "id": "2",
                    ...
                }
            ]
        },
        ...
    ],
    "meta": {
        "code": 200,
        "max_id": 10,
        "min_id": 4,
        "more": true
    }
}
```