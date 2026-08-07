---
title: Retrieving a list of DOIs
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
The DataCite REST API can be used to retrieve lists of DOIs. **List** results can contain multiple entries and can be filtered by various parameters.

A list response has four parts:

- **data**, which will contain the items matching the request.
- **included**, which will contain side-loaded associations, via the `?include=x` parameter.
- **meta**, which includes information about the results, e.g. number of items returned.
- **links**, which includes links to the current and next page.

> 📘 Working with lists
> 
> The next few guides will help you navigate list results:
> 
> - [Pagination](doc:pagination): Retrieve more than 25 records (the default page size).
> - [Queries and filtering](doc:api-queries): Add a "query" parameter to filter by DOI metadata properties.
> - [Retrieving a random sample of DOIs](doc:api-sampling): Get a random sample of DOIs for analysis.

## Request

Retrieve a list of DOIs via a GET request to `https://api.datacite.org/dois` with optional parameters.

### Parameters

The [API Reference](ref:get_dois) contains a complete list of URL parameters that can be used to filter lists. Here are some of the most commonly used parameters:

#### Repository

This request retrieves all DOIs registered by a specific Repository account (only Findable DOIs are listed unless authentication is included).

```shell
# GET /dois
$ curl https://api.datacite.org/dois?client_id=datacite.datacite
```

#### Prefix

This request retrieves all DOIs registered with a specific prefix (only Findable DOIs are listed unless authentication is included).

```shell
# GET /dois
$ curl https://api.datacite.org/dois?prefix=10.5438
```

#### Member/Consortium Organization ID

This request retrieves all DOIs registered by a specific Member/Consortium Organization account (only Findable DOIs are listed unless authentication is included).

```shell
# GET /dois
$ curl https://api.datacite.org/dois?provider-id=datacite
```

#### Consortium Lead

This request retrieves all DOIs registered with by a specific Consortium account (only Findable DOIs are listed unless authentication is included).

```shell
# GET /dois
$ curl https://api.datacite.org/dois?consortium-id=tibco
```

For more information on how to refine a list of DOIs, see [Queries and filtering](doc:api-queries).

## Response

Findable DOIs will always be included. Draft records and Registered state DOIs can also be retrieved by authenticating to use the Member API.

The response would look like this:

