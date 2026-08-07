---
title: How do DataCite services support the EOSC PIDGraph?
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Introduction to the PIDGraph

The PID Graph [started as an output of the FREYA project](https://doi.org/10.5438/jwvf-8a66), resulting in a GraphQL API and the first versions of [DataCite Commons](https://support.datacite.org/docs/datacite-commons). During the [FAIRCORE4EOSC project](https://faircore4eosc.eu), the [EOSC PIDGraph](https://faircore4eosc.eu/eosc-core-components/eosc-pid-graph-pid-graph) was created as a series of data enhancements, new services, and improvements to existing services, built on top of the original FREYA PID Graph.

The PIDGraph services are designed to facilitate the exposure and usage of PID metadata and connections, centered around a trusted source. In this instance, the core data of the graph is made up of DOI metadata held by DataCite. The network of the graph is built around the relationships that connect one DOI to another, and also outwards from DOIs to other established and trusted PIDs within the research community, including [ORCID iDs](https://orcid.org/) for people, [ROR IDs](https://ror.org/) for institutions, as well as domain-specific persistent identifiers such as [zbMATH Article Identifiers](https://zbmath.org/). 

## DataCite Services and the PIDGraph

DataCite provides different services that enable users to interact with the PIDGraph and the data it contains.

### DataCite REST API

The [DataCite REST API](doc:api) provides an interface for querying and retrieving the DOI metadata that makes up the core of the PIDGraph. Individual DOI records can be directly retrieved, and lists of DOI records can be returned by querying the API.

Full documentation is available from the [Introduction to the DataCite REST API](doc:api) page.

### DataCite Commons

[DataCite Commons](https://commons.datacite.org/) is a discovery, analytics, and reporting tool that harnesses the links among resources, people, and organizations found in DataCite DOI metadata. DataCite Commons supports searches for works (with DOIs), people (with ORCID iDs), organizations (with ROR IDs), and repositories

For more information, please see [Introduction to DataCite Commons](doc:datacite-commons).

### DataCite Public Data File and PID Links Data File

DataCite publishes two datasets of PID Graph data: one containing the metadata for all DataCite DOI nodes within the graph (the DataCite Public Data File), and one containing the vertices of the graph along with metadata about the connections (the DataCite PID Links Data File).

The [DataCite Public Data File](doc:datacite-public-data-file) is released yearly and comprises metadata for all publicly available DataCite DOIs that were registered up to the end of the year, stored as JSONLines and using the response structure from the DataCite REST API.

The DataCite PID Links file is released regularly, and comprises a core triple of object-subject-relationship as well as additional metadata about the relationship, such as the source of the assertion and when it occurred. The data is stored as JSONLines and is a subset of the [DataCite Event Data](doc:eventdata-guide) response structure.

Both Data Files are available via the [DataCite Data Files Service](https://datafiles.datacite.org/).

### DataCite OAI-PMH Service

The [DataCite OAI-PMH service](doc:doc:datacite-oai-pmh) can be used for harvesting the graph data using the [Open Archives Initiative Protocol for Metadata Harvesting](https://www.openarchives.org/pmh/), a common framework enabling interoperable exchange of data.

OAI-PMH compliant clients can make use of standard patterns such as sets, different metadata formats, and date-limited queries to retrieve targeted subsets of the graph.

More documentation on usage is available in the [DataCite OAI-PMH Guide](doc:datacite-oai-pmh).

### DataCite Event Data

[DataCite Event Data](doc:eventdata-guide) is the service that stores the connections between the different objects that make up the PIDGraph, as well as usage statistics. The data is sourced from DataCite DOI metadata, other DOI registration agencies, trusted third-party sources such as the zbMATH Open portal, and usage reports submitted to DataCite.

DataCite Event Data can be accessed as part of the PID Links Data File, or queried directly using the DataCite REST API. For guidance on querying, please see [DataCite Event Data](doc:eventdata-guide).