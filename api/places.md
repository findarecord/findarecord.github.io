---
layout: default
title: places
---

# Places
These are places that we have imported from [Open Place Database](http://www.openplacedatabase).

## GET /v0/places/:id
Retrieve a place.

### Parameters
(none)

### Example

`REQUEST`
> GET /v0/places/place:4a3dd60c-daa0-4577-9a03-5da1ac4a2b87 HTTP/1.1

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````
{
    "code": 200,
    "messages": [],
    "timestamp": 1392228994677,
    "duration": 68,
    "data": {
        "id": "place:4a3dd60c-daa0-4577-9a03-5da1ac4a2b87",
        "version": 1,
        "names": [
            {
                "from": "2014-01-27",
                "to": "9999-12-31",
                "name": "England",
                "raw": "england"
            }
        ],
        "geojsons": [
            {
                "from": "2014-01-27",
                "to": "9999-12-31",
                "id": "1"
            }
        ],
        "sources": [
            "Initially imported from Natural Earth."
        ],
        "last_edited_time": 1390859582429,
        "last_edited_by": "1 - John Clark"
    }
}
````

## GET /v0/search/places
Search for places.

### Parameters

* `q` (Required) - A lucene query_string. `String` between 1 (inclusive) and 200 (inclusive) characters.
* `count` (Default 10) - The number of results to return. `Int` between 1 (inclusive) and 10000 (inclusive).
* `offset` (Default 0) - The number of results to skip. `Int` greather than or equal to 0.
* `type` (Default match) - The type of query to perform. `String` equal to `match` or `boolean` (exact match against the raw field).

### Example

`REQUEST`
> GET /v0/search/places?q=England&count=1 HTTP/1.1

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````
{
    "code": 200,
    "messages": [],
    "timestamp": 1392229292181,
    "duration": 31,
    "data": [
        {
            "id": "place:4a3dd60c-daa0-4577-9a03-5da1ac4a2b87",
            "score": 1.9159065,
            "names": [
                {
                    "from": "2014-01-27",
                    "to": "9999-12-31",
                    "name": "England",
                    "raw": "england"
                }
            ],
            "geojsons": [
                {
                    "from": "2014-01-27",
                    "to": "9999-12-31",
                    "id": "1"
                }
            ]
        }
    ]
}
````

`REQUEST`
> GET /v0/search/places?q=england&type=boolean HTTP/1.1

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````
{
    "code": 200,
    "messages": [],
    "timestamp": 1392229292181,
    "duration": 31,
    "data": [
        {
            "id": "place:4a3dd60c-daa0-4577-9a03-5da1ac4a2b87",
            "score": 1.9159065,
            "names": [
                {
                    "from": "2014-01-27",
                    "to": "9999-12-31",
                    "name": "England",
                    "raw": "england"
                }
            ],
            "geojsons": [
                {
                    "from": "2014-01-27",
                    "to": "9999-12-31",
                    "id": "1"
                }
            ]
        }
    ]
}
````