```json
{
  "data": [
    {
      "id": "10.14454/qn00-qx85",
      "type": "dois",
      "attributes": {
        "doi": "10.14454/qn00-qx85",
        "identifiers": [],
        "creators": [
          {
            "name": "DataCite Metadata Working Group",
            "nameType": "Organizational",
            "affiliation": [],
            "nameIdentifiers": []
          }
        ],
        "titles": [
          {
            "title": "DataCite to Dublin Core Mapping v4.4."
          }
        ],
        "publisher": "DataCite",
        "container": {},
        "publicationYear": 2021,
        "subjects": [],
        "contributors": [
          {
            "name": "de Smaele, Madeleine",
            "givenName": "Madeleine",
            "familyName": "de Smaele",
            "affiliation": [
              "Delft University of Technology"
            ],
            "contributorType": "ProjectLeader",
            "nameIdentifiers": [
              {
                "schemeUri": "https://orcid.org",
                "nameIdentifier": "https://orcid.org/0000-0003-4149-8311",
                "nameIdentifierScheme": "ORCID"
              }
            ]
          },
          {
            "name": "Bernal Martínez, Isabel",
            "givenName": "Isabel",
            "familyName": "Bernal Martínez",
            "affiliation": [
              "Spanish National Research Council"
            ],
            "contributorType": "ProjectLeader",
            "nameIdentifiers": []
          },
          {
            "name": "Dasler, Robin",
            "givenName": "Robin",
            "familyName": "Dasler",
            "affiliation": [
              "DataCite"
            ],
            "contributorType": "Editor",
            "nameIdentifiers": [
              {
                "schemeUri": "https://orcid.org",
                "nameIdentifier": "https://orcid.org/0000-0002-4695-7874",
                "nameIdentifierScheme": "ORCID"
              }
            ]
          },
          {
            "name": "Ashton, Jan",
            "givenName": "Jan",
            "familyName": "Ashton",
            "affiliation": [
              "British Library"
            ],
            "contributorType": "Editor",
            "nameIdentifiers": []
          },
          {
            "name": "Roy, Sophie",
            "givenName": "Sophie",
            "familyName": "Roy",
            "affiliation": [
              "National Research Council Canada"
            ],
            "contributorType": "Editor",
            "nameIdentifiers": []
          },
          {
            "name": "Fenner, Martin",
            "givenName": "Martin",
            "familyName": "Fenner",
            "affiliation": [
              "DataCite"
            ],
            "contributorType": "Editor",
            "nameIdentifiers": [
              {
                "schemeUri": "https://orcid.org",
                "nameIdentifier": "https://orcid.org/0000-0001-6528-2027",
                "nameIdentifierScheme": "ORCID"
              }
            ]
          },
          {
            "name": "Chiloane, Leo",
            "givenName": "Leo",
            "familyName": "Chiloane",
            "affiliation": [
              "South African Environmental Observation Network"
            ],
            "contributorType": "Editor",
            "nameIdentifiers": []
          },
          {
            "name": "Burger, Marleen",
            "givenName": "Marleen",
            "familyName": "Burger",
            "affiliation": [
              "German National Library of Science and Technology"
            ],
            "contributorType": "Editor",
            "nameIdentifiers": []
          },
          {
            "name": "Yahia, Mohamed",
            "givenName": "Mohamed",
            "familyName": "Yahia",
            "affiliation": [
              "Institut de l'Information Scientifique et Technique"
            ],
            "contributorType": "Editor",
            "nameIdentifiers": []
          },
          {
            "name": "Zolly, Lisa",
            "givenName": "Lisa",
            "familyName": "Zolly",
            "affiliation": [
              "United States Geological Survey"
            ],
            "contributorType": "Editor",
            "nameIdentifiers": []
          },
          {
            "name": "Habermann, Ted",
            "givenName": "Ted",
            "familyName": "Habermann",
            "affiliation": [
              "Metadata Game Changers"
            ],
            "contributorType": "Editor",
            "nameIdentifiers": []
          },
          {
            "name": "Raugh, Anne",
            "givenName": "Anne",
            "familyName": "Raugh",
            "affiliation": [
              "University of Maryland, College Park"
            ],
            "contributorType": "Editor",
            "nameIdentifiers": []
          },
          {
            "name": "Ilik, Violeta",
            "givenName": "Violeta",
            "familyName": "Ilik",
            "affiliation": [
              "Columbia University"
            ],
            "contributorType": "Editor",
            "nameIdentifiers": []
          },
          {
            "name": "Foulger, Samantha",
            "givenName": "Samantha",
            "familyName": "Foulger",
            "affiliation": [
              "Swiss Federal Institute of Technology in Zurich"
            ],
            "contributorType": "Editor",
            "nameIdentifiers": []
          }
        ],
        "dates": [
          {
            "date": "2021",
            "dateType": "Issued"
          }
        ],
        "language": "en",
        "types": {
          "ris": "RPRT",
          "bibtex": "article",
          "citeproc": "article-journal",
          "schemaOrg": "ScholarlyArticle",
          "resourceType": "Documentation",
          "resourceTypeGeneral": "Text"
        },
        "relatedIdentifiers": [
          {
            "relationType": "References",
            "relatedIdentifier": "10.14454/3w3z-sa82",
            "relatedIdentifierType": "DOI"
          }
        ],
        "relatedItems": [],
        "sizes": [
          "7 pages"
        ],
        "formats": [
          "application/pdf"
        ],
        "version": "4.4",
        "rightsList": [],
        "descriptions": [
          {
            "description": "On the occasion of the release of v4.4 of the DataCite Metadata Schema its Metadata Working Group has updated the mapping to Dublin Core. This replaces the mapping in the Appendix of the DataCite-MetadataKernel v2.1. The mapping can be used to convert records described following version 4.4 of the DataCite Metadata Schema into records that comply with the Dublin Core Metadata Initiative Schema.",
            "descriptionType": "Abstract"
          }
        ],
        "geoLocations": [],
        "fundingReferences": [],
        "url": "https://schema.datacite.org/dc/",
        "contentUrl": null,
        "metadataVersion": 0,
        "schemaVersion": "http://datacite.org/schema/kernel-4",
        "source": "fabrica",
        "isActive": true,
        "state": "findable",
        "reason": null,
        "viewCount": 0,
        "downloadCount": 0,
        "referenceCount": 0,
        "citationCount": 0,
        "partCount": 0,
        "partOfCount": 0,
        "versionCount": 0,
        "versionOfCount": 0,
        "created": "2021-07-08T09:53:54Z",
        "registered": "2021-07-08T10:02:59Z",
        "published": null,
        "updated": "2021-07-08T10:02:59Z"
      },
      "relationships": {
        "client": {
          "data": {
            "id": "datacite.datacite",
            "type": "clients"
          }
        }
      }
    },
    {
      "id": "10.14454/3bpw-w381",
      "type": "dois",
      "attributes": {
        "doi": "10.14454/3bpw-w381",
        "identifiers": [],
        "creators": [
          {
            "name": "Fenner, Martin",
            "nameType": "Personal",
            "givenName": "Martin",
            "familyName": "Fenner",
            "affiliation": [],
            "nameIdentifiers": [
              {
                "schemeUri": "https://orcid.org",
                "nameIdentifier": "https://orcid.org/0000-0003-1419-2405",
                "nameIdentifierScheme": "ORCID"
              }
            ]
          }
        ],
        "titles": [
          {
            "lang": null,
            "title": "Jupyter Notebook FREYA PID Graph Key Performance Indicators (KPIs)",
            "titleType": null
          }
        ],
        "publisher": "DataCite",
        "container": {},
        "publicationYear": 2019,
        "subjects": [
          {
            "subject": "pid graph"
          },
          {
            "subject": "graphql"
          },
          {
            "subject": "kpi"
          },
          {
            "subject": "freya"
          },
          {
            "subject": "eosc"
          },
          {
            "subject": "FOS: Computer and information sciences",
            "subjectScheme": "Fields of Science and Technology (FOS)"
          }
        ],
        "contributors": [],
        "dates": [
          {
            "date": "2019-06-30",
            "dateType": "Issued",
            "dateInformation": null
          },
          {
            "date": "2019-06-30",
            "dateType": "Created",
            "dateInformation": null
          },
          {
            "date": "2019-06-30",
            "dateType": "Updated",
            "dateInformation": null
          }
        ],
        "language": null,
        "types": {
          "ris": "COMP",
          "bibtex": "misc",
          "citeproc": "article",
          "schemaOrg": "SoftwareSourceCode",
          "resourceType": "Jupyter notebook",
          "resourceTypeGeneral": "ComputationalNotebook"
        },
        "relatedIdentifiers": [],
        "relatedItems": [],
        "sizes": [],
        "formats": [],
        "version": "1.1.0",
        "rightsList": [
          {
            "rights": "MIT License",
            "rightsUri": "https://opensource.org/licenses/MIT",
            "schemeUri": "https://spdx.org/licenses/",
            "rightsIdentifier": "mit",
            "rightsIdentifierScheme": "SPDX"
          }
        ],
        "descriptions": [],
        "geoLocations": [],
        "fundingReferences": [
          {
            "awardUri": "info:eu-repo/grantAgreement/EC/H2020/777523/",
            "awardTitle": "Connected Open Identifiers for Discovery, Access and Use of Research Resources",
            "funderName": "European Commission",
            "awardNumber": "777523",
            "funderIdentifier": "https://doi.org/10.13039/501100000780",
            "funderIdentifierType": "Crossref Funder ID"
          }
        ],
        "url": "https://github.com/datacite/pidgraph-notebooks-r/tree/master/kpi",
        "contentUrl": null,
        "metadataVersion": 6,
        "schemaVersion": "http://datacite.org/schema/kernel-4",
        "source": "fabricaForm",
        "isActive": true,
        "state": "findable",
        "reason": null,
        "viewCount": 0,
        "downloadCount": 0,
        "referenceCount": 0,
        "citationCount": 2,
        "partCount": 0,
        "partOfCount": 0,
        "versionCount": 0,
        "versionOfCount": 0,
        "created": "2019-06-30T14:37:10Z",
        "registered": "2019-06-30T16:09:18Z",
        "published": null,
        "updated": "2021-04-23T14:36:16Z"
      },
      "relationships": {
        "client": {
          "data": {
            "id": "datacite.datacite",
            "type": "clients"
          }
        }
      }
    }
  ],
  "meta": {
    "total": 60,
    "totalPages": 30,
    "page": 1,
    "states": [
      {
        "id": "findable",
        "title": "Findable",
        "count": 60
      }
    ],
    "resourceTypes": [
      {
        "id": "text",
        "title": "Text",
        "count": 24
      },
      {
        "id": "software",
        "title": "Software",
        "count": 21
      },
      {
        "id": "collection",
        "title": "Collection",
        "count": 4
      },
      {
        "id": "dataset",
        "title": "Dataset",
        "count": 3
      },
      {
        "id": "report",
        "title": "Report",
        "count": 3
      },
      {
        "id": "event",
        "title": "Event",
        "count": 2
      },
      {
        "id": "computational-notebook",
        "title": "Computational Notebook",
        "count": 1
      },
      {
        "id": "model",
        "title": "Model",
        "count": 1
      },
      {
        "id": "other",
        "title": "Other",
        "count": 1
      }
    ],
    "created": [
      {
        "id": "2021",
        "title": "2021",
        "count": 3
      },
      {
        "id": "2020",
        "title": "2020",
        "count": 15
      },
      {
        "id": "2019",
        "title": "2019",
        "count": 6
      },
      {
        "id": "2018",
        "title": "2018",
        "count": 5
      },
      {
        "id": "2017",
        "title": "2017",
        "count": 9
      },
      {
        "id": "2016",
        "title": "2016",
        "count": 9
      },
      {
        "id": "2014",
        "title": "2014",
        "count": 3
      },
      {
        "id": "2013",
        "title": "2013",
        "count": 3
      },
      {
        "id": "2012",
        "title": "2012",
        "count": 1
      },
      {
        "id": "2011",
        "title": "2011",
        "count": 6
      }
    ],
    "published": [
      {
        "id": "2021",
        "title": "2021",
        "count": 3
      },
      {
        "id": "2020",
        "title": "2020",
        "count": 15
      },
      {
        "id": "2019",
        "title": "2019",
        "count": 7
      },
      {
        "id": "2018",
        "title": "2018",
        "count": 4
      },
      {
        "id": "2017",
        "title": "2017",
        "count": 6
      },
      {
        "id": "2016",
        "title": "2016",
        "count": 7
      },
      {
        "id": "2015",
        "title": "2015",
        "count": 4
      },
      {
        "id": "2014",
        "title": "2014",
        "count": 3
      },
      {
        "id": "2013",
        "title": "2013",
        "count": 3
      },
      {
        "id": "2012",
        "title": "2012",
        "count": 2
      },
      {
        "id": "2011",
        "title": "2011",
        "count": 6
      }
    ],
    "registered": [
      {
        "id": "2021",
        "title": "2021",
        "count": 3
      },
      {
        "id": "2020",
        "title": "2020",
        "count": 15
      },
      {
        "id": "2019",
        "title": "2019",
        "count": 7
      },
      {
        "id": "2018",
        "title": "2018",
        "count": 4
      },
      {
        "id": "2017",
        "title": "2017",
        "count": 9
      },
      {
        "id": "2016",
        "title": "2016",
        "count": 9
      },
      {
        "id": "2014",
        "title": "2014",
        "count": 3
      },
      {
        "id": "2013",
        "title": "2013",
        "count": 3
      },
      {
        "id": "2012",
        "title": "2012",
        "count": 1
      },
      {
        "id": "2011",
        "title": "2011",
        "count": 6
      }
    ],
    "providers": [
      {
        "id": "datacite",
        "title": "DataCite",
        "count": 60
      }
    ],
    "clients": [
      {
        "id": "datacite.datacite",
        "title": "DataCite",
        "count": 60
      }
    ],
    "affiliations": [
      {
        "id": "ror.org/04wxnsj81",
        "title": "DataCite",
        "count": 13
      },
      {
        "id": "ror.org/05dhe8b71",
        "title": "British Library",
        "count": 12
      },
      {
        "id": "ror.org/02catss52",
        "title": "European Bioinformatics Institute",
        "count": 7
      },
      {
        "id": "ror.org/057g20z61",
        "title": "Science and Technology Facilities Council",
        "count": 7
      },
      {
        "id": "ror.org/00hj8s172",
        "title": "Columbia University",
        "count": 5
      },
      {
        "id": "ror.org/02e2c7k09",
        "title": "Delft University of Technology",
        "count": 5
      },
      {
        "id": "ror.org/02gfc7t72",
        "title": "Spanish National Research Council",
        "count": 5
      },
      {
        "id": "ror.org/02mn0vt57",
        "title": "Institut de l'Information Scientifique et Technique",
        "count": 5
      },
      {
        "id": "ror.org/035a68863",
        "title": "United States Geological Survey",
        "count": 5
      },
      {
        "id": "ror.org/047s2c258",
        "title": "University of Maryland, College Park",
        "count": 5
      }
    ],
    "prefixes": [
      {
        "id": "10.5438",
        "title": "10.5438",
        "count": 34
      },
      {
        "id": "10.14454",
        "title": "10.14454",
        "count": 26
      }
    ],
    "certificates": [],
    "licenses": [
      {
        "id": "mit",
        "title": "MIT",
        "count": 17
      },
      {
        "id": "cc-by-4.0",
        "title": "CC-BY-4.0",
        "count": 1
      }
    ],
    "schemaVersions": [
      {
        "id": "4",
        "title": "Schema 4",
        "count": 27
      }
    ],
    "linkChecksStatus": [
      {
        "id": "200",
        "title": "200",
        "count": 31
      },
      {
        "id": "404",
        "title": "404",
        "count": 3
      }
    ],
    "subjects": [
      {
        "id": "freya",
        "title": "Freya",
        "count": 14
      },
      {
        "id": "graphql",
        "title": "Graphql",
        "count": 14
      },
      {
        "id": "pid graph",
        "title": "Pid Graph",
        "count": 14
      },
      {
        "id": "pid",
        "title": "Pid",
        "count": 13
      },
      {
        "id": "jupyter",
        "title": "Jupyter",
        "count": 12
      },
      {
        "id": "FOS: Computer and information sciences",
        "title": "Fos: Computer And Information Sciences",
        "count": 10
      },
      {
        "id": "ORCID",
        "title": "Orcid",
        "count": 3
      },
      {
        "id": "doi",
        "title": "Doi",
        "count": 3
      },
      {
        "id": "metadata",
        "title": "Metadata",
        "count": 3
      },
      {
        "id": "Assessment",
        "title": "Assessment",
        "count": 2
      }
    ],
    "fieldsOfScience": [
      {
        "id": "computer_and_information_sciences",
        "title": "Computer and information sciences",
        "count": 10
      }
    ],
    "citations": [
      {
        "id": "2021",
        "title": "2021",
        "count": 7
      },
      {
        "id": "2019",
        "title": "2019",
        "count": 4
      },
      {
        "id": "2018",
        "title": "2018",
        "count": 4
      },
      {
        "id": "2017",
        "title": "2017",
        "count": 9
      },
      {
        "id": "2016",
        "title": "2016",
        "count": 22
      },
      {
        "id": "2015",
        "title": "2015",
        "count": 2
      },
      {
        "id": "2014",
        "title": "2014",
        "count": 3
      },
      {
        "id": "2013",
        "title": "2013",
        "count": 4
      }
    ],
    "views": [],
    "downloads": []
  },
  "links": {
    "self": "https://api.datacite.org/dois?client_id=datacite.datacite&page%5Bsize%5D=2",
    "next": "https://api.datacite.org/dois?client-id=datacite.datacite&page%5Bnumber%5D=2&page%5Bsize%5D=2"
  }
}
```

