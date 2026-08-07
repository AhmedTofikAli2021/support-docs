---
title: What is the "identifiers" attribute in the REST API?
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
In the REST API, the `identifiers` attribute contains alternateIdentifier metadata and is equivalent to the `alternateIdentifiers` property in the DataCite Metadata Schema. 

> 📘 
> 
> The `identifiers` attribute in the REST API is unrelated to the mandatory `identifier` property in the DataCite Metadata Schema.

The `identifiers` attribute is always returned by the REST API when retrieving DOI metadata. The `alternateIdentifiers` attribute, which contains the same metadata as the `identifiers` attribute although with differently named sub-attributes, is returned only under certain conditions. For example, when creating a DOI, retrieving a single DOI's metadata, or when the `?detail=true` URL parameter is appended to requests to the `/dois` endpoint.

When creating or updating DOI alternateIdentifier metadata, the REST API accepts values in either the `alternateIdentifiers` or `identifiers` attributes. Including metadata in either attribute will populate the `identifiers` and `alternateIdentifiers` attributes in the REST API response and the `alternateIdentifiers` property in DataCite XML. 

Example JSON payload using the `identifiers` attribute to update a DOI's alternateIdentifier metadata: 

```json
{
    "data": {
        "type": "dois",
        "attributes": {
            "identifiers": [
                {
                    "identifier": "urn:nbn:de:0168-ssoar-426160",
                    "identifierType": "URN"
                }
            ]
        }
    }
}
```

Example JSON payload using the `alternateIdentifiers` attribute to update a DOI's alternateIdentifier metadata:

```json
{
    "data": {
        "type": "dois",
        "attributes": {
            "alternateIdentifiers": [
                {
                    "alternateIdentifier": "urn:nbn:de:0168-ssoar-426160",
                    "alternateIdentifierType": "URN"
                }
            ]
        }
    }
}
```



When creating or updating DOI alternateIdentifier metadata using the REST API, if an `identifiers` attribute is included in your request, any metadata sent in the `alternateIdentifiers` attribute _will be ignored_.