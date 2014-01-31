---
layout: default
title: places
---

# Places
Get places(s).

## GET /v0/places/:id
Retrieve a place.

### Parameters
(none)

### Example

`REQUEST`
> GET /v0/places/place:cada8149-c29c-4530-a802-82efe0d37f58 HTTP/1.1

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