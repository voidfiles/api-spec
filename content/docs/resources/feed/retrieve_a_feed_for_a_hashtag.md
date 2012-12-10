## Retrieve a feed for a hashtag

Retrieve a [feed](#feed) for the specified hashtag. This endpoint is similar to the '[Retrieve tagged Posts](/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-tagged-posts)' endpoint.

### URL
> https://alpha-api.app.net/feed/rss/posts/tag/hashtag

### Example
> GET https://alpha-api.app.net/feed/rss/posts/tag/hashtag

```xml
<?xml version='1.0' encoding='utf-8'?>
<rss xmlns:atom="http://www.w3.org/2005/Atom" version="2.0">
    <channel>
        <title>#hashtag - App.net</title>
        <link>https://alpha.app.net/hashtags/hashtag</link>
        <description>Posts about #hashtag</description>
        <atom:link href="https://alpha-api.app.net/feed/rss/posts/tag/hashtag" type="application/rss+xml"/>
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