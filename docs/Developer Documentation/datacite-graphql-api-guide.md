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
> 📘 What is GraphQL?
> 
> GraphQL is a query language for APIs and a runtime for fulfilling those queries with your existing data. GraphQL provides a complete and understandable description of the data in your API, gives clients the power to ask for exactly what they need, and nothing more, makes it easier to evolve APIs over time, and enables powerful developer tools.
> 
> Source: [GraphQL community website](https://graphql.org/)
> 
> GraphQL is not REST, so many functionalities common to many APIs are not supported, in particular, the use of HTTP verbs and resource paths. All GraphQL API calls are POST requests to <https://api.datacite.org/graphql>, and the query is defined in the body of the POST.
> 
> GraphQL was created in 2012, and made available as Open Source software in 2015. By 2020 it has been widely adopted by many communities, programming languages, and technology stacks. A good starting point to learn more is the [GraphQL community website](https://graphql.org/).

## Introduction

The DataCite GraphQL API support queries of the DataCite API using the [GraphQL query language](https://graphql.org/). The pre-release version of the API was launched in May 2019, with an official release of the DataCite GraphQL API in May 2020. The API endpoint is <https://api.datacite.org/graphql>.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FefvxGfU_oVM%3Ffeature%3Doembed&url=http%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DefvxGfU_oVM&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FefvxGfU_oVM%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=efvxGfU_oVM",
  "title": "Introduction to the DataCite GraphQL API (pre-release version)",
  "favicon": "https://s.ytimg.com/yts/img/favicon-vfl8qSV2F.ico",
  "image": "https://i.ytimg.com/vi/efvxGfU_oVM/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=efvxGfU_oVM"
}
[/block]
The GraphQL API is an alternative to the DataCite REST API, and currently only supports **queries**, but not **mutations** (create or update actions, e.g. registering a new DOI), or **subscriptions**.

## The PID Graph

DataCite DOIs describe resources such as datasets, samples, software and publications with rich metadata. An important part of this metadata is the description of connections between resources that use persistent identifiers (PIDs) provided by DataCite and others ([Crossref](https://crossref.org), [ORCID](https://orcid.org), [ROR](https://ror.org), [ISNI]\(<https://isni.org>, [IGSN](https://www.igsn.org/), etc.). Together these resources and their connections form a graph, the [PID Graph](https://doi.org/10.5438/jwvf-8a66):

![](https://files.readme.io/662994a-pid_graph_image.png "pid_graph_image.png")
Three important categories of user stories are described in Fig. A-C:

### Reuse across Versions and Parts (Fig. A)

Datasets and software (and to a lesser degree publications) are frequently versioned, and datasets can often be downloaded as subsets. Tracking the reuse (views, downloads, and citations) across versions and parts is a frequent use case and can lead to confusion in the community regarding proper versioning. An important publications user story is linking preprints and peer-reviewed publications.

### Reuse of Aggregated Research Outputs (Fig. B)

This might be the largest category of PID Graph user stories. We want to have a summary view of the reuse (via views, downloads, and citations) of all research outputs by a particular researcher, academic institution, data repository, or funder. This summary view can help demonstrate the impact of for example a researcher or repository.

### Research Objects (Fig. C)

Aggregate all scholarly resources that are linked together via a single publication, including underlying data and software used to generate the results, but also people, organizations, and funding involved in the work. Exploring the connections in and to a research object is currently very difficult, e.g. starting from a dataset included in a research object, getting a list of publications that indirectly cite this dataset by citing the publication based on the data.

## Using GraphQL to query the PID Graph

The REST APIs that most PID service providers, including DataCite, use to expose metadata about PIDs are a good fit to describe a single resource, e.g. a dataset, and show the connections to other resources (e.g. the authors of a dataset) by including the PIDs for those linked resources. REST APIs are not a good fit for complex queries of the PID Graph, and GraphQL is the better fit for these kinds of queries. GraphQL has these important features:

- Specify the fields and connections that should be included in the query result, including nested connections that traverse the PID Graph, not more and not less.
- Supports queries of external resources, e.g. information by other PID providers
- Schema that describes and enforces the queries that are possible
- Rich set of developer tools and supporting libraries

## GraphQL clients

Because the GraphQL query interfaces are standardized and described in a schema, any GraphQL client application can automatically work with any GraphQL API. This also includes built-in documentation and auto-complete functionality when constructing queries:

![](https://files.readme.io/a374210-Bildschirmfoto_2019-05-13_um_11.59.09.png "Bildschirmfoto 2019-05-13 um 11.59.09.png")
[Graphiql](https://github.com/graphql/graphiql) is a popular GraphQL client and is available as a library to include in other applications, or as a [desktop application](https://electronjs.org/apps/graphiql). The DataCite GraphQL API also includes a GraphQL client, available for the web browser at <https://api.datacite.org/graphql>.

GraphQL uses a special query language that resembles JSON. For example:

```graphql
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

The built-in documentation shows the available fields, not only helping with the construction of a query, but also validating the input. The built in documentations should therefore be used as the GraphQL API reference, e.g. details on what input format (e.g. number or text) for a particular field should be used.

![](https://files.readme.io/a05dcc4-Bildschirmfoto_2019-05-14_um_15.00.19.png "Bildschirmfoto 2019-05-14 um 15.00.19.png")

The API response is normal JSON, following exactly the structure of the query. 

![](https://files.readme.io/65346c2-Bildschirmfoto_2019-05-14_um_15.02.41.png "Bildschirmfoto 2019-05-14 um 15.02.41.png")

## Resources available in the DataCite GraphQL API

You can query the GraphQL API for the following resources:

- Members
- Repositories
- Prefixes
- DOIs
- Researchers (using the ORCID API)
- Funders (using the Crossref Funder ID API)
- Organizations (using the ROR API)

When querying DOIs you can specify the `resourceTypeGeneral` in the request, rather than querying all DOIs at large. For example, the query below specifies that it is looking for a `dataset`:

```graphql
{ 
  dataset(id: "https://doi.org/10.7910/dvn/nfzli3/cynkam") {
    titles {
      title
    }
    publicationYear
    publisher {
      name
    }
  }
 }
```
There are a few exception, as the API provides DOIs from both DataCite and Crossref: 

- use `publication` for resourceTypeGeneral `text`.
- use `dissertation` to find any resource of type `thesis` or `dissertation`.
- use `preprint` to find any resource with type `preprint` or `postedContent`.
- use `instrument` to find any instrument registered with a DOI.

You can either fetch information about a single resource using the PID, or do a query for multiple resources. The dataset query example above is fetching information about a single resource, as is the researcher query example below. 

```graphql
{
  researcher(id: "https://orcid.org/0000-0003-1419-2405") {
    id
    name
  }
}
```
The publications query below demonstrates how to do a query for multiple resources. In this case, we are fetching information about all items with a `resourceTypeGeneral` of `text` (because we're specifying `publications`) that contain the word "climate". 

```graphql
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

Queries support the `totalCount` field and return results under the `nodes` field (see example above). 

## Examples

### Researcher Profile

> As a researcher, I want to get a list of all my research outputs (publications, datasets, software, etc.) supported by grant funding, and how often they are cited, to demonstrate the impact of my work.

This example uses the ORCID ID of a person to find all publications, datasets, software, and other research outputs, and how often they have been reused (cited, viewed, or downloaded). Please replace the ORCID ID in the example with the ORCID ID of the person you are looking for. The example further filters the research outputs to only include those where funding has been specified.

```graphql
{
  person(id: "https://orcid.org/0000-0001-5934-7525") {
    id
    name
    givenName
    familyName
    citationCount
    works(hasFunder: true) {
      totalCount
      published {
        title
        count
      }
      resourceTypes {
        title
        count
      }
      nodes {
        id
        type
        titles {
          title
        }
        rights {
          rights
        }
        citationCount
      }
    }
  }
}
```

### Research Outputs per Organization

> As an administrator for the University of Oxford I am interested in the reuse of research outputs from our university, so that I can help identify the most interesting research outputs.

This example fetches all research outputs linked to the research organization identified by ROR ID <https://ror.org/052gg0110>. It then filters the results to only include research outputs that have been viewed at least 100 times, as a proxy for the "most interesting research outputs".

```graphql json
{
  organization(id: "https://ror.org/052gg0110") {
    id
    name
    alternateName
    citationCount
    viewCount
    downloadCount
    works(hasViews: 100, first: 100) {
      totalCount
      published {
        title
        count
      }
      resourceTypes {
        title
        count
      }
      nodes {
        id
        type
        publisher {
          name
        }
        publicationYear
        titles {
          title
        }
        creators {
          id
          name
          affiliation {
            id
            name
          }
        }
        citationCount
        viewCount
        downloadCount
      }
    }
  }
}

```
## PID Graph KPI

> As a software developer, I want to get an overview of all resources and their connections available in the PID Graph, so that I can see the information available to build value-added services on top of the PID Graph.

This example uses the DataCite GraphQL API to fetch summary statistics about the nodes and links (edges) in the PID Graph.

```graphql
{
  publications {
    totalCount
    datasetConnectionCount
    softwareConnectionCount
    personConnectionCount
    organizationConnectionCount
    funderConnectionCount
  }
  datasets {
    totalCount
    softwareConnectionCount
    personConnectionCount
    organizationConnectionCount
    funderConnectionCount
  }
  softwares {
    totalCount
    personConnectionCount
    organizationConnectionCount
    funderConnectionCount
  }
  people(query: "*") {
    totalCount
    organizationConnectionCount
  }
  organizations {
    totalCount
  }

  funders {
    totalCount
  }
}
```

### Query by Funder

> As a funder, I want to search all research outputs (including publications, datasets and software) funded by us, so that I can find relevant work that we funded.

This example aggregates all research outputs funded by a particular funder, and allows further queries and faceting (e.g. by year and resource type).

```graphql
{
  funder(id: "https://doi.org/10.13039/501100001659") {
    id
    name
    works(query: "polarstern") {
      totalCount
      published {
        title
        count
      }
      resourceTypes {
        title
        count
      }
      nodes {
        id
        type
        titles {
          title
        }
        creators {
          id
          name
        }
        publicationYear
        publisher {
          name
        }
      }
    }
  }
}```
`

## Questions and Feedback

Using a GraphQL client to explore what queries are supported in the DataCite GraphQL API, as described above, is a good starting point. To then develop an application using the DataCite GraphQL API we recommend picking a GraphQL library for the language you will be using, starting from [this list](https://graphql.org/code/).

Please post a message to [the PID Graph category of the PID Forum](https://www.pidforum.org/c/pid-graph) if you have any questions regarding the DataCite GraphQL API, or reach out to [DataCite Support](mailto:support@datacite.org).

> 📘 DOI connection indexing
> 
> Depending on system load, DOI connections, like citations, references, and parts, may not appear immediately in Commons when DataCite DOI metadata is updated or created. If expected DOI connections do not appear 24 hours after a DOI is created or updated, please reach out to [support@datacite.org](mailto:support@datacite.org).