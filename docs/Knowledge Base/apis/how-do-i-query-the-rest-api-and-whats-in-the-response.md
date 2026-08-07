---
title: How do I query the REST API and what’s in the response?
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
[DataCite’s REST API](doc:api) allows any user to retrieve, query and browse DataCite DOI metadata records. You can run a query for a single DOI, as follows:

```shell
# GET /dois
curl "https://api.datacite.org/dois/10.6084/m9.figshare.21545982"
```

You can also run a query to retrieve a list of DOIs, for example, search for all DOIs with a specific “publisher”.

```shell
# GET /dois
curl "https://api.datacite.org/dois?query=publisher:DataCite"
```

> 📘 
> 
> To run a GET request, you can use curl from the command line, an application like [Postman](https://www.postman.com/), or simply paste into your browser.

A successful query will generate a response from the REST API which includes all of the metadata fields in JSON format. The response also provides a list of additional fields at the bottom providing extra information about the DOI. The additional information for a single DOI includes; metadataVersion, state and citationCount, see the full list in the [guide about queries for a single DOI](doc:api-get-doi) with the REST API. For a list, you will see aggregated information for all the DOIs in the list, such as; resourceTypes, licenses and citations, see full list in the documentation about [retrieving a list with the REST API](doc:api-get-lists).