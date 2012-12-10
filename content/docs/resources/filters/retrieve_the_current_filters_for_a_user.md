## Get current user's Filters

Return the <a href="../objects/filter.md">Filters</a> for the current user.

> This endpoint is currently migrated by the ```response_envelope``` migration. Please refer to the [Migrations documentation](/appdotnet/api-spec/blob/master/migrations.md#current-migrations) for more info.

### URL
> https://alpha-api.app.net/stream/0/filters

### Parameters

None.

### Example

> GET https://alpha-api.app.net/stream/0/filters
```js
{
    "data": [
        {
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