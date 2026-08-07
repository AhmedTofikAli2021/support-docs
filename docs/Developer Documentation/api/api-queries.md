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

This includes the following frequently used filters:

| Filter             | Example values           | Description                                                                                               |
| :----------------- | :----------------------- | :-------------------------------------------------------------------------------------------------------- |
| `provider-id`      | `cern`                   | DOIs associated with a specific DataCite provider (Direct Member, Consortium, or Consortium Organization) |
| `client-id`        | `cern.zenodo`            | DOIs associated with a specific DataCite client (repository)                                              |
| `consortium-id`    | `dcan`                   | DOIs associated with a specific DataCite consortium                                                       |
| `resource-type-id` | `output-management-plan` | DOIs that use a specific resourceTypeGeneral                                                              |
| `prefix`           | `10.5061`                | DOIs with a specific prefix                                                                               |
| `registered`       | `2016`                   | DOIs with a specific year of DOI registration (registered in global handle server)                        |
| `created`          | `2020`                   | DOIs with a specific year of DOI creation (created in DataCite system)                                    |
| `schema-version`   | `4`                      | DOIs using a specific schema version for the associated metadata                                          |

For example, this request retrieves all DOIs registered by a specific Repository account:

```shell
curl https://api.datacite.org/dois?client-id=datacite.datacite
```

For a full list of parameters, please see the [API Reference](ref:get_dois).

## Using the "query" parameter

