# Objects

* [Entities](#entities) are links, tags, and mentions in Posts and User descriptions.
* [Filters](#filter) allow you to only receive Posts you want from our Stream API.
* [Interactions](#interactions) show what other Users have done with your Posts (replies, starred, reposted, etc).
* [Posts](#post) are the central message of the App.net API.
* [Streams](#stream) are real-time, filterable view of all Posts and actions happening on App.net
* [Stream Markers](#stream-marker) allow a User's position in a Stream of posts to be saved and synced between Apps.
* [Users](#user) are the central object that takes actions in the App.net API.

## Notes on data formats

### Dates

Dates will be formatted as a **strict** subset of [ISO 8601](http://en.wikipedia.org/wiki/ISO_8601). Dates are parseable by almost any ISO 8601 date parser or merely by parsing from position. All dates will be formatted as follows:

`2012-12-31T13:22:55Z`

where `2012` is the year, `12` represents December, `31` represents the 31st day of the month, `13` represents 1 PM, `22` minutes and `55` seconds past the hour. All times will be expressed in terms of UTC.

This format was chosen to minimize ambiguity and edge cases in terms of parsing while maximizing readability of dates during
development.

### Object IDs

Object ids will always be transferred as strings to avoid issues with with limitations of JavaScript integers. You can assume that object ids are integers.
