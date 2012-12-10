## Retrieve a Filter

Returns a specific <a href="../objects/filter.md">Filter</a> object.

> This endpoint is currently migrated by the ```response_envelope``` migration. Please refer to the [Migrations documentation](/appdotnet/api-spec/blob/master/migrations.md#current-migrations) for more info.

### URL
> https://alpha-api.app.net/stream/0/filters/[filter_id]

### Parameters

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
            <td><code>filter_id</code></td>
            <td>Required</td>
            <td>string</td>
            <td>The filter id</td>
        </tr>
    </tbody>
</table>

### Example

> GET https://alpha-api.app.net/stream/0/filters/1
```js
{
    "data": {
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
    "meta": {
        "code": 200
    }
}
```