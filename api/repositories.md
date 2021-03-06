---
layout: default
title: repos
---

# Repositories
Each repository represents a location that collections can be found. This may be online or in a physical location.

## GET /v0/repositories/:id
Retrieve a repository

### Parameters
(none)

### Example

`REQUEST`
> GET /v0/repositories/repo:5bec95ea-a3f0-4e57-a119-434e194ee97b HTTP/1.1

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````
{
    "code": 200,
    "messages": [],
    "timestamp": 1395853059585,
    "duration": 6,
    "data": {
        "name": "FamilySearch",
        "free": true,
        "online": true,
        "coordinates": null,
        "url": "https://familysearch.org/",
        "description": "",
        "url_template": "https://familysearch.org/search/collection/{{id}}",
        "payload_template": "Search this database online at <a target=\"_blank\" href=\"https://familysearch.org/search/collection/{{id}}\">familysearch.org</a>",
        "payload_descr": {
            "id": "FS collection id"
        },
        "contact_info": {},
        "sources": 1711,
        "collections": 934
    }
}
````