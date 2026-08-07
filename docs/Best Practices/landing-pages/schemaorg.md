---
title: schema.org
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
[schema.org](https://schema.org/) is a set of schemas for structured data on the internet, on web pages, in email messages, and for search engines like Google, Bing and Yandex to coordinate on metadata for indexing the web.

DataCite metadata can be expressed in schema.org format and can be used on repository landing pages. DataCite recommends adding schema.org to repository landing pages to [expose them to Google Dataset Search](doc:how-do-i-expose-my-datasets-to-google-dataset-search). For more information on exposing your datasets to Google Dataset Search, see Google's help page on the [Dataset content type](https://developers.google.com/search/docs/data-types/dataset).

The most important metadata to include on the landing page are the "mandatory" metadata properties from the [DataCite metadata Schema](http://schema.datacite.org/). The below example shows the schema.org on a landing page from the DataCite blog.
[block:code]
{
  "codes": [
    {
      "code": "<script type=\"application/ld+json\">\n      {\"@context\":\"http://schema.org\",\"@type\":\"BlogPosting\",\"@id\":\"https://doi.org/10.5438/v5tc-zz53\",\"name\":\"The DataCite Technology Stack\",\"url\":\"https://blog.datacite.org/datacite-technology-stack/\",\"author\":[{\"@type\":\"Person\",\"@id\":\"https://orcid.org/0000-0003-1419-2405\",\"givenName\":\"Martin\",\"familyName\":\"Fenner\",\"name\":\"Martin Fenner\",\"affiliation\":{\"@id\":\"https://ror.org/04wxnsj81\",\"name\":\"DataCite\",\"@type\":\"Organization\"}}],\"publisher\":{\"@type\":\"Organization\",\"name\":\"DataCite\"},\"dateCreated\":\"2021-06-17\",\"datePublished\":\"2021-06-17\",\"dateModified\":\"2021-06-17\",\"keywords\":\"aws, docker, graphql, react, featured\",\"version\":\"1.0\",\"description\":\"DataCite is a DOI registration agency that enables the registration of scholarly content with a persistent identifier (DOI) and metadata. This content can then be searched for, reused, and connected to other scholarly resources. But how does the underlying...\",\"license\":\"https://creativecommons.org/licenses/by/4.0/legalcode\",\"isPartOf\":{\"@type\":\"Blog\",\"@id\":\"https://doi.org/10.5438/0000-00SS\",\"name\":\"DataCite Blog\"}}\n    </script>",
      "language": "shell"
    }
  ]
}
[/block]
An example of a repository page using a wider range of metadata can be found here: [https://doi.pangaea.de/10.1594/PANGAEA.932235](https://doi.pangaea.de/10.1594/PANGAEA.932235)

If you’re not sure whether your repository landing pages contain the appropriate structured data, you can test them using Google’s [Structured Data Testing Tool](https://search.google.com/structured-data/testing-tool).

More information about [mapping different metadata formats](doc:how-can-i-map-different-metadata-formats-to-the-datacite-xml).