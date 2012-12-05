## Create a Post
Create a new <a href="../objects/post.md">Post</a> object. Mentions and hashtags will be parsed out of the post text, as will bare URLs.

You can also create a Post by sending JSON in the HTTP post body that matches the <a href="../objects/post.md">post schema</a> with an HTTP header of ```Content-Type: application/json```. Currently, the only keys we use from your JSON will be ```text```, ```reply_to```, ```machine_only```, ```annotations``` and ```entities```. To create complex posts (including [machine only posts](../objects/post.md#machine-only-posts)), you must use the JSON interface. See the [JSON example](#json-example) below. If you would like to specify your own entities, please refer to the [user specified entites](../objects/entities.md#user-specified-entities) documentation.

*Note: You cannot reply to a repost. Please reply to the parent Post.*


> This endpoint is currently migrated by the ```response_envelope``` migration. Please refer to the [Migrations documentation](/appdotnet/api-spec/blob/master/migrations.md#current-migrations) for more info.

### Required Scopes

* ```write_post```

### URL
> https://alpha-api.app.net/stream/0/posts

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
            <td><code>text</code></td>
            <td>Required</td>
            <td>string</td>
            <td>The raw text of the post</td>
        </tr>
        <tr>
            <td><code>reply_to</code></td>
            <td>Optional</td>
            <td>string</td>
            <td>The id of the post that this new post is replying to</td>
        </tr>
    </tbody>
</table>

### Example

> POST https://alpha-api.app.net/stream/0/posts
>
> DATA text=%40berg+FIRST+post+on+this+new+site+%23newsocialnetwork
```js
{
    "data": {
        "id": "1", // note this is a string
        "user": {
            ...
        },
        "created_at": "2012-07-16T17:25:47Z",
        "text": "@berg FIRST post on this new site #newsocialnetwork",
        "html": "<span itemprop=\"mention\" data-mention-name=\"berg\" data-mention-id=\"2\">@berg</span> FIRST post on this new site <span itemprop=\"hashtag\" data-hashtag-name=\"newsocialnetwork\">#newsocialnetwork</span>.",
        "source": {
            "client_id": "udxGzAVBdXwGtkHmvswR5MbMEeVnq6n4",
            "name": "Clientastic for iOS",
            "link": "http://app.net"
        },
        "machine_only": false,
        "reply_to": null,
        "thread_id": "1",
        "num_replies": 0,
        "num_reposts": 0,
        "num_stars": 0,
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
            "links": []
        },
        "you_reposted": false,
        "you_starred": false
    },
    "meta": {
        "code": 200,
    }
}
```

### JSON Example

> POST https://alpha-api.app.net/stream/0/posts?include_post_annotations=1
> 
> Content-Type: application/json
> 
> DATA '{"text": "@berg FIRST post on this new site #newsocialnetwork", "annotations": [{"type": "net.app.core.geolocation", "value": {"latitude": 74.0064, "longitude": 40.7142}}]}'
```js
{
    "data": {
        "id": "1", // note this is a string
        "user": {
            ...
        },
        "created_at": "2012-07-16T17:25:47Z",
        "text": "@berg FIRST post on this new site #newsocialnetwork",
        "html": "<span itemprop=\"mention\" data-mention-name=\"berg\" data-mention-id=\"2\">@berg</span> FIRST post on this new site <span itemprop=\"hashtag\" data-hashtag-name=\"newsocialnetwork\">#newsocialnetwork</span>.",
        "source": {
            "client_id": "udxGzAVBdXwGtkHmvswR5MbMEeVnq6n4",
            "name": "Clientastic for iOS",
            "link": "http://app.net"
        },
        "machine_only": false,
        "reply_to": null,
        "thread_id": "1",
        "num_replies": 0,
        "num_reposts": 0,
        "num_stars": 0,
        "annotations": [
            {
                "type": "net.app.core.geolocation",
                "value": {
                    "latitude": 74.0064,
                    "longitude": 40.7142
                }
            }
        ],
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
            "links": []
        },
        "you_reposted": false,
        "you_starred": false
    },
    "meta": {
        "code": 200,
    }
}
```