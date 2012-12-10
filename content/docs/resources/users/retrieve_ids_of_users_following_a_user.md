## List user ids following a user

Returns an array of user ids for users following the specified user.

> This endpoint is currently migrated by the ```response_envelope``` migration. Please refer to the [Migrations documentation](/appdotnet/api-spec/blob/master/migrations.md#current-migrations) for more info.

### URL

> https://alpha-api.app.net/stream/0/users/[user_id]/followers/ids

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
            <td><code>user_id</code></td>
            <td>Required</td>
            <td>string</td>
            <td>The user id. If the user id is <code>me</code> the current authenticated user will be used. You can also specify <code>@username</code> as a <code>user_id</code>.</td>
        </tr>
    </tbody>
</table>

### Example

> GET https://alpha-api.app.net/stream/0/users/1/followers/ids
```js
{
    "data": [
        "2",
        "3",
        ...
    ],
    "meta": {
        "code": 200,
    }
}
```