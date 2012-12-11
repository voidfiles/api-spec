# Posts

## Interacting with individual Posts
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
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#create-a-post">Create a Post</a></td>
            <td>/stream/0/posts</td>
            <td>POST</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-a-post">Retrieve a Post</a></td>
            <td>/stream/0/posts/[post_id]</td>
            <td>GET</td>
            <td>No</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#delete-a-post">Delete a Post</a></td>
            <td>/stream/0/posts/[post_id]</td>
            <td>DELETE</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#repost-a-post">Repost a Post</a></td>
            <td>/stream/0/posts/[post_id]/repost</td>
            <td>POST</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#unrepost-a-post">Unrepost a Post</a></td>
            <td>/stream/0/posts/[post_id]/repost</td>
            <td>DELETE</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#star-a-post">Star a Post</a></td>
            <td>/stream/0/posts/[post_id]/star</td>
            <td>POST</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#unstar-a-post">Unstar a Post</a></td>
            <td>/stream/0/posts/[post_id]/star</td>
            <td>DELETE</td>
            <td>Yes</td>
        </tr>

    </tbody>
</table>

## Retrieving lists of Posts

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
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-multiple-posts">Retrieve multiple Posts</a></td>
            <td>/stream/0/posts</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-posts-created-by-a-user">Retrieve a User's posts</a></td>
            <td>/stream/0/users/[user_id]/posts</td>
            <td>GET</td>
            <td>No</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-posts-starred-by-a-user">Retrieve a User's starred posts</a></td>
            <td>/stream/0/users/[user_id]/stars</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-posts-mentioning-a-user">Retrieve Posts mentioning a User</a></td>
            <td>/stream/0/users/[user_id]/mentions</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-tagged-posts">Retrieve Posts containing a hashtag</a></td>
            <td>/stream/0/posts/tag/[hashtag]</td>
            <td>GET</td>
            <td>No</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-the-replies-to-a-post">Retrieve replies to a Post</a></td>
            <td>/stream/0/posts/[post_id]/replies</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-a-users-personalized-stream">Retrieve a User's personalized stream</a></td>
            <td>/stream/0/posts/stream</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-a-users-unified-stream">Retrieve a User's unified stream</a></td>
            <td>/stream/0/posts/stream/unified</td>
            <td>GET</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td><a href="/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-the-global-stream">Retrieve the Global stream</a></td>
            <td>/stream/0/posts/stream/global</td>
            <td>GET</td>
            <td>No</td>
        </tr>
    </tbody>
</table>

### General parameters

Requests for streams of Posts can be filtered by passing query string parameters along with the request.

