---
title: Queries and filtering
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
# Making Queries

The API supports the use of queries, which return lists as responses. The previous section of this guide ([Retrieving a list of DOIs](doc:api-get-lists)) dealt with the basics of list results. This section will cover making queries and filtering the response lists. 

```shell
$ curl https://api.datacite.org/dois?query=climate%20change
```

The response is a list of all the DOI records that contain the phrases `climate` or `change` in their metadata. The REST API uses Elasticsearch [query string syntax](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html#query-string-syntax). 

The query string is parsed into a series of terms and operators. A term can be a single word — quick or brown — or a phrase, surrounded by double quotes — "quick brown" — which searches for all the words in the phrase, in the same order.

The specifics of query string queries are discussed at the link provided above; a summary is given below.

### Field names

Queries by default search all fields, but a specific field can be provided in the query, e.g. 

```shell
$ curl https://api.datacite.org/dois?query=publicationYear:2016
```

For nested fields use the same format as in the REST API response, e.g.

```shell
$ curl https://api.datacite.org/dois?query=creators.nameIdentifiers.nameIdentifierScheme:ORCID
```

### Wildcards

Wildcards are supported, e.g.

```shell
$ curl https://api.datacite.org/dois?query=creators.nameIdentifiers.nameIdentifier:*
$ curl https://api.datacite.org/dois?query=creators.familyName:mil*
```

### Boolean operators

By default, all terms are optional, as long as one term matches. Use `+` or `-` to specify terms that have to match or not match, respectively. For example 

```shell
$ curl https://api.datacite.org/dois?query=titles.title:(climate%20+change)
```

The boolean operators AND, OR and NOT (case-sensitive) are also supported. When multiple operators are used together, use parentheses to combine them.

### Additional parameters

Additional parameters can be used to query, filter and control the results returned by the DataCite API. They can be passed as normal URI parameters or as JSON in the body of the request.

| Parameter      | Description                     |
| :------------- | :------------------------------ |
| `page[size]`   | results per per page            |
| `page[number]` | page number                     |
| `sort`         | sort results by a certain field |
| `include`      | side-load associations          |

For example, to list one single work using the previously specified query, you would add a `page[size]` parameter with a value of 1, like so:

```shell
$ curl https://api.datacite.org/dois?query=climate+change&page[size]=1
```

For a full list of query params, please see the [API Reference](https://support.datacite.org/reference/get_dois).

# Filtering List Responses

The API supports filters that allow you to narrow queries. All filter results are lists. For example, if you wish to filter results by _client_ to find everything that is managed by the client `dryad.dryad` (Dryad Digital Repository), you would do the following:

```shell
$ curl https://api.datacite.org/dois?client-id=dryad.dryad
```

 The following filters are supported:

| Filter             | Possible values      | Description                                                                                                   |
| :----------------- | :------------------- | :------------------------------------------------------------------------------------------------------------ |
| `provider-id`      | `{provider-id}`      | metadata associated with a specific DataCite provider (Direct Member, Consortium, or Consortium Organization) |
| `client-id`        | `{client-id}`        | metadata associated with a specific DataCite client (repository)                                              |
| `consortium-id`    | `{consortium-id}`    | metadata associated with a specific DataCite consortium                                                       |
| `resource-type-id` | `{resource-type-id}` | metadata for a specific resourceTypeGeneral                                                                   |
| `person-id`        | `{person-id}`        | metadata associated with a specific person's ORCID iD                                                         |
| `registered`       | `{registered}`       | metadata where year of DOI registration (registered in global handle server) is `{year}`                      |
| `created`          | `{created}`          | metadata where year of DOI creation (created in DataCite system) is `{created}`                               |
| `schema-version`   | `{schema-version}`   | metadata where schema version of the deposited metadata is `{schema-version}`                                 |

> 👍 What's in the response?
> 
> Query results are returned as a list of DOI records in JSON format, as described in [Retrieving a list of DOIs](doc:api-get-lists).
> 
> Note: Affiliation identifiers (supported in Metadata Schema 4.3+) and publisher identifiers (supported in Metadata Schema 4.5+) are not included in REST API responses by default. [See our FAQ for more information](https://support.datacite.org/docs/can-i-see-more-detailed-affiliation-information-in-the-rest-api).
> 
> - To include affiliation identifier details, add &affiliation=true to your queries. 
> - To include publisher identifier details, add &publisher=true to your queries. 

The REST API also supports retrieving a random sample of results. The next section of this guide will cover sampling (see [Retrieving a random sample of DOIs](doc:api-sampling)).

## Elasticsearch queries

The API supports [Elasticsearch query string queries](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html#query-string-syntax). The query structure follows the same structure as the elements in the JSON API. All of the elements that can be searched can be seen in the response below:

```shell
$ curl https://api.test.datacite.org/dois/10.17596/qf5s-pc52?affiliation=true
```

> 📘 
> 
> This example uses the test endpoint to illustrate all of the JSON fields in the API response.

```json
{
  "data": {
    "id": "10.17596/qf5s-pc52",
    "type": "dois",
    "attributes": {
      "doi": "10.17596/qf5s-pc52",
      "prefix": "10.70126",
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
            "DataCite"
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
          "title": "Full DataCite XML Example"
        },
        {
          "lang": "en-US",
          "title": "Demonstration of DataCite Properties.",
          "titleType": "Subtitle"
        }
      ],
      "publisher": "DataCite",
      "container": {},
      "publicationYear": 2014,
      "subjects": [
        {
          "lang": "en-US",
          "subject": "computer science",
          "schemeUri": "http://dewey.info/",
          "subjectScheme": "dewey",
          "classificationCode": "000"
        }
      ],
      "contributors": [
        {
          "name": "Starr, Joan",
          "givenName": "Joan",
          "familyName": "Starr",
          "affiliation": [
            "California Digital Library"
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
          "dateType": "Issued"
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
      "relatedItems": [
        {
          "titles": [
            {
              "title": "Physics letters B"
            }
          ],
          "volume": "776",
          "creators": [],
          "lastPage": "264",
          "firstPage": "249",
          "contributors": [],
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
          "lang": "en-US",
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
      "xml": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4KPHJlc291cmNlIHhtbG5zOnhzaT0iaHR0cDovL3d3dy53My5vcmcvMjAwMS9YTUxTY2hlbWEtaW5zdGFuY2UiIHhtbG5zPSJodHRwOi8vZGF0YWNpdGUub3JnL3NjaGVtYS9rZXJuZWwtNCIgeHNpOnNjaGVtYUxvY2F0aW9uPSJodHRwOi8vZGF0YWNpdGUub3JnL3NjaGVtYS9rZXJuZWwtNCBodHRwczovL3NjaGVtYS5kYXRhY2l0ZS5vcmcvbWV0YS9rZXJuZWwtNC40L21ldGFkYXRhLnhzZCI+CiAgPGlkZW50aWZpZXIgaWRlbnRpZmllclR5cGU9IkRPSSI+MTAuNzAxMjYvSzdXSy1STTM2PC9pZGVudGlmaWVyPgogIDxjcmVhdG9ycz4KICAgIDxjcmVhdG9yPgogICAgICA8Y3JlYXRvck5hbWUgbmFtZVR5cGU9IlBlcnNvbmFsIj5NaWxsZXIsIEVsaXphYmV0aDwvY3JlYXRvck5hbWU+CiAgICAgIDxnaXZlbk5hbWU+RWxpemFiZXRoPC9naXZlbk5hbWU+CiAgICAgIDxmYW1pbHlOYW1lPk1pbGxlcjwvZmFtaWx5TmFtZT4KICAgICAgPG5hbWVJZGVudGlmaWVyIHNjaGVtZVVSST0iaHR0cHM6Ly9vcmNpZC5vcmcvIiBuYW1lSWRlbnRpZmllclNjaGVtZT0iT1JDSUQiPjAwMDAtMDAwMS01MDAwLTAwMDc8L25hbWVJZGVudGlmaWVyPgogICAgICA8YWZmaWxpYXRpb24+RGF0YUNpdGU8L2FmZmlsaWF0aW9uPgogICAgPC9jcmVhdG9yPgogIDwvY3JlYXRvcnM+CiAgPHRpdGxlcz4KICAgIDx0aXRsZSB4bWw6bGFuZz0iZW4tVVMiPkZ1bGwgRGF0YUNpdGUgWE1MIEV4YW1wbGU8L3RpdGxlPgogICAgPHRpdGxlIHhtbDpsYW5nPSJlbi1VUyIgdGl0bGVUeXBlPSJTdWJ0aXRsZSI+RGVtb25zdHJhdGlvbiBvZiBEYXRhQ2l0ZSBQcm9wZXJ0aWVzLjwvdGl0bGU+CiAgPC90aXRsZXM+CiAgPHB1Ymxpc2hlciB4bWw6bGFuZz0iZW4iPkRhdGFDaXRlPC9wdWJsaXNoZXI+CiAgPHB1YmxpY2F0aW9uWWVhcj4yMDE0PC9wdWJsaWNhdGlvblllYXI+CiAgPHN1YmplY3RzPgogICAgPHN1YmplY3QgeG1sOmxhbmc9ImVuLVVTIiBzY2hlbWVVUkk9Imh0dHA6Ly9kZXdleS5pbmZvLyIgc3ViamVjdFNjaGVtZT0iZGV3ZXkiIGNsYXNzaWZpY2F0aW9uQ29kZT0iMDAwIj5jb21wdXRlciBzY2llbmNlPC9zdWJqZWN0PgogIDwvc3ViamVjdHM+CiAgPGNvbnRyaWJ1dG9ycz4KICAgIDxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IlByb2plY3RMZWFkZXIiPgogICAgICA8Y29udHJpYnV0b3JOYW1lPlN0YXJyLCBKb2FuPC9jb250cmlidXRvck5hbWU+CiAgICAgIDxnaXZlbk5hbWU+Sm9hbjwvZ2l2ZW5OYW1lPgogICAgICA8ZmFtaWx5TmFtZT5TdGFycjwvZmFtaWx5TmFtZT4KICAgICAgPG5hbWVJZGVudGlmaWVyIHNjaGVtZVVSST0iaHR0cHM6Ly9vcmNpZC5vcmcvIiBuYW1lSWRlbnRpZmllclNjaGVtZT0iT1JDSUQiPjAwMDAtMDAwMi03Mjg1LTAyN1g8L25hbWVJZGVudGlmaWVyPgogICAgICA8YWZmaWxpYXRpb24+Q2FsaWZvcm5pYSBEaWdpdGFsIExpYnJhcnk8L2FmZmlsaWF0aW9uPgogICAgPC9jb250cmlidXRvcj4KICA8L2NvbnRyaWJ1dG9ycz4KICA8ZGF0ZXM+CiAgICA8ZGF0ZSBkYXRlVHlwZT0iVXBkYXRlZCIgZGF0ZUluZm9ybWF0aW9uPSJVcGRhdGVkIHdpdGggNC40IHByb3BlcnRpZXMiPjIwMjEtMDEtMjY8L2RhdGU+CiAgPC9kYXRlcz4KICA8bGFuZ3VhZ2U+ZW4tVVM8L2xhbmd1YWdlPgogIDxyZXNvdXJjZVR5cGUgcmVzb3VyY2VUeXBlR2VuZXJhbD0iU29mdHdhcmUiPlhNTDwvcmVzb3VyY2VUeXBlPgogIDxhbHRlcm5hdGVJZGVudGlmaWVycz4KICAgIDxhbHRlcm5hdGVJZGVudGlmaWVyIGFsdGVybmF0ZUlkZW50aWZpZXJUeXBlPSJVUkwiPmh0dHBzOi8vc2NoZW1hLmRhdGFjaXRlLm9yZy9tZXRhL2tlcm5lbC00LjQvZXhhbXBsZS9kYXRhY2l0ZS1leGFtcGxlLWZ1bGwtdjQuNC54bWw8L2FsdGVybmF0ZUlkZW50aWZpZXI+CiAgPC9hbHRlcm5hdGVJZGVudGlmaWVycz4KICA8cmVsYXRlZElkZW50aWZpZXJzPgogICAgPHJlbGF0ZWRJZGVudGlmaWVyIHJlbGF0ZWRJZGVudGlmaWVyVHlwZT0iVVJMIiByZWxhdGlvblR5cGU9Ikhhc01ldGFkYXRhIiByZWxhdGVkTWV0YWRhdGFTY2hlbWU9ImNpdGVwcm9jK2pzb24iIHNjaGVtZVVSST0iaHR0cHM6Ly9naXRodWIuY29tL2NpdGF0aW9uLXN0eWxlLWxhbmd1YWdlL3NjaGVtYS9yYXcvbWFzdGVyL2NzbC1kYXRhLmpzb24iPmh0dHBzOi8vZGF0YS5kYXRhY2l0ZS5vcmcvYXBwbGljYXRpb24vY2l0ZXByb2MranNvbi8xMC41MDcyL2V4YW1wbGUtZnVsbDwvcmVsYXRlZElkZW50aWZpZXI+CiAgICA8cmVsYXRlZElkZW50aWZpZXIgcmVsYXRlZElkZW50aWZpZXJUeXBlPSJhclhpdiIgcmVsYXRpb25UeXBlPSJJc1Jldmlld2VkQnkiIHJlc291cmNlVHlwZUdlbmVyYWw9IlRleHQiPmFyWGl2OjA3MDYuMDAwMTwvcmVsYXRlZElkZW50aWZpZXI+CiAgPC9yZWxhdGVkSWRlbnRpZmllcnM+CiAgPHNpemVzPgogICAgPHNpemU+NCBrQjwvc2l6ZT4KICA8L3NpemVzPgogIDxmb3JtYXRzPgogICAgPGZvcm1hdD5hcHBsaWNhdGlvbi94bWw8L2Zvcm1hdD4KICA8L2Zvcm1hdHM+CiAgPHZlcnNpb24+NC4yPC92ZXJzaW9uPgogIDxyaWdodHNMaXN0PgogICAgPHJpZ2h0cyB4bWw6bGFuZz0iZW4tVVMiIHNjaGVtZVVSST0iaHR0cHM6Ly9zcGR4Lm9yZy9saWNlbnNlcy8iIHJpZ2h0c0lkZW50aWZpZXJTY2hlbWU9IlNQRFgiIHJpZ2h0c0lkZW50aWZpZXI9IkNDMCAxLjAiIHJpZ2h0c1VSST0iaHR0cHM6Ly9jcmVhdGl2ZWNvbW1vbnMub3JnL3B1YmxpY2RvbWFpbi96ZXJvLzEuMC8iLz4KICA8L3JpZ2h0c0xpc3Q+CiAgPGRlc2NyaXB0aW9ucz4KICAgIDxkZXNjcmlwdGlvbiB4bWw6bGFuZz0iZW4tVVMiIGRlc2NyaXB0aW9uVHlwZT0iQWJzdHJhY3QiPlhNTCBleGFtcGxlIG9mIGFsbCBEYXRhQ2l0ZSBNZXRhZGF0YSBTY2hlbWEgdjQuNCBwcm9wZXJ0aWVzLjwvZGVzY3JpcHRpb24+CiAgPC9kZXNjcmlwdGlvbnM+CiAgPGdlb0xvY2F0aW9ucz4KICAgIDxnZW9Mb2NhdGlvbj4KICAgICAgPGdlb0xvY2F0aW9uUGxhY2U+QXRsYW50aWMgT2NlYW48L2dlb0xvY2F0aW9uUGxhY2U+CiAgICAgIDxnZW9Mb2NhdGlvblBvaW50PgogICAgICAgIDxwb2ludExvbmdpdHVkZT4tNjcuMzAyPC9wb2ludExvbmdpdHVkZT4KICAgICAgICA8cG9pbnRMYXRpdHVkZT4zMS4yMzM8L3BvaW50TGF0aXR1ZGU+CiAgICAgIDwvZ2VvTG9jYXRpb25Qb2ludD4KICAgICAgPGdlb0xvY2F0aW9uQm94PgogICAgICAgIDx3ZXN0Qm91bmRMb25naXR1ZGU+LTcxLjAzMjwvd2VzdEJvdW5kTG9uZ2l0dWRlPgogICAgICAgIDxlYXN0Qm91bmRMb25naXR1ZGU+LTY4LjIxMTwvZWFzdEJvdW5kTG9uZ2l0dWRlPgogICAgICAgIDxzb3V0aEJvdW5kTGF0aXR1ZGU+NDEuMDkwPC9zb3V0aEJvdW5kTGF0aXR1ZGU+CiAgICAgICAgPG5vcnRoQm91bmRMYXRpdHVkZT40Mi44OTM8L25vcnRoQm91bmRMYXRpdHVkZT4KICAgICAgPC9nZW9Mb2NhdGlvbkJveD4KICAgICAgPGdlb0xvY2F0aW9uUG9seWdvbj4KICAgICAgICA8cG9seWdvblBvaW50PgogICAgICAgICAgPHBvaW50TGF0aXR1ZGU+NDEuOTkxPC9wb2ludExhdGl0dWRlPgogICAgICAgICAgPHBvaW50TG9uZ2l0dWRlPi03MS4wMzI8L3BvaW50TG9uZ2l0dWRlPgogICAgICAgIDwvcG9seWdvblBvaW50PgogICAgICAgIDxwb2x5Z29uUG9pbnQ+CiAgICAgICAgICA8cG9pbnRMYXRpdHVkZT40Mi44OTM8L3BvaW50TGF0aXR1ZGU+CiAgICAgICAgICA8cG9pbnRMb25naXR1ZGU+LTY5LjYyMjwvcG9pbnRMb25naXR1ZGU+CiAgICAgICAgPC9wb2x5Z29uUG9pbnQ+CiAgICAgICAgPHBvbHlnb25Qb2ludD4KICAgICAgICAgIDxwb2ludExhdGl0dWRlPjQxLjk5MTwvcG9pbnRMYXRpdHVkZT4KICAgICAgICAgIDxwb2ludExvbmdpdHVkZT4tNjguMjExPC9wb2ludExvbmdpdHVkZT4KICAgICAgICA8L3BvbHlnb25Qb2ludD4KICAgICAgICA8cG9seWdvblBvaW50PgogICAgICAgICAgPHBvaW50TGF0aXR1ZGU+NDEuMDkwPC9wb2ludExhdGl0dWRlPgogICAgICAgICAgPHBvaW50TG9uZ2l0dWRlPi02OS42MjI8L3BvaW50TG9uZ2l0dWRlPgogICAgICAgIDwvcG9seWdvblBvaW50PgogICAgICAgIDxwb2x5Z29uUG9pbnQ+CiAgICAgICAgICA8cG9pbnRMYXRpdHVkZT40MS45OTE8L3BvaW50TGF0aXR1ZGU+CiAgICAgICAgICA8cG9pbnRMb25naXR1ZGU+LTcxLjAzMjwvcG9pbnRMb25naXR1ZGU+CiAgICAgICAgPC9wb2x5Z29uUG9pbnQ+CiAgICAgIDwvZ2VvTG9jYXRpb25Qb2x5Z29uPgogICAgPC9nZW9Mb2NhdGlvbj4KICA8L2dlb0xvY2F0aW9ucz4KICA8ZnVuZGluZ1JlZmVyZW5jZXM+CiAgICA8ZnVuZGluZ1JlZmVyZW5jZT4KICAgICAgPGZ1bmRlck5hbWU+TmF0aW9uYWwgU2NpZW5jZSBGb3VuZGF0aW9uPC9mdW5kZXJOYW1lPgogICAgICA8ZnVuZGVySWRlbnRpZmllciBmdW5kZXJJZGVudGlmaWVyVHlwZT0iQ3Jvc3NyZWYgRnVuZGVyIElEIj5odHRwczovL2RvaS5vcmcvMTAuMTMwMzkvMTAwMDAwMDAxPC9mdW5kZXJJZGVudGlmaWVyPgogICAgICA8YXdhcmROdW1iZXI+Q0JFVC0xMDY8L2F3YXJkTnVtYmVyPgogICAgICA8YXdhcmRUaXRsZT5GdWxsIERhdGFDaXRlIFhNTCBFeGFtcGxlPC9hd2FyZFRpdGxlPgogICAgPC9mdW5kaW5nUmVmZXJlbmNlPgogIDwvZnVuZGluZ1JlZmVyZW5jZXM+CiAgPHJlbGF0ZWRJdGVtcz4KICAgIDxyZWxhdGVkSXRlbSByZWxhdGlvblR5cGU9IklzUHVibGlzaGVkSW4iIHJlbGF0ZWRJdGVtVHlwZT0iSm91cm5hbCI+CiAgICAgIDxyZWxhdGVkSXRlbUlkZW50aWZpZXIgcmVsYXRlZEl0ZW1JZGVudGlmaWVyVHlwZT0iSVNTTiI+MDM3MC0yNjkzPC9yZWxhdGVkSXRlbUlkZW50aWZpZXI+CiAgICAgIDx0aXRsZXM+CiAgICAgICAgPHRpdGxlPlBoeXNpY3MgbGV0dGVycyBCPC90aXRsZT4KICAgICAgPC90aXRsZXM+CiAgICAgIDxwdWJsaWNhdGlvblllYXI+MjAxODwvcHVibGljYXRpb25ZZWFyPgogICAgICA8dm9sdW1lPjc3Njwvdm9sdW1lPgogICAgICA8Zmlyc3RQYWdlPjI0OTwvZmlyc3RQYWdlPgogICAgICA8bGFzdFBhZ2U+MjY0PC9sYXN0UGFnZT4KICAgIDwvcmVsYXRlZEl0ZW0+CiAgPC9yZWxhdGVkSXRlbXM+CjwvcmVzb3VyY2U+",
      "url": "https://example.org",
      "contentUrl": null,
      "metadataVersion": 0,
      "schemaVersion": "http://datacite.org/schema/kernel-4",
      "source": "fabrica",
      "isActive": true,
      "state": "findable",
      "reason": null,
      "viewCount": 0,
      "viewsOverTime": [],
      "downloadCount": 0,
      "downloadsOverTime": [],
      "referenceCount": 0,
      "citationCount": 0,
      "citationsOverTime": [],
      "partCount": 0,
      "partOfCount": 0,
      "versionCount": 0,
      "versionOfCount": 0,
      "created": "2023-01-04T16:25:04.000Z",
      "registered": "2023-01-04T16:25:05.000Z",
      "published": "2014",
      "updated": "2023-01-04T16:25:05.000Z"
    },
    "relationships": {
      "client": {
        "data": {
          "id": "datacite.mary",
          "type": "clients"
        }
      },
      "provider": {
        "data": {
          "id": "datacite",
          "type": "providers"
        }
      },
      "media": {
        "data": {
          "id": "10.70126/k7wk-rm36",
          "type": "media"
        }
      },
      "references": {
        "data": []
      },
      "citations": {
        "data": []
      },
      "parts": {
        "data": []
      },
      "partOf": {
        "data": []
      },
      "versions": {
        "data": []
      },
      "versionOf": {
        "data": []
      }
    }
  }
}
```

## Query examples

### 1. Publisher

Search for a specific publisher.

`publisher:DataCite`

```shell
$ curl https://api.datacite.org/dois?query=publisher:DataCite
```

### 2. DOI

Search for a specific DOI.

`doi:10.11570/18.0006`

```shell
$ curl https://api.datacite.org/dois?query=doi:10.11570/18.0006
```

### 3. Affiliation

Combine the parent and child elements to construct the to search for an affiliation.

```json
},
  "creators": [
    {
      "name": "Bloggs, Jane",
      "nameType": "Personal",
      "givenName": "Jane",
      "familyName": "Bloggs",
      "affiliation": [
          {
             "name": "DataCite",
             "schemeUri": "https://ror.org",
             "affiliationIdentifier": "https://ror.org/04wxnsj81",
             "affiliationIdentifierScheme": "ROR"
          }
      ],
```

```shell
$ curl https://api.datacite.org/dois?affiliation=true&query=creators.affiliation.name:DataCite
```

To include affiliation identifier details, add &affiliation=true to your queries. [See our FAQ for more information](https://support.datacite.org/docs/can-i-see-more-detailed-affiliation-information-in-the-rest-api).

### 4. Quotes

Search the exact string enclosed in the quotes.

`titles.title:"CrowdoMeter Tweets"`

```shell
$ curl https://api.datacite.org/dois?query=titles.title:"CrowdoMeter Tweets"
```

### 5. Boolean operators (e.g. AND OR + -)

Search using the "AND" boolean.

`types.resourceTypeGeneral:Software AND types.resourceType:XML`

```shell
$ curl https://api.datacite.org/dois?query=types.resourceTypeGeneral:Software%20AND%20types.resourceType:XML
```

Search using the "AND" and "OR" booleans.

```shell
$ curl https://api.datacite.org/dois?query=publisher:DataCite%20AND%20types.resourceTypeGeneral:(Text%20OR%20Dataset)
```

### 6. Wildcards

Search using a wildcard \*.

`subjects.subject:robot*`

```shell
$ curl https://api.datacite.org/dois?query=subjects.subject:robot*
```

### 7. Longer queries

Combine more than one element to limit the search results. In this example the creators and the relatedIdentifier properties are used to build the query.

`creators.name:"Fenner, Martin" AND relatedIdentifiers.relationType:HasPart`

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

```shell
$ curl https://api.datacite.org/dois?query=creators.name:"Fenner, Martin" AND relatedIdentifiers.relationType:HasPart
```