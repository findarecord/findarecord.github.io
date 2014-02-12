---
layout: default
title: status
---

# Status
Show the status of the Find-A-Record API.

## GET /v0/status

### Parameters
(none)

### Example

`REQUEST`
> GET /v0/status HTTP/1.1

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````
{
  code: 200
  messages: [ ]
  timestamp: 1391189633918
  duration: 0
  data: true
}
````