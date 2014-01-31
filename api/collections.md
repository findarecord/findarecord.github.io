---
layout: default
title: collections
---

# Collections
Get collection(s).

## GET /v0/collections/:id
Retrieve a collection

### Parameters
(none)

### Example

`REQUEST`
> GET /v0/collections/fs-online:collection:1666142 HTTP/1.1

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