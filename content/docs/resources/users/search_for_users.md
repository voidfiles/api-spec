## Search for Users

Search the App.net userbase.

> This endpoint is currently migrated by the ```response_envelope``` migration. Please refer to the [Migrations documentation](/appdotnet/api-spec/blob/master/migrations.md#current-migrations) for more info.

### URL

> https://alpha-api.app.net/stream/0/users/search

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
            <td><code>q</code></td>
            <td>Required</td>
            <td>string</td>
            <td>The search query. Supports @username or #tag searches as well as normal search terms. Searches username, display name, bio information. <b>Does not search posts.</b></td>
        </tr>
    </tbody>
</table>

### Example

> GET https://alpha-api.app.net/stream/0/users/search?q=%23mondaynightdanceparty

```js
{
  "data": [
    {
      "avatar_image": {
        "height": 200,
        "url": "https://d2rfichhc2fb9n.cloudfront.net/image/4/sRRkCKVga-subI-q0oTsiuUAoo6ZP-f4g0xneKB89OxKGrmNizM78Qv0p-FKRFekdLWy58o7cl21DQILfGJjQz-GKlisIUWI3ENw4YISVZnDKJM7f359Fuqq3ckhBmWO5xVBWrlIOi3odNtOjPeJdwv70B0",
        "width": 200
      },
      "counts": {
        "followers": 97,
        "following": 58,
        "posts": 934,
        "stars": 25
      },
      "cover_image": {
        "height": 250,
        "url": "https://d2rfichhc2fb9n.cloudfront.net/image/4/JeN1azqHPSPuzGtfk07SU7S7Hp4WNYIfiO_CiNxJ_gt9dnx4-ltGJZInJi7-ipXzrokyK7jUtQl8p6g2L6FOIIha9IU_Fm74AIDhftD6XvbGDPUS3s3pKSWGeyDkS28zL-RjyrfQHNpVLsJhgE0L6UuVfao",
        "width": 960
      },
      "created_at": "2012-08-10T21:28:45Z",
      "description": {
        "entities": {
          "hashtags": [
            {
              "len": 22,
              "name": "MondayNightDanceParty",
              "pos": 23
            }
          ],
          "links": [
            {
              "len": 13,
              "pos": 57,
              "text": "s3rv.com/mndp",
              "url": "http://s3rv.com/mndp"
            }
          ],
          "mentions": []
        },
        "html": "<span itemscope=\"https://app.net/schemas/Post\">gamer, dev, debaser\r\n\r\n<span itemprop=\"hashtag\" data-hashtag-name=\"MondayNightDanceParty\">#MondayNightDanceParty</span> details at <a href=\"http://s3rv.com/mndp\">s3rv.com/mndp</a>.</span>",
        "text": "gamer, dev, debaser\r\n\r\n#MondayNightDanceParty details at s3rv.com/mndp."
      },
      "follows_you": true,
      "id": "1411",
      "is_follower": true,
      "is_following": true,
      "is_muted": false,
      "locale": "en",
      "name": "Robert",
      "timezone": "America/Chicago",
      "type": "human",
      "username": "33mhz",
      "you_follow": true,
      "you_muted": false
    }
  ],
  "meta": {
    "code": 200
  }
}
```