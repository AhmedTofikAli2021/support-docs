---
title: How can I map different metadata formats to the DataCite schema?
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
[block:api-header]
{
  "title": "Supported formats"
}
[/block]
You can send metadata to DataCite in any of the following formats and it will be converted and validated against the DataCite XML schema. The [DataCite Schema website](http://schema.datacite.org) provides detailed descriptions of all fields in the XML schema and examples.

## Full metadata
  * DataCite XML
  * DataCite JSON API 
  * Schema.org JSON-LD
  * Codemeta JSON
  * BibTeX
  * RIS
  * Citeproc JSON
  * JATS XML  
[block:api-header]
{
  "title": "Citation metadata crosswalk"
}
[/block]
The required fields for citation.
[block:parameters]
{
  "data": {
    "h-0": "DataCite XML",
    "h-1": "schema.org",
    "h-2": "RIS",
    "h-3": "BibTex",
    "h-4": "Code meta",
    "h-5": "JSON API response",
    "0-0": "identifier",
    "1-0": "title",
    "2-0": "creator",
    "3-0": "publisher",
    "4-0": "publicationYear",
    "5-0": "version",
    "6-0": "resourceTypeGeneral",
    "0-1": "@id",
    "1-1": "name",
    "2-1": "author",
    "3-1": "publisher",
    "4-1": "datePublished",
    "5-1": "version",
    "6-1": "@type",
    "0-2": "DO",
    "1-2": "T1, T2",
    "2-2": "AU",
    "3-2": "PB",
    "4-2": "PY",
    "6-2": "TY",
    "0-3": "@misc",
    "1-3": "title",
    "2-3": "author",
    "3-3": "publisher",
    "4-3": "year",
    "6-3": "types",
    "0-4": "@id",
    "1-4": "name",
    "2-4": "author",
    "3-4": "publisher",
    "4-4": "datePublished",
    "5-4": "version",
    "6-4": "types",
    "0-5": "id",
    "1-5": "titles",
    "2-5": "creators",
    "3-5": "publisher",
    "4-5": "publicationYear",
    "5-5": "version",
    "6-5": "types",
    "h-6": "Citeproc JSON",
    "h-7": "Jats XML",
    "0-6": "Id",
    "0-7": "pub-id",
    "1-7": "source",
    "2-7": "person-group",
    "3-7": "publisher-name",
    "4-7": "year",
    "6-7": "publication-type",
    "6-6": "type",
    "2-6": "author",
    "1-6": "title",
    "3-6": "publisher",
    "4-6": "issued",
    "5-6": "version",
    "5-7": "version"
  },
  "cols": 8,
  "rows": 7
}
[/block]

[block:api-header]
{
  "title": "Discovery metadata crosswalk"
}
[/block]
The most important fields for describing the resource.
[block:parameters]
{
  "data": {
    "h-0": "DataCite XML",
    "h-1": "schema.org",
    "h-2": "RIS",
    "h-3": "BibTex",
    "h-4": "Code meta",
    "h-5": "JSON API response",
    "0-0": "description",
    "1-0": "subject",
    "2-0": "rights",
    "3-0": "relatedIdentifier",
    "0-1": "description",
    "1-1": "keywords",
    "2-1": "license",
    "3-1": "isPartOf\ncitation",
    "0-2": "AB",
    "1-2": "KW",
    "2-2": "SN",
    "3-2": "SN",
    "0-3": "",
    "1-3": "keywords",
    "2-3": "copyright",
    "0-4": "description",
    "2-4": "license",
    "3-4": "relatedLink",
    "0-5": "descriptions",
    "1-5": "subjects",
    "2-5": "rights",
    "3-5": "relatedIdentifiers",
    "h-6": "Citeproc JSON",
    "h-7": "Jats XML",
    "0-6": "abstract",
    "1-6": "categories"
  },
  "cols": 8,
  "rows": 4
}
[/block]

[block:api-header]
{
  "title": "what about the DataCite JSON Schema?"
}
[/block]
The "DataCite JSON Schema" is still a work in progress. To find a [JSON Schema for the DataCite metadata visit the Datacite Schema Github repository](https://github.com/datacite/schema/blob/master/source/json/kernel-4.3/datacite_4.3_schema.json). When complete, it will allow users to validate the "DataCite JSON Schema" in the same way as the XML schema.
Do note that the "DataCite JSON Schema" is based on json-schema.org and therefore the current "DataCite JSON" will not conform to this.
[block:api-header]
{
  "title": "Resources"
}
[/block]

1. The Research Data Alliance Research Metadata Schemas Working Group has put together a [prototype service](https://rd-alliance.github.io/Research-Metadata-Schemas-WG/) for the research data management community in support of managers who are investigating options for including schema.org markup into existing well formed metadata.

2. This publication from Scientific Data [a data citation roadmap for scholarly data repositories](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6472386/) is a practical roadmap for scholarly data repositories to implement data citation in accordance with the Joint Declaration of Data Citation Principles. 

3. The full Crosswork of [CodeMeta metadata](https://codemeta.github.io/crosswalk/datacite/).

4. DataCite's [Bolognese Github repository for metadata conversions](https://github.com/datacite/bolognese) for conversion of DOI metadata from and to different metadata formats, including schema.org.