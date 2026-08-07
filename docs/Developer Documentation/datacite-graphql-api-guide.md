---
title: DataCite GraphQL API Guide
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
[block:api-header]
{
  "title": "Introduction"
}
[/block]
The DataCite GraphQL API support queries of the DataCite API using the [GraphQL query language](https://graphql.org/). The pre-release version of the API was launched in May 2019, with an official release of the DataCite GraphQL API expected before the end of the year. The API endpoint is [https://api.datacite.org/graphql](https://api.datacite.org/graphql).
[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FefvxGfU_oVM%3Ffeature%3Doembed&url=http%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DefvxGfU_oVM&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FefvxGfU_oVM%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=efvxGfU_oVM",
  "title": "Introduction to the DataCite GraphQL API (pre-release version)",
  "favicon": "https://s.ytimg.com/yts/img/favicon-vfl8qSV2F.ico",
  "image": "https://i.ytimg.com/vi/efvxGfU_oVM/hqdefault.jpg"
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "GraphQL is a query language for APIs and a runtime for fulfilling those queries with your existing data. GraphQL provides a complete and understandable description of the data in your API, gives clients the power to ask for exactly what they need and nothing more, makes it easier to evolve APIs over time, and enables powerful developer tools.\n\nSource: [GraphQL community website](https://graphql.org/)\n\nGraphQL is not REST, so many functionalities common to many APIs are not supported, in particular, the use of HTTP verbs and resource paths. All GraphQL API calls are POST requests to https://api.datacite.org/graphql, and the query is defined in the body of the POST.",
  "title": "What is GraphQL?"
}
[/block]
The GraphQL API is an alternative to the DataCite REST API, and currently only supports **queries**, but not **mutations** (create or update actions, e.g. registering a new DOI). 

[block:callout]
{
  "type": "warning",
  "title": "DataCite GraphQL API Pre-Release",
  "body": "The GraphQL API launched in May 2019 is a pre-release version. This means that the functionality will change in the coming months, including support for additional fields, performance improvements, and bug fixes. Please post a message in the [PID Graph category of the PID Forum](https://www.pidforum.org/c/pid-graph) if you want to report a bug or suggest a feature."
}
[/block]

[block:api-header]
{
  "title": "The PID Graph"
}
[/block]
DataCite DOIs describe resources such as datasets, samples, software and publications with rich metadata. An important part of this metadata is the description of connections between resources that use persistent identifiers (PIDs) provided by DataCite and others (Crossref, ORCID, ROR, ISNI, IGSN, etc.). Together these resources and their connections form a graph, the [PID Graph](https://blog.datacite.org/introducing-the-pid-graph/):
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/662994a-pid_graph_image.png",
        "pid_graph_image.png",
        5597,
        1468,
        "#5c6f60"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Using GraphQL to query the PID Graph"
}
[/block]
The REST APIs that most PID service providers, including DataCite, use to expose metadata about PIDs are a good fit to describe a single resource, e.g. a dataset, and show the connections to other resources (e.g. the authors of a dataset) by including the PIDs for those linked resources. REST APIs are not a good fit for complex queries of the PID Graph, and GraphQL is the better fit for these kinds of queries. GraphQL has these important features:

* Specify the fields and connections that should be included in the query result, including nested connections that traverse the PID Graph.
* Supports queries of external resources, e.g. information by other PID providers
* Schema that describes and enforces the queries that are possible
* Rich set of developer tools and supporting libraries
[block:api-header]
{
  "title": "GraphQL clients"
}
[/block]
Because the GraphQL query interfaces are standardized and described in a schema, any GraphQL client application can automatically work with any GraphQL API. This also includes built-in documentation and auto-complete functionality when constructing queries:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a374210-Bildschirmfoto_2019-05-13_um_11.59.09.png",
        "Bildschirmfoto 2019-05-13 um 11.59.09.png",
        683,
        394,
        "#f4f5f7"
      ]
    }
  ]
}
[/block]
[Graphiql](https://github.com/graphql/graphiql) is a popular GraphQL client and is available as a library to include in other applications, or as a [desktop application](https://electronjs.org/apps/graphiql). You can also use web-hosted GraphQL clients, e.g. [here](https://www.graphqlbin.com).

GraphQL uses a special query language that resembles JSON. For example:

```json
{
  funder(id: "https://doi.org/10.13039/501100000780") {
    name
    alternateName
    datasets(first: 10, after: "Mg") {
      edges {
        relationType
        source
        cursor
        node {
          id
          titles {
            title
          }
          relatedIdentifiers {
            relatedIdentifier
            relationType
          }
          fundingReferences {
            awardTitle
            awardNumber
          }
        }
      }
    }
  }
}
```

The built-in documentation shows the available fields, not only helping with the construction of a query, but also validating the input. For this reason, we aren't listing the available fields in the support documentation.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a05dcc4-Bildschirmfoto_2019-05-14_um_15.00.19.png",
        "Bildschirmfoto 2019-05-14 um 15.00.19.png",
        1272,
        1150,
        "#fcfbfb"
      ]
    }
  ]
}
[/block]
The API response is normal JSON, following exactly the structure of the query. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/65346c2-Bildschirmfoto_2019-05-14_um_15.02.41.png",
        "Bildschirmfoto 2019-05-14 um 15.02.41.png",
        2622,
        1032,
        "#f6f6f8"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Resources available in the DataCite GraphQL API"
}
[/block]
You can query the GraphQL API for the following resources:

