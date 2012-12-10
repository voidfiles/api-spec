## Retrieve a feed for a User

Retrieve a [feed](#feeds) for the User [@voidfiles](http://alpha.app.net/voidfiles). This endpoint is similar to the '[Retrieve Posts created by a User](/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-posts-created-by-a-user)' endpoint.

### URL
> https://alpha-api.app.net/feed/rss/users/@username/posts

### Example

> GET https://alpha-api.app.net/feed/rss/users/@voidfiles/posts

```xml
<?xml version='1.0' encoding='utf-8'?>
<rss xmlns:atom="http://www.w3.org/2005/Atom" version="2.0">
    <channel>
        <title>Posts from voidfiles on App.net</title>
        <link>https://alpha.app.net/voidfiles</link>
        <description>Hi, I work at App.net</description>
        <atom:link href="https://alpha-api.app.net/feed/rss/users/@voidfiles/posts" type="application/rss+xml"/>
        <image>
            <title>Posts from voidfiles on App.net</title>
            <link>https://alpha.app.net/voidfiles</link>
            <url>https://dqdwyydysypcm.cloudfront.net/image/4/Go50UQd5N9mi_APkpQt9JAp4ZsDfMlOTnoB4P-0N5rmpFGtnro2b52yUcUr_bPbxKlxx_4EHHiujdE-RRpSB6oZd0bHGy4xKlwInNBClbebDS7DoyyPHtIK9LY5x-kQSdnPKyKhtogJxD04SGOQMLPkCasZM42nLVgZIIhcbmbBrzxNJaoRoCNOrzS1ib9fQcAwPEg</url>
        </image>
        <item>
            <title>voidfiles: #hashtag test</title>
            <description>
                <span itemscope="https://join.app.net/schemas/Post"><a href="https://alpha.app.net/hashtags/hashtag" itemprop="hashtag" data-hashtag-name="hashtag">#hashtag</a> test</span>
            </description>
            <pubDate>Fri, 31 Aug 2012 17:15:31 +0000</pubDate>
            <guid>https://alpha.app.net/voidfiles/post/1387</guid>
            <link>https://alpha.app.net/voidfiles/post/1387</link>
            <category>hashtag</category>
        </item>
    </channel>
</rss>
```