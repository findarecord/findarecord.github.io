---
layout: default
title: sources
---

# Sources
These are the raw-ish representations of the information we have collected and imported. You probably will never need these.

## GET /v0/sources/:id
Retrieve a source.

### Parameters
(none)

### Example

`REQUEST`
> GET /v0/sources/fs-online:collection:1921547 HTTP/1.1

`RESPONSE`
> 200 (OK)
> Content-Type: application/json

````
{
    "code": 200,
    "messages": [],
    "timestamp": 1392227160990,
    "duration": 135,
    "data": {
        "description": "Imported on Mon Feb 03 2014 22:16:26 GMT+0000 (UTC)",
        "schema": "fs-online",
        "data": {
            "metadata": {
                "externalId": [
                    {
                        "value": "1921547",
                        "type": "org.familysearch.easy.collection_id"
                    }
                ],
                "language": {
                    "value": "en"
                },
                "type": "COLLECTION",
                "description": [
                    {
                        "value": "Census returns of England and Wales, 1911",
                        "lang": "en-US"
                    }
                ],
                "identifier": {
                    "value": "https://familysearch.org/records/collection/1921547"
                },
                "format": {
                    "value": "application/sord+xml"
                },
                "isPartOf": {
                    "countParam": null,
                    "offsetInParent": null,
                    "sortKeyInParent": null,
                    "type": "ARCHIVE",
                    "identifier": {
                        "value": "https://familysearch.org/records/collection"
                    },
                    "title": [
                        {
                            "value": "http://familysearch.org Records Archive",
                            "lang": "en-US"
                        }
                    ]
                },
                "title": [
                    {
                        "value": "England and Wales Census, 1911",
                        "lang": "en-US"
                    }
                ],
                "bibliographicCitation": "\"England and Wales Census, 1911.\" Index. <i>FamilySearch</i>. http://FamilySearch.org : accessed 2014. Citing \"1911 England and Wales census.\" Index and images. <i>findmypast.co.uk.</i> www.findmypast.co.uk : Brightsolid, n.d. PRO RG 14. The National Archives of the UK, Kew, Surrey.",
                "issued": {
                    "value": "2011-06-08T05:21:49.000Z"
                },
                "coverage": [
                    {
                        "recordType": "CENSUS",
                        "temporal": {
                            "end": "1911",
                            "start": "1911"
                        },
                        "spatial": [
                            {
                                "placeId": {
                                    "value": "1986340",
                                    "type": {
                                        "value": "https://api.familysearch.org/authorities/v1/place/"
                                    }
                                }
                            }
                        ]
                    },
                    {
                        "recordType": "CENSUS",
                        "temporal": {
                            "end": "1911",
                            "start": "1911"
                        },
                        "spatial": [
                            {
                                "placeId": {
                                    "value": "1986311",
                                    "type": {
                                        "value": "https://api.familysearch.org/authorities/v1/place/"
                                    }
                                }
                            }
                        ]
                    }
                ],
                "created": {
                    "value": "2011-06-08T05:21:49.000Z"
                },
                "creator": [
                    "www.findmypast.co.uk"
                ]
            },
            "leafSummary": [
                {
                    "type": "RECORD",
                    "count": 36354828,
                    "completeness": 100
                },
                {
                    "type": "IMAGE",
                    "count": 36354828,
                    "completeness": 100
                }
            ],
            "contents": {
                "content": [
                    {
                        "type": "CONTAINER",
                        "url": "https://familysearch.org/records/collection/1921547/records",
                        "title": null,
                        "sortKey": null,
                        "otherAttributes": {}
                    }
                ],
                "offset": 0,
                "contentType": "CONTAINER",
                "contentCount": 1,
                "contentsAreAlternatePartitionings": null,
                "countParam": null
            },
            "template": {
                "eventTypeMappings": [],
                "fields": [
                    {
                        "originalName": null,
                        "displayName": [
                            {
                                "value": "Name",
                                "lang": "en-US"
                            }
                        ],
                        "value": null,
                        "personId": null,
                        "fieldId": "PR_NAME"
                    },
                    {
                        "originalName": null,
                        "displayName": [
                            {
                                "value": "Event Type",
                                "lang": "en-US"
                            }
                        ],
                        "value": null,
                        "personId": null,
                        "fieldId": "EVENT_TYPE"
                    },
                    {
                        "originalName": null,
                        "displayName": [
                            {
                                "value": "Event Date",
                                "lang": "en-US"
                            }
                        ],
                        "value": null,
                        "personId": null,
                        "fieldId": "EVENT_DATE"
                    },
                    {
                        "originalName": null,
                        "displayName": [
                            {
                                "value": "Gender",
                                "lang": "en-US"
                            }
                        ],
                        "value": null,
                        "personId": null,
                        "fieldId": "PR_SEX_CODE"
                    },
                    {
                        "originalName": null,
                        "displayName": [
                            {
                                "value": "Age",
                                "lang": "en-US"
                            }
                        ],
                        "value": null,
                        "personId": null,
                        "fieldId": "PR_AGE_IN_YEARS"
                    },
                    {
                        "originalName": null,
                        "displayName": [
                            {
                                "value": "Birthplace",
                                "lang": "en-US"
                            }
                        ],
                        "value": null,
                        "personId": null,
                        "fieldId": "PR_BIRTH_PLACE"
                    },
                    {
                        "originalName": null,
                        "displayName": [
                            {
                                "value": "Schedule Type",
                                "lang": "en-US"
                            }
                        ],
                        "value": null,
                        "personId": null,
                        "fieldId": "RECORD_TYPE"
                    },
                    {
                        "originalName": null,
                        "displayName": [
                            {
                                "value": "Registration District",
                                "lang": "en-US"
                            }
                        ],
                        "value": null,
                        "personId": null,
                        "fieldId": "REGISTRATION_DISTRICT"
                    },
                    {
                        "originalName": null,
                        "displayName": [
                            {
                                "value": "Sub-District",
                                "lang": "en-US"
                            }
                        ],
                        "value": null,
                        "personId": null,
                        "fieldId": "SUB_DISTRICT"
                    },
                    {
                        "originalName": null,
                        "displayName": [
                            {
                                "value": "Parish",
                                "lang": "en-US"
                            }
                        ],
                        "value": null,
                        "personId": null,
                        "fieldId": "PARISH"
                    },
                    {
                        "originalName": null,
                        "displayName": [
                            {
                                "value": "County",
                                "lang": "en-US"
                            }
                        ],
                        "value": null,
                        "personId": null,
                        "fieldId": "COUNTY"
                    }
                ],
                "metadata": {
                    "type": null,
                    "coverage": [
                        {
                            "recordType": null,
                            "temporal": null
                        }
                    ]
                },
                "note": [],
                "id": "1",
                "sourceCitation": []
            },
            "search": {
                "url": "http://familysearch.org/searchapi/",
                "searchFields": [
                    {
                        "displayName": [
                            {
                                "value": "First Names",
                                "lang": "en-US"
                            }
                        ],
                        "searchFieldId": "givenname",
                        "controlType": null,
                        "controlUrl": null,
                        "minChars": null
                    },
                    {
                        "displayName": [
                            {
                                "value": "Last Names",
                                "lang": "en-US"
                            }
                        ],
                        "searchFieldId": "surname",
                        "controlType": null,
                        "controlUrl": null,
                        "minChars": null
                    },
                    {
                        "displayName": [
                            {
                                "value": "Birthplace",
                                "lang": "en-US"
                            }
                        ],
                        "searchFieldId": "birth_place",
                        "controlType": null,
                        "controlUrl": null,
                        "minChars": null
                    },
                    {
                        "displayName": [
                            {
                                "value": "Residence Place",
                                "lang": "en-US"
                            }
                        ],
                        "searchFieldId": "residence_place",
                        "controlType": null,
                        "controlUrl": null,
                        "minChars": null
                    },
                    {
                        "displayName": [
                            {
                                "value": "Gender",
                                "lang": "en-US"
                            }
                        ],
                        "searchFieldId": "gender",
                        "controlType": "list",
                        "controlUrl": "https://familysearch.org/searchapi/search/field/gender?collection_id=1921547",
                        "minChars": null
                    }
                ]
            },
            "completeness": null,
            "leafType": null,
            "leafCount": null,
            "note": [],
            "id": "1",
            "sourceCitation": []
        },
        "timestamp": 1391465786123,
        "user_id": 0,
        "source_id": "fs-online:collection:1921547"
    }
}
````