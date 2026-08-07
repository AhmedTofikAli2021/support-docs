---
title: DataCite GraphQL API Deprecation
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
## What’s changing?

The DataCite GraphQL API will be deprecated in **July 2027**.

The DataCite GraphQL API was first launched as a pre-release in May 2019, with an official release of the DataCite GraphQL API in May 2020. It was originally designed to serve as the basis for [DataCite Commons](doc:datacite-commons), making it possible to query relationships between works with DOIs, people with ORCID iDs, and organizations with ROR IDs. 

Over the past year, we have successfully transitioned DataCite Commons to rely exclusively on the DataCite REST API, while making the same metadata and relationships available in the interface and simultaneously improving performance. 

From our usage data, we can see that the vast majority of users have also shifted to the REST API for the types of queries GraphQL was intended to support. As part of shifting our development and support efforts to focus on the DataCite REST API, the DataCite GraphQL API will be deprecated on 1 July 2027. This deprecation will only affect a small number of users.

## What do I need to do?

If you’re currently using the DataCite GraphQL API, update your requests to use the DataCite REST API. Refer to the [DataCite REST API Guide](doc:api) and [API Reference](ref:get_dois) for more information.

For support with identifying suitable REST API queries, please reach out to us at [support@datacite.org](mailto:support@datacite.org).