You can search DOI metadata using the “query” parameter. The REST API uses Elasticsearch [query string syntax](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html#query-string-syntax).

The full specifics of query string queries are discussed in the [Elasticsearch documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html#query-string-syntax). This guide contains selected examples to get you started with querying DataCite DOI metadata.

### Building an Elasticsearch query string

#### Field names

A specific field can be provided in the query. For example:

```shell
curl https://api.datacite.org/dois?query=publicationYear:2016
```

Nested fields are joined by a `.`. For example:

```shell
curl https://api.datacite.org/dois?query=creators.nameIdentifiers.nameIdentifierScheme:ORCID
```

Nested fields use the same structure as in the [REST API response for a DOI metadata record](doc:api-get-doi#response). You can also refer to the [DataCite XML to JSON mapping](doc:datacite-xml-to-json-mapping) for a full list of how DataCite metadata is represented in JSON.

When a field is _not_ specified, the query by default searches commonly queried fields (including title, creator name, creator nameIdentifier, publisher, description, subject, and relatedIdentifier).

#### Wildcards

The wildcards `*` and `?` are supported, e.g.:

```shell
curl https://api.datacite.org/dois?query=creators.nameIdentifiers.nameIdentifier:*
curl https://api.datacite.org/dois?query=creators.familyName:mil*
```

`*` matches zero or more characters and `?` matches any single character.

#### Boolean operators

By default, all terms are optional, as long as one term matches. Use `+` or `-` to specify terms that have to match or not match, respectively. For example, to search for DOIs containing both "climate" and "change" in the title field:

```shell
curl https://api.datacite.org/dois?query=titles.title:(climate%20+change)
```

The boolean operators AND, OR and NOT (case-sensitive) are also supported.

When multiple operators are used together, use parentheses to combine them. For example:  
`(titles.title:(climate AND change) OR descriptions.description:(climate AND change)) AND (publicationYear:2023)`

```shell
curl https://api.datacite.org/dois?query=(titles.title:(climate%20AND%20change)%20OR%20descriptions.description:(climate%20AND%20change))%20AND%20(publicationYear:2023)
```

### Query examples

#### 1. Publisher

Search for a specific publisher.

`publisher:DataCite`

```shell
curl https://api.datacite.org/dois?query=publisher:DataCite
```

#### 2. DOI

Search for a specific DOI.

`doi:10.11570/18.0006`

```shell
curl https://api.datacite.org/dois?query=doi:10.11570/18.0006
```

#### 3. Affiliation

Combine the parent and child elements to construct the search for an affiliation.

```json
},
  "creators": [
    {
      "name": "Bloggs, Jane",
      "nameType": "Personal",
      "givenName": "Jane",
      "familyName": "Bloggs",
      "affiliation": [
          {
             "name": "DataCite",
             "schemeUri": "https://ror.org",
             "affiliationIdentifier": "https://ror.org/04wxnsj81",
             "affiliationIdentifierScheme": "ROR"
          }
      ],
```

```shell
curl https://api.datacite.org/dois?affiliation=true&query=creators.affiliation.name:DataCite
```

To include affiliation identifier details, add `&affiliation=true `to your requests. [See our FAQ for more information](https://support.datacite.org/docs/can-i-see-more-detailed-affiliation-information-in-the-rest-api).

#### 4. Quotes

Search the exact string enclosed in the quotes.

`titles.title:"CrowdoMeter Tweets"`

```shell
curl https://api.datacite.org/dois?query=titles.title:"CrowdoMeter Tweets"
```

#### 5. Boolean operators

Search using the "AND" boolean.

`types.resourceTypeGeneral:Software AND types.resourceType:XML`

```shell
curl https://api.datacite.org/dois?query=types.resourceTypeGeneral:Software%20AND%20types.resourceType:XML
```

Search using the "AND" and "OR" booleans.

`publisher:DataCite AND types.resourceTypeGeneral:(Text OR Dataset)`

```shell
curl https://api.datacite.org/dois?query=publisher:DataCite%20AND%20types.resourceTypeGeneral:(Text%20OR%20Dataset)
```

#### 6. Wildcards

Search using a wildcard `*`.

`subjects.subject:robot*`

```shell
curl https://api.datacite.org/dois?query=subjects.subject:robot*
```

#### 7. Longer queries

Combine more than one element to limit the search results. In this example, the creators and the relatedIdentifier properties are used to build the query.

`creators.name:"Fenner, Martin" AND relatedIdentifiers.relationType:HasPart`

creators:

```json
"creators": [
    {
      "name": "Fenner, Martin",
      "nameType": "Personal",
      "givenName": "Martin",
      "familyName": "Fenner",
      "affiliation": [],
      "nameIdentifiers": [
        {
          "nameIdentifier": "https://orcid.org/0000-0003-1419-2405",
          "nameIdentifierScheme": "ORCID"
        }
      ]
    }
  ],
```

relatedIdentifiers:

```json
"relatedIdentifiers": [
    {
      "relationType": "HasPart",
      "relatedIdentifier": "10.5438/6423",
      "relatedIdentifierType": "DOI"
    },
```

```shell
curl https://api.datacite.org/dois?query=creators.name:"Fenner, Martin" AND relatedIdentifiers.relationType:HasPart
```

## Sorting results

The sort parameter is used to reorder the results. For example, this request retrieves all DOIs sorted by the updated date (from most to least recent):

```shell
curl https://api.datacite.org/dois?sort=-updated
```

The sort parameter accepts the following options:

| Option          | Description                         |
| :-------------- | :---------------------------------- |
| name            | DOI name alphabetical ascending     |
| -name           | DOI name alphabetical descending    |
| created         | created date ascending              |
| -created        | created date descending             |
| updated         | updated date ascending              |
| -updated        | updated date descending             |
| published       | published date ascending            |
| -published      | published date descending           |
| view-count      | viewCount ascending                 |
| -view-count     | viewCount descending                |
| download-count  | downloadCount ascending             |
| -download-count | downloadCount descending            |
| citation-count  | citationCount ascending             |
| -citation-count | citationCount descending            |
| title           | first title alphabetical ascending  |
| -title          | first title alphabetical descending |
| relevance       | relevance score descending          |

## Additional parameters

Additional parameters can be used to control the results returned by the DataCite REST API. They can be passed as normal URI parameters or as JSON in the body of the request.

### Selecting which metadata fields to retrieve

Affiliation identifiers (supported in Metadata Schema 4.3+) and publisher identifiers (supported in Metadata Schema 4.5+) are not included in REST API responses by default. [See our FAQ for more information](doc:can-i-see-more-detailed-affiliation-information-in-the-rest-api).

- To include affiliation identifier details, add `&affiliation=true` to your requests.
- To include publisher identifier details, add `&publisher=true` to your requests.
- To include additional attributes in a list of DOIs (prefix, suffix, viewsOverTime, citationsOverTime, provider, references, citations. parts, partOf, versions, versionOf, xml, alternateIdentifiers), add `&detail=true` to your requests.

It is also possible to specify which fields are returned using the `fields[dois]` parameter. For example, `fields[dois]=titles,subjects` will only return titles and subjects:

```shell
curl https://api.datacite.org/dois?fields[dois]=titles,subjects
```

### Pagination

The `page[number]`, `page[size]`, and `page[cursor]` parameters are used for pagination. See the [Pagination](doc:pagination) guide for more information.

### Sampling

The REST API also supports retrieving a random sample of results with the `random`, `sample`, and `sample-group` parameters. The next section of this guide covers sampling (see [Retrieving a random sample of DOIs](doc:api-sampling)).