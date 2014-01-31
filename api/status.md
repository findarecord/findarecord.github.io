---
layout: default
title: status
---

# Status
Show the status of the Find-A-Record API.

## GET /status

### Parameters
(none)

### Example

`REQUEST`
> GET /status HTTP/1.1

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