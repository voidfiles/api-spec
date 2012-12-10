# Feeds

## General Information

### Basic Use

Feeds describe our system for simple syndication of public posts on App.net. We currently support RSS as a syndication format. This means you should be able to use them anywhere you currently use RSS feeds.

There are 2 different kinds of feeds, but they all follow the same pattern:

* Users Post feed: A feed for a single User's public posts on App.net. This is a feed version of the [Retrieve Posts created by a User](/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-posts-created-by-a-user) endpoint.
* Hashtag feed: A feed containing all public Posts that are tagged with a specific hashtag. This is a feed version of the [Retrieve tagged Posts](/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-tagged-posts) endpoint.

We intend to support more feed formats and richer support for filters in the near future.

*Note:* While the URLs are similar to other API URLs feeds, they are under a different root.

### Filters

Feeds do not currently support filters or general parameters like the JSON API.

### Response Format

All responses are returned as RSS. We are following the spec for RSS 2.0 as described in the [RSS 2.0 specification](http://cyber.law.harvard.edu/rss/rss.html).