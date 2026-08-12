---
title: Advanced search queries in DataCite Commons
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
> 📘 
> 
> Searches for Works in DataCite Commons follow the same structure as the [query string used in the REST API](https://support.datacite.org/docs/api-queries#building-a-query-string) .

### Field names

Queries by default search commonly used fields, but a specific field can be provided in the query, e.g. <https://commons.datacite.org?query=publicationYear:2016>

For nested fields use the same format as in the REST API response, e.g. <https://commons.datacite.org?query=creators.nameIdentifiers.nameIdentifierType:ORCID>

### Wildcards

Wildcards are supported, e.g. <https://commons.datacite.org??query=creators.familyName:mil>\*

### Boolean operators

By default, all terms are optional, as long as one term matches. Use `+` or `-` to specify terms that have to match or not match, respectively. For example <https://commons.datacite.org?query=titles.title:climate%20+change>

### Ranges

For number and date fields, we can specify a range. Wildcards are supported e.g. <https://commons.datacite.org?query=publicationYear:[2019%20TO%20*]> or <https://commons.datacite.org?query=view_count:[1000%20TO%201999]> 

It is possible to search any element from the DataCite metadata schema using the JSON API response format for the query, for example to search the title: 

**titles.title:Mars**

Run this [search in DataCite Commons](https://commons.datacite.org/doi.org?query=titles.title%3Amars).

> 📘 
> 
> The syntax you use for the query must match the elements in the JSON API (different to the XML). All the properties are listed in API the response below. More examples are listed in the [examples section](https://support.datacite.org/docs/datacite-commons-search#examples).

<https://api.test.datacite.org/dois/10.17596/qf5s-pc52?affiliation=true&publisher=true>

```json
{
  "data": {
    "id": "10.17596/qf5s-pc52",
    "type": "dois",
    "attributes": {
      "doi": "10.17596/qf5s-pc52",
      "prefix": "10.17596",
      "suffix": "qf5s-pc52",
      "identifiers": [
        {
          "identifier": "https://schema.datacite.org/meta/kernel-4.4/example/datacite-example-full-v4.4.xml",
          "identifierType": "URL"
        }
      ],
      "alternateIdentifiers": [
        {
          "alternateIdentifierType": "URL",
          "alternateIdentifier": "https://schema.datacite.org/meta/kernel-4.4/example/datacite-example-full-v4.4.xml"
        }
      ],
      "creators": [
        {
          "name": "Miller, Elizabeth",
          "nameType": "Personal",
          "givenName": "Elizabeth",
          "familyName": "Miller",
          "affiliation": [
            {
              "name": "DataCite",
              "schemeUri": null,
              "affiliationIdentifier": null,
              "affiliationIdentifierScheme": null
            },
            {
              "name": "California Institute of Technology",
              "schemeUri": "https://ror.org",
              "affiliationIdentifier": "https://ror.org/05dxps055",
              "affiliationIdentifierScheme": "ROR"
            }
          ],
          "nameIdentifiers": [
            {
              "schemeUri": "https://orcid.org",
              "nameIdentifier": "https://orcid.org/0000-0001-5000-0007",
              "nameIdentifierScheme": "ORCID"
            }
          ]
        }
      ],
      "titles": [
        {
          "lang": "en-US",
          "title": "Full DataCite XML Example",
          "titleType": null
        },
        {
          "lang": "en-US",
          "title": "Demonstration of DataCite Properties.",
          "titleType": "Subtitle"
        }
      ],
      "publisher": {
        "name": "DataCite",
        "schemeUri": "https://ror.org",
        "publisherIdentifier": "https://ror.org/04wxnsj81",
        "publisherIdentifierScheme": "ROR"
      },
      "container": {},
      "publicationYear": 2014,
      "subjects": [
        {
          "subject": "computer science",
          "schemeUri": "http://dewey.info/",
          "subjectScheme": "dewey",
          "classificationCode": "000"
        }
      ],
      "contributors": [
        {
          "name": "Starr, Joan",
          "nameType": null,
          "givenName": "Joan",
          "familyName": "Starr",
          "affiliation": [
            {
              "name": "California Digital Library",
              "schemeUri": null,
              "affiliationIdentifier": null,
              "affiliationIdentifierScheme": null
            }
          ],
          "contributorType": "ProjectLeader",
          "nameIdentifiers": [
            {
              "schemeUri": "https://orcid.org",
              "nameIdentifier": "https://orcid.org/0000-0002-7285-027X",
              "nameIdentifierScheme": "ORCID"
            }
          ]
        }
      ],
      "dates": [
        {
          "date": "2021-01-26",
          "dateType": "Updated",
          "dateInformation": "Updated with 4.4 properties"
        },
        {
          "date": "2014",
          "dateType": "Issued",
          "dateInformation": null
        }
      ],
      "language": "en",
      "types": {
        "ris": "COMP",
        "bibtex": "misc",
        "citeproc": "article",
        "schemaOrg": "SoftwareSourceCode",
        "resourceType": "XML",
        "resourceTypeGeneral": "Software"
      },
      "relatedIdentifiers": [
        {
          "schemeUri": "https://github.com/citation-style-language/schema/raw/master/csl-data.json",
          "schemeType": null,
          "relationType": "HasMetadata",
          "relatedIdentifier": "https://data.datacite.org/application/citeproc+json/10.5072/example-full",
          "resourceTypeGeneral": null,
          "relatedIdentifierType": "URL",
          "relatedMetadataScheme": "citeproc+json"
        },
        {
          "schemeUri": null,
          "schemeType": null,
          "relationType": "IsReviewedBy",
          "relatedIdentifier": "arXiv:0706.0001",
          "resourceTypeGeneral": "Text",
          "relatedIdentifierType": "arXiv",
          "relatedMetadataScheme": null
        }
      ],
      "relatedItems": [
        {
          "titles": [
            {
              "title": "Physics letters B"
            }
          ],
          "volume": "776",
          "lastPage": "264",
          "firstPage": "249",
          "relationType": "IsPublishedIn",
          "publicationYear": "2018",
          "relatedItemType": "Journal",
          "relatedItemIdentifier": {
            "relatedItemIdentifier": "0370-2693",
            "relatedItemIdentifierType": "ISSN"
          }
        }
      ],
      "sizes": [
        "4 kB"
      ],
      "formats": [
        "application/xml"
      ],
      "version": "4.2",
      "rightsList": [
        {
          "rights": "Creative Commons Zero v1.0 Universal",
          "rightsUri": "https://creativecommons.org/publicdomain/zero/1.0/legalcode",
          "schemeUri": "https://spdx.org/licenses/",
          "rightsIdentifier": "cc0-1.0",
          "rightsIdentifierScheme": "SPDX"
        }
      ],
      "descriptions": [
        {
          "lang": "en-US",
          "description": "XML example of all DataCite Metadata Schema v4.4 properties.",
          "descriptionType": "Abstract"
        }
      ],
      "geoLocations": [
        {
          "geoLocationBox": {
            "eastBoundLongitude": -68.211,
            "northBoundLatitude": 42.893,
            "southBoundLatitude": 41.09,
            "westBoundLongitude": -71.032
          },
          "geoLocationPlace": "Atlantic Ocean",
          "geoLocationPoint": {
            "pointLatitude": 31.233,
            "pointLongitude": -67.302
          }
        }
      ],
      "fundingReferences": [
        {
          "awardUri": "https://www.moore.org/grants/list/GBMF3859.01",
          "awardTitle": "Full DataCite XML Example",
          "funderName": "National Science Foundation",
          "awardNumber": "CBET-106",
          "funderIdentifier": "05dxps055",
          "funderIdentifierType": "ROR"
        }
      ],
      "url": "https://example.org",
      "metadataVersion": 3,
      "schemaVersion": "http://datacite.org/schema/kernel-4"
    }
  }
}
```

## Examples

### 1\. Search for a specific publisher

```text
publisher:DataCite
```

Run the [publisher example search in DataCite Commons.](https://commons.datacite.org/doi.org?query=publisher%3ADataCite)

### 2\. Search for a single DOI

To search for a specific DOI use the DOI field in the metadata. 

```text
doi:10.11570/18.0006
```

[Run the example DOI search in DataCite Commons.](https://commons.datacite.org/doi.org?query=doi%3A10.11570%2F18.0006)

### 3\. Search the affiliation

In this case include both the parent and child elements from the schema and use a period (.) to separate the different levels in your search query.

```json

 },
  "creators": [
    {
      "name": "Bloggs, Jane",
      "nameType": "Personal",
      "givenName": "Jane",
      "familyName": "Bloggs",
      "affiliation": "DataCite",
      "nameIdentifiers": [
        {

```

```text
creators.affiliation.name:DataCite
```

Run the [example affiliation search in DataCite Commons](https://commons.datacite.org/doi.org?query=creators.affiliation.name%3ADataCite).

### 4\. Use quotes

To search for an exact string, for example, an author’s name, include the text between quotation marks, the search looks for the the exact string contained within the quotes.

```text
titles.title:"CrowdoMeter Tweets"
```

Run the [example search using quotation marks in DataCite Commons.](https://commons.datacite.org/doi.org?query=titles.title%3A%22CrowdoMeter+Tweets%22)

### 5\. Using operators ( e.g AND OR  + -)

Building more complex queries can be done with different syntax including AND OR + - (AND / OR must be capitalised)

Search for all works using the AND operator.

```text
types.resourceTypeGeneral:Software AND types.resourceType:XML
```

Run the [example query using the AND boolean in DataCite Commons.](https://commons.datacite.org/doi.org?query=types.resourceTypeGeneral%3ASoftware+AND+types.resourceType%3AXML)

Search for works using the "AND" and "OR" booleans.

```text
publisher:DataCite AND types.resourceTypeGeneral:(Text OR Dataset)
```

Run the [example query using the AND / OR booleans in DataCite Commons.](https://commons.datacite.org/doi.org?query=publisher%3ADataCite+AND+types.resourceTypeGeneral%3A%28Text+OR+Dataset%29)

### 6\. Wildcards

To run a broader search you can include the wildcard (\*)

Search for all works with the subject robot\*

```text
subjects.subject:robot*
```

Run the [example query using the wildcard in DataCite Commons](https://commons.datacite.org/doi.org?query=subjects.subject%3Arobot*) 

### 7\. Longer queries

Combine numerous elements to limit the search results. In this example the creators and the relatedIdentifier properties are used to build the query:

creators:

```json
"creators": [
    {
      "name": "Fenner, Martin",
      "nameType": "Personal",
      "givenName": "Martin",
      "familyName": "Fenner",
      "affiliation": [],
      "nameIdentifiers": [
        {
          "nameIdentifier": "https://orcid.org/0000-0003-1419-2405",
          "nameIdentifierScheme": "ORCID"
        }
      ]
    }
  ],
```

relatedIdentifiers:

```json
"relatedIdentifiers": [
    {
      "relationType": "HasPart",
      "relatedIdentifier": "10.5438/6423",
      "relatedIdentifierType": "DOI"
    },
```

```text
creators.name:"Fenner, Martin" AND relatedIdentifiers.relationType:hasPart
```

Run this longer query [example combining 2 elements in DataCite Commons.](https://commons.datacite.org/doi.org?query=creators.name%3A%22Fenner%2C+Martin%22+AND+relatedIdentifiers.relationType%3AHasPart)