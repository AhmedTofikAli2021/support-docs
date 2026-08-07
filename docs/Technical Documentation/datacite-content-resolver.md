---
title: DataCite Content Resolver
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
Access the DataCite Content Resolver here: [https://data.datacite.org](https://data.datacite.org)
[block:api-header]
{
  "title": "What is the DataCite Content Resolver?"
}
[/block]
The DataCite Content Resolver allows you to retrieve a particular representation of DOI in different formats. A content negotiated request to a DOI resolver is very similar to a standard HTTP request, but based on the list of acceptable content types.

It can be used by an HTTP client by configuring its HTTP `Accept` headers, or directly through a browser, constructing a URL.
[block:callout]
{
  "type": "info",
  "title": "Citation Formatter",
  "body": "The DataCite Citation Formatter is a particular implementation of the DataCite Content Resolver. If you want more information, please visit [DataCite Citation Formatter Documentation](doc:datacite-citation-formatter)."
}
[/block]

[block:api-header]
{
  "title": "Who can use the DataCite Content Resolver?"
}
[/block]
The Content Resolver is open to the whole community and does not require authentication. It is particularly designed to provide direct access to all our DOIs, simplify integrations and avoid format conversions.
[block:api-header]
{
  "title": "How does the DataCite Content Resolver work?"
}
[/block]
The DOI proxy at doi.org will normally redirect a user to the resource location URL of a DOI. For example, the DOI "10.5284/1015681" redirects to a landing page describing the dataset, "Excavation of a Romano-British Cemetery...". Content negotiated requests to doi.org that ask for a content type which isn't "text/html" will be redirected to the metadata service hosted by DataCite.
[block:code]
{
  "codes": [
    {
      "code": "       GET \"Accept: text/html\"\nhttps://doi.org/10.5284/1015681\n\n                   |\n                   |\n                   |\n                   V\n\n       Repository landing page\narchaeologydataservice.ac.uk/archives/view/greylit/details.cfm?id=13979",
      "language": "text"
    }
  ]
}
[/block]
Normal browser requests or explicit requests for text/html redirect to the content's landing page.
[block:code]
{
  "codes": [
    {
      "code": "    GET \"Accept: application/rdf+xml\"\n     https://doi.org/10.5284/1015681\n                 |\n                 |\n                 |\n                 V\n       DataCite metadata service\nhttp://data.datacite.org/10.5284/1015681",
      "language": "text"
    }
  ]
}
[/block]
Requests for a data type redirect to a registration agency's metadata service.
[block:api-header]
{
  "title": "Content Negotiation"
}
[/block]
Making a content negotiated request requires the use of the `Accept` HTTP header. Content types that are acceptable to the client (those that it knows how to parse), each with an optional "quality" value indicating its relative suitability. For example, a client that wishes to receive citeproc JSON if it is available, but which can also handle RDF XML if citeproc JSON is unavailable, would make a request with an Accept header listing both "application/citeproc+json" and "application/rdf+xml":
[block:code]
{
  "codes": [
    {
      "code": "$ curl -LH \"Accept: application/rdf+xml;q=0.5, application/vnd.citationstyles.csl+json;q=1.0\" https://doi.org/10.5284/1015681",
      "language": "text"
    }
  ]
}
[/block]
This request favours citeproc JSON but will accept RDF XML if citeproc is unavailable. The q values are optional. The request could have been written without them. The order of content types then becomes important; more suitable content types should be placed at the front of the Accept header.
[block:code]
{
  "codes": [
    {
      "code": "$ curl -LH \"Accept: application/vnd.citationstyles.csl+json, application/rdf+xml\" https://doi.org/10.5284/1015681",
      "language": "text"
    }
  ]
}
[/block]
DataCite supports different response codes, listed below. If multiple content types specified by the client are supported by a DOI then the content type with the highest "q" value (or, if no "q" values are specified, the one that appears first in the "accept" header) will be returned.
[block:parameters]
{
  "data": {
    "h-0": "Code",
    "h-1": "Meaning",
    "0-1": "The request was OK.",
    "0-0": "200",
    "1-0": "204",
    "2-0": "404",
    "1-1": "The request was OK but there was no metadata available.",
    "2-1": "The DOI requested doesn't exist."
  },
  "cols": 2,
  "rows": 3
}
[/block]

[block:api-header]
{
  "title": "Link-based Content Type Requests"
}
[/block]
DataCite supports link-based content type requests. This method can be used with a regular web browser. In order to get a specific format please construct a URL following this pattern: `https://data.datacite.org/MIME_TYPE/DOI`.

Extra parameters, e.g. when using the `text/x-bliography` content type, can be included, e.g. 

```
curl https://data.datacite.org/text/x-bibliography;style=ieee/10.5061/dryad.8515
```

This method allows DataCite data centres to link additional metadata and data itself using custom URLs, still using the primary URL for the DOI to point to the landing page of a data set.

For example, https://doi.org/10.5284/1015681 is a report in PDF format. It can be downloaded from its landing page, or automatically requesting:
[block:code]
{
  "codes": [
    {
      "code": "$ curl https://data.datacite.org/application/pdf/10.5284/1015681",
      "language": "text"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Supported Content Types"
}
[/block]
DataCite supports a number of metadata content types:
[block:parameters]
{
  "data": {
    "h-0": "Format",
    "h-1": "Content Type",
    "0-0": "[RDF XML](http://www.w3.org/TR/rdf-syntax-grammar/)",
    "0-1": "application/rdf+xml",
    "1-0": "[RDF Turtle](http://www.w3.org/TeamSubmission/turtle/)",
    "1-1": "text/turtle",
    "2-0": "[Citeproc JSON](http://gsl-nagoya-u.net/http/pub/citeproc-doc.html)",
    "2-1": "application/vnd.citationstyles.csl+json",
    "3-0": "[Schema.org in JSON-LD](http://schema.org/)",
    "3-1": "application/vnd.schemaorg.ld+json",
    "5-0": "[Formatted text citation](http://citationstyles.org/)",
    "5-1": "text/x-bibliography",
    "6-0": "[RIS](http://en.wikipedia.org/wiki/RIS_(file_format)",
    "6-1": "application/x-research-info-systems",
    "7-0": "[BibTeX](http://en.wikipedia.org/wiki/BibTeX)",
    "7-1": "application/x-bibtex",
    "8-0": "[DataCite XML](https://schema.datacite.org/)",
    "8-1": "application/vnd.datacite.datacite+xml",
    "4-0": "[Codemeta](http://codemeta.github.io)",
    "4-1": "application/vnd.codemeta.ld+json",
    "9-1": "application/vnd.datacite.datacite+json",
    "9-0": "[DataCite JSON](https://schema.datacite.org/)"
  },
  "cols": 2,
  "rows": 10
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Would you like to know more?",
  "body": "This document has been adapted from the [Crosscite documentation](http://citation.crosscite.org/docs.html), maintained by Crossref, DataCite, mEDRA and ISTIC.\n\nIf you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)"
}
[/block]