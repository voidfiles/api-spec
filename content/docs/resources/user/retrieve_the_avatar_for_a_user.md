## Retrieve a User's avatar image

Retrieve a User's avatar image. This endpoint does not require authentication and will return an HTTP 302 redirect to the user's current avatar image. It will include any [query string parameters](../objects/user.md#images) you pass to the endpoint.

### URL
> https://alpha-api.app.net/stream/0/users/[user_id]/avatar

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

> GET https://alpha-api.app.net/stream/0/users/me/avatar
>
> 302 Location: https://example.com/avatar.jpg
