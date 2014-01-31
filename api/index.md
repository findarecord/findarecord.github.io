---
layout: default
title: API docs
---

# API
The public api lives at https://api.findarecord.com. This is the same API used by [www.findarecord.com](https://www.findarecord.com), and is currently at v0.

# Overview
The Find-A-Record API is REST-ish in nature, and is divided into several sections. The URL is structured as follows
````
[https://][api.findarecord.com]/[v0]/[section]/[section-specific]
    |               |           |      |        |
    |               |           |      |        +- Everything here and beyond is specific to each section.
    |               |           |      |
    |               |           |      +- The section of the API (collections, search, etc...)
    |               |           |
    |               |           +- The API version (Currently at v0)
    |               |
    |               +- The base URL
    |
    +- The protocol. Our API runs on https ONLY (via port 443)
````

## Authentication
Authentication is done via 2 URL parameters, `user_id` and `key`. Every endpoint is authenticated except for status. An invalid user_id/key combination will result in a 401 being returned.
To obtain development or production credentials, contact Find-A-Record.

## Response HTTP Status Codes
We use standard HTTP status codes when responding to a request. The actual response's status code will always match the Return Object's code (See below). This means that you will get a 404 NOT FOUND from an API endpoint when the requested information is not found. Please note that the JSON return object is always returned, even for non-200 HTTP status codes.

## Response Return Object
The following JSON object is always returned.
````javascript
{
  "code":200,
  "messages":[],
  "timestamp":1383063137924,
  "duration":20,
  "data":{}
}
````
* `code` - An HTTP status code. Will always be an integer.
* `messages` - An array of message strings.
* `timestamp` - A timestamp of when the request was received by our servers (UTC). It is the output of Javascript Date.now();
* `duration` - The total time spent in milliseconds processing the request on our servers. It does not include time for DNS lookup, connection, Receiving, or Sending.
* `data` - The data returned. See the documentation below.

# API Sections

## Status
[Docs](status) - A basic status endpoint.

## Search
[Docs](search) - A set of search endpoints (collections, places, etc).

## Collections
[Docs](collections) - Retrieve information about collections.

## Places
[Docs](places) - Retrieve information about places.

## Repos
[Docs](repos) - Retrieve information about repositories.

# Other API Sections

## Sources
[Docs](sources) - These are the source documents that we use to derive collection and entry information. Unless you are helping us debug something, nothing to see here.

## Entries
[Docs](entries) - An entry is analogous to an entry in an index. The endpoints here return entry information. You probably want to search Collections instead (See above).