## Update a Filter

Updates a specific <a href="../objects/filter.md">Filter</a> object. When a filter is updated, all the streams using the filter will start using the new filter criteria. You can update a filter by PUTing an object that matches the [filter schema](../objects/filter.md) with an HTTP header of ```Content-Type: application/json```. The entire filter will be replaced with new value but id's ```id``` will remain the same. Please refer to the documentation on [how to create a filter](#create-a-filter) for more information.

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

> PUT https://alpha-api.app.net/stream/0/filters/1
> 
> Content-Type: application/json
> 
> DATA {"match_policy": "include_any", "clauses": [{"operator": "contains", "field": "/data/entities/hashtags/*/name", "object_type": "post", "value": "rollout"}, {"operator": "contains", "field": "/data/entities/hashtags/*/name", "object_type": "post", "value": "bug"}], "name": "Posts about rollouts or bugs"}
```js
{
    "data": {
        "clauses": [
            {
                "field": "/data/entities/hashtags/*/name",
                "object_type": "post",
                "operator": "contains",
                "value": "rollout"
            },
            {
                "field": "/data/entities/hashtags/*/name",
                "object_type": "post",
                "operator": "contains",
                "value": "bug"
            }
        ],
        "id": "1",
        "match_policy": "include_any",
        "name": "Posts about rollouts or bugs"
    },
    "meta": {
        "code": 200
    }
}
```