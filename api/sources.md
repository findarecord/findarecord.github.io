---
layout: default
title: sources
---

# Sources
Get sources(s).

## GET /v0/sources/:id
Retrieve a source.

### Parameters
(none)

### Example

`REQUEST`
> GET /v0/source/fs-online:collection:1666142 HTTP/1.1

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````
{
  code: 200
  messages: [ ]
  timestamp: 1391189633918
  duration: 0
  data: {}
}
````