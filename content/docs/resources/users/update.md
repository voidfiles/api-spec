## Update a User

Updates a specific <a href="../objects/user.md">User's</a> profile details. You can update a user by PUTing an object that matches the [user schema](../objects/user.md) with an HTTP header of ```Content-Type: application/json```. You must provide values for each of the following keys: ```name```, ```locale```, ```timezone```, and ```description```. For the description, you must specify ```description.text``` as a child key. You can also specific [custom links](../objects/entities.md#user-specified-entities) for a user description.

If you want to add or update a User's annotations, you may include the optional ```annotations``` key and pass in the annotations that are changing.

> This endpoint is currently migrated by the ```response_envelope``` migration. Please refer to the [Migrations documentation](/appdotnet/api-spec/blob/master/migrations.md#current-migrations) for more info.

### Required Scopes

* ```update_profile```

### URL
> https://alpha-api.app.net/stream/0/users/me

### Data

None.

### Example

> PUT https://alpha-api.app.net/stream/0/users/me?include_user_annotations=1
>
> Content-Type: application/json
>
> DATA {"name": "Mark Thurman 2", "locale":"en", "timezone":"US/Central", "description":{"text": "new description"}, "annotations":[{"type": "net.app.core.directory.blog", "value": {"url": "http://mynewblog.com"}}]}
```js
{
    "data": {
        "id": "1", // note this is a string
        "username": "mthurman",
        "name": "Mark Thurman 2",
        "description": {
           "text": "new description",
           "html": "new description",
           "entities": {}
        },
        "timezone": "US/Central",
        "locale": "en",
        "avatar_image": {
            "height": 512,
            "width": 512,
            "url": "https://example.com/avatar_image.jpg"
        },
        "cover_image": {
            "height": 118,
            "width": 320,
            "url": "https://example.com/cover_image.jpg"
        },
        "type": "human",
        "created_at": "2012-07-16T17:23:34Z",
        "counts": {
            "following": 100,
            "followers": 200,
            "posts": 24,
            "stars": 76
        },
        "annotations": [
            {
                "type": "net.app.core.directory.blog",
                "value": "http://mynewblog.com"
            }
        ]
    },
    "meta": {
        "code": 200
    }
}
```