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

The [DataCite REST API](https://support.datacite.org/reference) allows any user to retrieve, query and browse DataCite DOI metadata records. In addition, DataCite Repositories can register DOIs and DataCite Members can manage Repositories and prefixes via the API. 

The API is generally RESTful and returns results in JSON, as the API follows the [JSONAPI](http://jsonapi.org/) specification. The retrieve, query and browse functions do not require authentication, but the DataCite Member and Repository functions do require authentication with your DataCite Member or Repository ID. 

Other alternatives to retrieve, query and browse DataCite DOI metadata records include the [DataCite OAI-PMH](http://oai.datacite.org) service and the [DataCite Commons](http://commons.datacite.org) service. OAI-PMH is used primarily for bulk harvesting of metadata, and DataCite Search – which uses the DataCite REST API under the hood – provides a web interface to retrieve, query and browse DataCite metadata records.

This guide will walk you through the basic operations of the DataCite REST API **(all examples use the test endpoint)**: 

[block:callout]
{
  "type": "info",
  "body": "All examples use the test endpoint. The production endpoint is https://api.datacite.org",
  "title": "Examples"
}
[/block]
* [Retrieving a single DOI](doc:api-get-doi) 
* [Retrieving a list of DOIs](doc:api-get-lists) 
* [Making and filtering queries](doc:api-queries) 
* [Retrieving a random sample of DOIs](doc:api-sampling) 
* [Creating DOIs with the REST API](doc:api-create-dois)
* [Retrieving citations and other relations](doc:api-citations)
* [Tracking metadata provenance](doc:tracking-provenance) 

# Member Vs Public API

As of December 2019 the REST API is split into two versions: a Public API and a Member API. These two APIs use exactly the same URLs (starting with https://api.datacite.org), run exactly the same code, and provide exactly the same public data, the only difference being that traffic is directed to a different set of servers if users authenticate as a member. 

The DataCite [status page](https://status.datacite.org/) page reflects this change, you can now see separate metrics (both response time and request count) for the Public API and Member API.

More information in this [blog post](https://blog.datacite.org/announcing-member-api/)
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]