---
title: DataCite REST API Guide
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
[block:callout]
{
  "type": "warning",
  "body": "The current version of the REST API is version 2. If you are using the endpoints `/works`, `/members`, or `/data-centers`, you are using [version 1](doc:api-v1).",
  "title": "REST API versions"
}
[/block]
# Purpose of the DataCite REST API

The [DataCite REST API](https://support.datacite.org/reference) allows any user to retrieve, query and browse DataCite DOI metadata records. In addition, DataCite Clients can register DOIs and DataCite Providers can manage Clients and prefixes via the API. 

The API is generally RESTful and returns results in JSON, as the API follows the [JSONAPI](http://jsonapi.org/) specification. The retrieve, query and browse functions do not require authentication, but the DataCite Provider and Client functions do require authentication with your DataCite Provider or Client ID. 

Other alternatives to retrieve, query and browse DataCite DOI metadata records include the [DataCite OAI-PMH](http://oai.datacite.org) service and the [DataCite Search](http://search.datacite.org) service. OAI-PMH is used primarily for bulk harvesting of metadata, and DataCite Search – which uses the DataCite REST API under the hood – provides a web interface to retrieve, query and browse DataCite metadata records.

Other alternatives to register DOIs are the [MDS API](doc:mds-api-guide) and the [EZ API](doc:datacite-ez-api-guide). Neither of these are JSON APIs. 

This guide will walk you through the basic operations of the DataCite REST API: 
* [Retrieving a single DOI](doc:api-get-doi) 
* [Retrieving a list of DOIs](doc:api-get-lists) 
* [Making and filtering queries](doc:api-queries) 
* [Retrieving a random sample of DOIs](doc:api-sampling) 
* [Creating DOIs with the REST API](doc:api-create-dois)
* [Retrieving citations and other relations](doc:api-citations)
* [Tracking metadata provenance](doc:tracking-provenance) 
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]