---
layout: default
title: collections
---

# Collections
Find-A-Record indexes collections of historical records and makes them available for searching.

## GET /v0/collections/:id
Retrieve a collection

### Parameters

* `return_repo` (Default false) - If present, the repository information will be included

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
        },
        "place_ids": [
            "place:4a3dd60c-daa0-4577-9a03-5da1ac4a2b87/1",
            "place:f09e35f6-ea11-4a6c-a868-73d855e4f099/1"
        ],
        "description": "Census returns of England and Wales, 1911"
    }
}
````

`REQUEST`
> GET /v0/collections/fs-online:collection:1921547?return_repo HTTP/1.1

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````
{
    "code": 200,
    "messages": [],
    "timestamp": 1395851863436,
    "duration": 13,
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
        },
        "place_ids": [
            "place:4a3dd60c-daa0-4577-9a03-5da1ac4a2b87/1",
            "place:f09e35f6-ea11-4a6c-a868-73d855e4f099/1"
        ],
        "description": "Census returns of England and Wales, 1911",
        "url": "https://familysearch.org/search/collection/1921547",
        "instructions": "Search this database online at <a target=\"_blank\" href=\"https://familysearch.org/search/collection/1921547\">familysearch.org</a>",
        "repo": {
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
}
````

## POST /v0/search/collections
Search for collections using a geojson (passed in via body)

### Parameters

* `from` (Default -9999) - Return collections no earlier than from. `Int` between -9999 (inclusive) and 9999 (inclusive), but smaller than `to`.
* `to` (Default 9999) - Return collections no later than to. `Int` between -9999 (inclusive) and 9999 (inclusive), but larger than `from`.
* `tags` (Default "") - What to filter on. `String` of comma separated tags (Valid tags are `birth`,`marriage`,`death`,`census`,`misc`).
* `online` (Default "") - Return collections from only either online or offline repositories. `String` of either `true` or `false`. When parameter is unset, collections from both online and offline repositories are returned.
* `free` (Default "") - Return collections from only either free or paid repositories. `String` of either `true` or `false`. When parameter is unset, collections from both free and paid repositories are returned.
* `count` (Default 10) - The number of restuls to return. `Int` between 1 (inclusive) and 100 (inclusive).
* `offset` (Default 0) - The number of results to skip. `Int` greather than or equal to 0.
* `return_repos` (Default false) - If present, repository information will be returned as well

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
    "timestamp": 1395852643899,
    "duration": 2548,
    "data": [
        {
            "id": "fs-online:collection:1473014",
            "source_id": "fs-online:collection:1473014",
            "repo_id": "repo:5bec95ea-a3f0-4e57-a119-434e194ee97b",
            "name": "England Births and Christenings, 1538-1975",
            "from": 1538,
            "to": 1975,
            "tags": [
                "birth"
            ],
            "payload": {
                "id": "1473014"
            },
            "place_ids": [
                "place:4a3dd60c-daa0-4577-9a03-5da1ac4a2b87/1"
            ],
            "description": "Index to selected England births and christenings.  Only a few localities are included and the time period varies by locality.  Due to privacy laws, recent records may not be displayed.  The year range represents most of the records. A few records may be earlier or later.  "
        }
    ]
}
````

`REQUEST`
> POST /v0/search/collections?tags=birth&count=1&return_repos HTTP/1.1
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
    "timestamp": 1395852827176,
    "duration": 2615,
    "data": [
        {
            "id": "fs-online:collection:1473014",
            "source_id": "fs-online:collection:1473014",
            "repo_id": "repo:5bec95ea-a3f0-4e57-a119-434e194ee97b",
            "name": "England Births and Christenings, 1538-1975",
            "from": 1538,
            "to": 1975,
            "tags": [
                "birth"
            ],
            "payload": {
                "id": "1473014"
            },
            "place_ids": [
                "place:4a3dd60c-daa0-4577-9a03-5da1ac4a2b87/1"
            ],
            "description": "Index to selected England births and christenings.  Only a few localities are included and the time period varies by locality.  Due to privacy laws, recent records may not be displayed.  The year range represents most of the records. A few records may be earlier or later.  ",
            "url": "https://familysearch.org/search/collection/1473014",
            "instructions": "Search this database online at <a target=\"_blank\" href=\"https://familysearch.org/search/collection/1473014\">familysearch.org</a>",
            "repo": {
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
    ]
}
````