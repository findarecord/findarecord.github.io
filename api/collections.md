---
layout: default
title: collections
---

# Collections
Find-A-Record indexes collections of historical records and makes them available for searching.

## GET /v0/collections/:id
Retrieve a collection

### Parameters

* `return_geojson` (Default 0) - If present, geojson will be attached and returned

### Example

`REQUEST`
> GET /v0/collections/fs-online:collection:1921547 HTTP/1.1

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````
{
    "code": 200,
    "messages": [],
    "timestamp": 1392229940924,
    "duration": 172,
    "data": {
        "id": "fs-online:collection:1921547",
        "source_id": "fs-online:collection:1921547",
        "repo_id": "repo:5bec95ea-a3f0-4e57-a119-434e194ee97b",
        "name": "England and Wales Census, 1911",
        "from": 1911,
        "to": 1911,
        "tags": [
            "census"
        ],
        "payload": {
            "id": "1921547"
        }
    }
}
````

## POST /v0/search/collections
Search for collections using a geojson (passed in via body)

### Parameters

* `from` (Default -9999) - Return collections no earlier than from. `Int` between -9999 (inclusive) and 9999 (inclusive), but smaller than `to`.
* `to` (Default 9999) - Return collections no later than to. `Int` between -9999 (inclusive) and 9999 (inclusive), but larger than `from`.
* `tags` (Default "") - What to filter on. `String` of comma separated tags (Valid tags are `birth`,`marriage`,`death`,`census`,`misc`).
* `count` (Default 10) - The number of restuls to return. `Int` between 1 (inclusive) and 100 (inclusive).
* `offset` (Default 0) - The number of results to skip. `Int` greather than or equal to 0.
* `return_geojson` (Default 0) - If present, geojson will be attached and returned

### Example

`REQUEST`
> POST /v0/search/collections?tags=birth&count=1 HTTP/1.1
> Content-Type: application/json

````javascript
{ "type": "Polygon",
  "coordinates": [
    [ [-1, 52], [-2, 52], [-2, 53], [-1, 53], [-1, 52] ]
  ]
}
````

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````javascript
{
    "code": 200,
    "messages": [],
    "timestamp": 1392232887299,
    "duration": 847,
    "data": [
        {
            "id": "fs-online:collection:1911752",
            "source_id": "fs-online:collection:1911752",
            "repo_id": "repo:5bec95ea-a3f0-4e57-a119-434e194ee97b",
            "name": "England, Derbyshire, Church of England Parish Registers, 1538-1910",
            "from": 1538,
            "to": 1910,
            "tags": [
                "birth",
                "marriage",
                "death"
            ],
            "payload": {
                "id": "1911752"
            }
        }
    ]
}
````

`REQUEST`
> POST /v0/search/collections?tags=birth&count=1&return_geojson HTTP/1.1
> Content-Type: application/json

````javascript
{ "type": "Polygon",
  "coordinates": [
    [ [-1, 52], [-2, 52], [-2, 53], [-1, 53], [-1, 52] ]
  ]
}
````

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````javascript
{
    "code": 200,
    "messages": [],
    "timestamp": 1392232887299,
    "duration": 847,
    "data": [
        {
            "id": "fs-online:collection:1911752",
            "source_id": "fs-online:collection:1911752",
            "repo_id": "repo:5bec95ea-a3f0-4e57-a119-434e194ee97b",
            "name": "England, Derbyshire, Church of England Parish Registers, 1538-1910",
            "from": 1538,
            "to": 1910,
            "tags": [
                "birth",
                "marriage",
                "death"
            ],
            "payload": {
                "id": "1911752"
            },
            "geojson":{
                "type":"Polygon",
                "coordinates":[]
            }
        }
    ]
}
````