---
layout: default
title: entries
---

# Entries
These are analagous to entries in the collection index that we use when searching for collections. You most likely want [collections](/api/collections).

## GET /v0/entries/:id
Retrieve a entry.

### Parameters
(none)

### Example

`REQUEST`
> GET /v0/entries/entry:3d0daa84-258d-42f9-8c26-f916d13846b6 HTTP/1.1

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````
{
    "code": 200,
    "messages": [],
    "timestamp": 1395853205897,
    "duration": 15,
    "data": {
        "repo_id": "repo:5c7ecb92-5167-4715-abf5-b52fa8034535",
        "source_id": "fs-catalog:title:552584",
        "collection_id": "fs-catalog:title:552584.5",
        "geojson_id": "place:af780812-01ca-453f-9763-27cc0c600afc/1",
        "from": 1881,
        "to": 1881,
        "name": "Census returns for Gamlingay, 1841-1891: 1881",
        "tags": [
            "misc"
        ],
        "free": true,
        "online": false,
        "place_name": "Gamlingay CP, Cambridgeshire, England",
        "id": "entry:3d0daa84-258d-42f9-8c26-f916d13846b6"
    }
}
````

## GET /v0/search/entries
Search for entries.

### Parameters

* `q` (Required) - A lucene query_string. `String` between 1 (inclusive) and 200 (inclusive) characters.
* `count` (Default 10) - The number of results to return. `Int` between 1 (inclusive) and 10000 (inclusive).
* `offset` (Default 0) - The number of results to skip. `Int` greather than or equal to 0.

### Example

`REQUEST`
> GET /v0/search/entries?q=Gamlingay&count=1 HTTP/1.1

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````
{
    "code": 200,
    "messages": [],
    "timestamp": 1395853158715,
    "duration": 30,
    "data": [
        {
            "repo_id": "repo:5c7ecb92-5167-4715-abf5-b52fa8034535",
            "source_id": "fs-catalog:title:552584",
            "collection_id": "fs-catalog:title:552584.5",
            "geojson_id": "place:af780812-01ca-453f-9763-27cc0c600afc/1",
            "from": 1881,
            "to": 1881,
            "name": "Census returns for Gamlingay, 1841-1891: 1881",
            "tags": [
                "misc"
            ],
            "free": true,
            "online": false,
            "place_name": "Gamlingay CP, Cambridgeshire, England",
            "id": "entry:3d0daa84-258d-42f9-8c26-f916d13846b6"
        }
    ]
}
````