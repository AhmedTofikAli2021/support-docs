---
title: Landing pages and Google Dataset Search
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
[Google Dataset Search](https://datasetsearch.research.google.com/) is a search engine specifically for datasets. It relies on exposed crawlable structured data on landing pages via schema.org markup, using the schema.org [Dataset](https://schema.org/Dataset) class.

To ensure your repository's datasets are included in Google Dataset Search, we recommended following the guidelines below to embed schema.org metadata in your landing pages and ensure that Google can find your landing pages.
[block:callout]
{
  "type": "info",
  "body": "DataCite has no control over the processes and time it takes Google to index \"Dataset\" items in Google Dataset Search."
}
[/block]
For more information on exposing your datasets to Google Dataset Search, see Google's help page on the [Dataset content type](https://developers.google.com/search/docs/data-types/dataset).
[block:callout]
{
  "type": "success",
  "title": "Your repository's datasets should appear in Google Dataset Search if:",
  "body": "1. Landing pages include schema.org markup and use the `Dataset` class.\n2. Landing pages are reachable through navigation or through a sitemap file."
}
[/block]

[block:api-header]
{
  "title": "Structured Data"
}
[/block]
For datasets to show up in Google Dataset Search, a repository must include structured data on each landing page by implementing schema.org markup with the `Dataset` class.

For more information about how to implement schema.org markup on repository landing pages please review the [schema.org for repository landing pages documentation](doc:schemaorg).

To confirm whether landing pages contain the appropriate structured data, use Google’s [Structured Data Testing Tool](https://search.google.com/structured-data/testing-tool).
[block:callout]
{
  "type": "warning",
  "body": "Landing pages must use the `Dataset` class to be included in Google Dataset Search. When using Content Negotiation to generate schema.org markup, DOIs must:\n\n1. Have the Findable state (which is what makes them indexable).\n2. Use Dataset as the resourceTypeGeneral in the metadata you have registered with DataCite. Text items, for example, won't appear in Google Dataset Search."
}
[/block]

[block:api-header]
{
  "title": "Sitemaps"
}
[/block]
Using a sitemap file is recommended to help Google find your URLs. Using sitemap files and sameAs markup helps document how dataset descriptions are published throughout your site. More info: https://developers.google.com/search/docs/data-types/dataset