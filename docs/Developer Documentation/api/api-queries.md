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
# Making Queries

The API supports the use of queries, which return lists as responses. The previous section of this guide ([Retrieving a list of DOIs](doc:api-get-lists)) dealt with the basics of list results. This section will cover making queries and filtering the response lists. 

```shell
$ curl https://api.test.datacite.org/dois?query=climate%20change
```

The response is a list of all the DOI records that contain the phrases `climate` or `change` in their metadata. The REST API uses Elasticsearch [Query String Queries](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html). 

The query string is parsed into a series of terms and operators. A term can be a single word — quick or brown — or a phrase, surrounded by double quotes — "quick brown" — which searches for all the words in the phrase, in the same order.

The specifics of Query String Queries are discussed at the link provided above, but a summary is given below.

### Field names
Queries by default search all fields, but a specific field can be provided in the query, e.g. 

```shell
$ curl https://api.test.datacite.org/dois?query=publicationYear:2016
```

For nested fields use the same format as in the REST API response, e.g.

```shell
$ curl https://api.test.datacite.org/dois?query=creators.nameIdentifiers.nameIdentifierType:ORCID
```

### Wildcards
Wildcards are supported, e.g.

```shell
$ curl https://api.test.datacite.org/dois?query=creators.nameIdentifiers.nameIdentifier:*
$ curl https://api.test.datacite.org/dois?query=creators.familyName:mil*
```

### Boolean operators
By default, all terms are optional, as long as one term matches. Use `+` or `-` to specify terms that have to match or not match, respectively. For example 

```shell
$ curl https://api.test.datacite.org/dois?query=titles.title:climate%20+change
```

Additional parameters can be used to query, filter and control the results returned by the DataCite API. They can be passed as normal URI parameters or as JSON in the body of the request.

| Parameter                    | Description                 |
|:-----------------------------|:----------------------------|
| `page[size]`              | results per per page |
| `page[number]`        | page number |
| `sort`                       | sort results by a certain field |
| `include`                    | side-load associations |

For example, to list one single work using the previously specified query, you would add a `page[size]` parameter with a value of 1, like so:

```shell
#GET dois?query=
$ curl https://api.test.datacite.org/dois?query=climate+change&page[size]=1
```

# Filtering List Responses

The API supports filters that allow you to narrow queries. All filter results are lists. For example, if you wish to filter results by *client* to find everything that is managed by the client `dryad.dryad` (Dryad Digital Repository), you would do the following:

```shell
$ curl https://api.test.datacite.org/dois?client-id=dryad.dryad
```

 The following filters are supported:

| Filter     | Possible values | Description|
|:-----------|:----------------|:-----------|
| `provider-id` | `{provider-id}` | metadata associated with a specific DataCite provider |
| `client-id` | `{client-id}` | metadata associated with a specific DataCite client |
| `resource-type-id` | `{resource-type-id}` | metadata for a specific resourceTypeGeneral |
| `person-id` | `{person-id}` | metadata associated with a specific person's ORCID iD |
| `registered` | `{registered}` | metadata where year of DOI registration is `{year}` |
| `created` | `{created}` | metadata where year of DOI creation is `{created}` |
| `schema-version` | `{schema-version}` | metadata where schema version of the deposited metadata is `{schema-version}` |

The REST API also supports retrieving a random sample of results. The next section of this guide will cover sampling (see [Retrieving a random sample of DOIs](doc:api-sampling)).