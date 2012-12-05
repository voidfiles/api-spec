## Update a Stream Marker

Update the User's current place in a Stream. To update a Stream Marker, you can POST an object that matches the [Stream Marker schema](../objects/stream_marker.md) with an HTTP header of ```Content-Type: application/json```. Only the ```id```, ```name```, and ```percentage``` fields will be used. ```name``` will come from the marker you received in the last GET request you made for the stream.

The purpose of a Stream Marker is _not_ to allow a user to scroll a stream on one device and see the scroll happen on another device in realtime. A stream marker should only be updated when a user has stopped scrolling (i.e. the stream's position hasn't changed in multiple seconds) or when the app is being closed. Please make sure your code understands our [rate limit headers](../authentication/limits.md#response-headers) so if the rate limits for this endpoint change in the future your app handles this gracefully.

> This endpoint is currently migrated by the ```response_envelope``` migration. Please refer to the [Migrations documentation](/appdotnet/api-spec/blob/master/migrations.md#current-migrations) for more info.

### URL
> https://alpha-api.app.net/stream/0/posts/marker

### Data

None.

### Example

> POST https://alpha-api.app.net/stream/0/posts/marker
>
> Content-Type: application/json
> 
> DATA {"name": "global", "id": 2}
```js
{
    "data": {
        "id": "2",
        "name": "global",
        "percentage": 0,
        "updated_at": "2012-11-12T20:04:58Z",
        "version": "d95o2uzYI7q7tY7bHI4U1xBug7s"
    },
    "meta": {
        "code": 200
    }
}
```