<table class="table table-striped">
    <thead>
        <tr>
            <th>Name</th>
            <th>Required?</th>
            <th width="50">Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>min_id</code> (<em><a href="#deprecating-min_id-and-max_id">Deprecating</a></em>)</td>
            <td>Optional</td>
            <td>string</td>
            <td>The minimum Post id to return (the response *will include* this post id if it is valid).</td>
        </tr>
        <tr>
            <td><code>max_id</code> (<em><a href="#deprecating-min_id-and-max_id">Deprecating</a></em>)</td>
            <td>Optional</td>
            <td>string</td>
            <td>The maximum Post id to return (the response *will include* this post id if it is valid)</td>
        </tr>
        <tr>
            <td><code>since_id</code></td>
            <td>Optional</td>
            <td>string</td>
            <td>Include posts with ids greater than this id. This value is not guaranteed to be a Post id and should come from the <code>max_id</code> parameter of a previous request's <a href="/appdotnet/api-spec/blob/master/responses.md#pagination-metadata">pagination metadata</a>. The response <strong>will not include</strong> this id.</td>
        </tr>
        <tr>
            <td><code>before_id</code></td>
            <td>Optional</td>
            <td>string</td>
            <td>Include posts with ids smaller than this id. This value is not guaranteed to be a Post id and should come from the <code>min_id</code> parameter of a previous request's <a href="/appdotnet/api-spec/blob/master/responses.md#pagination-metadata">pagination metadata</a>. The response <strong>will not include</strong> this id.</td>
        </tr>
        <tr>
            <td><code>count</code></td>
            <td>Optional</td>
            <td>integer</td>
            <td>The number of Posts to return, up to a maximum of 200. Sorry, negative counts are temporarily disabled.</td>
        </tr>
        <tr>
            <td><code>include_muted</code></td>
            <td>Optional</td>
            <td>integer (0 or 1)</td>
            <td>Should posts from muted users be included? Defaults to false except when you specifically request a Post from a muted user or when you specifically request a muted user's stream.</td>
        </tr>
        <tr>
            <td><code>include_deleted</code></td>
            <td>Optional</td>
            <td>integer (0 or 1)</td>
            <td>Should deleted posts be included? Defaults to true.</td>
        </tr>
        <tr>
            <td><code>include_directed_posts</code></td>
            <td>Optional</td>
            <td>integer (0 or 1)</td>
            <td>Should posts directed at people I don't follow be included? A directed post is a post that starts with 1 or more @mentions. A machine only post with mentions is also considered a directed post. Defaults to false for "My Stream" and true everywhere else.</td>
        </tr>
        <tr>
            <td><code>include_machine</code></td>
            <td>Optional</td>
            <td>integer (0 or 1)</td>
            <td>Should <a href="../objects/post.md#machine-only-posts">machine only posts</a> be included? (Default: <code>False</code>)</td>
        </tr>
        <tr>
            <td><code>include_annotations</code></td>
            <td>Optional</td>
            <td>integer (0 or 1)</td>
            <td>Should the <a href="../objects/annotations.md">user and post annotations</a> be included in the Post? (Default: <code>False</code>)</td>
        </tr>
        <tr>
            <td><code>include_post_annotations</code></td>
            <td>Optional</td>
            <td>integer (0 or 1)</td>
            <td>Should the <a href="../objects/annotations.md">post annotations</a> be included in the Post? (Default: <code>False</code>)</td>
        </tr>
        <tr>
            <td><code>include_user_annotations</code></td>
            <td>Optional</td>
            <td>integer (0 or 1)</td>
            <td>Should the <a href="../objects/annotations.md">user annotations</a> be included in the Post? (Default: <code>False</code>)</td>
        </tr>
        <tr>
            <td><code>include_starred_by</code></td>
            <td>Optional</td>
            <td>integer (0 or 1)</td>
            <td>Should a sample of Users who have starred a Post be returned with the Post objects? Please see the <a href="../objects/post.md">Post schema</a>. (Default: <code>False</code>)</td>
        </tr>
        <tr>
            <td><code>include_reposters</code></td>
            <td>Optional</td>
            <td>integer (0 or 1)</td>
            <td>Should a sample of Users who have reposted a Post be returned with the Post objects? Please see the <a href="../objects/post.md">Post schema</a>. (Default: <code>False</code>)</td>
        </tr>
        <tr>
            <td><code>include_user</code> (<em>Coming soon</em>)</td>
            <td>Optional</td>
            <td>integer (0 or 1)</td>
            <td>Should the nested User object be included in the Post? (Default depends upon the endpoint)</td>
        </tr>
    </tbody>
</table>

#### Deprecating min_id and max_id

After thinking through the pagination use cases more, we don't think ```min_id``` and ```max_id``` are the most useful parameters. We're planning on deprecating them in favor of ```since_id``` and ```before_id```. If you have a use case that would benefit from inclusive parameters (```min_id``` and ```max_id```), please [let us know](https://github.com/appdotnet/api-spec/issues).

### Sorting Posts

Post id is the ordering field for multiple posts (not ```created_at```). ```created_at``` is meant to be displayed to users, not to sort posts. This also makes pagination with ```since_id``` and ```before_id``` more straightforward. Posts are presently always returned in reverse chronological order (newest to oldest). As a result, the Posts endpoints will always return the newest posts that meet the requested criteria e.g. before_id and count.