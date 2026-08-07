---
title: How can I make my DOI list query more efficient when using the REST API?
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
You may be able to improve the efficiency and response time of your REST API DOI list query by using the methods below. 

## Use the `disable-facets=true` URL parameter

The [`meta` attribute](https://support.datacite.org/docs/api-get-lists#whats-in-the-api-response) returned in a DOI list response contains aggregated information about the DOIs in the list. These fields include `states`, `resourceTypes`, and more. If you do not need these fields, you can disable them to help improve the efficiency of your query by setting the URL parameter `disable-facets=true` . For example:

```
https://api.datacite.org/dois?query=climate%20change&disable-facets=true
```

The following `meta` fields will still be returned when `disable-facets=true`: `total`, `totalPages`, and `page`.

## Filter lists using filter parameters instead of the `query` parameter

DOI lists can be filtered [using filter parameters](https://support.datacite.org/docs/api-queries#applying-filter-parameters) and searched [using the `query` parameter](https://support.datacite.org/docs/api-queries#using-the-query-parameter). You may be able to improve the efficiency of your request by using supported filter parameters rather than queries in the `query` parameter where possible. For example, instead of using the query parameter `query=prefix:10.48321` to find all DOIs with the prefix 10.48321:

```
https://api.datacite.org/dois?query=prefix:10.48321
```

Use the `prefix` filter parameter `prefix=10.48321`:

```
https://api.datacite.org/dois?prefix=10.48321
```