* Providers
* Clients
* Prefixes
* DOIs
* Researchers (using the ORCID API)
* Funders (using the Crossref Funder ID API)
* Organizations (using the ROR API)

When querying DOIs you must specify the `resourceTypeGeneral` in the request, rather than querying all DOIs at large. For example, the query below specifies that it is looking for a `dataset`:

```json
{ 
  dataset(id: "https://doi.org/10.7910/dvn/nfzli3/cynkam") {
    titles {
      title
    }
    publicationYear
    publisher
  }
 }
```

There is one exception: use `publication` for resourceTypeGeneral `text`.

You can either fetch information about a single resource using the PID, or do a query for multiple resources. The dataset query example above is fetching information about a single resource, as is the researcher query example below. 

```json
{
  researcher(id: "https://orcid.org/0000-0003-1419-2405") {
    id
    name
  }
}
```

The publications query below demonstrates how to do a query for multiple resources. In this case, we are fetching information about all items with a `resourceTypeGeneral` of `text` (because we're specifying `publications`) that contain the word "climate". 

```json
{
  publications(query: "climate") {
    totalCount
    
    nodes {
      id
      titles {
        title
      }
      descriptions {
        description
      }
      creators {
        name
        familyName
      }
      fundingReferences {
        funderIdentifier
        funderName
        awardTitle
        awardNumber
      }
    }
  }
}
```

Queries for researchers by anything other than id are not yet supported, as the ORCID API that is used for that query currently only returns the ORCID ID in the query results.

Queries support the `totalCount` field and return results under the `nodes` field (see example above). For queries using the Event Data service, results are returned under an `edges` field, optionally returning the meta information contained in Event Data (e.g. `source` or `relationType`), and then the related resources (datasets in the example below) under a `node` field.

```json
{
  funder(id: "https://doi.org/10.13039/501100000780") {
    name
    alternateName
    datasets(first: 10, after: "Mg") {
      edges {
        relationType
        source
        cursor
        node {
          id
          titles {
            title
          }
          relatedIdentifiers {
            relatedIdentifier
            relationType
          }
          fundingReferences {
            awardTitle
            awardNumber
          }
        }
      }
    }
  }
}
```
[block:api-header]
{
  "title": "Developing applications using the DataCite GraphQL API"
}
[/block]
Using a GraphQL client to explore what queries are supported in the DataCite GraphQL API, as described above, is a good starting point. To then develop an application using the DataCite GraphQL API we recommend picking a GraphQL library for the language you will be using, starting from [this list](https://graphql.org/code/).

Please post a message to [the PID Graph category of the PID Forum](https://www.pidforum.org/c/pid-graph) if you have any questions regarding the DataCite GraphQL API.