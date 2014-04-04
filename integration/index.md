---
layout: default
title: Integration
---

# Integration
There are two main types of integration with Find-a-Record. 

## API Integration
This is where you call Find-A-Record's APIs and display the information in your own application. You will need to get an API key from Find-A-Record, and then you can call any of the APIs documented [here](/api/).

## Web Integration
This is where you forward your user over to the search page at [findarecord.com/search](https://www.findarecord.com/search). You can prefill all of the parameters by setting the appropriate variables in the URL hash.

### Hash Parameters

| parameter  | default | description |
| ------------- | ------------- | -------------- |
| `s` | | Place name string. If this is present without a longitude and latitude, we will attempt to automatically geocode it to set the longitude and latitude. |
| `lat` | User's IP location | Longitude. |
| `lat` | User's IP location | Latitude. |
| `r` | `10000` | Search radius in meters. |
| `t` | `birth,marriage,death` | Comma separate list of record types (tags). |
| `from` | | Only include collections that cover years including or after this year. |
| `to` | | Only include collections that cover years including or before this year. |
| `free` | `true` | `true` or `false` |
| `online` | `true` | `true` or `false` |
