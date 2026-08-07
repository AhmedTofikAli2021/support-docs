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
## About the DataCite REST API

The [DataCite REST API](https://support.datacite.org/reference) enables retrieval, creation, and update of DataCite DOI metadata records and account information.

The API is generally RESTful and returns results in JSON (following the [JSON:API](http://jsonapi.org/) specification).

### REST API Reference

> 📘 
> 
> Access the [REST API Reference](ref:introduction) to explore all REST API functions and parameters.

### REST API Guide

This guide will walk you through the basic operations of the DataCite REST API:

- [Retrieving a single DOI](doc:api-get-doi) 
- [Retrieving a list of DOIs](doc:api-get-lists) 
- [Pagination](doc:pagination)
- [Queries and filtering](doc:api-queries) 
- [Retrieving a random sample of DOIs](doc:api-sampling) 
- [Creating DOIs with the REST API](doc:api-create-dois)
- [Updating metadata with the REST API](doc:updating-metadata-with-the-rest-api)
- [Tracking metadata provenance](doc:tracking-provenance)

### Additional resources

- Our [DataCite API Training](https://youtu.be/mh_r6ohJOac) video walks through the basics of the REST API.
- Fork the [DataCite REST API Training collection](https://www.postman.com/datacite/workspace/datacite-rest-api-training/overview) on Postman to explore examples.

## Member vs. Public API

The REST API is split into two versions: a Public API and a Member API. Traffic is directed to a different set of servers if users authenticate:

- Public API: Accessed **without** authentication.
- Member API: Accessed **with** authentication.

These two APIs use the same URL (starting with <https://api.datacite.org>) and run the same code. When users authenticate to access the Member API, they have access to additional functionality, depending on their account type.

### Public API (No authentication)

The Public API is accessed without authentication. We recommend using the Public API to retrieve and search for DOI metadata.

The Public API only returns DOIs in Findable state, excluding draft records and Registered DOIs. Learn more about [DOI States](docs:doi-states).

> 📘 Harvesting DataCite metadata
> 
> Members and non-members wishing to harvest DataCite metadata should use the Public API, which does not require authentication.
> 
> Other alternatives to retrieve, query and browse DataCite DOI metadata records include the [DataCite OAI-PMH](http://oai.datacite.org) service and the [DataCite Commons](http://commons.datacite.org) service. OAI-PMH is used primarily for bulk harvesting of metadata.

### Member API (Requires authentication)

Authentication provides access to additional functionality to create and update DOIs, view draft records and Registered DOIs, and view contact information.

Users must authenticate with a Repository account to create and update DOIs.

| Account Type                              | Create and update DOIs | View draft records and Registered (non-Findable) state DOIs | View organization contact information |
| :---------------------------------------- | :--------------------- | :---------------------------------------------------------- | :------------------------------------ |
| Repository                                | x                      | x                                                           |                                       |
| Member (Direct Member or Consortium Lead) |                        | x                                                           | x                                     |
| Consortium Organization                   |                        | x                                                           | x                                     |

## Test vs. Production

The REST API is available in both test and production. Many examples in this guide use the test endpoint.

- Test endpoint: <https://api.test.datacite.org>
- Production endpoint: <https://api.datacite.org>

Learn more about the differences between Test and Production in our [Testing Guide](https://support.datacite.org/docs/testing-guide).

## API Versions

The current version of the REST API is version 2. If you are using the endpoints `/works`, `/members`, or `/data-centers`, you are using [version 1](doc:api-v1).

> 📘 Would you like to know more?
> 
> If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)