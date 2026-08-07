---
title: >-
  How do I know which metadata elements to include in the body of a request to
  the DataCite JSON REST API?
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
The DataCite REST API uses a standard JSON API format based on [https://jsonapi.org/](https://jsonapi.org/).  The elements correspond to the [DataCite metadata schema](http://schema.datacite.org/). The best way to see the properties in JSON is to look at the response from a DOI request.

Example:
https://api.test.datacite.org/dois/10.70126/t70h-qt35?affiliation=true 

The [API reference](https://support.datacite.org/reference/post_dois) also lists all the possible property options for the REST API. In most cases it is best to start from the [REST API guide](doc:api), make the basics, then work with the metadata schema to add mandatory/recommended fields as appropriate (e.g. Identifier).

There is also an [OpenAPI specification](https://github.com/datacite/lupo/blob/master/openapi.yaml) available in Github which describes the REST API.