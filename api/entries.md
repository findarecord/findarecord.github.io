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
> GET /v0/entries/entry:1c051674-a52c-4411-923d-4935a4120b94 HTTP/1.1

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````
{
  "code": 200,
  "messages": [],
  "timestamp": 1392226742714,
  "duration": 5,
  "data": {
    "repo_id": "repo:5bec95ea-a3f0-4e57-a119-434e194ee97b",
    "source_id": "fs-online:collection:1921547",
    "collection_id": "fs-online:collection:1921547",
    "geojson_id": "place:4a3dd60c-daa0-4577-9a03-5da1ac4a2b87/1",
    "from": 1911,
    "to": 1911,
    "name": "England and Wales Census, 1911",
    "tags": [
      "census"
    ],
    "area": 130207963111.13187,
    "free": true,
    "online": true,
    "id": "entry:1c051674-a52c-4411-923d-4935a4120b94"
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
  "timestamp": 1392225793058,
  "duration": 5,
  "data": [
    {
      "id": "entry:0d0b26b8-604e-4353-be3d-0dda505f709e",
      "repo_id": "repo:5c7ecb92-5167-4715-abf5-b52fa8034535",
      "source_id": "fs-catalog:title:205336",
      "collection_id": "fs-catalog:title:205336.5",
      "geojson_id": "place:af780812-01ca-453f-9763-27cc0c600afc/1",
      "from": 1849,
      "to": 1864,
      "name": "Parish registers for Gamlingay: Overseers rates, 1849-1864.",
      "tags": [
        "misc"
      ],
      "area": 12995391.630998915,
      "free": true,
      "online": false
    }
  ]
}
````