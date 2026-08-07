---
title: DataCite REST API
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
The [DataCite REST API](https://support.datacite.org/reference) enables retrieval of DataCite DOI metadata records and account information.

The API is generally RESTful and returns results in JSON (following the [JSON:API](http://jsonapi.org/) specification).

### REST API for Metadata Retrieval

This guide will walk you through the options for retrieving metadata with the REST API:

- [Retrieving a single DOI](doc:api-get-doi) 
- [Retrieving a list of DOIs](doc:api-get-lists) 
- [Pagination](doc:pagination)
- [Queries and filtering](doc:api-queries) 
- [Retrieving a random sample of DOIs](doc:api-sampling)
- [Tracking metadata provenance](doc:tracking-provenance)

### Public API (No authentication)

The Public API is accessed without authentication. We recommend using the Public API to retrieve and search for DOI metadata.

The Public API only returns DOIs in Findable state, excluding draft records and Registered DOIs. Learn more about [DOI States](doc:doi-states).

> 📘 Harvesting DataCite metadata
> 
> Members and non-members wishing to harvest DataCite metadata should use the Public API, which does not require authentication.
> 
> DataCite DOI metadata records can also be harvested in bulk with the [DataCite OAI-PMH](http://oai.datacite.org).

### REST API Reference

> 📘 
> 
> Access the [REST API Reference](ref:introduction) to explore all REST API functions and parameters.