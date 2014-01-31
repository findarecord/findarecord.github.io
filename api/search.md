---
layout: default
title: search
---

# Search
Search for collections, places, etc.

## GET /v0/search/collections
Search for collections using a simple radius search

### Parameters
* `lat` (Required) - The latitude to search on (WGS84 datum). `Float` between -90 (inclusive) and 90 (inclusive).
* `lon` (Required) - The longitude to search on (WGS84 datum). `Float` between -180 (inclusive) and 180 (inclusive).
* `radius` (Default 10) - The distance if the search radius (in km). `Int` between 1 (inclusive) and 100 (inclusive).
* `from` (Default -9999) - Return collections no earlier than from. `Int` between -9999 (inclusive) and 9999 (inclusive), but smaller than `to`.
* `to` (Default 9999) - Return collections no later than to. `Int` between -9999 (inclusive) and 9999 (inclusive), but larger than `from`.
* `tags` (Default "") - The distance if the search radius (in km). `String` of comma separated tags (Valid tags are `birth`,`marriage`,`death`,census`,`misc`).
* `count` (Default 10) - The number of restuls to return. `Int` between 1 (inclusive) and 100 (inclusive).
* `offset` (Default 0) - The number of collections to skip. `Int` between 0 (inclusive) and 1000 (inclusive).

### Example

`REQUEST`
> GET /v0/search/collections?lat=52.32*lon=-2.54&tags=birth,marriage HTTP/1.1

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

## POST /v0/search/collections
Search for collections using a geojson (passed in via body)

### Parameters
* `from` (Default -9999) - Return collections no earlier than from. `Int` between -9999 (inclusive) and 9999 (inclusive), but smaller than `to`.
* `to` (Default 9999) - Return collections no later than to. `Int` between -9999 (inclusive) and 9999 (inclusive), but larger than `from`.
* `tags` (Default "") - The distance if the search radius (in km). `String` of comma separated tags (Valid tags are `birth`,`marriage`,`death`,census`,`misc`).
* `count` (Default 10) - The number of restuls to return. `Int` between 1 (inclusive) and 100 (inclusive).
* `offset` (Default 0) - The number of collections to skip. `Int` between 0 (inclusive) and 1000 (inclusive).

### Example

`REQUEST`
> POST /v0/search/collections?tags=birth,marriage HTTP/1.1
> Content-Type: application/json

````
{ "type": "Polygon",
    "coordinates": [
      [ [100.0, 0.0], [101.0, 0.0], [101.0, 1.0], [100.0, 1.0], [100.0, 0.0] ]
      ]
   }
````

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

## GET /v0/search/places
Search for places. To use a lucene style querystring make sure to set `type` to "querystring".

### Parameters
* `q` (Required) - The actual query string. `String` between 1 and 200 characters.
* `type` (Default "match") - The type of query to perform. `String` must be one of "match", "querystring", "boolean".
* `count` (Default 10) - The number of restuls to return. `Int` between 1 (inclusive) and 100 (inclusive).
* `offset` (Default 0) - The number of collections to skip. `Int` between 0 (inclusive) and 1000 (inclusive).

### Example

`REQUEST`
> GET /v0/search/places?q=Knighton on Teme, England HTTP/1.1

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