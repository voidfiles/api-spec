## Star a Post

Save a given Post to the current User's stars. This is just a "save" action, not a sharing action. A User's stars are visible to others, but they are not automatically added to your followers' streams.

*Note: A repost cannot be starred. Please star the parent Post.*

> This endpoint is currently migrated by the ```response_envelope``` migration. Please refer to the [Migrations documentation](/appdotnet/api-spec/blob/master/migrations.md#current-migrations) for more info.

### URL
> https://alpha-api.app.net/stream/0/posts/[post_id]/star

### Data

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
            <td><code>post_id</code></td>
            <td>Required</td>
            <td>string</td>
            <td>The post id</td>
        </tr>
    </tbody>
</table>

### Example

> POST https://alpha-api.app.net/stream/0/posts/1/star
```js
{
    "data": {
        "id": "1", // note this is a string
        "user": {
            ...
        },
        "created_at": "2012-07-16T17:25:47Z",
        "text": "@berg FIRST post on this new site #newsocialnetwork",
        "html": "<span itemprop=\"mention\" data-mention-name=\"berg\" data-mention-id=\"2\">@berg</span> FIRST post on <a href=\"https://join.app.net\" rel=\"nofollow\">this new site</a> <span itemprop=\"hashtag\" data-hashtag-name=\"newsocialnetwork\">#newsocialnetwork</span>.",
        "source": {
            "client_id": "udxGzAVBdXwGtkHmvswR5MbMEeVnq6n4",
            "name": "Clientastic for iOS",
            "link": "http://app.net"
        },
        "machine_only": false,
        "reply_to": null,
        "thread_id": "1",
        "num_replies": 3,
        "num_reposts": 0,
        "num_stars": 1,
        "entities": {
            "mentions": [{
                "name": "berg",
                "id": "2",
                "pos": 0,
                "len": 5
            }],
            "hashtags": [{
                "name": "newsocialnetwork",
                "pos": 34,
                "len": 17
            }],
            "links": [{
                "text": "this new site",
                "url": "https://join.app.net"
                "pos": 20,
                "len": 13
            }]
        },
        "you_reposted": false,
        "you_starred": true
    },
    "meta": {
        "code": 200,
    }
}
```