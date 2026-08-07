---
title: Search fields in DataCite Commons
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

## Search fields

It is possible to search in any field from the DOI metadata schema. It is important to use the JSON API response format for the query fields for example to search the title field use

**titles.title:Mars**

Run this [search in DataCite Commons](https://commons.datacite.org/doi.org?query=titles.title%3Amars).

All the fields are listed in API the response below:

https://api.test.datacite.org/dois/10.70126/t70h-qt35?affiliation=true

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