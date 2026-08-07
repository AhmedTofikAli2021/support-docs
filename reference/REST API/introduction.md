---
title: REST API
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
## Version History

* v.1: June 25, 2016, first draft.
* v.1.1: October 10, 2016, follow JSONAPI spec for side-loading associations
* v.1.2: December 9, 2017, follow JSONAPI spec for pagination

## Overview

The DataCite REST API returns information about DataCite content. The API is generally RESTFUL and returns results in JSON. It follows the [JSONAPI](http://jsonapi.org/) specification. The mime-type for API results is `application/vnd.api+json`. There are two general types of results:

* Singletons
* Lists

### Singletons

Singletons are single results. Retrieving metadata for a specific identifier (e.g. DOI, ORCID) typically returns a singleton result.

### Lists

Lists results can contain multiple entries. Searching or filtering typically returns a list result. A list has three parts:

* **meta**, which includes information about the query, e.g. number of results returned.
* **data**, which will contain the items matching the query or filter.
* **included**, which will contain side-loaded associations, via the `?include=x` parameter.

Major resource components supported by the DataCite API are (in alphabetical order):

These can be used alone like this

| Resource                 | Description                       |
|:-------------------------|:----------------------------------|
| `/data-centers`            | returns a list of all DataCite data centers |
| `/members`               | returns a list of all DataCite members |
| `/works`                 | returns a list of all works (datasets, text documents, etc.), 25 per page

### Resource components and identifiers
Resource components can be used in conjunction with identifiers to retrieve the metadata for that identifier.

| Resource                     | Description                                      |
|:-----------------------------|:-------------------------------------------------|
| `/members/{member-id}`       | returns metadata for a DataCite member           |
| `/data-centers/{data-center-id}`  | returns metadata for a DataCite data center      |
| `/works/{doi}`               | returns metadata for the specified DataCite DOI. |

## Notes on dates

Note that dates in filters should always be of the form `YYYY-MM-DD`, `YYYY-MM` or `YYYY`. Also note that the date published in DataCite metadata is always expressed as `YYYY` (the `publicationYear` field).

## Page[size]

Normally, results are returned 25 at a time. You can control the number of results returns by using the `page[size]` parameter. To limit results to 5, for example, you could do the following:

```shell
# GET /works?query=
$ curl https://api.datacite.org/works?query=allen+renear&page[size]=5
```

If you would just like to get the `summary` of the results, you can set the page[size] to 1.

```shell
# GET /works?query=
$ curl https://api.datacite.org/works?query=allen+renear&page[size]=1
```

The maximum page[size] you can ask for in one query is `1000`.

## Page[number]

The number of returned items is controlled by the `page[size]` parameter, but you can select the page of the result list by using the `page[number]` parameter.  So, for example, to select the second set of 5 results (i.e. results 6 through 10), you would do the following:

```shell
# GET /works?query=
$ curl https://api.datacite.org/works?query=allen+renear&page[size]=5&page[number]=2
```

## Includes

To sideload associations use the `include` parameter, for example:

```shell
# GET /works?query=
$ curl https://api.datacite.org/works?query=climate&include=data-center,resource-type
```

Sideload *multiple* associations by providing them in a comma-separated list.

### Notes on owner prefixes

The prefix of a DataCite DOI does **NOT** indicate who currently owns the DOI.

DataCite also has `data-center_id` (`datacentre_symbol` in the DataCite metadata) for depositing organisations. A single data center may control multiple owner prefixes, which in turn may control a number of DOIs. When looking at works published by a certain organisation, data_center_ids and the data center routes should be used.

Queries support a subset of [DisMax](https://wiki.apache.org/solr/DisMax), so, for example, you can refine queries as follows.

Works that include "renear" but not "ontologies":

```shell
GET /works?query=
$ curl https://api.datacite.org/works?query=renear+-ontologies
```

## Sorting

Results from a list response can be sorted by applying the `sort` and `order` parameters. Order sets the result ordering, either `asc` or `desc`. Sort sets the field by which results will be sorted. Possible values are:

| Sort value  | Description                                    |
|-------------|------------------------------------------------|
| `score`     | Sort by relevance score                        |
| `updated`   | Sort by date of most recent change to metadata |
| `deposited` | Sort by time of most recent deposit            |
| `published` | Sort by publication date                       |

An example that sorts results in order of publication, beginning with the least recent:

```shell
GET /works?query=
$ curl https://api.datacite.org/works?query=josiah+carberry&sort=published&order=asc
```

### Facet Counts

Facet counts are returned via the `meta` object. Facet counts give counts per field value for an entire result set. The following facet counts are returned:

| Resource                 | Facet counts                                                                       |
|:-------------------------|:-----------------------------------------------------------------------------------|
| `/data centers`            | total, members |                                                                                                             |
| `/works`                 | total, data-centers, resource-types, schema-versions, sources, years |

All other resources return only `total` in the `meta` object.

### Filter Names

Filters allow you to narrow queries. All filter results are lists.  The following filters are supported:

| Filter     | Possible values | Description|
|:-----------|:----------------|:-----------|
| `member-id` | `{member-id}` | metadata associated with a specific DataCite member |
| `data-center-id` | `{data-center-id}` | metadata associated with a specific DataCite data center |
| `resource-id` | `{resource-type-id}` | metadata for a specific resourceTypeGeneral |
| `source-id` | `{source-id}` | metadata associated with a specific source |
| `relation-type-id` | `{relation-type-id}` | metadata associated with a specific relation type |
| `from-created-date` | `{date}` | metadata where deposited date is since (inclusive) `{date}` |
| `until-created-date` | `{date}` | metadata where deposited date is before (inclusive)  `{date}` |
| `from-update-date` | `{date}` | metadata where updated date is since (inclusive) `{date}` |
| `until-update-date` | `{date}` | metadata where updated date is before (inclusive)  `{date}` |
| `year` | `{year}` | publication year of the resource `{year}` |

## Includes

To sideload associations (as [specified](http://jsonapi.org/format/#fetching-includes) in the JSONAPI documentation) use the `include` parameter, for example:

```shell
# GET /works?query=
$ curl https://api.datacite.org/works?query=climate&include=data-center,resource-type
```

Sideload multiple associations by providing them in a comma-separated list. The following resources can be sideloaded:

| Resource                 | Resources that can be included                                   |
|:-------------------------|:-----------------------------------------------------------------|
| `/data-centers`            | member                                      |
| `/works`                 | data-center, member, resource-type |

When an error occurs, the API will return a [JSONAPI error object](http://jsonapi.org/examples/#error-objects), for example


```json
{
  "errors": [
    {
      "status": "422",
      "title":  "Invalid Attribute"
    }
  ]
}
```

## Further Details

Review or github repository for further details:
https://github.com/datacite/spinone