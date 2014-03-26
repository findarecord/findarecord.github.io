---
layout: default
title: Integration
---

# Integration
There are two main types of integration with Find-a-Record. 

## API Integration
This is where you call Find-A-Record's APIs and display the information in your own application. You will need to get an API key from Find-A-Record, and then you can call any of the APIs documented [here](/api/).

## Web Integration
This is where you forward your user over to the search page at [findarecord.com/search](https://www.findarecord.com/search). You can prefill all of the parameters by setting the appropriate variables in the URL Hash

### Hash Parameters

| parameter  | default | description |
| ------------- | ------------- | -------------- |
| `s` | | place name string |
| `lat` | user's IP location | latitude |
| `lat` | user's IP location | longitude |
| `r` | `10000` | radius in meters |
| `t` | `birth,marriage,death` | comma separate list of record types (tags) |
