---
title: DataCite Search
excerpt: User Documentation
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Access the DataCite Search web interface here: [https://search.datacite.org](https://search.datacite.org) 
[block:api-header]
{
  "type": "basic",
  "title": "What is DataCite Search?"
}
[/block]
DataCite search is a web interface where you can explore the complete collection of  publicly available DataCite DOIs. You can search, filter, cite results, push them to your ORCID profile, and more!
[block:api-header]
{
  "type": "basic",
  "title": "Who can use DataCite Search?"
}
[/block]
DataCite Search is open to the whole community. It is particularly designed to showcase the possibilities of the DataCite API and its metadata, while serving the community as a central search platform.
[block:api-header]
{
  "type": "basic",
  "title": "How to search?"
}
[/block]
The DataCite Search and DOI Fabrica user interfaces are now based on Elasticsearch and you can read more about the query string queries [ here.](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html#query-string-syntax)

If you are interested in setting up queries with the REST API check this page: https://support.datacite.org/docs/api-queries 

**Search fields**

It is possible to search in any field from the DOI metadata schema. Use the JSON format as seen below:

https://api.test.datacite.org/dois/10.70048/sc61-b496 

[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
```json

{
  "id": "https://doi.org/10.70048/sc61-b496",
  "doi": "10.70048/SC61-B496",
  "url": "http://example.com",
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
      "name": "Hallett, Richard",
      "nameType": "Personal",
      "givenName": "Richard",
      "familyName": "Hallett",
      "affiliation": "DataCite",
      "nameIdentifiers": [
        {
          "nameIdentifier": "https://orcid.org/0000-0002-7352-517X",
          "nameIdentifierScheme": "ORCID"
        }
      ]
    },
    {
      "name": "Smith, John",
      "nameType": "Personal",
      "givenName": "John",
      "familyName": "Smith",
      "affiliation": "DataCite"
    }
  ],
  "titles": [
    {
      "lang": "en-US",
      "title": "DataCite DOI Test Example"
    },
    {
      "lang": "en-US",
      "title": "Testy Test of DataCite Properties.",
      "titleType": "Subtitle"
    }
  ],
  "publisher": "DataCite",
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
      "nameType": "Personal",
      "givenName": "Joan",
      "familyName": "Starr",
      "affiliation": "California Digital Library",
      "contributorType": "ProjectLeader",
      "nameIdentifiers": [
        {
          "nameIdentifier": "https://orcid.org/0000-0002-7285-027X",
          "nameIdentifierScheme": "ORCID"
        }
      ]
    }
  ],
  "dates": [
    {
      "date": "2017-09-13",
      "dateType": "Updated",
      "dateInformation": "Updated with 4.1 properties"
    },
    {
      "date": "2017",
      "dateType": "Issued"
    }
  ],
  "publicationYear": 2017,
  "language": "en-US",
  "identifiers": [
    {
      "identifier": "https://handle.test.datacite.org/10.70048/sc61-b496",
      "identifierType": "DOI"
    }
  ],
  "sizes": [
    "4 kB"
  ],
  "formats": [
    "application/xml"
  ],
  "rightsList": [
    {
      "lang": "en-US",
      "rights": "CC0 1.0 Universal",
      "rightsUri": "http://creativecommons.org/publicdomain/zero/1.0"
    }
  ],
  "descriptions": [
    {
      "lang": "en-US",
      "description": "3 Test of DOI registrationenv",
      "descriptionType": "Abstract"
    }
  ],
  "geoLocations": [],
  "fundingReferences": [
    {
      "awardTitle": "Full DataCite XML Example",
      "funderName": "National Science Foundation",
      "awardNumber": "CBET-106",
      "funderIdentifier": "https://doi.org/10.13039/100000001",
      "funderIdentifierType": "Crossref Funder ID"
    }
  ],
  "relatedIdentifiers": [],
  "schemaVersion": "http://datacite.org/schema/kernel-4",
  "providerId": "datacite",
  "clientId": "datacite.rph",
  "agency": "DataCite",
  "state": "findable"
}


```






To look for information in a specific field of the the metadata select the name of the field exactly as it appears in the JSON format. Use a colon (:) between the field and the search terms.

Examples:

##1. Search the for a specific publisher

publisher:datacite
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/09e1fd4-Screen_Shot_2019-02-26_at_14.51.49.png",
        "Screen Shot 2019-02-26 at 14.51.49.png",
        1348,
        653,
        "#f3f4f4"
      ]
    }
  ]
}
[/block]
The results list includes all works where DataCite is the publisher.

##2. Search for a single DOI

To search for a specific DOI use the DOI field in the metadata. 

doi:10.11570/18.0006

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d7da6a7-Screen_Shot_2019-02-26_at_14.33.05.png",
        "Screen Shot 2019-02-26 at 14.33.05.png",
        1451,
        521,
        "#f1f2f2"
      ]
    }
  ]
}
[/block]
The results show one record https://search.datacite.org/works/10.11570/18.0006 
[block:callout]
{
  "type": "info",
  "body": "DOIs containing alphabetic characters in the suffix should be capitalized e.g doi:10.5281/ZENODO.2577807"
}
[/block]
##3. Search the affiliation

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

