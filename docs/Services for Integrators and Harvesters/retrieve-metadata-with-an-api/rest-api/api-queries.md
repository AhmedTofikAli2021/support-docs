---
title: Queries and filtering
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
When [retrieving a list of DOIs,](doc:api-get-lists) the REST API supports several parameters that can be used to refine, sort, and change the presentation of the results. This guide provides more detail on the available options.

## Applying filter parameters

The API supports filter parameters that refine the list of results.

This includes the following filters:

| Filter                               | Example values              | Description                                                                                                                                                                                                                                                                                                                                       |
| :----------------------------------- | :-------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `created`                            | `2025`                      | Filter by the DOI date created in DataCite system (yyyy). Use commas to filter by multiple years (yyyy,yyyy).                                                                                                                                                                                                                                     |
| `registered`                         | `2025,2026`                 | Filter by the DOI date registered in the global handle server (yyyy). Use commas to filter by multiple years (yyyy,yyyy).                                                                                                                                                                                                                         |
| `provider-id`                        | `cern`                      | Filter by a specific DataCite provider (Direct Member or Consortium Organization). Use commas to include multiple providers.                                                                                                                                                                                                                      |
| `client-id`                          | `cern.zenodo`               | Filter by a specific DataCite client (repository). Use commas to include multiple repositories.                                                                                                                                                                                                                                                   |
| `consortium-id`                      | `dcan`                      | Filter by a specific DataCite consortium.                                                                                                                                                                                                                                                                                                         |
| `prefix`                             | `10.5061`                   | Filter by a specific prefix. Use commas to include multiple prefixes.                                                                                                                                                                                                                                                                             |
| `schema-version`                     | `4`                         | Filter by the specific schema version for the associated metadata.                                                                                                                                                                                                                                                                                |
| `affiliation-id`                     | `https://ror.org/05dhe8b71` | Search creators.affiliation.affiliationIdentifier and contributors.affiliation.affiliationIdentifier for a ROR ID.                                                                                                                                                                                                                                |
| `affiliation-country`                | `US,GB`                     | Filter DOIs by associated country inferred from ROR IDs in creators/contributors affiliations. Use comma-separated ISO 3166-1 alpha-2 country codes.                                                                                                                                                                                             |
| `funded-by`                          | `https://ror.org/01cwqze88` | Search fundingReferences.funderIdentifier for a ROR ID. Results also include DOIs containing a Crossref Funder ID in fundingReferences.funderIdentifier corresponding to the ROR ID.                                                                                                                                                              |
| `include-funder-child-organizations` | `true`                      | When the `funded-by=` parameter is set to a ROR ID and `include-funder-child-organizations=true`, the returned list of DOIs will be filtered to DataCite resources funded by the organization identified by the ROR ID as well as all of its child organizations. Child organizations include direct descendants as well as children of children. |
| `resource-type-id`                   | `output-management-plan`    | Filter by the resourceTypeGeneral. Use commas to include multiple values.                                                                                                                                                                                                                                                                         |
| `resource-type`                      | `Map`                       | Filter by the free text resourceType. Use commas to include multiple values.                                                                                                                                                                                                                                                                      |

For example, this request retrieves all DOIs registered by a specific Repository account:

```shell
curl "https://api.datacite.org/dois?client-id=datacite.datacite"
```

For a full list of parameters, please see the [API Reference](ref:get_dois).

## Using the "query" parameter

You can search DOI metadata using the "query" parameter. The `query=` parameter allows you to perform advanced queries on specific DOI metadata fields using wildcards, boolean operators, and more.

For guidance on constructing a query, see [Search DOI Metadata with Queries](doc:queries) .

## Sorting results

The sort parameter is used to reorder the results. For example, this request retrieves all DOIs sorted by the updated date (from most to least recent):

```shell
curl "https://api.datacite.org/dois?sort=-updated"
```

The sort parameter accepts the following options:

| Option           | Description                         |
| :--------------- | :---------------------------------- |
| name             | DOI name alphabetical ascending     |
| \-name           | DOI name alphabetical descending    |
| created          | created date ascending              |
| \-created        | created date descending             |
| updated          | updated date ascending              |
| \-updated        | updated date descending             |
| published        | published date ascending            |
| \-published      | published date descending           |
| view-count       | viewCount ascending                 |
| \-view-count     | viewCount descending                |
| download-count   | downloadCount ascending             |
| \-download-count | downloadCount descending            |
| citation-count   | citationCount ascending             |
| \-citation-count | citationCount descending            |
| title            | first title alphabetical ascending  |
| \-title          | first title alphabetical descending |
| relevance        | relevance score descending          |

## Additional parameters

Additional parameters can be used to control the results returned by the DataCite REST API. 

### Selecting which metadata fields to retrieve

Affiliation identifiers (supported in Metadata Schema 4.3+) and publisher identifiers (supported in Metadata Schema 4.5+) are not included in REST API responses by default. [See our FAQ for more information](doc:can-i-see-more-detailed-affiliation-information-in-the-rest-api).

- To include affiliation identifier details, add `&affiliation=true` to your requests.
- To include publisher identifier details, add `&publisher=true` to your requests.

> 📘 Retrieving the full metadata record
> 
> To retrieve the full metadata record with the REST API, include both the affiliation parameter `&affiliation=true`and publisher parameter`&publisher=true`in your requests:
> 
> `https://api.datacite.org/dois?client-id=datacite.datacite&affiliation=true&publisher=true`

To include additional attributes in a list of DOIs (prefix, suffix, viewsOverTime, citationsOverTime, provider, references, citations. parts, partOf, versions, versionOf, xml, alternateIdentifiers), add `&detail=true` to your requests.

> 📘 Retrieving the XML metadata with the REST API
> 
> To retrieve the XML version of the metadata in your response, include the `&detail=true` parameter in your requests:
> 
> `https://api.datacite.org/dois?client-id=datacite.datacite&detail=true`

It is also possible to specify which fields are returned using the `fields[dois]` parameter. 

> 📘 Specify which fields to retrieve in the response
> 
> For example, to return only titles and subjects, include`fields[dois]=titles,subjects` in your request:
> 
> ` https://api.datacite.org/dois?fields[dois]=titles,subjects`

### Pagination

The `page[number]`, `page[size]`, and `page[cursor]` parameters are used for pagination. See the [Pagination](doc:pagination) guide for more information.

### Sampling

The REST API also supports retrieving a random sample of results with the `random`, `sample`, and `sample-group` parameters. The next section of this guide covers sampling (see [Retrieving a random sample of DOIs](doc:api-sampling)).