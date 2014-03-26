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

### Hash variables

* `s` - place name string
* `lat` - latitude
* `lon` - longitude
* `r` - radius in meters; defaults to "10000"
* `t` - comma separated list of "tags" (record types); for example: "birth,death" or just "birth"; defaults to "birth,marriage,death"