creators.affiliation:Leeds
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/efeb505-Screen_Shot_2019-02-25_at_17.21.47.png",
        "Screen Shot 2019-02-25 at 17.21.47.png",
        1434,
        570,
        "#f2f3f3"
      ]
    }
  ]
}
[/block]
The results include works where the affiliation field contains the word Leeds.

##4. Use quotes

To search for an exact string, for example, an author’s name, include the text between quotation marks, the search looks for the the exact string contained within the quotes.

creators.name:"Fenner, Martin"

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/969e5d5-Screen_Shot_2019-02-25_at_15.36.47.png",
        "Screen Shot 2019-02-25 at 15.36.47.png",
        1478,
        648,
        "#f4f5f5"
      ]
    }
  ]
}
[/block]
The results contain only works where one of the authors is Martin Fenner.

##5. Using operators ( e.g AND OR  + -)

Building more complex queries can be done with different syntax including AND OR + -

Search for all works that have a resourceType of software and XML.

types.resourceTypeGeneral:Software AND types.resourceType:XML
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/773a28f-Screen_Shot_2019-02-25_at_17.45.50.png",
        "Screen Shot 2019-02-25 at 17.45.50.png",
        1528,
        681,
        "#f3f4f4"
      ]
    }
  ]
}
[/block]

The results are works where the resouceTypeGeneral field contains Software and the resourceType field contains XML.

Search for all records published by DataCIte that are text objects:

publisher:datacite AND +text (in this case the + means that “text” must be present)
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6f3bab6-Screen_Shot_2019-02-25_at_17.30.02.png",
        "Screen Shot 2019-02-25 at 17.30.02.png",
        1433,
        606,
        "#f2f4f4"
      ]
    }
  ]
}
[/block]
The results include a list of works where DataCite appears in the publisher field, they are also text works.

**6. Wildcards**

To run a broader search you can include the wildcard (*)

Search for all works with the subject robot*

subjects.subject:robot*
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/92ce998-Screen_Shot_2019-02-26_at_13.09.34.png",
        "Screen Shot 2019-02-26 at 13.09.34.png",
        1346,
        610,
        "#f2f4f4"
      ]
    }
  ]
}
[/block]
The results include all works where the word "robot" appears, plus extensions, in the subject field e.g robotic, robotic surgery

[block:api-header]
{
  "title": "Facets"
}
[/block]
You can filter your results using the column on the right. These boxes are called facets, and will help you find the results you are looking for in an easier way.

Imagine you want to know more about the Standard Model. If you search for `"standard model" physics` you will find almost two thousand results:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/af27b9c-Screen_Shot_2017-05-09_at_15.25.16.png",
        "Screen Shot 2017-05-09 at 15.25.16.png",
        1926,
        1366,
        "#f3f3f3"
      ]
    }
  ]
}
[/block]
If you use the facets on the right and choose Audiovisual content (under the Resource Types category) you will only see videos related to your query:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c8db574-Screen_Shot_2017-05-09_at_15.29.28.png",
        "Screen Shot 2017-05-09 at 15.29.28.png",
        1910,
        1228,
        "#f3f3f3"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Cite results"
}
[/block]
DataCite search can export the results of your queries to different formats. Just click on the "Cite" button on the bottom bar of each search result and a pop-up window will show you all the available citation formats.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4dc3682-Screen_Shot_2017-05-09_at_15.31.30.png",
        "Screen Shot 2017-05-09 at 15.31.30.png",
        1806,
        464,
        "#775454"
      ]
    }
  ]
}
[/block]
These are the most common ones but, of course, you can always our [DataCite Citation Formatter](doc:datacite-citation-formatter) to produce more!
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8961d54-Screen_Shot_2017-05-09_at_15.33.22.png",
        "Screen Shot 2017-05-09 at 15.33.22.png",
        1834,
        648,
        "#e7e7e6"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Add to ORCID record"
}
[/block]
You can also use DataCite Search you update your ORCID record. Login using [DataCite Profiles](doc:datacite-profiles-user-documentation) and each one of the boxes will show you an "Add to ORCID record" button. Hit "OK" if you are sure it is your work, and we will take care of the rest! Your ORCID record will soon include your new information.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eec3966-Screen_Shot_2017-05-09_at_15.36.28.png",
        "Screen Shot 2017-05-09 at 15.36.28.png",
        1802,
        968,
        "#ebeded"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Remove from ORCID Record"
}
[/block]
Works that have been added to your ORCID record show the label "In your ORCID record", and you can remove them from your ORCID record by clicking on that label, and then "OK".
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/70b265f-Bildschirmfoto_2017-07-03_um_16.21.46.png",
        "Bildschirmfoto 2017-07-03 um 16.21.46.png",
        1816,
        992,
        "#606f75"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]