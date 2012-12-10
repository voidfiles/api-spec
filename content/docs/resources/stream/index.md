# Streams

**These features are still highly experimental. If you make use of them, please idle in our [developer chat room](https://www.hipchat.com/garqCaGOZ) so you can report bugs and we can communicate updates.**

## General Information

### Basic Use

A Stream is a real-time, ordered collection of messages. A message will always be a [response envelope](/appdotnet/api-spec/blob/master/migrations.md#current-migrations). If you are receiving a message about an object, the ```data``` key will contain that object. Some actions (like following a user) will contain extra information in the ```meta``` key.

There are 3 different kinds of Streams, but they all follow the same pattern:

* Public stream: A Stream containing all public activity. **It must be accessed with an [App access token](/appdotnet/api-spec/blob/master/auth.md#app-access-token-flow)**.

* Coming soon:
    * User stream: A Stream for a single User's view of App.net. This is a Stream version of the [Retrieve a User's personalized stream]
(/appdotnet/api-spec/blob/master/resources/posts.md#retrieve-a-users-personalized-stream) endpoint. It is very useful for client
based Apps that need a single User's Stream. **It must be accessed with a User access token**.
    * App stream: A Stream for Apps to request multiple Users Streams at once. It is very useful for server based Apps that need the
streams of lots of users. **It must be accessed with an App access token**.

Since memory and bandwidth is not unlimited, each Stream has associated limits. App.net maintains a buffer of messages to send to a
client, but if that buffer fills, your Stream will be disconnected. Please ensure that you are only requesting streams of data that
you can actually process.

### Filters

Streams will give you lots of data, much of which your application may not want. A [Filter](../objects/filter.md) can be passed to the [stream creation endpoint](#create-a-stream) to control what messages are actually delivered to your App by our servers.

### Response Format

A Stream is a long-lived HTTP connection that enables clients to receive messages in near real-time from App.net.

When a Stream is established, App.net will send response that includes the ```endpoint``` that the app can use to consume the newly created stream. You may pass ?purge=1 if you do not wish to receive any messages previously queued up for this stream.

Once connected to the stream endpoint, the response will be encoded using HTTP ```Transfer-Encoding: chunked```.

The Stream contains frames separated by ```\r\n```. For example:


    HELLO\r\nWORLD!!!\r\n


#### Control Message

A control message is a JSON object that gives the client important information about the current Stream. For instance, if the buffer
is getting too full, the client will receive a control message with that warning. A control message will always have ```control```
as a key in the object so it is easy to distinguish from a Post.
