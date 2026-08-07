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
## Supported formats

You can send metadata to DataCite in any of the following formats and it will be converted and validated against the DataCite XML schema. The [DataCite Metadata Schema website](http://schema.datacite.org) provides detailed descriptions of all fields in the XML schema and examples.

## Full metadata

- DataCite XML
- DataCite JSON API 
- Schema.org JSON-LD
- Codemeta JSON
- BibTeX
- RIS
- Citeproc JSON
- JATS XML  

## Citation metadata crosswalk

The required fields for citation.

| DataCite XML        | schema.org    | RIS | BibTex    | Code meta     | JSON API response | Citeproc JSON | Jats XML         |
| :------------------ | :------------ | :-- | :-------- | :------------ | :---------------- | :------------ | :--------------- |
| identifier          | @id           | DO  | @misc     | @id           | id                | Id            | pub-id           |
| title               | name          | T1  | title     | name          | titles            | title         | source           |
| creator             | author        | AU  | author    | author        | creators          | author        | person-group     |
| publisher           | publisher     | PB  | publisher | publisher     | publisher         | publisher     | publisher-name   |
| publicationYear     | datePublished | PY  | year      | datePublished | publicationYear   | issued        | year             |
| version             | version       |     |           | version       | version           | version       | version          |
| resourceTypeGeneral | @type         | TY  | types     | types         | types             | type          | publication-type |

## Discovery metadata crosswalk

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
    "h-6": "Citeproc JSON",
    "h-7": "Jats XML",
    "0-0": "description",
    "0-1": "description",
    "0-2": "AB",
    "0-3": "",
    "0-4": "description",
    "0-5": "descriptions",
    "0-6": "abstract",
    "0-7": "",
    "1-0": "subject",
    "1-1": "keywords",
    "1-2": "KW",
    "1-3": "keywords",
    "1-4": "",
    "1-5": "subjects",
    "1-6": "categories",
    "1-7": "",
    "2-0": "rights",
    "2-1": "license",
    "2-2": "SN",
    "2-3": "copyright",
    "2-4": "license",
    "2-5": "rights",
    "2-6": "",
    "2-7": "",
    "3-0": "relatedIdentifier",
    "3-1": "isPartOf  \ncitation",
    "3-2": "SN",
    "3-3": "",
    "3-4": "relatedLink",
    "3-5": "relatedIdentifiers",
    "3-6": "",
    "3-7": ""
  },
  "cols": 8,
  "rows": 4,
  "align": [
    "left",
    "left",
    "left",
    "left",
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


## DataCite JSON

The [DataCite REST API](https://support.datacite.org/docs/api) supports JSON-formatted DataCite metadata for creating and updating DOI metadata. 

- Example payloads to create a DOI: <https://support.datacite.org/docs/api-create-dois#examples>

DataCite JSON is a supported format for retrieving DataCite metadata via content negotiation, DataCite Commons, and other sources.

- Example response when retrieving a DOI: <https://support.datacite.org/docs/api-get-doi#response>

## Dublin Core

The DataCite Metadata Working Group has created a [DataCite to Dublin Core Mapping](https://datacite-metadata-schema.readthedocs.io/en/4/mappings/dublincore/).

## Resources

1. The Research Data Alliance Research Metadata Schemas Working Group has put together a [prototype service](https://rd-alliance.github.io/Research-Metadata-Schemas-WG/) for the research data management community in support of managers who are investigating options for including schema.org markup into existing well formed metadata.

2. This publication from Scientific Data [a data citation roadmap for scholarly data repositories](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6472386/) is a practical roadmap for scholarly data repositories to implement data citation in accordance with the Joint Declaration of Data Citation Principles. 

3. The full Crosswalk of [CodeMeta metadata](https://codemeta.github.io/crosswalk/datacite/).

4. DataCite's [Bolognese Github repository for metadata conversions](https://github.com/datacite/bolognese) for conversion of DOI metadata from and to different metadata formats, including schema.org.