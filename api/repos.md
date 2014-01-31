---
layout: default
title: repos
---

# Repositories
Get repositories.

## GET /v0/repos/:id
Retrieve a repository

### Parameters
(none)

### Example

`REQUEST`
> GET /v0/repos/repo:5bec95ea-a3f0-4e57-a119-434e194ee97b HTTP/1.1

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