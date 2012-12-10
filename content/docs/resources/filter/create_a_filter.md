## Create a Filter

Create a <a href="../objects/filter.md">Filter</a> for the current user.

Send a JSON document that matches the  <a href="../objects/filter.md">filter schema</a> with an HTTP header of ```Content-Type: application/json```. Currently, the only keys we use from your JSON will be ```name```, ```match_policy``` and ```clauses```.

> This endpoint is currently migrated by the ```response_envelope``` migration. Please refer to the [Migrations documentation](/appdotnet/api-spec/blob/master/migrations.md#current-migrations) for more info.

### URL
> https://alpha-api.app.net/stream/0/filters

### Data

A JSON object representing the filter to create. See <a href="../objects/filter.md">the filter object</a> for more information. (Omit the <code>id</code> parameter).</td>

### Example

> POST https://alpha-api.app.net/stream/0/filters
> 
> Content-Type: application/json
> 
> DATA {"match_policy": "include_any", "clauses": [{"operator": "contains", "field": "/data/entities/hashtags/*/name", "object_type": "post", "value": "rollout"}], "name": "Posts about rollouts"}
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