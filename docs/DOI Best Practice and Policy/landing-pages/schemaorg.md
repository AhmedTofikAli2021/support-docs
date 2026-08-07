---
title: Schema.org markup for repository landing pages
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
[Schema.org](https://schema.org/) is a set of schemas for structured data on the Internet, on web pages, in email messages, and for search engines to coordinate on metadata for indexing the web.

DataCite metadata can be expressed in Schema.org format and can be used on repository landing pages. DataCite recommends adding Schema.org markup to repository landing pages to [expose them to Google Dataset Search](doc:how-do-i-expose-my-datasets-to-google-dataset-search). For more information on exposing your datasets to Google Dataset Search, see Google's help page on the [Dataset content type](https://developers.google.com/search/docs/data-types/dataset).

## How do I create the Schema.org markup for my repository landing pages?

There are two ways to do this: 1. manually implementing this in the repository pages, or 2. automating the process using the DataCite Content negotiation service.

1. DataCite has published a crosswalk which maps the DataCite Metadata Schema 4.4 to Schema.org to help with manually implementing Schema.org markup on repository landing pages.

> 📘 DataCite Metadata Schema 4.4 to Schema.org Mapping
> 
> Here is a full crosswalk from the [DataCite Metadata Schema to Schema.org](https://zenodo.org/record/7661399#.ZBsmHOzMKWB).

2. The DataCite Content Negotiation service is also available to enable retrieval of Schema.org metadata to embed on repository landing pages.

> 📘 DataCite Content Negotiation for schema.org metadata
> 
> [DataCite Content Negotiation](https://support.datacite.org/docs/datacite-content-resolver) can be used to retrieve Schema.org metadata to embed in landing pages.
> 
> For example, you can include this [Javascript file](https://github.com/datacite/utilities/blob/main/support/metadata_schema_org_request.js) that will return metadata in Schema.org markup dynamically through DataCite Content Negotiation. Add a `<script>` tag with the file to the script to your landing page template. Whenever a landing page is requested, the script will append the appropriate metadata in Schema.org markup.

An example of a repository page using schema.org markup can be found here: <https://doi.pangaea.de/10.1594/PANGAEA.932235>

If you’re not sure whether your repository landing pages contain the appropriate structured data, you can test them using Google’s [Structured Data Testing Tool](https://search.google.com/structured-data/testing-tool).