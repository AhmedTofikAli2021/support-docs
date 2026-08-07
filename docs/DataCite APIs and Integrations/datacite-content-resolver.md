---
title: DataCite Content Negotiation
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
## What is content negotiation?

Content negotiation allows a user to request a particular representation of a web resource. DOI resolvers use content negotiation to provide different representations of metadata associated with DOIs.

## What is DataCite Content Negotiation?

DataCite content negotiation allows you to retrieve metadata for DataCite DOIs in different formats. It can be used by an HTTP client by configuring its HTTP `Accept` headers, or directly through a browser by constructing a URL (see [Link-based Content Type Requests](#link-based-content-type-requests)).

DOI content negotiation allows you retrieve metadata for DOIs registered by DataCite _and_ other DOI registration agencies. For more information on using content negotiation with DOIs from other DOI registration agencies, see the [Crosscite documentation](https://citation.crosscite.org/docs.html).

## Who can use DataCite Content Negotiation?

DataCite content negotiation is open to the whole community and does not require authentication. It is designed to provide direct access to all DataCite DOIs, simplify integrations and avoid format conversions.

> 📘 Citation Formatter
> 
> The DataCite Citation Formatter is one example of what can be done with DOI content negotiation. For more information, please visit [DataCite Citation Formatter Documentation](doc:datacite-citation-formatter).

## How does the DataCite Content Negotiation work?

The DOI proxy at doi.org will normally redirect a user to the resource location URL of a DOI. This applies to normal browser requests or explicit requests for text/html redirect to the content's landing page. For example, the DOI "<https://doi.org/10.5284/1015681>" redirects to a landing page describing a dataset with the title "Excavation of a Romano-British Cemetery at the water treatment plant, Saltersford, Grantham, Lincolnshire". 

```text
GET "Accept: text/html"
https://doi.org/10.5284/1015681

                   |
                   |
                   |
                   V

       Repository landing page
archaeologydataservice.ac.uk/archives/view/greylit/details.cfm?id=13979
```



Content negotiated requests to doi.org that ask for a content type other than "text/html" will be redirected to the registration agency's metadata service content negotiation service. For DataCite DOIs, this is the DataCite content negotiation service at <https://data.crosscite.org>.

```text
GET "Accept: application/csl+json"
     https://doi.org/10.5284/1015681
                 |
                 |
                 |
                 V
       DataCite content negotiation service
https://data.crosscite.org/10.5284/1015681
```



## Content Negotiation

### The Accept Header

Making a content negotiated request requires the use of the `Accept` HTTP header.  This header is used to indicate which content type(s) the client is able to understand.

For example, a client that wishes to receive citeproc JSON could make the following request:

```shell
curl -LH "Accept: application/vnd.citationstyles.csl+json" https://doi.org/10.5284/1015681
```



It is also possible to specify more than one content type. The order of preference is indicated either through the order of the content types, or through the inclusion of [quality values](https://developer.mozilla.org/en-US/docs/Glossary/Quality_values).

For example, a client that wishes to receive citeproc JSON if it is available, but which can also handle BibTeX if citeproc JSON is unavailable, would make a request with an Accept header listing both "application/citeproc+json" and "application/x-bibtex":

```shell
curl -LH "Accept: application/vnd.citationstyles.csl+json, application/rdf+xml" https://doi.org/10.5284/1015681
```



The same request can also be made with explicit quality values (e.g., q=0.5):

```shell
curl -LH "Accept: application/x-bibtex;q=0.5, application/vnd.citationstyles.csl+json;q=1.0" https://doi.org/10.5284/1015681
```



### Response codes

DataCite supports different response codes, listed below. If multiple content types specified by the client are supported by a DOI, then the content type with the highest "q" value (or, if no "q" values are specified, the one that appears first in the "accept" header) will be returned.

| Code | Meaning                                                 |
| :--- | :------------------------------------------------------ |
| 200  | The request was OK.                                     |
| 204  | The request was OK but there was no metadata available. |
| 404  | The DOI requested doesn't exist.                        |

## Link-based Content Type Requests

DataCite supports link-based content type requests. This method can be used with a regular web browser. In order to get a specific format please construct a URL following this pattern: `https://data.crosscite.org/MIME_TYPE/DOI`.

> 📘 
> 
> Direct requests to the DataCite content negotiation service via <https://data.crosscite.org> only supports DataCite DOIs

Extra parameters, e.g., when using the `text/x-bibliography` content type, can be included via query parameters. For example:

```shell
curl "https://data.crosscite.org/text/x-bibliography/10.5061/dryad.8515?style=ieee&locale=de"
```



## Supported Content Types

DataCite content negotiation supports a number of metadata content types:

| Format                                                                             | Content Type                            |
| :--------------------------------------------------------------------------------- | :-------------------------------------- |
| [RDF XML](http://www.w3.org/TR/rdf-syntax-grammar/)                                | application/rdf+xml                     |
| [RDF Turtle](http://www.w3.org/TeamSubmission/turtle/)                             | text/turtle                             |
| [Citeproc JSON](https://github.com/citation-style-language/schema#csl-json-schema) | application/vnd.citationstyles.csl+json |
| [Schema.org in JSON-LD](http://schema.org/)                                        | application/ld+json                     |
| [Codemeta](http://codemeta.github.io)                                              | application/vnd.codemeta.ld+json        |
| [Formatted text citation](http://citationstyles.org/)                              | text/x-bibliography                     |
| [RIS](http://en.wikipedia.org/wiki/RIS_(file_format))                              | application/x-research-info-systems     |
| [BibTeX](http://en.wikipedia.org/wiki/BibTeX)                                      | application/x-bibtex                    |
| [DataCite XML](https://schema.datacite.org/)                                       | application/vnd.datacite.datacite+xml   |
| [DataCite JSON](https://schema.datacite.org/)                                      | application/vnd.datacite.datacite+json  |
| [JATS](https://jats.nlm.nih.gov/)                                                  | application/vnd.jats+xml                |

> 🚧 Custom content types are no longer supported since January 1st, 2020
> 
> Registration of custom content types has been retired on October 1st, 2019 from the content negotiation via <https://doi.org> and on January 1st, 2020 from content negotiation via <https://data.datacite.org>. All requests for unknown content types will then be forwarded to the URL registered for the DOI in the handle system. The [media API](https://support.datacite.org/reference/media) will continue to support registration and retrieval of content with custom content types.
> 
> More information in this [blog post](https://doi.org/10.5438/nz0m-rb06)

## Formatted Citations

DataCite supports formatted citations via the text/bibliography content type. These are the output of the [Citation Style Language](https://citationstyles.org/) processor, citeproc-js. The content type can take two additional parameters to customise its response format. A "style" can be chosen from the list of style names found in the [CSL style repository](https://github.com/citation-style-language/styles). Many styles are supported, including common styles such as APA and MLA:

```shell
curl -LH "Accept: text/x-bibliography; style=apa" https://doi.org/10.5284/1015681

Archaeological Project Services. (1995). <i>Excavation of a Romano-British Cemetery at the water treatment plant, Saltersford, Grantham, Lincolnshire</i>. Archaeology Data Service. https://doi.org/10.5284/1015681
```



A locale can also be specified. Use one of the locale names from the [CSL locales repository](https://github.com/citation-style-language/locales):

```shell
curl -LH "Accept: text/x-bibliography; style=modern-language-association; locale=fr-FR" https://doi.org/10.5284/1101253

Dougherty, Eddie, et Gav Robinson. « Land east of the Nursery, Medburn, Northumberland: Excavation Report ». <i>Archaeologia Aeliana</i>, vol. 50.5, Archaeology Data Service, 2022, p. 1‑9, doi:10.5284/1101253
```



> 📘 Would you like to know more?
> 
> If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)