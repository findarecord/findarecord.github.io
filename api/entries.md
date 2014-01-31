---
layout: default
title: entries
---

# Places
Get entries.

## GET /v0/entries/:id
Retrieve a entry.

### Parameters
(none)

### Example

`REQUEST`
> GET /v0/entries/entry:0000002d-c878-4bbc-9c38-98f2834eb064 HTTP/1.1

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