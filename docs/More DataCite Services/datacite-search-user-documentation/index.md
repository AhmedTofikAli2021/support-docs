---
title: DataCite Search
excerpt: User Documentation
deprecated: false
hidden: true
link:
  new_tab: false
  url: https://support.datacite.org/docs/datacite-commons
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> ❗️ DataCite Search has been discontinued!
> 
> As of 1 June 2023 DataCite Search has been discontinued and superseded by [DataCite Commons](https://commons.datacite.org/).

## What is DataCite Search?

DataCite search is a web interface where you can explore the complete collection of  publicly available DataCite DOIs. You can search, filter, cite results, push them to your ORCID profile, and more! 

## Who can use DataCite Search?

DataCite Search is open to the whole community. It is particularly designed to showcase the possibilities of the DataCite API and its metadata, while serving the community as a central search platform.

## How to search?

The DataCite Search and DOI Fabrica user interfaces are now based on Elasticsearch and you can read more about the query string queries [ here.](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html#query-string-syntax)

If you are interested in setting up queries with the REST API check this page: <https://support.datacite.org/docs/api-queries> 

**Search fields**

It is possible to search in any field from the DOI metadata schema. Use the JSON format as seen below:

<https://api.test.datacite.org/dois/10.70126/t70h-qt35?affiliation=true>

```json

{
  "id": "https://doi.org/10.70126/t70h-qt35",
  "doi": "10.70126/T70H-QT35",
  "url": "https://dataverse.scholarsportal.info/dataverse.xhtml",
  "types": {
    "ris": "COMP",
    "bibtex": "misc",
    "citeproc": "article",
    "schemaOrg": "SoftwareSourceCode",
    "resourceType": "XML",
    "resourceTypeGeneral": "Software"
  },
  "creators": [
    {
      "name": "Miller, Elizabeth",
      "nameType": "Personal",
      "givenName": "Elizabeth",
      "familyName": "Miller",
      "affiliation": [
        {
          "name": "DataCite",
          "affiliationIdentifier": "https://ror.org/04wxnsj81",
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
    },
    {
      "name": "Ontario Ministry Of Natural Resources And Forestry",
      "nameType": "Organizational",
      "affiliation": [],
      "nameIdentifiers": []
    },
    {
      "name": "Université Du Québec à Montréal",
      "nameType": "Organizational",
      "affiliation": [],
      "nameIdentifiers": []
    }
  ],
  "titles": [
    {
      "lang": "en-US",
      "title": "Full DataCite XML Example"
    },
    {
      "lang": "en-US",
      "title": "Demonstration of DataCite Properties.",
      "titleType": "Subtitle"
    }
  ],
  "publisher": "National Research Council of Canada",
  "container": {},
  "subjects": [
    {
      "lang": "en-US",
      "subject": "000 computer science",
      "schemeUri": "http://dewey.info/",
      "subjectScheme": "dewey"
    }
  ],
  "contributors": [
    {
      "name": "Starr, Joan",
      "givenName": "Joan",
      "familyName": "Starr",
      "affiliation": [
        {
          "name": "California Digital Library",
          "affiliationIdentifier": "https://ror.org/03yrm5c26",
          "affiliationIdentifierScheme": "ROR"
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
    },
    {
      "name": "International Joint Commission",
      "affiliation": [],
      "contributorType": "Sponsor",
      "nameIdentifiers": []
    },
    {
      "name": "United States Geological Survey",
      "affiliation": [],
      "contributorType": "Producer",
      "nameIdentifiers": []
    }
  ],
  "dates": [
    {
      "date": "2017-09-13",
      "dateType": "Updated",
      "dateInformation": "Updated with 4.3 properties"
    },
    {
      "date": "2014",
      "dateType": "Issued"
    }
  ],
  "publicationYear": 2014,
  "language": "en-US",
  "identifiers": [],
  "sizes": [
    "4 kB"
  ],
  "formats": [
    "application/xml"
  ],
  "version": "4.3",
  "rightsList": [
    {
      "lang": "en-US",
      "rightsUri": "http://creativecommons.org/publicdomain/zero/1.0"
    }
  ],
  "descriptions": [
    {
      "lang": "en-US",
      "description": "XML example of all DataCite Metadata Schema v4.3 properties.",
      "descriptionType": "Abstract"
    }
  ],
  "geoLocations": [
    {
      "geoLocationBox": {
        "eastBoundLongitude": "-68.211",
        "northBoundLatitude": "42.893",
        "southBoundLatitude": "41.090",
        "westBoundLongitude": "-71.032"
      },
      "geoLocationPlace": "Atlantic Ocean",
      "geoLocationPoint": {
        "pointLatitude": "31.233",
        "pointLongitude": "-67.302"
      },
      "geoLocationPolygon": [
        {
          "polygonPoint": {
            "pointLatitude": "41.991",
            "pointLongitude": "-71.032"
          }
        },
        {
          "polygonPoint": {
            "pointLatitude": "42.893",
            "pointLongitude": "-69.622"
          }
        },
        {
          "polygonPoint": {
            "pointLatitude": "41.991",
            "pointLongitude": "-68.211"
          }
        },
        {
          "polygonPoint": {
            "pointLatitude": "41.090",
            "pointLongitude": "-69.622"
          }
        },
        {
          "polygonPoint": {
            "pointLatitude": "41.991",
            "pointLongitude": "-71.032"
          }
        }
      ]
    }
  ],
  "fundingReferences": [
    {
      "awardTitle": "Full DataCite XML Example",
      "funderName": "National Science Foundation",
      "awardNumber": "CBET-106",
      "funderIdentifier": "https://doi.org/10.13039/100000001",
      "funderIdentifierType": "Crossref Funder ID"
    }
  ],
  "relatedIdentifiers": [
    {
      "schemeUri": "https://github.com/citation-style-language/schema/raw/master/csl-data.json",
      "relationType": "HasMetadata",
      "relatedIdentifier": "https://data.datacite.org/application/citeproc+json/10.5072/example-full",
      "relatedIdentifierType": "URL",
      "relatedMetadataScheme": "citeproc+json"
    },
    {
      "relationType": "IsReviewedBy",
      "relatedIdentifier": "arXiv:0706.0001",
      "resourceTypeGeneral": "Text",
      "relatedIdentifierType": "arXiv"
    }
  ],
  "schemaVersion": "http://datacite.org/schema/kernel-4",
  "providerId": "datacite",
  "clientId": "datacite.mary",
  "agency": "DataCite",
  "state": "findable"
}
```

To look for information in a specific field of the the metadata select the name of the field exactly as it appears in the JSON format. Use a colon (:) between the field and the search terms.

Examples:

## 1. Search the for a specific publisher

publisher:datacite

![](https://files.readme.io/09e1fd4-Screen_Shot_2019-02-26_at_14.51.49.png "Screen Shot 2019-02-26 at 14.51.49.png")

The results list includes all works where DataCite is the publisher.

## 2. Search for a single DOI

To search for a specific DOI use the DOI field in the metadata. 

doi:10.11570/18.0006

![](https://files.readme.io/d7da6a7-Screen_Shot_2019-02-26_at_14.33.05.png "Screen Shot 2019-02-26 at 14.33.05.png")

The results show one record <https://search.datacite.org/works/10.11570/18.0006> 

> 📘 
> 
> DOIs containing alphabetic characters in the suffix should be capitalized e.g doi:10.5281/ZENODO.2577807

## 3. Search the affiliation

In this case include both the parent and child elements from the schema and use a period (.) to separate the different levels in your search query.

```json

 },
  "creators": [
    {
      "name": "Hallett, Richard",
      "nameType": "Personal",
      "givenName": "Richard",
      "familyName": "Hallett",
      "affiliation": "DataCite",
      "nameIdentifiers": [
        {

```

creators.affiliation.name:Leeds\*

![](https://files.readme.io/7782ce6-Screen_Shot_2020-06-08_at_11.37.48.png "Screen Shot 2020-06-08 at 11.37.48.png")

The results include works where the affiliation field contains the word Leeds.

## 4. Use quotes

To search for an exact string, for example, an author’s name, include the text between quotation marks, the search looks for the the exact string contained within the quotes.

creators.name:"Fenner, Martin"

![](https://files.readme.io/969e5d5-Screen_Shot_2019-02-25_at_15.36.47.png "Screen Shot 2019-02-25 at 15.36.47.png")

The results contain only works where one of the authors is Martin Fenner.

## 5. Using operators ( e.g AND OR  + -)

Building more complex queries can be done with different syntax including AND OR + -

Search for all works that have a resourceType of software and XML.

types.resourceTypeGeneral:Software AND types.resourceType:XML

![](https://files.readme.io/773a28f-Screen_Shot_2019-02-25_at_17.45.50.png "Screen Shot 2019-02-25 at 17.45.50.png")

The results are works where the resouceTypeGeneral field contains Software and the resourceType field contains XML.

Search for all records published by DataCIte that are text objects:

publisher:datacite AND +text (in this case the + means that “text” must be present)

![](https://files.readme.io/6f3bab6-Screen_Shot_2019-02-25_at_17.30.02.png "Screen Shot 2019-02-25 at 17.30.02.png")

The results include a list of works where DataCite appears in the publisher field, they are also text works.

**6. Wildcards**

To run a broader search you can include the wildcard (\*)

Search for all works with the subject robot\*

subjects.subject:robot\*

![](https://files.readme.io/92ce998-Screen_Shot_2019-02-26_at_13.09.34.png "Screen Shot 2019-02-26 at 13.09.34.png")

The results include all works where the word "robot" appears, plus extensions, in the subject field e.g robotic, robotic surgery

## Facets

You can filter your results using the column on the right. These boxes are called facets, and will help you find the results you are looking for in an easier way.

Imagine you want to know more about the Standard Model. If you search for `"standard model" physics` you will find almost two thousand results:

![](https://files.readme.io/af27b9c-Screen_Shot_2017-05-09_at_15.25.16.png "Screen Shot 2017-05-09 at 15.25.16.png")

If you use the facets on the right and choose Audiovisual content (under the Resource Types category) you will only see videos related to your query:

![](https://files.readme.io/c8db574-Screen_Shot_2017-05-09_at_15.29.28.png "Screen Shot 2017-05-09 at 15.29.28.png")

## Cite results

DataCite search can export the results of your queries to different formats. Just click on the "Cite" button on the bottom bar of each search result and a pop-up window will show you all the available citation formats.

![](https://files.readme.io/4dc3682-Screen_Shot_2017-05-09_at_15.31.30.png "Screen Shot 2017-05-09 at 15.31.30.png")

These are the most common ones but, of course, you can always our [DataCite Citation Formatter](doc:datacite-citation-formatter) to produce more!

![](https://files.readme.io/8961d54-Screen_Shot_2017-05-09_at_15.33.22.png "Screen Shot 2017-05-09 at 15.33.22.png")

## Add to ORCID record

- You can also use DataCite Search to update your ORCID record. Login using [DataCite Profiles](doc:datacite-profiles-user-documentation) and each one of the boxes will show you an "Add to ORCID record" button. Hit "OK" if you are sure it is your work, and we will take care of the rest! Your ORCID record will soon include your new information. 

![](https://files.readme.io/eec3966-Screen_Shot_2017-05-09_at_15.36.28.png "Screen Shot 2017-05-09 at 15.36.28.png")

## Remove from ORCID Record

Works that have been added to your ORCID record show the label "In your ORCID record", and you can remove them from your ORCID record by clicking on that label, and then "OK".

![](https://files.readme.io/70b265f-Bildschirmfoto_2017-07-03_um_16.21.46.png "Bildschirmfoto 2017-07-03 um 16.21.46.png")

> 📘 Would you like to know more?
> 
> If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)