To save space, the example response shows only two records in this list and the resource type "meta" counts. 

### What's in the API response?

The REST API response includes all metadata in JSON format as well as meta fields that provide aggregated information about the DOIs in the list.

> 👍 
> 
> _Note: Affiliation identifiers (supported in Metadata Schema 4.3+) are not included in REST API responses by default. To include affiliation identifier details, add `&affiliation=true` to your queries. [See our FAQ for more information](https://support.datacite.org/docs/can-i-see-more-detailed-affiliation-information-in-the-rest-api)_

The list below provides a description of the meta fields that appear in the API response. This information is different from the DOI metadata.

**total**	  
Total results count.

**totalPages**  
Total pages count.

**page**	  
Current page.

**states**  
Counts by DOI state.

**resourceTypes**  
resourceTypes in the search results with counts.

**created	**  
Histogram of the create date of the DOI record by top 10 years with counts.

**published**	  
Histogram of publicationYear years with counts.

**registered**	  
Histogram of the registered date of the DOI record by top 10 years with counts.

**providers**	  
The top 10 DataCite Members or Consortium Organizations with Members IDs, Member titles, and counts.

**clients**	  
The top 10 repositories in the search results with repository IDs, repository titles, and counts.

**affiliations**	  
The top 10 represented ROR affliations with ROR ID, research organization title, and counts.

**prefixes**	  
The top 10 prefixes in the search with counts.

**certificates**	  
Repository certificates in the search with counts.

**licenses**	  
The top 10 rights with rights identifiers in the search with counts.

**schemaVersions**	  
The DataCite Metadata Schema versions represented in the search with counts.

**linkChecksStatus**	  
The status of the landing pages of DOIs in the search (when and if last checked) with counts.

**subjects**	  
The top 10 subjects represented in the search with counts.

**fieldsOfScience	**  
The top 10 Fields of Science and Technology (FOS) subjects in the search with counts.

**citations**	  
A histogram of citations by publicationYear in the search by top 10 years with counts.

**views**	  
A histogram of views by publicationYear in the search by top 10 years with counts.

**downloads**  
A histogram of downloads by publicationYear in the search by top 10 years with counts.

> 📘 Can I export the results in CSV format?
> 
> Including the text/CSV format in the header of the API call exports the results in CSV format. Add more filtering parameters to narrow or scope-out the file.

## Other useful lists

There are many other resources in the API (see table below) and all of them can be retrieved in the same fashion. Major resource components supported by the DataCite API are (in alphabetical order) presented below and can be used alone like this:

| Resource     | Description                                                                              |
| :----------- | :--------------------------------------------------------------------------------------- |
| `/clients`   | returns a list of all DataCite clients                                                   |
| `/dois`      | returns a list of all DOIs (datasets, text documents, etc.)                              |
| `/events`    | returns a list of all events from the [DataCite Event Data](doc:eventdata-guide) service |
| `/prefixes`  | returns a list of all DOI prefixes                                                       |
| `/providers` | returns a list of all DataCite providers                                                 |
| `/reports`   | returns a list of all usage reports                                                      |

Results of queries are also returned as lists. The next section of this guide ([Queries and Filtering](doc:api-queries)) will cover making and filtering queries.