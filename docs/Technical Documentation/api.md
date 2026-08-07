---
title: DataCite REST API Guide
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
# Purpose of the DataCite REST API

The [DataCite REST API](http://api.datacite.org) allows users to retrieve, query and browse DataCite DOI metadata records. The API is generally RESTFUL and returns results in JSON, as the API follows the [JSONAPI](http://jsonapi.org/) specification. It should be highlighted that the DataCite REST API is not intended for creating DOIs or metadata records. This API is for wide consumption and thus does NOT requires authentication. Other alternatives to retrieve, query and browse DataCite DOI metadata records include [DataCite OAI-PMH](http://oai.datacite.org) service and the [DataCite Search](http://search.datacite.org) service. OAI-PMH is used primarily for bulk harvesting of metadata, and DataCite Search – which uses the DataCite REST API under the hood – provides a web interface to retrieve, query and browse DataCite metadata records.

# Getting Started

In this tutorial we will look at four basic operations of the DataCite REST API: Listing works; listing a specific work; querying works by topic; and filtering lists.

Most applications will use an existing wrapper library in the language of your choice, but it's important to familiarise yourself with the underlying API HTTP methods first.

There's no easier way to kick the tires than through [cURL](https://curl.haxx.se/docs/manpage.html).

Let's start by testing our setup. Open up a command prompt and enter the following command:

```shell
$ curl https://api.datacite.org/works/10.5438/0012
```
```json
{
  "data": {
    "id": "https://doi.org/10.5438/0012",
    "type": "works",
    "attributes": {
      "doi": "10.5438/0012",
      "url": null,
      "author": [
        {
          "literal": "DataCite Metadata Working Group"
        }
      ],
      "title": "DataCite Metadata Schema Documentation for the Publication and Citation of Research Data v4.0",
      "container-title": "DataCite e.V.",
      "description": "1 Introduction\n1.1 The DataCite Consortium\n1.2 DataCite Community Participation\n1.3 The Metadata Schema\n1.4 Version 4.0 Update\n2 DataCite Metadata Properties\n2.1 Overview\n2.2 Citation\n2.3 DataCite Properties\n3 XML Example\n4 XML Schema\n5 Other DataCite Services\nAppendices\nAppendix 1: Controlled List Definitions\nAppendix 2: Earlier Version Update Notes",
      "resource-type-subtype": "Documentation",
      "publisher-id": "datacite.datacite",
      "member-id": "datacite",
      "registration-agency-id": "datacite",
      "resource-type-id": "text",
      "work-type-id": "report",
      "version": "4.0",
      "license": null,
      "schema-version": "4",
      "results": [],
      "published": "2016",
      "deposited": "2016-09-19T21:53:56Z",
      "updated": "2016-09-19T22:16:45Z",
      "media": null,
      "xml": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NCjxyZXNvdXJjZSB4bWxucz0iaHR0cDovL2RhdGFjaXRlLm9yZy9zY2hlbWEva2VybmVsLTQiIHhtbG5zOnhzaT0iaHR0cDovL3d3dy53My5vcmcvMjAwMS9YTUxTY2hlbWEtaW5zdGFuY2UiIHhzaTpzY2hlbWFMb2NhdGlvbj0iaHR0cDovL2RhdGFjaXRlLm9yZy9zY2hlbWEva2VybmVsLTQgaHR0cDovL3NjaGVtYS5kYXRhY2l0ZS5vcmcvbWV0YS9rZXJuZWwtNC9tZXRhZGF0YS54c2QiPg0KCTxpZGVudGlmaWVyIGlkZW50aWZpZXJUeXBlPSJET0kiPjEwLjU0MzgvMDAxMjwvaWRlbnRpZmllcj4NCgk8Y3JlYXRvcnM+DQoJCTxjcmVhdG9yPg0KCQkJPGNyZWF0b3JOYW1lPkRhdGFDaXRlIE1ldGFkYXRhIFdvcmtpbmcgR3JvdXA8L2NyZWF0b3JOYW1lPg0KCQk8L2NyZWF0b3I+DQoJPC9jcmVhdG9ycz4NCgk8dGl0bGVzPg0KCQk8dGl0bGU+RGF0YUNpdGUgTWV0YWRhd"
    },
    "relationships": {
      "publisher": {
        "meta": {}
      },
      "member": {
        "meta": {}
      },
      "registration-agency": {
        "meta": {}
      },
      "resource-type": {
        "meta": {}
      },
      "work-type": {
        "meta": {}
      }
    }
  }
}
```

The response will be the metadata of the record of the DOI use requested for. Mmmmm, tastes like JSON. Let's add the `-i` flag to include headers:


```shell
$ curl https://api.datacite.org/works/10.5438/0012 -i
HTTP/1.1 200 OK

Server: openresty/1.11.2.1
Date: Mon, 09 Jan 2017 09:34:21 GMT
Content-Type: application/vnd.api+json; charset=utf-8
Transfer-Encoding: chunked
Connection: keep-alive
Status: 200 OK
Cache-Control: max-age=0, private, must-revalidate
Access-Control-Allow-Origin: *
Vary: Accept-Encoding
Access-Control-Max-Age: 1728000
X-XSS-Protection: 1; mode=block
X-Request-Id: 8f7093e4-b8ca-45ad-b8cc-1be199d69092
Access-Control-Allow-Methods: GET, POST, OPTIONS
ETag: W/"12e33c8ee2d4b8d07b05dce337aee491"
X-Frame-Options: SAMEORIGIN
X-Runtime: 0.086434
X-Content-Type-Options: nosniff
X-Powered-By: Phusion Passenger 5.1.1
Access-Control-Allow-Headers: Content-Type,Accept,Accept-Encoding,Origin,User-Agent,Cache-Control,Keep-Alive

```

There are a few interesting bits in the response headers. As expected, the Content-Type is `application/vnd.api+json`. Additional responses status include: `200 OK`: operation successful;`422` : - The request is taking too much time to responde; `404 Not Found`: The page you are looking for doesn't exist.





## Retrieving Metadata records

Almost any meaningful use of the DataCite REST API will involve some level of record retrieval. The responses from each of your request fall in two basics categories: Singletons (i.e., a single record) and Lists (i.e., a list of records).


**Singletons** are single results. Retrieving metadata for a specific identifier (e.g. DOI, ORCID) typically returns in a singleton result.



For example, retrieving the metadata record for the DOI `10.5438/0012` can be done as follows:

```shell
# GET /works
$ curl https://api.datacite.org/works/10.5438/0012
```

Or if you are using `Python`  you can retrieve it his way:


```python
import requests, sys
endpoint = 'https://api.datacite.org/works'
if (len(sys.argv) < 2):
    raise Exception('Please provide a DOI')
doi = sys.argv[1:]
response = requests.get(endpoint + '/' + doi)
if (response.status_code != 200):
    print str(response.status_code) + " " + response.text
else:
    print response.text
```


```json
{
  "data": {
    "id": "https://doi.org/10.5438/0012",
    "type": "works",
    "attributes": {
      "doi": "10.5438/0012",
      "url": null,
      "author": [
        {
          "literal": "DataCite Metadata Working Group"
        }
      ],
      "title": "DataCite Metadata Schema Documentation for the Publication and Citation of Research Data v4.0",
      "container-title": "DataCite e.V.",
      "description": "1 Introduction\n1.1 The DataCite Consortium\n1.2 DataCite Community Participation\n1.3 The Metadata Schema\n1.4 Version 4.0 Update\n2 DataCite Metadata Properties\n2.1 Overview\n2.2 Citation\n2.3 DataCite Properties\n3 XML Example\n4 XML Schema\n5 Other DataCite Services\nAppendices\nAppendix 1: Controlled List Definitions\nAppendix 2: Earlier Version Update Notes",
      "resource-type-subtype": "Documentation",
      "publisher-id": "datacite.datacite",
      "member-id": "datacite",
      "registration-agency-id": "datacite",
      "resource-type-id": "text",
      "work-type-id": "report",
      "version": "4.0",
      "license": null,
      "schema-version": "4",
      "results": [],
      "published": "2016",
      "deposited": "2016-09-19T21:53:56Z",
      "updated": "2016-09-19T22:16:45Z",
      "media": null,
      "xml": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NCjxyZXNvdXJjZSB4bWxucz0iaHR0cDovL2RhdGFjaXRlLm9yZy9zY2hlbWEva2VybmVsLTQiIHhtbG5zOnhzaT0iaHR0cDovL3d3dy53My5vcmcvMjAwMS9YTUxTY2hlbWEtaW5zdGFuY2UiIHhzaTpzY2hlbWFMb2NhdGlvbj0iaHR0cDovL2RhdGFjaXRlLm9yZy9zY2hlbWEva2VybmVsLTQgaHR0cDovL3NjaGVtYS5kYXRhY2l0ZS5vcmcvbWV0YS9rZXJuZWwtNC9tZXRhZGF0YS54c2QiPg0KCTxpZGVudGlmaWVyIGlkZW50aWZpZXJUeXBlPSJET0kiPjEwLjU0MzgvMDAxMjwvaWRlbnRpZmllcj4NCgk8Y3JlYXRvcnM+DQoJCTxjcmVhdG9yPg0KCQkJPGNyZWF0b3JOYW1lPkRhdGFDaXRlIE1ldGFkYXRhIFdvcmtpbmcgR3JvdXA8L2NyZWF0b3JOYW1lPg0KCQk8L2NyZWF0b3I+DQoJPC9jcmVhdG9ycz4NCgk8dGl0bGVzPg0KCQk8dGl0bGU+RGF0YUNpdGUgTWV0YWRhd"
    },
    "relationships": {
      "publisher": {
        "meta": {}
      },
      "member": {
        "meta": {}
      },
      "registration-agency": {
        "meta": {}
      },
      "resource-type": {
        "meta": {}
      },
      "work-type": {
        "meta": {}
      }
    }
  }
}
```





**Lists** results can contain multiple entries. Searching or filtering typically returns a list result.


A **list** has three parts:

* **meta**, which includes information about the query, e.g. number of results returned.
* **data**, which will contain the items matching the query or filter.
* **included**, which will contain side-loaded associations, via the `?include=x` parameter.



For example, retrieving the all metadata records for all DOIs can be done as follows:

```shell
# GET /works
$ curl https://api.datacite.org/works/
```

```json
{
  "data": [
    {
      "id": "https://doi.org/10.15468/DL.PTJ8XW",
      "type": "works",
      "attributes": {
        "doi": "10.15468/DL.PTJ8XW",
        "url": null,
        "author": [
          {
            "literal": "Occdownload Gbif.Org"
          }
        ],
        "title": "GBIF Occurrence Download",
        "container-title": "The Global Biodiversity Information Facility",
        "description": "A dataset containing 137 species occurrences available in GBIF matching the query: TaxonKey: Muhlenbergia torreyi (Kunth) Hitchc. ex Bush \nHasCoordinate: TRUE. The dataset includes 137 records from 16 constituent datasets: \n 2 records from Australia's Virtual Herbarium. \n 14 records from Kathryn Kalmbach Herbarium. \n 2 records from iNaturalist Research-grade Observations. \n 6 records from LSU Shirley C. Tucker Herbarium at Louisiana State University - Vascular Plants. \n 5 records from Tropicos Specimen Data. \n 24 records from Estudio taxonómico y base de datos del género Muhlenbergia de México. \n 16 records from NMNH Extant Specimen and Observation Records. \n 10 records from USU-UTC Specimen Database. \n 4 records from Herbarium de Geo. B. Hinton, México. \n 3 records from Specimen Database of Colorado Vascular Plants. \n 4 records from Repatriación de datos del Herbario de Arizona (ARIZ). \n 15 records from Colorado State University Herbarium. \n 12 records from R. L. McGregor Herbarium Vascular Plants Collection. \n 1 records from The New York Botanical Garden Herbarium (NY) - Vascular Plant Collection. \n 1 records from Florística de las gramíneas de Chihuahua. \n 18 records from Instituto de Botánica Darwinion. Data from some individual datasets included in this download may be licensed under less restrictive terms.",
        "resource-type-subtype": null,
        "publisher-id": "dk.gbif",
        "member-id": "dk",
        "registration-agency-id": "datacite",
        "resource-type-id": "dataset",
        "work-type-id": "dataset",
        "version": null,
        "license": "https://creativecommons.org/licenses/by-nc/4.0/",
        "schema-version": "3",
        "results": [],
        "published": "2017",
        "deposited": "2017-01-04T01:13:28Z",
        "updated": "2017-01-04T01:13:28Z",
        "media": null,
        "xml": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiIHN0YW5kYWxvbmU9InllcyI/Pgo8cmVzb3VyY2UgeHNpOnNjaGVtYUxvY2F0aW9uPSJodHRwOi8vZGF0YWNpdGUub3JnL3NjaGVtYS9rZXJuZWwtMyBodHRwOi8vc2NoZW1hLmRhdGFjaXRlLm9yZy9tZXRhL2tlcm5lbC0zL21ldGFkYXRhLnhzZCIgeG1sbnM9Imh0dHA6Ly9kYXRhY2l0ZS5vcmcvc2NoZW1hL2tlcm5lbC0zIiB4bWxuczp4c2k9Imh0dHA6Ly93d3cudzMub3JnLzIwMDEvWE1MU2NoZW1hLWluc3RhbmNlIj4KICAgIDxpZGVudGlmaWVyIGlkZW50aWZpZXJUeXBlPSJET0kiPjEwLjE1NDY4L2RsLnB0ajh4dzwvaWRlbnRpZmllcj4KICAgIDxjcmVhdG9ycz4KICAgICAgICA8Y3JlYXRvcj4KICAgICAgICAgICAgPGNyZWF0b3JOYW1lPm9jY2Rvd25sb2FkIGdiaWYub3JnPC9jcmVhdG9yTmFtZT4KICAgICAgICA8L2NyZWF0b3I+CiAgICA8L2NyZWF0b3JzPgogICAgPHRpdGxlcz4KICAgICAgICA8dGl0bGU+R0JJRiBPY2N1cnJlbmNlIERvd25sb2FkPC90aXRsZT4KICAgIDwvdGl0bGVzPgogICAgPHB1Ymxpc2hlcj5UaGUgR2xvYmFsIEJpb2RpdmVyc2l0eSBJbmZvcm1hdGlvbiBGYWNpbGl0eTwvcHVibGlzaGVyPgogICAgPHB1YmxpY2F0aW9uWWVhcj4yMDE3PC9wdWJsaWNhdGlvblllYXI+CiAgICA8c3ViamVjdHM+CiAgICAgICAgPHN1Y"
      },
      "relationships": {
        "publisher": {
          "meta": {}
        },
        "member": {
          "meta": {}
        },
        "registration-agency": {
          "meta": {}
        },
        "resource-type": {
          "meta": {}
        },
        "work-type": {
          "meta": {}
        }
      }
    },
    {
      "id": "https://doi.org/10.14288/1.0340201",
      "type": "works",
      "attributes": {
        "doi": "10.14288/1.0340201",
        "url": null,
        "author": [
          {
            "family": "Holland",
            "given": "Laura"
          }
        ],
        "title": "[Letter from Laura Holland to her mother]",
        "container-title": "The University of British Columbia",
        "description": "",
        "resource-type-subtype": null,
        "publisher-id": "cisti.ubc",
        "member-id": "cisti",
        "registration-agency-id": "datacite",
        "resource-type-id": null,
        "work-type-id": "work",
        "version": "1",
        "license": null,
        "schema-version": "3",
        "results": [],
        "published": "2016",
        "deposited": "2017-01-04T01:13:27Z",
        "updated": "2017-01-04T01:13:27Z",
        "media": null,
        "xml": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4KPHJlc291cmNlIHhtbG5zOnhzaT0iaHR0cDovL3d3dy53My5vcmcvMjAwMS9YTUxTY2hlbWEtaW5zdGFuY2UiIHhtbG5zPSJodHRwOi8vZGF0YWNpdGUub3JnL3NjaGVtYS9rZXJuZWwtMyIgeHNpOnNjaGVtYUxvY2F0aW9uPSJodHRwOi8vZGF0YWNpdGUub3JnL3NjaGVtYS9rZXJuZWwtMyBodHRwOi8vc2NoZW1hLmRhdGFjaXRlLm9yZy9tZXRhL2tlcm5lbC0zL21ldGFkYXRhLnhzZCI+PGlkZW50aWZpZXIgaWRlbnRpZmllclR5cGU9IkRPSSI+MTAuMTQyODgvMS4wMzQwMjAxPC9pZGVudGlmaWVyPjxjcmVhdG9ycz48Y3JlYXRvcj48Y3JlYXRvck5hbWU+SG9sbGFuZCwgTGF1cmE8L2NyZWF0b3JOYW1lPjwvY3JlYXRvcj48L2NyZWF0b3JzPjx0aXRsZ"
      },
      "relationships": {
        "publisher": {
          "meta": {}
        },
        "member": {
          "meta": {}
        },
        "registration-agency": {
          "meta": {}
        },
        "resource-type": {
          "meta": {}
        },
        "work-type": {
          "meta": {}
        }
      }
    }
  ],
  "meta": {
    "resource-types": [
      {
        "id": "dataset",
        "title": "Dataset",
        "count": 2923633
      },
      {
        "id": "text",
        "title": "Text",
        "count": 1588230
      },
      {
        "id": "workflow",
        "title": "Workflow",
        "count": 252
      },
      {
        "id": "service",
        "title": "Service",
        "count": 29
      }
    ],
    "years": [
      {
        "id": "2016",
        "title": "2016",
        "count": 834677
      },
      {
        "id": "2015",
        "title": "2015",
        "count": 2080251
      },
      {
        "id": "2014",
        "title": "2014",
        "count": 973996
      },
      {
        "id": "2013",
        "title": "2013",
        "count": 353263
      },
      {
        "id": "2003",
        "title": "2003",
        "count": 80393
      },
      {
        "id": "2002",
        "title": "2002",
        "count": 52403
      }
    ],
    "publishers": [
      {
        "id": "cdl.dplanet",
        "title": "Data-Planet",
        "count": 867774
      },
      {
        "id": "bl.ccdc",
        "title": "The Cambridge Crystallographic Data Centre",
        "count": 639461
      },
      {
        "id": "figshare.ars",
        "title": "figshare Academic Research System",
        "count": 527635
      },
      {
        "id": "ands.centre72",
        "title": "PARADISEC",
        "count": 153467
      },
      {
        "id": "cern.zenodo",
        "title": "ZENODO - Research. Shared.",
        "count": 116167
      }
    ],
    "schema-versions": [
      {
        "id": "4",
        "title": "Schema 4",
        "count": 108228
      },
      {
        "id": "3",
        "title": "Schema 3",
        "count": 6662751
      },
      {
        "id": "2.2",
        "title": "Schema 2.2",
        "count": 1070998
      },
      {
        "id": "2.1",
        "title": "Schema 2.1",
        "count": 5700
      },
      {
        "id": "2.0",
        "title": "Schema 2.0",
        "count": 756
      }
    ],
    "total": 7848433,
    "sources": [],
    "relation-types": []
  }
}
```

The response shows some interesting things. First, let us clarify that we have truncated the response for the benefit of space to show only two records in this list. Normally, results are returned 25 at a time. The full DataCite Metadata storage has more than 7 Million records as can be noted in the `meta:,total:7848433,` property. The sort order of the List ( in `data:` object) is done by DOI deposit date. Facet counts are returned via the `meta:` object. Facet counts give counts per field value for an entire result set.



## Making Queries

Additionally, the API supports the use of `queries`, which also return **lists** as responses. Queries support a subset of [DisMax](https://wiki.apache.org/solr/DisMax), so, for example, you can refine queries as follows.


```shell
#GET works?query=
$ curl https://api.datacite.org/works?query=climate+-change
```

Or in `python` you can do:

```python
import requests, sys
endpoint = 'https://api.datacite.org/works'
if (len(sys.argv) < 2):
    raise Exception('Please provide a DOI')
query = sys.argv[1:]
response = requests.get(endpoint + '?query=' + query)
if (response.status_code != 200):
    print str(response.status_code) + " " + response.text
else:
    print response.text
```


the response is a list of all the `works` that contain the term *climate* in their metadata excluding those that have the term *change*.



Additional parameters can be used to query, filter and control the results returned by the DataCite API. They can be passed as normal URI parameters or as JSON in the body of the request.

| Parameter                    | Description                 |
|:-----------------------------|:----------------------------|
| `query`                      | limited [DisMax](https://wiki.apache.org/solr/DisMax) query terms |
| `rows`                       | results per per page |
| `offset`                     | result offset |
| `sort`                       | sort results by a certain field |
| `order`                      | set the sort order to `asc` or `desc` |
| `include`                    | side-load associations |


For example to list one single work using the previously specified query:

```shell
#GET works?query=
$ curl https://api.datacite.org/works?query=climate+-change&rows=1
```


## Filtering List Responses

Finally, the API supports filters that allow you to narrow queries. All filter results are **lists**. For example, if you which to filter results by their *publisher* and this publisher is `cdl.dryad` (Dryad Digital Repository)

```
curl https://api.datacite.org/works?publisher-id=cdl.dryad
```

 The following filters are supported:

| Filter     | Possible values | Description|
|:-----------|:----------------|:-----------|
| `member-id` | `{member-id}` | metadata associated with a specific DataCite member |
| `publisher-id` | `{publisher-id}` | metadata associated with a specific DataCite data center |
| `resource-type-id` | `{resource-type-id}` | metadata for a specific resourceTypeGeneral |
| `from-created-date` | `{date}` | metadata where deposited date is since (inclusive) `{date}` |
| `until-created-date` | `{date}` | metadata where deposited date is before (inclusive)  `{date}` |
| `from-update-date` | `{date}` | metadata where updated date is since (inclusive) `{date}` |
| `until-update-date` | `{date}` | metadata where updated date is before (inclusive)  `{date}` |
| `year` | `{year}` | publication year of the resource `{year}` |


Woot! Now you know the basics of the DataCite REST API!

- Retrieving single items and List
- Querying
- Filtering

There are many other resources in the API (see table below) and all of them can be retrieved in the same fashion. Major resource components supported by the DataCite API are (in alphabetical order) presented below and can be used alone like this:

| Resource                 | Description                       |
|:-------------------------|:----------------------------------|
| `/members`               | returns a list of all DataCite members |
| `/publishers`            | returns a list of all DataCite publishers |
| `/works`                 | returns a list of all works (datasets, text documents, etc.), 25 per page


Keep learning with the [API Reference](http://support.datacite.org/reference)!
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]