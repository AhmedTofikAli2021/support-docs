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
> ❗️ Upcoming DataCite Event Data Changes
> 
> We are streamlining the data stored in DataCite Event Data in Q3 and Q4 2026. Learn more here: [DataCite Event Data Changes](doc:datacite-event-data-changes)

DataCite Event Data collects and exposes links to DataCite DOIs. For DataCite DOIs, Event Data provides links to other DOIs from DataCite, Crossref or other DOI registration agencies, links to other PIDs from third-party sources, as well as usage statistics sent to DataCite as [usage reports](doc:usage-reports-api-guide).

The DataCite REST API provides a query API for the Event Data service. This allows users to retrieve events filtered by DOI or prefix, source of the event, relation type of the event, and/or the year and month the event occurred. See [Query Filters](doc:eventdata-guide#section-query-filters) for details.

> 🚧 
> 
> Event Data is not part of the DataCite test system. Because of the dependency between citation data and event data, citation counts are not available in DataCite test environments, including doi.test.datacite.org (Fabrica test) and api.test.datacite.org (REST API test).

## Linking Events

### Works

Linking events for works are relations between two DOIs or between a DOI and a URL. For DataCite DOIs, these are described in DataCite metadata using the `relatedIdentifier` property, and there is a controlled list of relation types that can be used.

Linking events describe several types of relations, including:

- citations and references
- versioning
- granularity (is part of / has part)

For more information, see [Connecting to Works](doc:connecting-to-works).

Linking events for works have a `relation-type-id` from the `relationType` of the  `relatedIdentifier` property. For a full list of DataCite relation types, see [Summary of all relationTypes](https://support.datacite.org/docs/connecting-to-works#summary-of-all-relationtypes).

- Relation types in Event Data are lowercase and words are separated by dashes: for example, the relationType `IsCitedBy` becomes the relation-type-id `is-cited-by`.
- Events generated from Crossref metadata uses the relation-type-id `references`.

### Authors

For DataCite DOIs, an ORCID iD referenced in a Creator `nameIdentifier` generates an event if the DOI has no `relatedIdentifiers` with `relationType` "IsIdenticalTo", "IsPartOf", "IsPreviousVersionOf", or "IsVersionOf". The `relation-type-id` for this linking event is `is-authored-by`.

### Affiliations

For DataCite DOIs, a ROR ID referenced in a Creator `affiliationIdentifier` generates an an event if the DOI has no `relatedIdentifiers` with `relationType` "IsIdenticalTo", "IsPartOf", "IsPreviousVersionOf", or "IsVersionOf". The `relation-type-id` for this linking event is `is-authored-at`.

### Funders

For DataCite DOIs, a Crossref Funder ID referenced in a FundingReference `funderIdentifier` generates an event. The `relation-type-id` for this linking event is `is-funded-by`.

## Usage Events

Usage events (views and downloads of the content associated with a DOI) are provided by the `datacite-usage` source, and are generated from usage reports in the standard [SUSHI](https://www.niso.org/schemas/sushi) format sent to DataCite. Usage reports for datasets are generated using the [COUNTER Code of Practice for Research Data](https://www.projectcounter.org/code-practice-research-data/) and the [SUSHI specification for research data usage metrics](https://app.swaggerhub.com/apis/COUNTER/researchdata-sushi_1_0_api/1.0.0#/).

The usage reports summarize usage events for a given month and break them down into three categories:

- **total vs. unique**: for unique usage events accesses are only counted once per content item if they are within a unique user session.
- **access method**: track content usage by machines. The access method can be `regular` or `machine`.
- **metric type**: activities where content was retrieved (`requests`) or information about content (e.g. metadata) was examined (`investigations`). 

With these three categories, there are 8 (2 x 2 x 2) `relation-type-id`s for usage events:

1. `total-dataset-investigations-regular`
2. `unique-dataset-investigations-regular`
3. `total-dataset-requests-regular`
4. `unique-dataset-requests-regular`
5. `total-dataset-investigations-machine`
6. `unique-dataset-investigations-machine`
7. `total-dataset-requests-machine`
8. `unique-dataset-requests-machine`

## Query Filters

The following filters are available in the Event Data Query API:

### query

Query for any event information.

### subj-id

The identifier for the event subject expressed as URL, for example: `https://doi.org/10.14454/g8e5-6293`

### obj-id

The identifier for the event object expressed as URL, for example: `https://doi.org/10.14454/g8e5-6293`

### doi

The `subj-id` or `obj-id` of the event expressed as DOI, for example: `10.14454/g8e5-6293`.

### prefix

The DOI prefix of the `subj-id` or `obj-id` of the event, for example: `10.14454`.

### orcid

The `subj-id` or `obj-id` of the event expressed as an ORCID iD, for example: `0000-0002-4684-9769`.

### year-month

The year and month in which the event occurred  in the format `YYYY-MM`, for example: `2018-08`.

### source-id

The source of the event:

| source-id                  | description                                                            | provided by                         |
| :------------------------- | :--------------------------------------------------------------------- | :---------------------------------- |
| datacite-usage             | Usage Events for DataCite DOIs                                         | Usage Reports submitted to DataCite |
| datacite-related           | DataCite DOI as related identifier from DataCite metadata              | DataCite                            |
| datacite-crossref          | Crossref DOI as related identifier in DataCite metadata                | DataCite                            |
| datacite-kisti             | KISTI DOI as related identifier in DataCite metadata                   | DataCite                            |
| datacite-op                | OP DOI as related identifier in DataCite metadata                      | DataCite                            |
| datacite-medra             | mEDRA DOI as related identifier in DataCite metadata                   | DataCite                            |
| datacite-istic             | ISTIC DOI as related identifier in DataCite metadata                   | DataCite                            |
| datacite-funder            | Crossref Funder ID as funder identifier in DataCite metadata           | DataCite                            |
| datacite-orcid-auto-update | ORCID iD as creator name identifier in DataCite metadata               | DataCite                            |
| datacite-url               | URL as related identifier in DataCite metadata                         | DataCite                            |
| crossref                   | DataCite DOI in Crossref metadata                                      | Crossref                            |
| zbmath_identifier          | zbMATH identifier as alternate identifier in zbMATH metadata           | zbMATH                              |
| zbmath_author              | zbMATH author identifier as creator name identifier in zbMATH metadata | zbMATH                              |
| zbmath_related             | DataCite or Crossref DOI as related identifier in zbMATH metadata      | zbMATH                           |

### relation-type-id

The relation type of the event. See [Linking events](doc:eventdata-guide#linking-events) and [Usage events](doc:eventdata-guide#section-usage-events) above for definitions. 

## Pagination

The DataCite Event Data Query API by default returns 25 events per page. This number can be adjusted by the `page[size]` query parameter, and must be between 0 and 1,000. For `page[size]=0` only the `meta` object is returned.

To paginate through up to 10,000 results, the `page[number]` query parameter can be used.

For query results with more than 1,000 events, e.g. to harvest all events from a particular source or for a particular prefix, cursor-based pagination should be used. For more information, see [Pagination](doc:pagination).

## Sorting

By default, all events are sorted in ascending chronological order (using the last updated timestamp). Other sort criteria can be set using the `sort` query parameter and the following options:

- **relevance**: the relevance score of the query
- **obj-id**: the obj-id of each event
- **total**: total count of each event; only > 1 for usage events
- **created**: using the timestamp when the event was created in the DataCite Event Data Query API
- **updated**: using the timestamp when the event was updated in the DataCite Event Data Query API. The default sort method. 

With the exception of `relevance`, events can be sorted in descending order by prefixing the sort parameter with a minus sign, e.g. `-total`. When using a sort parameter, only the first 10,000 events can be retrieved, as pagination based on page number is used.

## Statistics

The DataCite Event Data Query API returns statistics in a `meta` JSON object, with the following properties:

- **total**: the total number of events found for this query
- **total-pages**: the number of API calls needed to return all results
- **sources**: the sources for the events found in this query and the number of events per source (up to 10 sources)
- **occurred**: a histogram of the date the events in the query occurred by year (up to 10 years)
- **created**: a histogram of the date the events in the query were created by year (up to 10 years)
- **prefixes**: the DOI prefixes for the events found in this query and the number of events per prefix (up to 10 prefixes)
- **citation-types**: the citation types for the events found in this query and the number of events per citation type, further broken down by year and month (up to 10 citation types)
- **relation-types**: the relation types for the events found in this query and the number of events per relation type, further broken down by year and month (up to 10 relation types)
- **registrants**: the registrants for the events found in this query by registrant ID and the number of events per source (up to 10 registrants)

## More information about Event Data

> 📘 Why does the Event Data response not always match the DataCite DOI metadata for a given DOI?
> 
> Event data consists of a series of events over time. If the Event Data response does not match the current DataCite DOI metadata, there could be a number of reasons for this:
> 
> - Removing a related identifier from the DataCite DOI metadata does not remove the corresponding event from event data.
> - Similarly, updating the DataCite DOI metadata may result in a duplicate event being added to Event Data. This duplicate event will not be counted twice in citation/reference counts.
> - Event Data also includes linking events that originated from other related DOIs, from both DataCite and Crossref. These events will have the given DOI as the object (“obj-id”).
> - Event Data only includes linking events between DOIs and DOIs and DOIs and URLs. Other types of relatedIdentifiers are not included.