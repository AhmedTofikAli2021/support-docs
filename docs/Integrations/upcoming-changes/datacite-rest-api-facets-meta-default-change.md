---
title: 'DataCite REST API: Facets ("meta") Default Change'
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## What changed

By default, requests to the `/dois` endpoint no longer include the facets under the "meta" attribute. To retrieve facets, requests must include the URL parameter `disable-facets=false`. This change took effect on **1 March 2026**.

## Why did we make this change?

The meta attribute of the DataCite REST API `/dois` endpoint used to display a set of facets (aggregations) about a result set by default. These included attributes like resourceTypes, created, and affiliations.

As the DataCite Metadata Store has grown, these facets have become less performant, slowing down common REST API use cases like querying DOI metadata and harvesting DOI metadata records.

To better support these important REST API activities, facets are no longer be returned by default. If needed, facets can be easily re-enabled using a `disable-facets=false` URL parameter. 

The total, totalPages, and page attributes will continue to be returned for every `/dois` list request.

## How to update your requests

### To continue retrieving the "meta" facets

If you would like to continue retrieving facet information from the "meta" section of the response, you can update your REST API requests to include `disable-facets=false`.

| Current request with facets enabled by default            | Updated request to enable facets for 1 March 2026 transition                   |
| :-------------------------------------------------------- | :----------------------------------------------------------------------------- |
| `https://api.datacite.org/dois`                           | `https://api.datacite.org/dois?disable-facets=false`                           |
| `https://api.datacite.org/dois?query=biological+sciences` | `https://api.datacite.org/dois?query=biological+sciences&disable-facets=false` |