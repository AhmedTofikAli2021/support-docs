---
title: How can I include facets in API requests?
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
If you are using the DataCite REST API /dois endpoint for [querying DOI metadata](docs:api-queries)  or harvesting DOI metadata records, you can choose whether to include facets in the response.

[Facets are aggregations](https://support.datacite.org/docs/api-get-lists#whats-in-the-api-response) about the results, e.g., resourceTypes, created date, and affiliations. To optimize querying, facets are not included by default.

To retrieve facets, requests must include the URL parameter disable-facets=false

For example, this query retrieves DOIs with the resourceTypeGeneral:Software and includes facets in the results:

<https://api.datacite.org/dois?resource-type-id=software&disable-facets=false>

Use the facets to see aggregated information, e.g., the top ten DataCite Members or Consortium Organizations publishing the most software DOIs:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b9d33a805be73068fc175bf4da9f955ddd4fcb0d87c49d803ddedc36275aae7-Screenshot_2026-03-02_at_17.18.59.png",
        "",
        "Facet included in the REST API Results"
      ],
      "align": "center",
      "sizing": "500px",
      "caption": "Facet in the REST API Results"
    }
  ]
}
[/block]


Note: The meta attribute of the DataCite REST API /dois endpoint previously displayed facets by default.

[Learn more about these changes](https://support.datacite.org/docs/datacite-rest-api-facets-meta-default-change)