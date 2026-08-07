---
title: DOI Content Negotiation
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
##  Introduction

DOIs provide a persistent link to content. They identify many types of work, from journal articles to research data sets. Typically, someone interacting with DOIs will be a researcher, who will resolve DOIs found in scholarly references to content using a [DOI resolver](https://doi.org). Such researchers may not even realize they are using DOIs and a DOI resolver since they may follow links with embedded DOIs.

Yet DOIs can provide more than a permanent, indirect link to content. DOI registration agencies such as Crossref, DataCite and mEDRA collect bibliographic metadata about the works they link to. This metadata can be retrieved from a DOI resolver too, using content negotiation to request a particular representation of the metadata.

For some DOIs content negotiation can be used to retrieve different representations of a work. For example, some DataCite DOIs identify data sets that may be available in a number of data formats and container formats.



##  Redirection


The DOI resolver at doi.org will normally redirect a user to the resource location of a DOI. For example, the DOI "10.1126/science.169.3946.635" redirects to a landing page describing the article, "The Structure of Ordinary Water". Content negotiated requests to doi.org that ask for a content type which isn't "text/html" will be redirected to a metadata service hosted by the DOI's registration agency. Crossref, DataCite and mEDRA support content negotiated DOIs via [http://data.crossref.org](http://data.crossref.org), [http://data.datacite.org](http://data.datacite.org) and [http://data.medra.org](http://data.medra.org) respectively.



```shell
      GET "Accept: text/html"
https://doi.org/10.1126/science.169.3946.635

                   |
                   |
                   |
                   V

       Publisher landing page
http://www.sciencemag.org/content/169/3946/635
```


Normal browser requests or explicit requests for text/html redirect to the content's landing page.


```shell       
GET "Accept: application/rdf+xml"
https://doi.org/10.1126/science.169.3946.635

                   |
                   |
                   |
                   V

       Crossref metadata service
http://data.crossref.org/10.1126/science.169.3946.635

```

Requests for a data type redirect to a registration agency's metadata service.



##  What is Content Negotiation?



Content negotiation allows a user to request a particular representation of a web resource. DOI resolvers use content negotiation to provide different representations of metadata associated with DOIs.

A content negotiated request to a DOI resolver is much like a standard HTTP request, except server-driven negotiation will take place based on the list of acceptable content types a client provides.



### The Accept Header


Making a content negotiated request requires the use of a HTTP header, "Accept". Content types that are acceptable to the client (those that it knows how to parse), each with an optional "quality" value indicating its relative suitability. For example, a client that wishes to receive citeproc JSON if it is available, but which can also handle RDF XML if citeproc JSON is unavailable, would make a request with an Accept header listing both "application/citeproc+json" and "application/rdf+xml":

```shell
$ curl -LH "Accept: application/rdf+xml;q=0.5, application/vnd.citationstyles.csl+json;q=1.0" https://doi.org/10.1126/science.169.3946.635
```

``` json
{
  "volume" : "169",
  "issue" : "3946",
  "DOI" : "10.1126/science.169.3946.635",
  "URL" : "https://doi.org/10.1126/science.169.3946.635",
  "title" : "The Structure of Ordinary Water: New data and interpretations are
           yielding new insights into this fascinating substance",
  "container-title" : "Science",
  "publisher" : "American Association for the Advancement of Science AAAS (Science)",
  "issued" : { "date-parts" : [ [ 1970,8,14 ] ] },
  "author" : [ { "family" : "Frank", "given" : "H. S."} ],
  "editor" : [],
  "page" : "635-641",
  "type" : "article-journal"
}
```

This request favours citeproc JSON but will accept RDF XML if citeproc is unavailable. The q values are optional. The request could have been written without them. The order of content types then becomes important; more suitable content types should be placed at the front of the Accept header.

```shell
$ curl -LH "Accept: application/vnd.citationstyles.csl+json, application/rdf+xml" https://doi.org/10.1126/science.169.3946.635
```


###  Response Codes


| Code | Meaning                                                 |
|------|---------------------------------------------------------|
| 200  | The request was OK.                                     |
| 204  | The request was OK but there was no metadata available. |
| 404  | The DOI requested doesn't exist.                        |
| 406  | Can't serve any requested content type.                 |

Individual registration agency metadata services may have additional response codes but they will always use the response codes above in event of the case described.

If multiple content types specified by the client are supported by a DOI then the content type with the highest "q" value (or, if no "q" values are specified, the one that appears first in the "accept" header) will be returned.

##  Supported Content Types


Currently three DOI registration agencies have implemented content negotiation for their DOIs: Crossref, DataCite and mEDRA. They support a number of metadata content types, some of which are common to the three agencies.




| Format                  | Content Type                            | Crossref | DataCite | mEDRA |
|-------------------------|-----------------------------------------|----------|----------|-------|
| RDF XML                 | application/rdf+xml                     | Yes      | Yes      | Yes   |
| RDF Turtle              | text/turtle                             | Yes      | Yes      | Yes   |
| Citeproc JSON           | application/vnd.citationstyles.csl+json | Yes      | Yes      | Yes   |
| Formatted text citation | text/x-bibliography                     | Yes      | Yes      | Yes   |
| RIS                     | application/x-research-info-systems     | Yes      | Yes      | No    |
| BibTeX                  | application/x-bibtex                    | Yes      | Yes      | Yes   |
| Crossref Unixref XML    | application/vnd.crossref.unixref+xml    | Yes      | No       | No    |
| DataCite XML            | application/vnd.datacite.datacite+xml   | No       | Yes      | No    |
| ONIX for DOI            | application/vnd.medra.onixdoi+xml       | No       | No       | Yes   |




Using content negotiation it is possible to make a request that favours content types specific to a particular registration agency but which will also degrade to respond with a more standard content type for other registration agencies. For example:

```shell
$ curl -LH "Accept: application/vnd.crossref.unixref+xml;q=1, application/rdf+xml;q=0.5" https://doi.org/10.1126/science.169.3946.635
```

This request will return Crossref XML for Crossref DOIs and RDF XML for non-Crossref DOIs, such as DataCite DOIs.


###  Formatted Citations


Crossref, DataCite and mEDRA support formatted citations via the text/bibliography content type. These are the output of the [Citation Style Language](http://citationstyles.org/) processor, citeproc-js. The content type can take two additional parameters to customise its response format. A "style" can be chosen from the list of style names found in the [CSL style repository](https://github.com/citation-style-language/styles). Many styles are supported, including common styles such as apa and harvard3:

```shell
$ curl -LH "Accept: text/x-bibliography; style=apa" https://doi.org/10.1126/science.169.3946.635

Frank, H. S. (1970). The Structure of Ordinary Water: New data and interpretations are yielding
  new insights into this fascinating substance. Science, 169(3946), 635-641\. American Association
  for the Advancement of Science AAAS (Science). doi:10.1126/science.169.3946.635

```

A locale can also be specified. Use one of the locale names from the [CSL locales repository](https://github.com/citation-style-language/locales):

```shell
 $ curl -LH "Accept: text/x-bibliography; style=harvard3; locale=fr-FR" https://doi.org/10.1126/science.169.3946.635

Frank, HS 1970, « The Structure of Ordinary Water: New data and interpretations are yielding new
  insights into this fascinating substance ». Science, vol. 169, no. 3946, p. 635-641\. Consulté
  de https://doi.org/10.1126/science.169.3946.635
```

##  Link-based Content Type Requests


DataCite supports link-based content type requests, for example:

```shell
$ curl http://data.datacite.org/application/x-datacite+text/10.5524/100005
```

For documentation see [http://data.datacite.org](http://data.datacite.org).

Crossref also supports link-based content type requests via their REST API:

```shell
$ curl http://api.crossref.org/works/10.5555/12345678/transform/application/x-bibtex
```

For documentation see [http://api.crossref.org](http://api.crossref.org).


[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite).\nYou can also contact labs@crossref.org or medrastaff@cineca.it for support.",
  "title": "Would you like to know more?"
}
[/block]