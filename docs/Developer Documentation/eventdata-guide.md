---
title: DataCite Event Data
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
[Event Data](https://www.crossref.org/services/event-data/) is a joint service by Crossref and Datacite to collect and expose links to Crossref and DataCite DOIs. For DataCite DOIs Event Data provides links to other DOIs from DataCite, Crossref or other DOI registration agencies, as well as usage statistics sent to DataCite as [usage reports](doc:usage-reports-api-guide).

The DataCite REST API provides a query API for the Event Data service, and allows users to retrieve events filtered by DOI or DOI prefix, source of the event, relation type of the event, and/or year and month the event occurred. See section [Query Filters](doc:eventdata-guide#section-query-filters) for details.
[block:callout]
{
  "type": "warning",
  "body": "DataCite services that contain citation data rely on an external service, [Crossref Event Data](https://www.crossref.org/services/event-data/). Because of this dependency, citation data is not available in DataCite test environments, doi.test.datacite.org (Fabrica test), api.test.datacite.org (API test)."
}
[/block]
## Linking Events
Linking events are relations between two DOIs, or a DOI and a URL. For DataCite DOIs these are described in DataCite metadata using the `<relatedIdentifier>` property, and there is a controlled list of relation types that can be used (see section [relation-type-id](doc:eventdata-guide#section-relation-type-id) for details). Linking events describe a large number of relations, including

* citations
* versioning
* granularity (is part of / has part)

There is no single relation type to describe citations, and relation types relevant for citations are sometimes used differently across organizations. The most commonly used relation types for citations are `references`, `documents`,  `cites`, and `is-supplemented-by`.

## Usage Events
Usage events (views and downloads of the content associated with a DOI) are provided by the `datacite-usage` source, and are generated from usage reports in the standard [SUSHI](https://www.niso.org/schemas/sushi) format sent to DataCite. Usage reports for datasets are generated using the [Code of Practice for Research Data Usage Metrics](https://doi.org/10.7287/peerj.preprints.26505v1) and the [SUSHI specification for research data usage metrics](https://app.swaggerhub.com/apis/COUNTER/researchdata-sushi_1_0_api/1.0.0#/).

The usage reports summarize all usage events for a given month, and break them down into three categories:

* **total vs. unique**: for unique usage events accesses are only counted once per content item if they are within a unique user session.
* **access method**: track content usage by machines. The access method can be `regular` or `machine`.
* **metric type**: activities where content was retrieved (`requests`) or information about content (e.g. metadata) was examined (`investigations`). 

With these three categories there are 8 (2 x 2 x 2) relation types for usage events (see [relation-type-id](doc:eventdata-guide#section-relation-type-id) below).

## Query Filters
The following filters are available in the Event Data Query API:

### query
Query for any event information.

### subj-id
The identifier for the event subject, expressed as URL. For example `https://doi.org/10.7272/q6qn64nk`. 

### obj-id
The identifier for the event object, expressed as URL. For example `https://doi.org/10.7272/q6qn64nk`.

### doi
The `subj-id` or `obj-id` of the event, expressed as DOI. For example `10.7272/q6qn64nk`.

### prefix
The DOI prefix of the `subj-id` or `obj-id` of the event. For example `10.7272`.

### year-month
The year and month in which the event occurred, in the format `YYYY-MM`. For example `2018-08`.

### source-id
[block:parameters]
{
  "data": {
    "h-0": "source-id",
    "h-1": "description",
    "h-2": "provided by",
    "0-0": "datacite-usage",
    "0-1": "Usage Events for DataCite DOIs",
    "0-2": "Usage Reports submitted to DataCite",
    "1-0": "datacite-related",
    "1-1": "DataCite DOI as related identifier from DataCite metadata",
    "1-2": "DataCite",
    "2-0": "datacite-crossref",
    "2-1": "Crossref DOI as related identifier in DataCite metadata",
    "2-2": "DataCite",
    "3-0": "datacite-kisti",
    "3-1": "KISTI DOI as related identifier in DataCite metadata",
    "3-2": "DataCite",
    "4-0": "datacite-op",
    "4-1": "OP DOI as related identifier in DataCite metadata",
    "4-2": "DataCite",
    "5-0": "datacite-medra",
    "5-1": "mEDRA DOI as related identifier in DataCite metadata",
    "5-2": "DataCite",
    "6-0": "datacite-istic",
    "6-1": "ISTIC DOI as related identifier in DataCite metadata",
    "6-2": "DataCite",
    "9-0": "crossref",
    "9-1": "DataCite DOI in Crossref Metadata",
    "9-2": "Crossref",
    "7-0": "datacite-funder",
    "7-2": "DataCite",
    "7-1": "Crossref Funder ID as funder identifier in DataCite metadata",
    "8-0": "datacite-url",
    "8-1": "URL as related identifier in DataCite metadata",
    "8-2": "DataCite"
  },
  "cols": 3,
  "rows": 10
}
[/block]
### relation-type-id
`datacite-usage` events use one of these relation-types:

1. total-dataset-investigations-regular
2. unique-dataset-investigations-regular
3. total-dataset-requests-regular
4. unique-dataset-requests-regular
5. total-dataset-investigations-machine
6. unique-dataset-investigations-machine
7. total-dataset-requests-machine
8. unique-dataset-requests-machine

For events generated from DataCite metadata, the `relationType` from the DataCite Metadata Schema is used: 

1. Is-cited-by
2. cites
3. is-supplement-to
4. is-supplemented-by
5. is-continued-by
6. continues
7. describes
8. is-described-by
9. has-metadata
10. is-metadata-for
11. has-version
12. is-version-of
13. is-new-version-of
14. is-previous-version-of
15. is-part-of
16. has-part
17. is-referenced-by
18. references
19. is-documented-by
20. documents
21. is-compiled-by
22. compiles
23. is-variant-form-of
24. is-original-form-of
25. is-identical-to
26. is-reviewed-by
27. reviews
28. is-derived-from
29. is-source-of
30. is-required-by
31. requires

`datacite-funder` uses the relation type `is-funded-by`. `crossref` uses the relation type `references`.

## Pagination

The DataCite Event Data Query API by default returns 1000 events per query. This number can be adjusted by the `page[size]` query parameter, and must be between 0 and 1,000. For `page[size]=0` only the `meta` object is returned.

To paginate through up to 10,000 results, the `page[number]` query parameter can be used.

For query results with more than 1,000 events, e.g. to harvest all events from a particular source or for a particular prefix, cursor-based pagination should be used. The DataCite Event Data Query API returns a `links` JSON object, use the URL in the `next` property to fetch the next page, and this URL includes a `page[cursor]` query parameter. With cursor-based pagination all events are retrieved in chronological order (using the `timestamp` property), oldest events first. The cursor used is the UNIX epoch time, i.e. the number of seconds passed since 1 January 1970. 

## Sorting

By default all events are sorted in ascending chronological order (using the last updated timestamp). Other sort criteria are:

* **relevance**: the relevance score of the query
* **obj-id**: the obj-id of each event
* **total**: total count of each event. Is > 1 only for usage events.
* **created**: using the timestamp when the event was created in the DataCite Event Data Query API

With the exception of `relevance`, events can be sorted in descending order by prefixing the sort parameter with a minus sign, e.g. `-total`. When using a sort parameter, only the first 10,000 events can be retrieved, as pagination based on page number is used.

## Statistics

The DataCite Event Data Query API returns statistics in a `meta` JSON object, with the following properties:

* **total**: the total number of events found for this query (the API only shows 1,000 events at a time)
* **total-pages**: the number of API calls needed to return all results (fetching 1,000 events at a time)
* **sources**: the sources for the events found in this query, and the number of events per source
* **prefixes**: the DOI prefixes for the events found in this query, and the number of events per prefix, for up to 50 prefixes
* **relation types**: the relation types for the events found in this query, and the number of events per relation type, further broken down by year and month