---
title: Can I see more detailed affiliation and publisher information in the REST API?
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
DataCite added support for affiliation identifiers in Metadata Schema 4.3 and publisher identifiers in Metadata Schema 4.5. By default, this information is not visible in the JSON REST API to avoid breaking changes that could cause problems with existing API integrations. Additional parameters can be added to REST API requests to include affiliation and publisher identifiers in the response. This applies to all types of requests (GET, POST, and PUT) and only affects the response body.

## Affiliation identifiers

Add the URL parameter `&affiliation=true` to your REST API requests to include affiliation identifiers in the response. This parameter changes the affiliation structure from a string to an array of objects. The objects will include the affiliation name, affiliationIdentifier, affiliationIdentifierScheme, and schemeUri when these are part of the DOI metadata.

```json
"affiliation": [  
  {  
    "name": "United States Geological Survey",  
    "schemeUri": "https://ror.org",  
    "affiliationIdentifier": "https://ror.org/035a68863",  
    "affiliationIdentifierScheme": "ROR"  
  }  
]
```

### Example requests

Display affiliation information for results of a query:

```curl
curl https://api.test.datacite.org/dois?query=climate%20change&affiliation=true
```

Display affiliation information for a specific DOI:

```curl
curl https://api.test.datacite.org/dois/10.24427/8gt9-nk59?affiliation=true
```

Search for a specific affiliation by name:

```curl
curl https://api.datacite.org/dois?query=creators.affiliation.name:%22University%20of%20Kentucky%22*&affiliation=true
```

## Publisher identifiers

Add the URL parameter `&publisher=true` to your REST API requests to include publisher identifiers in the response. This parameter changes the publisher structure from a string to an object. The object will include the publisher name, publisherIdentifier, publisherIdentifierScheme, schemeUri, and lang when these are part of the DOI metadata.

```json
"publisher": 
  {  
    "name": "Dryad",  
    "schemeUri": "https://ror.org",  
    "publisherIdentifier": "https://ror.org/00x6h5n95",  
    "publisherIdentifierScheme": "ROR",
    "lang": "en"
  }  
```

### Example requests

Display publisher information for results of a query:

```curl
curl https://api.test.datacite.org/dois?query=climate%20change&publisher=true
```

Display publisher information for a specific DOI:

```curl
curl https://api.test.datacite.org/dois/10.24427/8gt9-nk59?publisher=true
```