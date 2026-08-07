---
title: Advanced search queries in DataCite Commons
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
The DataCite Commons and DOI Fabrica user interfaces are based on Elasticsearch. Both use the Elasticsearch [query string queries](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html#query-string-syntax)

To set up queries with the REST API, refer to the [REST API documentation for queries and filtering](doc:api-queries).

## How to Search

### Field names
Queries by default search all fields, but a specific field can be provided in the query, e.g. https://commons.datacite.org?query=publicationYear:2016

For nested fields use the same format as in the REST API response, e.g. https://commons.datacite.org?query=creators.nameIdentifiers.nameIdentifierType:ORCID

### Wildcards
Wildcards are supported, e.g. https://commons.datacite.org??query=creators.familyName:mil*

### Boolean operators
By default, all terms are optional, as long as one term matches. Use `+` or `-` to specify terms that have to match or not match, respectively. For example https://commons.datacite.org?query=titles.title:climate%20+change

### Ranges
For number and date fields, we can specify a range. Wildcards are supported e.g. [https://commons.datacite.org?query=publicationYear:[2019%20TO%20*]](https://commons.datacite.org?query=publicationYear:[2019%20TO%20*] ) or [https://commons.datacite.org?query=view_count:[1000%20TO%201999]](https://commons.datacite.org?query=view_count:[1000%20TO%201999]) 

It is possible to search any element from the DataCite metadata schema using the JSON API response format for the query, for example

###Search the title:

**titles.title:Mars**

Run this [search in DataCite Commons](https://commons.datacite.org/doi.org?query=titles.title%3Amars).
[block:callout]
{
  "type": "info",
  "body": "The syntax you use for the query must match the elements in the JSON API (different to the XML). All the properties are listed in API the response below. More examples are listed in the [examples section](https://support.datacite.org/docs/datacite-commons-search#examples)."
}
[/block]
https://api.test.datacite.org/dois/10.17596/qf5s-pc52?affiliation=true
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"data\": {\n    \"id\": \"10.70126/k7wk-rm36\",\n    \"type\": \"dois\",\n    \"attributes\": {\n      \"doi\": \"10.70126/k7wk-rm36\",\n      \"prefix\": \"10.70126\",\n      \"suffix\": \"k7wk-rm36\",\n      \"identifiers\": [\n        {\n          \"identifier\": \"https://schema.datacite.org/meta/kernel-4.4/example/datacite-example-full-v4.4.xml\",\n          \"identifierType\": \"URL\"\n        }\n      ],\n      \"alternateIdentifiers\": [\n        {\n          \"alternateIdentifierType\": \"URL\",\n          \"alternateIdentifier\": \"https://schema.datacite.org/meta/kernel-4.4/example/datacite-example-full-v4.4.xml\"\n        }\n      ],\n      \"creators\": [\n        {\n          \"name\": \"Miller, Elizabeth\",\n          \"nameType\": \"Personal\",\n          \"givenName\": \"Elizabeth\",\n          \"familyName\": \"Miller\",\n          \"affiliation\": [\n            \"DataCite\"\n          ],\n          \"nameIdentifiers\": [\n            {\n              \"schemeUri\": \"https://orcid.org\",\n              \"nameIdentifier\": \"https://orcid.org/0000-0001-5000-0007\",\n              \"nameIdentifierScheme\": \"ORCID\"\n            }\n          ]\n        }\n      ],\n      \"titles\": [\n        {\n          \"lang\": \"en-US\",\n          \"title\": \"Full DataCite XML Example\"\n        },\n        {\n          \"lang\": \"en-US\",\n          \"title\": \"Demonstration of DataCite Properties.\",\n          \"titleType\": \"Subtitle\"\n        }\n      ],\n      \"publisher\": \"DataCite\",\n      \"container\": {},\n      \"publicationYear\": 2014,\n      \"subjects\": [\n        {\n          \"lang\": \"en-US\",\n          \"subject\": \"computer science\",\n          \"schemeUri\": \"http://dewey.info/\",\n          \"subjectScheme\": \"dewey\",\n          \"classificationCode\": \"000\"\n        }\n      ],\n      \"contributors\": [\n        {\n          \"name\": \"Starr, Joan\",\n          \"givenName\": \"Joan\",\n          \"familyName\": \"Starr\",\n          \"affiliation\": [\n            \"California Digital Library\"\n          ],\n          \"contributorType\": \"ProjectLeader\",\n          \"nameIdentifiers\": [\n            {\n              \"schemeUri\": \"https://orcid.org\",\n              \"nameIdentifier\": \"https://orcid.org/0000-0002-7285-027X\",\n              \"nameIdentifierScheme\": \"ORCID\"\n            }\n          ]\n        }\n      ],\n      \"dates\": [\n        {\n          \"date\": \"2021-01-26\",\n          \"dateType\": \"Updated\",\n          \"dateInformation\": \"Updated with 4.4 properties\"\n        },\n        {\n          \"date\": \"2014\",\n          \"dateType\": \"Issued\"\n        }\n      ],\n      \"language\": \"en\",\n      \"types\": {\n        \"ris\": \"COMP\",\n        \"bibtex\": \"misc\",\n        \"citeproc\": \"article\",\n        \"schemaOrg\": \"SoftwareSourceCode\",\n        \"resourceType\": \"XML\",\n        \"resourceTypeGeneral\": \"Software\"\n      },\n      \"relatedIdentifiers\": [\n        {\n          \"schemeUri\": \"https://github.com/citation-style-language/schema/raw/master/csl-data.json\",\n          \"relationType\": \"HasMetadata\",\n          \"relatedIdentifier\": \"https://data.datacite.org/application/citeproc+json/10.5072/example-full\",\n          \"relatedIdentifierType\": \"URL\",\n          \"relatedMetadataScheme\": \"citeproc+json\"\n        },\n        {\n          \"relationType\": \"IsReviewedBy\",\n          \"relatedIdentifier\": \"arXiv:0706.0001\",\n          \"resourceTypeGeneral\": \"Text\",\n          \"relatedIdentifierType\": \"arXiv\"\n        }\n      ],\n      \"relatedItems\": [\n        {\n          \"titles\": [\n            {\n              \"title\": \"Physics letters B\"\n            }\n          ],\n          \"volume\": \"776\",\n          \"creators\": [],\n          \"lastPage\": \"264\",\n          \"firstPage\": \"249\",\n          \"contributors\": [],\n          \"relationType\": \"IsPublishedIn\",\n          \"publicationYear\": \"2018\",\n          \"relatedItemType\": \"Journal\",\n          \"relatedItemIdentifier\": {\n            \"relatedItemIdentifier\": \"0370-2693\",\n            \"relatedItemIdentifierType\": \"ISSN\"\n          }\n        }\n      ],\n      \"sizes\": [\n        \"4 kB\"\n      ],\n      \"formats\": [\n        \"application/xml\"\n      ],\n      \"version\": \"4.2\",\n      \"rightsList\": [\n        {\n          \"lang\": \"en-US\",\n          \"rights\": \"Creative Commons Zero v1.0 Universal\",\n          \"rightsUri\": \"https://creativecommons.org/publicdomain/zero/1.0/legalcode\",\n          \"schemeUri\": \"https://spdx.org/licenses/\",\n          \"rightsIdentifier\": \"cc0-1.0\",\n          \"rightsIdentifierScheme\": \"SPDX\"\n        }\n      ],\n      \"descriptions\": [\n        {\n          \"lang\": \"en-US\",\n          \"description\": \"XML example of all DataCite Metadata Schema v4.4 properties.\",\n          \"descriptionType\": \"Abstract\"\n        }\n      ],\n      \"geoLocations\": [\n        {\n          \"geoLocationBox\": {\n            \"eastBoundLongitude\": \"-68.211\",\n            \"northBoundLatitude\": \"42.893\",\n            \"southBoundLatitude\": \"41.090\",\n            \"westBoundLongitude\": \"-71.032\"\n          },\n          \"geoLocationPlace\": \"Atlantic Ocean\",\n          \"geoLocationPoint\": {\n            \"pointLatitude\": \"31.233\",\n            \"pointLongitude\": \"-67.302\"\n          },\n          \"geoLocationPolygon\": [\n            {\n              \"polygonPoint\": {\n                \"pointLatitude\": \"41.991\",\n                \"pointLongitude\": \"-71.032\"\n              }\n            },\n            {\n              \"polygonPoint\": {\n                \"pointLatitude\": \"42.893\",\n                \"pointLongitude\": \"-69.622\"\n              }\n            },\n            {\n              \"polygonPoint\": {\n                \"pointLatitude\": \"41.991\",\n                \"pointLongitude\": \"-68.211\"\n              }\n            },\n            {\n              \"polygonPoint\": {\n                \"pointLatitude\": \"41.090\",\n                \"pointLongitude\": \"-69.622\"\n              }\n            },\n            {\n              \"polygonPoint\": {\n                \"pointLatitude\": \"41.991\",\n                \"pointLongitude\": \"-71.032\"\n              }\n            }\n          ]\n        }\n      ],\n      \"fundingReferences\": [\n        {\n          \"awardTitle\": \"Full DataCite XML Example\",\n          \"funderName\": \"National Science Foundation\",\n          \"awardNumber\": \"CBET-106\",\n          \"funderIdentifier\": \"https://doi.org/10.13039/100000001\",\n          \"funderIdentifierType\": \"Crossref Funder ID\"\n        }\n      ],\n      \"url\": \"https://example.org\",\n      \"contentUrl\": null,\n      \"metadataVersion\": 0,\n      \"schemaVersion\": \"http://datacite.org/schema/kernel-4\",\n      }\n    }\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Examples"
}
[/block]
###1. Search the for a specific publisher
[block:code]
{
  "codes": [
    {
      "code": "publisher:DataCite",
      "language": "text"
    }
  ]
}
[/block]
Run the [publisher example search in DataCite Commons.](https://commons.datacite.org/doi.org?query=publisher%3ADataCite)

###2. Search for a single DOI

To search for a specific DOI use the DOI field in the metadata. 
[block:code]
{
  "codes": [
    {
      "code": "doi:10.11570/18.0006",
      "language": "text"
    }
  ]
}
[/block]
[Run the example DOI search in DataCite Commons.](https://commons.datacite.org/doi.org?query=doi%3A10.11570%2F18.0006)

###3. Search the affiliation

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
[block:code]
{
  "codes": [
    {
      "code": "creators.affiliation.name:DataCite",
      "language": "text"
    }
  ]
}
[/block]
Run the [example affiliation search in DataCite Commons](https://commons.datacite.org/doi.org?query=creators.affiliation.name%3ADataCite).

###4. Use quotes

To search for an exact string, for example, an author’s name, include the text between quotation marks, the search looks for the the exact string contained within the quotes.
[block:code]
{
  "codes": [
    {
      "code": "titles.title:\"CrowdoMeter Tweets\"",
      "language": "text"
    }
  ]
}
[/block]
Run the [example search using quotation marks in DataCite Commons.](https://commons.datacite.org/doi.org?query=titles.title%3A%22CrowdoMeter+Tweets%22)

###5. Using operators ( e.g AND OR  + -)

Building more complex queries can be done with different syntax including AND OR + - (AND / OR must be capitalised)

Search for all works using the AND operator.
[block:code]
{
  "codes": [
    {
      "code": "types.resourceTypeGeneral:Software AND types.resourceType:XML",
      "language": "text"
    }
  ]
}
[/block]
Run the [example query using the AND boolean in DataCite Commons.](https://commons.datacite.org/doi.org?query=types.resourceTypeGeneral%3ASoftware+AND+types.resourceType%3AXML)

Search for works using the "AND" and "OR" booleans.
[block:code]
{
  "codes": [
    {
      "code": "publisher:DataCite AND types.resourceTypeGeneral:(Text OR Dataset)",
      "language": "text"
    }
  ]
}
[/block]
Run the [example query using the AND / OR booleans in DataCite Commons.](https://commons.datacite.org/doi.org?query=publisher%3ADataCite+AND+types.resourceTypeGeneral%3A%28Text+OR+Dataset%29)

###6. Wildcards

To run a broader search you can include the wildcard (*)

Search for all works with the subject robot*
[block:code]
{
  "codes": [
    {
      "code": "subjects.subject:robot*",
      "language": "text"
    }
  ]
}
[/block]
Run the [example query using the wildcard in DataCite Commons](https://commons.datacite.org/doi.org?query=subjects.subject%3Arobot*) 


### 7. Longer queries 

Combine numerous elements to limit the search results. In this example the creators and the relatedIdentifier properties are used to build the query:

creators:
[block:code]
{
  "codes": [
    {
      "code": "\"creators\": [\n    {\n      \"name\": \"Fenner, Martin\",\n      \"nameType\": \"Personal\",\n      \"givenName\": \"Martin\",\n      \"familyName\": \"Fenner\",\n      \"affiliation\": [],\n      \"nameIdentifiers\": [\n        {\n          \"nameIdentifier\": \"https://orcid.org/0000-0003-1419-2405\",\n          \"nameIdentifierScheme\": \"ORCID\"\n        }\n      ]\n    }\n  ],",
      "language": "json"
    }
  ]
}
[/block]
relatedIdentifiers:
[block:code]
{
  "codes": [
    {
      "code": "\"relatedIdentifiers\": [\n    {\n      \"relationType\": \"HasPart\",\n      \"relatedIdentifier\": \"10.5438/6423\",\n      \"relatedIdentifierType\": \"DOI\"\n    },",
      "language": "json"
    }
  ]
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "creators.name:\"Fenner, Martin\" AND relatedIdentifiers.relationType:hasPart",
      "language": "text"
    }
  ]
}
[/block]
Run this longer query [example combining 2 elements in DataCite Commons.](https://commons.datacite.org/doi.org?query=creators.name%3A%22Fenner%2C+Martin%22+AND+relatedIdentifiers.relationType%3AHasPart)