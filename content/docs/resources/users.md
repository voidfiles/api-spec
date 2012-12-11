# Users

## Interacting with individual Users

<table class="table table-striped">
    <thead>
        <tr>
            <th>Description</th>
            <th>Path</th>
            <th>HTTP Method</th>
            <th>Authentication Required?</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#retrieve-a-user">Retrieve a User</a></td>
            <td>/stream/0/users/[user_id]</td>
            <td>GET</td>
            <td>No</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#update-a-user">Update a User</a></td>
            <td>/stream/0/users/me</td>
            <td>PUT</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#retrieve-a-users-avatar-image">Retrieve a User's avatar image</a></td>
            <td>/stream/0/users/[user_id]/avatar</td>
            <td>GET</td>
            <td>No</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#update-a-users-avatar-image">Update a User's avatar image</a></td>
            <td>/stream/0/users/me/avatar</td>
            <td>POST</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#retrieve-a-users-cover-image">Retrieve a User's cover image</a></td>
            <td>/stream/0/users/[user_id]/cover</td>
            <td>GET</td>
            <td>No</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#update-a-users-cover-image">Update a User's cover image</a></td>
            <td>/stream/0/users/me/cover</td>
            <td>POST</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#follow-a-user">Follow a User</a></td>
            <td>/stream/0/users/[user_id]/follow</td>
            <td>POST</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#unfollow-a-user">Unfollow a User</a></td>
            <td>/stream/0/users/[user_id]/follow</td>
            <td>DELETE</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#mute-a-user">Mute a User</a></td>
            <td>/stream/0/users/[user_id]/mute</td>
            <td>POST</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#unmute-a-user">Unmute a User</a></td>
            <td>/stream/0/users/[user_id]/mute</td>
            <td>DELETE</td>
            <td>Yes</td>
        </tr>
    </tbody>
</table>

## Retrieving lists of Users

<table class="table table-striped">
    <thead>
        <tr>
            <th>Description</th>
            <th>Path</th>
            <th>HTTP Method</th>
            <th>Authentication Required?</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#search-for-users">Search for Users</a></td>
            <td>/stream/0/users/search</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#retrieve-multiple-users">Retrieve multiple Users</a></td>
            <td>/stream/0/users</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#list-users-a-user-is-following">Retrieve Users a User is following</a></td>
            <td>/stream/0/users/[user_id]/following</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#list-user-ids-a-user-is-following">Retrieve IDs of Users a User is following</a></td>
            <td>/stream/0/users/[user_id]/following/ids</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#list-users-following-a-user">Retrieve Users following a User</a></td>
            <td>/stream/0/users/[user_id]/followers</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#list-user-ids-following-a-user">Retrieve IDs of Users following a User</a></td>
            <td>/stream/0/users/[user_id]/followers/ids</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#list-muted-users">Retrieve Users muted by the current User</a></td>
            <td>/stream/0/users/me/muted</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#list-user-interactions-with-me">Retrieve Interactions with the current User</a></td>
            <td>/stream/0/users/me/interactions</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#list-users-who-have-reposted-a-post">Retrieve Users who reposted a Post</a></td>
            <td>/stream/0/posts/[post_id]/reposters</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/users.md#list-users-who-have-starred-a-post">Retrieve Users who starred a Post</a></td>
            <td>/stream/0/posts/[post_id]/stars</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
    </tbody>
</table>