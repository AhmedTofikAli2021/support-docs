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

The [DataCite REST API](https://support.datacite.org/reference) allows any user to retrieve, query and browse DataCite DOI metadata records. In addition, DataCite Clients can register DOIs and DataCite Providers can manage Clients and prefixes via the API. 

The API is generally RESTful and returns results in JSON, as the API follows the [JSONAPI](http://jsonapi.org/) specification. The retrieve, query and browse functions do not require authentication, but the DataCite Provider and Client functions do require authentication with your DataCite Provider or Client ID. 

Other alternatives to retrieve, query and browse DataCite DOI metadata records include the [DataCite OAI-PMH](http://oai.datacite.org) service and the [DataCite Search](http://search.datacite.org) service. OAI-PMH is used primarily for bulk harvesting of metadata, and DataCite Search – which uses the DataCite REST API under the hood – provides a web interface to retrieve, query and browse DataCite metadata records.

Other alternatives to register DOIs are the [MDS API](doc:mds-api-guide) and the [EZ API](doc:datacite-ez-api-guide). Neither of these are JSON APIs. 

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
  "data":{
    "id":"https://doi.org/10.5438/0012",
    "type":"works",
    "attributes":{
      "doi":"10.5438/0012",
      "identifier":"https://doi.org/10.5438/0012",
      "url":null,
      "author":[
        {
          "literal":"DataCite Metadata Working Group"
        }
      ],
      "title":"DataCite Metadata Schema Documentation for the Publication and Citation of Research Data v4.0",
      "container-title":"DataCite e.V.",
      "description":"1 Introduction\n1.1 The DataCite Consortium\n1.2 DataCite Community Participation\n1.3 The Metadata Schema\n1.4 Version 4.0 Update\n2 DataCite Metadata Properties\n2.1 Overview\n2.2 Citation\n2.3 DataCite Properties\n3 XML Example\n4 XML Schema\n5 Other DataCite Services\nAppendices\nAppendix 1: Controlled List Definitions\nAppendix 2: Earlier Version Update Notes",
      "resource-type-subtype":"Documentation",
      "data-center-id":"datacite.datacite",
      "member-id":"datacite",
      "resource-type-id":"text",
      "version":"4.0",
      "license":null,
      "schema-version":"4",
      "results":[
        {
          "id":"Documents",
          "title":"Documents",
          "count":1
        },
        {
          "id":"IsNewVersionOf",
          "title":"Is new version of",
          "count":1
        }
      ],
      "related-identifiers":[
        {
          "relation-type-id":"Documents",
          "related-identifier":"https://doi.org/10.5438/0013"
        },
        {
          "relation-type-id":"IsNewVersionOf",
          "related-identifier":"https://doi.org/10.5438/0010"
        }
      ],
      "published":"2016",
      "registered":"2016-09-19T21:53:56Z",
      "checked":null,
      "updated":"2016-09-19T22:16:45Z",
      "media":null,
      "xml":"PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NCjxyZXNvdXJjZSB4bWxucz0iaHR0cDovL2RhdGFjaXRlLm9yZy9zY2hlbWEva2VybmVsLTQiIHhtbG5zOnhzaT0iaHR0cDovL3d3dy53My5vcmcvMjAwMS9YTUxTY2hlbWEtaW5zdGFuY2UiIHhzaTpzY2hlbWFMb2NhdGlvbj0iaHR0cDovL2RhdGFjaXRlLm9yZy9zY2hlbWEva2VybmVsLTQgaHR0cDovL3NjaGVtYS5kYXRhY2l0ZS5vcmcvbWV0YS9rZXJuZWwtNC9tZXRhZGF0YS54c2QiPg0KCTxpZGVudGlmaWVyIGlkZW50aWZpZXJUeXBlPSJET0kiPjEwLjU0MzgvMDAxMjwvaWRlbnRpZmllcj4NCgk8Y3JlYXRvcnM+DQoJCTxjcmVhdG9yPg0KCQkJPGNyZWF0b3JOYW1lPkRhdGFDaXRlIE1ldGFkYXRhIFdvcmtpbmcgR3JvdXA8L2NyZWF0b3JOYW1lPg0KCQk8L2NyZWF0b3I+DQoJPC9jcmVhdG9ycz4NCgk8dGl0bGVzPg0KCQk8dGl0bGU+RGF0YUNpdGUgTWV0YWRhdGEgU2NoZW1hIERvY3VtZW50YXRpb24gZm9yIHRoZSBQdWJsaWNhdGlvbiBhbmQgQ2l0YXRpb24gb2YgUmVzZWFyY2ggRGF0YSB2NC4wPC90aXRsZT4NCgk8L3RpdGxlcz4NCgk8cHVibGlzaGVyPkRhdGFDaXRlIGUuVi48L3B1Ymxpc2hlcj4NCgk8cHVibGljYXRpb25ZZWFyPjIwMTY8L3B1YmxpY2F0aW9uWWVhcj4NCgk8Y29udHJpYnV0b3JzPg0KCQk8Y29udHJpYnV0b3IgY29udHJpYnV0b3JUeXBlPSJQcm9qZWN0TGVhZGVyIj4NCgkJCTxjb250cmlidXRvck5hbWU+U3RhcnIsIEpvYW48L2NvbnRyaWJ1dG9yTmFtZT4NCgkJCTxnaXZlbk5hbWU+Sm9hbjwvZ2l2ZW5OYW1lPg0KCQkJPGZhbWlseU5hbWU+U3RhcnI8L2ZhbWlseU5hbWU+DQoJCQk8bmFtZUlkZW50aWZpZXIgbmFtZUlkZW50aWZpZXJTY2hlbWU9Ik9SQ0lEIiBzY2hlbWVVUkk9Imh0dHA6Ly9vcmNpZC5vcmciPjAwMDAtMDAwMi03Mjg1LTAyN1g8L25hbWVJZGVudGlmaWVyPg0KCQkJPGFmZmlsaWF0aW9uPkNhbGlmb3JuaWEgRGlnaXRhbCBMaWJyYXJ5PC9hZmZpbGlhdGlvbj4NCgkJPC9jb250cmlidXRvcj4NCgkJPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iUHJvamVjdExlYWRlciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPlNtYWVsZSwgTWFkZWxlaW5lIGRlPC9jb250cmlidXRvck5hbWU+DQoJCQk8Z2l2ZW5OYW1lPk1hZGVsZWluZSBkZTwvZ2l2ZW5OYW1lPg0KCQkJPGZhbWlseU5hbWU+U21hZWxlPC9mYW1pbHlOYW1lPg0KCQkJPGFmZmlsaWF0aW9uPlRVIERlbGZ0PC9hZmZpbGlhdGlvbj4NCgkJPC9jb250cmlidXRvcj4NCgkJPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iRWRpdG9yIj4NCgkJCTxjb250cmlidXRvck5hbWU+QXNodG9uLCBKYW48L2NvbnRyaWJ1dG9yTmFtZT4NCgkJCTxnaXZlbk5hbWU+SmFuPC9naXZlbk5hbWU+DQoJCQk8ZmFtaWx5TmFtZT5Bc2h0b248L2ZhbWlseU5hbWU+DQoJCQk8YWZmaWxpYXRpb24+QnJpdGlzaCBMaWJyYXJ5PC9hZmZpbGlhdGlvbj4NCgkJPC9jb250cmlidXRvcj4NCgkJPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iRWRpdG9yIj4NCgkJCTxjb250cmlidXRvck5hbWU+QmFydG9uLCBBbXk8L2NvbnRyaWJ1dG9yTmFtZT4NCgkJCTxnaXZlbk5hbWU+QW15PC9naXZlbk5hbWU+DQoJCQk8ZmFtaWx5TmFtZT5CYXJ0b248L2ZhbWlseU5hbWU+DQoJCQk8YWZmaWxpYXRpb24+UHVyZHVlIFVuaXZlcnNpdHkgTGlicmFyeTwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPkJyYWRmb3JkLCBUaW5hPC9jb250cmlidXRvck5hbWU+DQoJCQk8Z2l2ZW5OYW1lPlRpbmE8L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPkJyYWRmb3JkPC9mYW1pbHlOYW1lPg0KCQkJPGFmZmlsaWF0aW9uPk5SQy9DSVNUSTwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPkNpb2xla+KAkEZpZ2llbCwgQW5uZTwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5Bbm5lPC9naXZlbk5hbWU+DQoJCQk8ZmFtaWx5TmFtZT5DaW9sZWstRmlnaWVsPC9mYW1pbHlOYW1lPg0KCQkJPGFmZmlsaWF0aW9uPkluaXN04oCQQ05SUzwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPkRpZXRpa2VyLCBTdGVmYW5pZTwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5TdGVmYW5pZTwvZ2l2ZW5OYW1lPg0KCQkJPGZhbWlseU5hbWU+RGlldGlrZXI8L2ZhbWlseU5hbWU+DQoJCQk8YWZmaWxpYXRpb24+RVRIIFrDvHJpY2g8L2FmZmlsaWF0aW9uPg0KCQk8L2NvbnRyaWJ1dG9yPg0KCQk8Y29udHJpYnV0b3IgY29udHJpYnV0b3JUeXBlPSJFZGl0b3IiPg0KCQkJPGNvbnRyaWJ1dG9yTmFtZT5FbGxpb3R0LCBKYW5uZWFuPC9jb250cmlidXRvck5hbWU+DQoJCQk8Z2l2ZW5OYW1lPkphbm5lYW48L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPkVsbGlvdDwvZmFtaWx5TmFtZT4NCgkJCTxhZmZpbGlhdGlvbj5ET0UvT1NUSTwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPkdlbmF0LCBCZXJyaXQ8L2NvbnRyaWJ1dG9yTmFtZT4NCgkJCTxnaXZlbk5hbWU+QmVycml0PC9naXZlbk5hbWU+DQoJCQk8ZmFtaWx5TmFtZT5HZW5hdDwvZmFtaWx5TmFtZT4NCgkJCTxhZmZpbGlhdGlvbj5USUI8L2FmZmlsaWF0aW9uPg0KCQk8L2NvbnRyaWJ1dG9yPg0KCQk8Y29udHJpYnV0b3IgY29udHJpYnV0b3JUeXBlPSJFZGl0b3IiPg0KCQkJPGNvbnRyaWJ1dG9yTmFtZT5IYXJ6ZW5ldHRlciwgS2Fyb2xpbmU8L2NvbnRyaWJ1dG9yTmFtZT4NCgkJCTxnaXZlbk5hbWU+S2Fyb2xpbmU8L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPkhhcnplbmV0dGVyPC9mYW1pbHlOYW1lPg0KCQkJPGFmZmlsaWF0aW9uPkdFU0lTPC9hZmZpbGlhdGlvbj4NCgkJPC9jb250cmlidXRvcj4NCgkJPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iRWRpdG9yIj4NCgkJCTxjb250cmlidXRvck5hbWU+SGlyc2NobWFubiwgQmFyYmFyYTwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5CYXJiYXJhPC9naXZlbk5hbWU+DQoJCQk8ZmFtaWx5TmFtZT5IaXJzY2htYW5uPC9mYW1pbHlOYW1lPg0KCQkJPG5hbWVJZGVudGlmaWVyIG5hbWVJZGVudGlmaWVyU2NoZW1lPSJPUkNJRCIgc2NoZW1lVVJJPSJodHRwOi8vb3JjaWQub3JnIj4wMDAwLTAwMDMtMDI4OS0wMzQ1PC9uYW1lSWRlbnRpZmllcj4NCgkJCTxhZmZpbGlhdGlvbj5FVEggWsO8cmljaDwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPkpha29ic3NvbiwgU3RlZmFuPC9jb250cmlidXRvck5hbWU+DQoJCQk8Z2l2ZW5OYW1lPlN0ZWZhbjwvZ2l2ZW5OYW1lPg0KCQkJPGZhbWlseU5hbWU+SmFrb2Jzc29uPC9mYW1pbHlOYW1lPg0KCQkJPGFmZmlsaWF0aW9uPlNORDwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPk1haWxsb3V4LCBKZWFu4oCQWXZlczwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5KZWFuLVl2ZXM8L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPk1haWxsb3V4PC9mYW1pbHlOYW1lPg0KCQkJPGFmZmlsaWF0aW9uPk5SQy9DSVNUSTwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPk5ld2JvbGQsIEVsaXphYmV0aDwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5FbGl6YWJldGg8L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPk5ld2JvbGQ8L2ZhbWlseU5hbWU+DQoJCQk8bmFtZUlkZW50aWZpZXIgbmFtZUlkZW50aWZpZXJTY2hlbWU9Ik9SQ0lEIiBzY2hlbWVVUkk9Imh0dHA6Ly9vcmNpZC5vcmciPjAwMDAtMDAwMi04MjU1LTkwMTM8L25hbWVJZGVudGlmaWVyPg0KCQkJPGFmZmlsaWF0aW9uPkJyaXRpc2ggTGlicmFyeTwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCQkJPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iRWRpdG9yIj4NCgkJCTxjb250cmlidXRvck5hbWU+TmllbHNlbiwgTGFycyBIb2xtIDwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5MYXJzIEhvbG08L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPk5pZWxzZW48L2ZhbWlseU5hbWU+DQoJCQk8bmFtZUlkZW50aWZpZXIgbmFtZUlkZW50aWZpZXJTY2hlbWU9Ik9SQ0lEIiBzY2hlbWVVUkk9Imh0dHA6Ly9vcmNpZC5vcmciPjAwMDAtMDAwMS04MTM1LTM0ODk8L25hbWVJZGVudGlmaWVyPg0KCQkJPGFmZmlsaWF0aW9uPkNFUk48L2FmZmlsaWF0aW9uPg0KCQk8L2NvbnRyaWJ1dG9yPg0KCQk8Y29udHJpYnV0b3IgY29udHJpYnV0b3JUeXBlPSJFZGl0b3IiPg0KCQkJPGNvbnRyaWJ1dG9yTmFtZT5ZYWhpYSwgTW9oYW1lZDwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5Nb2hhbWVkPC9naXZlbk5hbWU+DQoJCQk8ZmFtaWx5TmFtZT5ZYWhpYTwvZmFtaWx5TmFtZT4NCgkJCTxhZmZpbGlhdGlvbj5JbmlzdC1DTlJTPC9hZmZpbGlhdGlvbj4NCgkJPC9jb250cmlidXRvcj4NCgkJPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iU3VwZXJ2aXNvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPlppZWRvcm4sIEZyYXVrZTwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5GcmF1a2U8L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPlppZWRvcm48L2ZhbWlseU5hbWU+DQoJCQk8bmFtZUlkZW50aWZpZXIgbmFtZUlkZW50aWZpZXJTY2hlbWU9Ik9SQ0lEIiBzY2hlbWVVUkk9Imh0dHA6Ly9vcmNpZC5vcmciPjAwMDAtMDAwMi0xMTQzLTc4MVg8L25hbWVJZGVudGlmaWVyPg0KCQkJPGFmZmlsaWF0aW9uPlRJQjwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJPC9jb250cmlidXRvcnM+DQoJPGxhbmd1YWdlPmVuZzwvbGFuZ3VhZ2U+DQoJPHJlc291cmNlVHlwZSByZXNvdXJjZVR5cGVHZW5lcmFsPSJUZXh0Ij5Eb2N1bWVudGF0aW9uPC9yZXNvdXJjZVR5cGU+DQoJPHJlbGF0ZWRJZGVudGlmaWVycz4NCgkJPHJlbGF0ZWRJZGVudGlmaWVyIHJlbGF0ZWRJZGVudGlmaWVyVHlwZT0iRE9JIiByZWxhdGlvblR5cGU9IkRvY3VtZW50cyI+MTAuNTQzOC8wMDEzPC9yZWxhdGVkSWRlbnRpZmllcj4NCgkJPHJlbGF0ZWRJZGVudGlmaWVyIHJlbGF0ZWRJZGVudGlmaWVyVHlwZT0iRE9JIiByZWxhdGlvblR5cGU9IklzTmV3VmVyc2lvbk9mIj4xMC41NDM4LzAwMTA8L3JlbGF0ZWRJZGVudGlmaWVyPg0KCTwvcmVsYXRlZElkZW50aWZpZXJzPg0KCTxzaXplcz4NCgkJPHNpemU+NDUgcGFnZXM8L3NpemU+DQoJPC9zaXplcz4NCgk8Zm9ybWF0cz4NCgkJPGZvcm1hdD5hcHBsaWNhdGlvbi9wZGY8L2Zvcm1hdD4NCgk8L2Zvcm1hdHM+DQoJPHZlcnNpb24+NC4wPC92ZXJzaW9uPg0KCTxkZXNjcmlwdGlvbnM+DQoJCTxkZXNjcmlwdGlvbiBkZXNjcmlwdGlvblR5cGU9IlRhYmxlT2ZDb250ZW50cyI+MSBJbnRyb2R1Y3Rpb248YnIvPg0KMS4xIFRoZSBEYXRhQ2l0ZSBDb25zb3J0aXVtPGJyLz4NCjEuMiBEYXRhQ2l0ZSBDb21tdW5pdHkgUGFydGljaXBhdGlvbjxici8+DQoxLjMgVGhlIE1ldGFkYXRhIFNjaGVtYTxici8+DQoxLjQgVmVyc2lvbiA0LjAgVXBkYXRlPGJyLz4NCjIgRGF0YUNpdGUgTWV0YWRhdGEgUHJvcGVydGllczxici8+DQoyLjEgT3ZlcnZpZXc8YnIvPg0KMi4yIENpdGF0aW9uPGJyLz4NCjIuMyBEYXRhQ2l0ZSBQcm9wZXJ0aWVzPGJyLz4NCjMgWE1MIEV4YW1wbGU8YnIvPg0KNCBYTUwgU2NoZW1hPGJyLz4NCjUgT3RoZXIgRGF0YUNpdGUgU2VydmljZXM8YnIvPg0KQXBwZW5kaWNlczxici8+DQpBcHBlbmRpeCAxOiBDb250cm9sbGVkIExpc3QgRGVmaW5pdGlvbnM8YnIvPg0KQXBwZW5kaXggMjogRWFybGllciBWZXJzaW9uIFVwZGF0ZSBOb3RlczwvZGVzY3JpcHRpb24+DQoJPC9kZXNjcmlwdGlvbnM+DQo8L3Jlc291cmNlPg0K"
    },
    "relationships":{
      "data-center":{
        "data":{
          "id":"datacite.datacite",
          "type":"data-centers"
        }
      },
      "member":{
        "data":{
          "id":"datacite",
          "type":"members"
        }
      },
      "resource-type":{
        "data":{
          "id":"text",
          "type":"resource-types"
        }
      }
    }
  }
}
```
[block:callout]
{
  "type": "success",
  "body": "The REST API includes the most important attributes as JSON elements, plus the complete DOI Metadata record in XML serialized using Base64 (you can find it under the xml: element).",
  "title": "What's in the response ?"
}
[/block]
The response will be the metadata of the record of the requested DOI in JSON format. Let's add the `-i` flag to include headers:


```shell
$ curl https://api.datacite.org/works/10.5438/0012 -i
HTTP/2 200 

date: Fri, 28 Sep 2018 11:30:02 GMT
content-type: application/json; charset=utf-8
status: 200 OK
x-anonymous-consumer: true
cache-control: max-age=0, private, must-revalidate
vary: Accept-Encoding
etag: W/"94a7e97149e115d9f5cd9c6d2b9f60e2"
x-runtime: 0.287494
x-request-id: 90444ed8-99b9-4cd1-bba7-d71dc0847063
x-powered-by: Phusion Passenger 5.3.4
server: nginx/1.14.0 + Phusion Passenger 5.3.4
access-control-allow-origin: *
access-control-allow-methods: GET, POST, PUT, DELETE, OPTIONS
access-control-allow-headers: DNT,X-CustomHeader,Keep-Alive,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type,Content-Range,Range,Authorization
access-control-expose-headers: DNT,X-CustomHeader,Keep-Alive,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type,Content-Range,Range,Authorization

```

There are a few interesting bits in the response headers. As expected, the Content-Type is `application/json`. The response `200 OK` indicates the operation was successful. 

## Retrieving Metadata records

Almost any meaningful use of the DataCite REST API will involve some level of record retrieval. The responses from each of your requests fall into two basic categories: Singletons (i.e., a single record) and Lists (i.e., a list of records).


**Singletons** are single results. Retrieving metadata for a specific identifier (e.g. DOI, ORCID) typically returns a singleton result.



For example, retrieving the metadata record for the DOI `10.5438/0012` can be done as follows:

```shell
# GET /works
$ curl https://api.datacite.org/works/10.5438/0012
```

Or if you are using `Python` you can retrieve it this way:


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
The response would look like this:

```json
{
  "data":{
    "id":"https://doi.org/10.5438/0012",
    "type":"works",
    "attributes":{
      "doi":"10.5438/0012",
      "identifier":"https://doi.org/10.5438/0012",
      "url":null,
      "author":[
        {
          "literal":"DataCite Metadata Working Group"
        }
      ],
      "title":"DataCite Metadata Schema Documentation for the Publication and Citation of Research Data v4.0",
      "container-title":"DataCite e.V.",
      "description":"1 Introduction\n1.1 The DataCite Consortium\n1.2 DataCite Community Participation\n1.3 The Metadata Schema\n1.4 Version 4.0 Update\n2 DataCite Metadata Properties\n2.1 Overview\n2.2 Citation\n2.3 DataCite Properties\n3 XML Example\n4 XML Schema\n5 Other DataCite Services\nAppendices\nAppendix 1: Controlled List Definitions\nAppendix 2: Earlier Version Update Notes",
      "resource-type-subtype":"Documentation",
      "data-center-id":"datacite.datacite",
      "member-id":"datacite",
      "resource-type-id":"text",
      "version":"4.0",
      "license":null,
      "schema-version":"4",
      "results":[
        {
          "id":"Documents",
          "title":"Documents",
          "count":1
        },
        {
          "id":"IsNewVersionOf",
          "title":"Is new version of",
          "count":1
        }
      ],
      "related-identifiers":[
        {
          "relation-type-id":"Documents",
          "related-identifier":"https://doi.org/10.5438/0013"
        },
        {
          "relation-type-id":"IsNewVersionOf",
          "related-identifier":"https://doi.org/10.5438/0010"
        }
      ],
      "published":"2016",
      "registered":"2016-09-19T21:53:56Z",
      "checked":null,
      "updated":"2016-09-19T22:16:45Z",
      "media":null,
      "xml":"PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NCjxyZXNvdXJjZSB4bWxucz0iaHR0cDovL2RhdGFjaXRlLm9yZy9zY2hlbWEva2VybmVsLTQiIHhtbG5zOnhzaT0iaHR0cDovL3d3dy53My5vcmcvMjAwMS9YTUxTY2hlbWEtaW5zdGFuY2UiIHhzaTpzY2hlbWFMb2NhdGlvbj0iaHR0cDovL2RhdGFjaXRlLm9yZy9zY2hlbWEva2VybmVsLTQgaHR0cDovL3NjaGVtYS5kYXRhY2l0ZS5vcmcvbWV0YS9rZXJuZWwtNC9tZXRhZGF0YS54c2QiPg0KCTxpZGVudGlmaWVyIGlkZW50aWZpZXJUeXBlPSJET0kiPjEwLjU0MzgvMDAxMjwvaWRlbnRpZmllcj4NCgk8Y3JlYXRvcnM+DQoJCTxjcmVhdG9yPg0KCQkJPGNyZWF0b3JOYW1lPkRhdGFDaXRlIE1ldGFkYXRhIFdvcmtpbmcgR3JvdXA8L2NyZWF0b3JOYW1lPg0KCQk8L2NyZWF0b3I+DQoJPC9jcmVhdG9ycz4NCgk8dGl0bGVzPg0KCQk8dGl0bGU+RGF0YUNpdGUgTWV0YWRhdGEgU2NoZW1hIERvY3VtZW50YXRpb24gZm9yIHRoZSBQdWJsaWNhdGlvbiBhbmQgQ2l0YXRpb24gb2YgUmVzZWFyY2ggRGF0YSB2NC4wPC90aXRsZT4NCgk8L3RpdGxlcz4NCgk8cHVibGlzaGVyPkRhdGFDaXRlIGUuVi48L3B1Ymxpc2hlcj4NCgk8cHVibGljYXRpb25ZZWFyPjIwMTY8L3B1YmxpY2F0aW9uWWVhcj4NCgk8Y29udHJpYnV0b3JzPg0KCQk8Y29udHJpYnV0b3IgY29udHJpYnV0b3JUeXBlPSJQcm9qZWN0TGVhZGVyIj4NCgkJCTxjb250cmlidXRvck5hbWU+U3RhcnIsIEpvYW48L2NvbnRyaWJ1dG9yTmFtZT4NCgkJCTxnaXZlbk5hbWU+Sm9hbjwvZ2l2ZW5OYW1lPg0KCQkJPGZhbWlseU5hbWU+U3RhcnI8L2ZhbWlseU5hbWU+DQoJCQk8bmFtZUlkZW50aWZpZXIgbmFtZUlkZW50aWZpZXJTY2hlbWU9Ik9SQ0lEIiBzY2hlbWVVUkk9Imh0dHA6Ly9vcmNpZC5vcmciPjAwMDAtMDAwMi03Mjg1LTAyN1g8L25hbWVJZGVudGlmaWVyPg0KCQkJPGFmZmlsaWF0aW9uPkNhbGlmb3JuaWEgRGlnaXRhbCBMaWJyYXJ5PC9hZmZpbGlhdGlvbj4NCgkJPC9jb250cmlidXRvcj4NCgkJPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iUHJvamVjdExlYWRlciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPlNtYWVsZSwgTWFkZWxlaW5lIGRlPC9jb250cmlidXRvck5hbWU+DQoJCQk8Z2l2ZW5OYW1lPk1hZGVsZWluZSBkZTwvZ2l2ZW5OYW1lPg0KCQkJPGZhbWlseU5hbWU+U21hZWxlPC9mYW1pbHlOYW1lPg0KCQkJPGFmZmlsaWF0aW9uPlRVIERlbGZ0PC9hZmZpbGlhdGlvbj4NCgkJPC9jb250cmlidXRvcj4NCgkJPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iRWRpdG9yIj4NCgkJCTxjb250cmlidXRvck5hbWU+QXNodG9uLCBKYW48L2NvbnRyaWJ1dG9yTmFtZT4NCgkJCTxnaXZlbk5hbWU+SmFuPC9naXZlbk5hbWU+DQoJCQk8ZmFtaWx5TmFtZT5Bc2h0b248L2ZhbWlseU5hbWU+DQoJCQk8YWZmaWxpYXRpb24+QnJpdGlzaCBMaWJyYXJ5PC9hZmZpbGlhdGlvbj4NCgkJPC9jb250cmlidXRvcj4NCgkJPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iRWRpdG9yIj4NCgkJCTxjb250cmlidXRvck5hbWU+QmFydG9uLCBBbXk8L2NvbnRyaWJ1dG9yTmFtZT4NCgkJCTxnaXZlbk5hbWU+QW15PC9naXZlbk5hbWU+DQoJCQk8ZmFtaWx5TmFtZT5CYXJ0b248L2ZhbWlseU5hbWU+DQoJCQk8YWZmaWxpYXRpb24+UHVyZHVlIFVuaXZlcnNpdHkgTGlicmFyeTwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPkJyYWRmb3JkLCBUaW5hPC9jb250cmlidXRvck5hbWU+DQoJCQk8Z2l2ZW5OYW1lPlRpbmE8L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPkJyYWRmb3JkPC9mYW1pbHlOYW1lPg0KCQkJPGFmZmlsaWF0aW9uPk5SQy9DSVNUSTwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPkNpb2xla+KAkEZpZ2llbCwgQW5uZTwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5Bbm5lPC9naXZlbk5hbWU+DQoJCQk8ZmFtaWx5TmFtZT5DaW9sZWstRmlnaWVsPC9mYW1pbHlOYW1lPg0KCQkJPGFmZmlsaWF0aW9uPkluaXN04oCQQ05SUzwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPkRpZXRpa2VyLCBTdGVmYW5pZTwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5TdGVmYW5pZTwvZ2l2ZW5OYW1lPg0KCQkJPGZhbWlseU5hbWU+RGlldGlrZXI8L2ZhbWlseU5hbWU+DQoJCQk8YWZmaWxpYXRpb24+RVRIIFrDvHJpY2g8L2FmZmlsaWF0aW9uPg0KCQk8L2NvbnRyaWJ1dG9yPg0KCQk8Y29udHJpYnV0b3IgY29udHJpYnV0b3JUeXBlPSJFZGl0b3IiPg0KCQkJPGNvbnRyaWJ1dG9yTmFtZT5FbGxpb3R0LCBKYW5uZWFuPC9jb250cmlidXRvck5hbWU+DQoJCQk8Z2l2ZW5OYW1lPkphbm5lYW48L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPkVsbGlvdDwvZmFtaWx5TmFtZT4NCgkJCTxhZmZpbGlhdGlvbj5ET0UvT1NUSTwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPkdlbmF0LCBCZXJyaXQ8L2NvbnRyaWJ1dG9yTmFtZT4NCgkJCTxnaXZlbk5hbWU+QmVycml0PC9naXZlbk5hbWU+DQoJCQk8ZmFtaWx5TmFtZT5HZW5hdDwvZmFtaWx5TmFtZT4NCgkJCTxhZmZpbGlhdGlvbj5USUI8L2FmZmlsaWF0aW9uPg0KCQk8L2NvbnRyaWJ1dG9yPg0KCQk8Y29udHJpYnV0b3IgY29udHJpYnV0b3JUeXBlPSJFZGl0b3IiPg0KCQkJPGNvbnRyaWJ1dG9yTmFtZT5IYXJ6ZW5ldHRlciwgS2Fyb2xpbmU8L2NvbnRyaWJ1dG9yTmFtZT4NCgkJCTxnaXZlbk5hbWU+S2Fyb2xpbmU8L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPkhhcnplbmV0dGVyPC9mYW1pbHlOYW1lPg0KCQkJPGFmZmlsaWF0aW9uPkdFU0lTPC9hZmZpbGlhdGlvbj4NCgkJPC9jb250cmlidXRvcj4NCgkJPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iRWRpdG9yIj4NCgkJCTxjb250cmlidXRvck5hbWU+SGlyc2NobWFubiwgQmFyYmFyYTwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5CYXJiYXJhPC9naXZlbk5hbWU+DQoJCQk8ZmFtaWx5TmFtZT5IaXJzY2htYW5uPC9mYW1pbHlOYW1lPg0KCQkJPG5hbWVJZGVudGlmaWVyIG5hbWVJZGVudGlmaWVyU2NoZW1lPSJPUkNJRCIgc2NoZW1lVVJJPSJodHRwOi8vb3JjaWQub3JnIj4wMDAwLTAwMDMtMDI4OS0wMzQ1PC9uYW1lSWRlbnRpZmllcj4NCgkJCTxhZmZpbGlhdGlvbj5FVEggWsO8cmljaDwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPkpha29ic3NvbiwgU3RlZmFuPC9jb250cmlidXRvck5hbWU+DQoJCQk8Z2l2ZW5OYW1lPlN0ZWZhbjwvZ2l2ZW5OYW1lPg0KCQkJPGZhbWlseU5hbWU+SmFrb2Jzc29uPC9mYW1pbHlOYW1lPg0KCQkJPGFmZmlsaWF0aW9uPlNORDwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPk1haWxsb3V4LCBKZWFu4oCQWXZlczwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5KZWFuLVl2ZXM8L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPk1haWxsb3V4PC9mYW1pbHlOYW1lPg0KCQkJPGFmZmlsaWF0aW9uPk5SQy9DSVNUSTwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCTxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPk5ld2JvbGQsIEVsaXphYmV0aDwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5FbGl6YWJldGg8L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPk5ld2JvbGQ8L2ZhbWlseU5hbWU+DQoJCQk8bmFtZUlkZW50aWZpZXIgbmFtZUlkZW50aWZpZXJTY2hlbWU9Ik9SQ0lEIiBzY2hlbWVVUkk9Imh0dHA6Ly9vcmNpZC5vcmciPjAwMDAtMDAwMi04MjU1LTkwMTM8L25hbWVJZGVudGlmaWVyPg0KCQkJPGFmZmlsaWF0aW9uPkJyaXRpc2ggTGlicmFyeTwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJCQkJPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iRWRpdG9yIj4NCgkJCTxjb250cmlidXRvck5hbWU+TmllbHNlbiwgTGFycyBIb2xtIDwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5MYXJzIEhvbG08L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPk5pZWxzZW48L2ZhbWlseU5hbWU+DQoJCQk8bmFtZUlkZW50aWZpZXIgbmFtZUlkZW50aWZpZXJTY2hlbWU9Ik9SQ0lEIiBzY2hlbWVVUkk9Imh0dHA6Ly9vcmNpZC5vcmciPjAwMDAtMDAwMS04MTM1LTM0ODk8L25hbWVJZGVudGlmaWVyPg0KCQkJPGFmZmlsaWF0aW9uPkNFUk48L2FmZmlsaWF0aW9uPg0KCQk8L2NvbnRyaWJ1dG9yPg0KCQk8Y29udHJpYnV0b3IgY29udHJpYnV0b3JUeXBlPSJFZGl0b3IiPg0KCQkJPGNvbnRyaWJ1dG9yTmFtZT5ZYWhpYSwgTW9oYW1lZDwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5Nb2hhbWVkPC9naXZlbk5hbWU+DQoJCQk8ZmFtaWx5TmFtZT5ZYWhpYTwvZmFtaWx5TmFtZT4NCgkJCTxhZmZpbGlhdGlvbj5JbmlzdC1DTlJTPC9hZmZpbGlhdGlvbj4NCgkJPC9jb250cmlidXRvcj4NCgkJPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iU3VwZXJ2aXNvciI+DQoJCQk8Y29udHJpYnV0b3JOYW1lPlppZWRvcm4sIEZyYXVrZTwvY29udHJpYnV0b3JOYW1lPg0KCQkJPGdpdmVuTmFtZT5GcmF1a2U8L2dpdmVuTmFtZT4NCgkJCTxmYW1pbHlOYW1lPlppZWRvcm48L2ZhbWlseU5hbWU+DQoJCQk8bmFtZUlkZW50aWZpZXIgbmFtZUlkZW50aWZpZXJTY2hlbWU9Ik9SQ0lEIiBzY2hlbWVVUkk9Imh0dHA6Ly9vcmNpZC5vcmciPjAwMDAtMDAwMi0xMTQzLTc4MVg8L25hbWVJZGVudGlmaWVyPg0KCQkJPGFmZmlsaWF0aW9uPlRJQjwvYWZmaWxpYXRpb24+DQoJCTwvY29udHJpYnV0b3I+DQoJPC9jb250cmlidXRvcnM+DQoJPGxhbmd1YWdlPmVuZzwvbGFuZ3VhZ2U+DQoJPHJlc291cmNlVHlwZSByZXNvdXJjZVR5cGVHZW5lcmFsPSJUZXh0Ij5Eb2N1bWVudGF0aW9uPC9yZXNvdXJjZVR5cGU+DQoJPHJlbGF0ZWRJZGVudGlmaWVycz4NCgkJPHJlbGF0ZWRJZGVudGlmaWVyIHJlbGF0ZWRJZGVudGlmaWVyVHlwZT0iRE9JIiByZWxhdGlvblR5cGU9IkRvY3VtZW50cyI+MTAuNTQzOC8wMDEzPC9yZWxhdGVkSWRlbnRpZmllcj4NCgkJPHJlbGF0ZWRJZGVudGlmaWVyIHJlbGF0ZWRJZGVudGlmaWVyVHlwZT0iRE9JIiByZWxhdGlvblR5cGU9IklzTmV3VmVyc2lvbk9mIj4xMC41NDM4LzAwMTA8L3JlbGF0ZWRJZGVudGlmaWVyPg0KCTwvcmVsYXRlZElkZW50aWZpZXJzPg0KCTxzaXplcz4NCgkJPHNpemU+NDUgcGFnZXM8L3NpemU+DQoJPC9zaXplcz4NCgk8Zm9ybWF0cz4NCgkJPGZvcm1hdD5hcHBsaWNhdGlvbi9wZGY8L2Zvcm1hdD4NCgk8L2Zvcm1hdHM+DQoJPHZlcnNpb24+NC4wPC92ZXJzaW9uPg0KCTxkZXNjcmlwdGlvbnM+DQoJCTxkZXNjcmlwdGlvbiBkZXNjcmlwdGlvblR5cGU9IlRhYmxlT2ZDb250ZW50cyI+MSBJbnRyb2R1Y3Rpb248YnIvPg0KMS4xIFRoZSBEYXRhQ2l0ZSBDb25zb3J0aXVtPGJyLz4NCjEuMiBEYXRhQ2l0ZSBDb21tdW5pdHkgUGFydGljaXBhdGlvbjxici8+DQoxLjMgVGhlIE1ldGFkYXRhIFNjaGVtYTxici8+DQoxLjQgVmVyc2lvbiA0LjAgVXBkYXRlPGJyLz4NCjIgRGF0YUNpdGUgTWV0YWRhdGEgUHJvcGVydGllczxici8+DQoyLjEgT3ZlcnZpZXc8YnIvPg0KMi4yIENpdGF0aW9uPGJyLz4NCjIuMyBEYXRhQ2l0ZSBQcm9wZXJ0aWVzPGJyLz4NCjMgWE1MIEV4YW1wbGU8YnIvPg0KNCBYTUwgU2NoZW1hPGJyLz4NCjUgT3RoZXIgRGF0YUNpdGUgU2VydmljZXM8YnIvPg0KQXBwZW5kaWNlczxici8+DQpBcHBlbmRpeCAxOiBDb250cm9sbGVkIExpc3QgRGVmaW5pdGlvbnM8YnIvPg0KQXBwZW5kaXggMjogRWFybGllciBWZXJzaW9uIFVwZGF0ZSBOb3RlczwvZGVzY3JpcHRpb24+DQoJPC9kZXNjcmlwdGlvbnM+DQo8L3Jlc291cmNlPg0K"
    },
    "relationships":{
      "data-center":{
        "data":{
          "id":"datacite.datacite",
          "type":"data-centers"
        }
      },
      "member":{
        "data":{
          "id":"datacite",
          "type":"members"
        }
      },
      "resource-type":{
        "data":{
          "id":"text",
          "type":"resource-types"
        }
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

For example, retrieving the metadata records for all DOIs can be done as follows:

```shell
# GET /works
$ curl https://api.datacite.org/works/
```

```json
{
  "data":[
    {
      "id":"https://doi.org/10.13140/rg.2.2.26382.41280",
      "type":"works",
      "attributes":{
        "doi":"10.13140/rg.2.2.26382.41280",
        "identifier":"https://doi.org/10.13140/rg.2.2.26382.41280",
        "url":"http://rgdoi.net/10.13140/RG.2.2.26382.41280",
        "author":[
          {
            "literal":"Myo AUNG Myanmar"
          },
          {
            "literal":"NATHAN THOMPSON"
          },
          {
            "literal":"ROLANDO GOMEZ"
          }
        ],
        "title":"UNITED NATIONS HUMAN RIGHTS COUNCIL AND MYANMAR 2018",
        "container-title":"Unpublished",
        "description":null,
        "resource-type-subtype":"Presentation",
        "data-center-id":"rg.rg",
        "member-id":"rg",
        "resource-type-id":"text",
        "version":null,
        "license":null,
        "schema-version":"4",
        "results":[],
        "related-identifiers":[],
        "published":"2018",
        "registered":"2018-09-28T05:07:37Z",
        "checked":null,
        "updated":"2018-09-28T05:07:37Z",
        "media":null,
        "xml":"PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiIHN0YW5kYWxvbmU9InllcyI/Pgo8cmVzb3VyY2UgeG1sbnM9Imh0dHA6Ly9kYXRhY2l0ZS5vcmcvc2NoZW1hL2tlcm5lbC00IiB4bWxuczp4c2k9Imh0dHA6Ly93d3cudzMub3JnLzIwMDEvWE1MU2NoZW1hLWluc3RhbmNlIiB4c2k6c2NoZW1hTG9jYXRpb249Imh0dHA6Ly9kYXRhY2l0ZS5vcmcvc2NoZW1hL2tlcm5lbC00IGh0dHA6Ly9zY2hlbWEuZGF0YWNpdGUub3JnL21ldGEva2VybmVsLTQvbWV0YWRhdGEueHNkIj4KICA8aWRlbnRpZmllciBpZGVudGlmaWVyVHlwZT0iRE9JIj4xMC4xMzE0MC9SRy4yLjIuMjYzODIuNDEyODA8L2lkZW50aWZpZXI+CiAgPGNyZWF0b3JzPgogICAgPGNyZWF0b3I+CiAgICAgIDxjcmVhdG9yTmFtZT5NeW8gQVVORyBNeWFubWFyPC9jcmVhdG9yTmFtZT4KICAgIDwvY3JlYXRvcj4KICAgIDxjcmVhdG9yPgogICAgICA8Y3JlYXRvck5hbWU+TkFUSEFOIFRIT01QU09OPC9jcmVhdG9yTmFtZT4KICAgIDwvY3JlYXRvcj4KICAgIDxjcmVhdG9yPgogICAgICA8Y3JlYXRvck5hbWU+Uk9MQU5ETyBHT01FWjwvY3JlYXRvck5hbWU+CiAgICA8L2NyZWF0b3I+CiAgPC9jcmVhdG9ycz4KICA8dGl0bGVzPgogICAgPHRpdGxlPlVOSVRFRCBOQVRJT05TIEhVTUFOIFJJR0hUUyBDT1VOQ0lMIEFORCBNWUFOTUFSIDIwMTg8L3RpdGxlPgogIDwvdGl0bGVzPgogIDxwdWJsaXNoZXI+VW5wdWJsaXNoZWQ8L3B1Ymxpc2hlcj4KICA8cHVibGljYXRpb25ZZWFyPjIwMTg8L3B1YmxpY2F0aW9uWWVhcj4KICA8cmVzb3VyY2VUeXBlIHJlc291cmNlVHlwZUdlbmVyYWw9IlRleHQiPlByZXNlbnRhdGlvbjwvcmVzb3VyY2VUeXBlPgogIDxsYW5ndWFnZT5lbjwvbGFuZ3VhZ2U+CjwvcmVzb3VyY2U+"
      },
      "relationships":{
        "data-center":{
          "data":{
            "id":"rg.rg",
            "type":"data-centers"
          }
        },
        "member":{
          "data":{
            "id":"rg",
            "type":"members"
          }
        },
        "resource-type":{
          "data":{
            "id":"text",
            "type":"resource-types"
          }
        }
      }
    },
    {
      "id":"https://doi.org/10.26193/1nlofy",
      "type":"works",
      "attributes":{
        "doi":"10.26193/1nlofy",
        "identifier":"https://doi.org/10.26193/1nlofy",
        "url":"https://dataverse.ada.edu.au/citation?persistentId=doi:10.26193/1NLOFY",
        "author":[
          {
            "literal":"Roy Morgan"
          }
        ],
        "title":"Australian Gallup Polls, Survey 175, February 12, 1965",
        "container-title":"ADA Dataverse",
        "description":"Themes-Names: Motor cars: insurance / Dental health: fluoride / International Relations: Australia's best friend / international relationships: influential nations / Malaysia: troops in / national anthem / nuclear energy: bans and test of bombs / politicians: wages, determination of / schools: scholarships / Senate: abolition; functions / United Nations: election of members. Background Variables age / sex / economic classification / occupation of head of household / religion/ vote at last Federal election / present voting intention / car ownership / country of birth / numbers of voters in household.",
        "resource-type-subtype":null,
        "data-center-id":"ands.centre87",
        "member-id":"ands",
        "resource-type-id":"dataset",
        "version":null,
        "license":null,
        "schema-version":"3",
        "results":[],
        "related-identifiers":[],
        "published":"2018",
        "registered":"2018-09-28T05:04:20Z",
        "checked":null,
        "updated":"2018-09-28T05:04:20Z",
        "media":null,
        "xml":"PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4KPHJlc291cmNlIHhtbG5zPSJodHRwOi8vZGF0YWNpdGUub3JnL3NjaGVtYS9rZXJuZWwtMyIgeG1sbnM6eHNpPSJodHRwOi8vd3d3LnczLm9yZy8yMDAxL1hNTFNjaGVtYS1pbnN0YW5jZSIgeHNpOnNjaGVtYUxvY2F0aW9uPSJodHRwOi8vZGF0YWNpdGUub3JnL3NjaGVtYS9rZXJuZWwtMyBodHRwOi8vc2NoZW1hLmRhdGFjaXRlLm9yZy9tZXRhL2tlcm5lbC0zL21ldGFkYXRhLnhzZCI+CiAgPGlkZW50aWZpZXIgaWRlbnRpZmllclR5cGU9IkRPSSI+MTAuMjYxOTMvMU5MT0ZZPC9pZGVudGlmaWVyPgogIDxjcmVhdG9ycz4KICAgIDxjcmVhdG9yPgogICAgICA8Y3JlYXRvck5hbWU+Um95IE1vcmdhbjwvY3JlYXRvck5hbWU+CiAgICA8L2NyZWF0b3I+CiAgPC9jcmVhdG9ycz4KICA8dGl0bGVzPgogICAgPHRpdGxlPkF1c3RyYWxpYW4gR2FsbHVwIFBvbGxzLCBTdXJ2ZXkgMTc1LCBGZWJydWFyeSAxMiwgMTk2NTwvdGl0bGU+CiAgPC90aXRsZXM+CiAgPHB1Ymxpc2hlcj5BREEgRGF0YXZlcnNlPC9wdWJsaXNoZXI+CiAgPHB1YmxpY2F0aW9uWWVhcj4yMDE4PC9wdWJsaWNhdGlvblllYXI+CiAgPHJlc291cmNlVHlwZSByZXNvdXJjZVR5cGVHZW5lcmFsPSJEYXRhc2V0Ii8+CiAgPGRlc2NyaXB0aW9ucz4KICAgIDxkZXNjcmlwdGlvbiBkZXNjcmlwdGlvblR5cGU9IkFic3RyYWN0Ij5UaGVtZXMtTmFtZXM6IE1vdG9yIGNhcnM6IGluc3VyYW5jZSAvIERlbnRhbCBoZWFsdGg6IGZsdW9yaWRlIC8gSW50ZXJuYXRpb25hbCBSZWxhdGlvbnM6IEF1c3RyYWxpYSdzIGJlc3QgZnJpZW5kIC8gaW50ZXJuYXRpb25hbCByZWxhdGlvbnNoaXBzOiBpbmZsdWVudGlhbCBuYXRpb25zIC8gTWFsYXlzaWE6IHRyb29wcyBpbiAvIG5hdGlvbmFsIGFudGhlbSAvIG51Y2xlYXIgZW5lcmd5OiBiYW5zIGFuZCB0ZXN0IG9mIGJvbWJzIC8gcG9saXRpY2lhbnM6IHdhZ2VzLCBkZXRlcm1pbmF0aW9uIG9mIC8gc2Nob29sczogc2Nob2xhcnNoaXBzIC8gU2VuYXRlOiBhYm9saXRpb247IGZ1bmN0aW9ucyAvIFVuaXRlZCBOYXRpb25zOiBlbGVjdGlvbiBvZiBtZW1iZXJzLiBCYWNrZ3JvdW5kIFZhcmlhYmxlcyBhZ2UgLyBzZXggLyBlY29ub21pYyBjbGFzc2lmaWNhdGlvbiAvIG9jY3VwYXRpb24gb2YgaGVhZCBvZiBob3VzZWhvbGQgLyByZWxpZ2lvbi8gdm90ZSBhdCBsYXN0IEZlZGVyYWwgZWxlY3Rpb24gLyBwcmVzZW50IHZvdGluZyBpbnRlbnRpb24gLyBjYXIgb3duZXJzaGlwIC8gY291bnRyeSBvZiBiaXJ0aCAvIG51bWJlcnMgb2Ygdm90ZXJzIGluIGhvdXNlaG9sZC48L2Rlc2NyaXB0aW9uPgogIDwvZGVzY3JpcHRpb25zPgogIDxjb250cmlidXRvcnM+CiAgICA8Y29udHJpYnV0b3IgY29udHJpYnV0b3JUeXBlPSJDb250YWN0UGVyc29uIj4KICAgICAgPGNvbnRyaWJ1dG9yTmFtZT5BdXN0cmFsaWFuIERhdGEgQXJjaGl2ZTwvY29udHJpYnV0b3JOYW1lPgogICAgICA8YWZmaWxpYXRpb24+QXVzdHJhbGlhbiBOYXRpb25hbCBVbml2ZXJzaXR5PC9hZmZpbGlhdGlvbj4KICAgIDwvY29udHJpYnV0b3I+CiAgPC9jb250cmlidXRvcnM+CjwvcmVzb3VyY2U+"
      },
      "relationships":{
        "data-center":{
          "data":{
            "id":"ands.centre87",
            "type":"data-centers"
          }
        },
        "member":{
          "data":{
            "id":"ands",
            "type":"members"
          }
        },
        "resource-type":{
          "data":{
            "id":"dataset",
            "type":"resource-types"
          }
        }
      }
    },
  ],
  "meta":{
    "resource-types":[
      {
        "id":"dataset",
        "title":"Dataset",
        "count":5069357
      },
      {
        "id":"text",
        "title":"Text",
        "count":3488685
      },
      {
        "id":"image",
        "title":"Image",
        "count":1083575
      },
      {
        "id":"physical-object",
        "title":"Physical object",
        "count":737141
      },
      {
        "id":"collection",
        "title":"Collection",
        "count":532704
      },
      {
        "id":"other",
        "title":"Other",
        "count":426670
      },
      {
        "id":"workflow",
        "title":"Workflow",
        "count":70877
      },
      {
        "id":"software",
        "title":"Software",
        "count":69373
      },
      {
        "id":"audiovisual",
        "title":"Audiovisual",
        "count":56140
      },
      {
        "id":"interactive-resource",
        "title":"Interactive resource",
        "count":35304
      },
      {
        "id":"event",
        "title":"Event",
        "count":8222
      },
      {
        "id":"model",
        "title":"Model",
        "count":3903
      },
      {
        "id":"sound",
        "title":"Sound",
        "count":1731
      },
      {
        "id":"film",
        "title":"Film",
        "count":1605
      },
      {
        "id":"data-paper",
        "title":"Data paper",
        "count":78
      }
    ],
  }
}

```

The response shows some interesting things. First, let us clarify that we have truncated the response for the benefit of space to show only two records in this list and to show only the resource type meta counts. Normally, results are returned 25 at a time. The List is sorted by DOI deposit date (which you can see in the `data:` object). Facet counts are returned via the `meta:` object. Facet counts give counts per field value for an entire result set.

There are many other resources in the API (see table below) and all of them can be retrieved in the same fashion. Major resource components supported by the DataCite API are (in alphabetical order) presented below and can be used alone like this:

| Resource                 | Description                       |
|:-------------------------|:----------------------------------|
| `/members`               | returns a list of all DataCite members |
| `/data-centers`            | returns a list of all DataCite data centers (clients) |
| `/works`                 | returns a list of all works (datasets, text documents, etc.), 25 per page

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

The response is a list of all the `works` that contain the term *climate* in their metadata excluding those that have the term *change*.

Additional parameters can be used to query, filter and control the results returned by the DataCite API. They can be passed as normal URI parameters or as JSON in the body of the request.

| Parameter                    | Description                 |
|:-----------------------------|:----------------------------|
| `query`                      | limited [DisMax](https://wiki.apache.org/solr/DisMax) query terms |
| `page[size]`              | results per per page |
| `page[number]`        | page number |
| `sort`                       | sort results by a certain field |
| `order`                      | set the sort order to `asc` or `desc` |
| `include`                    | side-load associations |
| `sample`                    | random sample |
| `sample-group`          | specifies the grouping for a random sample |

For example, to list one single work using the previously specified query, you would add a `page[size]` parameter with a value of 1, like so:

```shell
#GET works?query=
$ curl https://api.datacite.org/works?query=climate+-change&page[size]=1
```

## Filtering List Responses

Finally, the API supports filters that allow you to narrow queries. All filter results are **lists**. For example, if you wish to filter results by their *data center* and this data center is `cdl.dryad` (Dryad Digital Repository), you would do the following:

```
curl https://api.datacite.org/works?data-center-id=cdl.dryad
```

 The following filters are supported:

| Filter     | Possible values | Description|
|:-----------|:----------------|:-----------|
| `member-id` | `{member-id}` | metadata associated with a specific DataCite member |
| `data-center-id` | `{data-center-id}` | metadata associated with a specific DataCite data center |
| `resource-type-id` | `{resource-type-id}` | metadata for a specific resourceTypeGeneral |
| `person-id` | `{person-id}` | metadata associated with a specific person's ORCID iD |
| `from-created-date` | `{date}` | metadata where deposited date is since (inclusive) `{date}` |
| `until-created-date` | `{date}` | metadata where deposited date is before (inclusive)  `{date}` |
| `from-update-date` | `{date}` | metadata where updated date is since (inclusive) `{date}` |
| `until-update-date` | `{date}` | metadata where updated date is before (inclusive)  `{date}` |
| `registered` | `{date}` | metadata where date of DOI registration is `{date}` |
| `year` | `{year}` | metadata where publication year of the resource is `{year}` |
| `schema-version` | `{schema-version}` | metadata where schema version of the deposited metadata is `{schema-version}` |

## Sample

Being able to select random results is useful for both testing and sampling. You can use the `sample` parameter to retrieve a set of random results. So, for example, the following would select 10 random works from among all DataCite records:

```
https://api.datacite.org/works?sample=10
```

Note that when you use the sample parameter, the `page[size]` and `page[number]` parameters are ignored.

### Sample Group

Samples can be grouped:

```
https://api.datacite.org/works?sample=10&sample-group=data-center&page[size]=20
```

This query will retrieve 10 samples per data center, for 20 data centers. Allowed parameters for `sample-group` are `client`, `data-center`, `provider` and `resource-type`.

## Creating DOIs
DOIs can be created using the `https://api.datacite.org/dois` endpoint. Only Clients have the ability to create DOIs. Clients must authenticate using their DataCite Client ID and password. We will show you how to create, first a `draft` doi and the a `findable` doi.

To create a `draft` DOI, first, you will need to create a file with the essential information to create the draft DOI, it should look like this:

```json
{
  "data": {
    "type": "dois",
    "attributes": {
      "doi": "10.5012/rd4t-1a57"
    },
    "relationships": {
      "client": {
        "data": {
          "type": "clients",
          "id": "demo.datacite"
        }
      }
    }
  }
}
```
save can save that file as my_draft_doi.json

Then you can use the next call to submit that information like this:

```shell
# POST to /dois
curl -X POST -H "Content-Type: application/vnd.api+json" --user YOUR_CLIENT_ID:YOUR_PASSWORD -d @my_draft_doi.json https://api.test.datacite.org/dois 
```

Your response will look like this:

```json
{
	"data": {
		"id": "10.5072/rd4t-1a5f7",
		"type": "dois",
		"attributes": {
			"doi": "10.5072/rd4t-1a5f7",
			"identifier": "https://handle.test.datacite.org/10.5072/rd4t-1a5f7",
			"url": null,
			"prefix": "10.5072",
			"suffix": "rd4t-1a5f7",
			"author": [],
			"title": null,
			"publisher": null,
			"resource-type-subtype": null,
			"description": null,
			"version": null,
			"metadata-version": 0,
			"schema-version": "http://datacite.org/schema/kernel-4",
			"reason": null,
			"source": null,
			"state": "draft",
			"is-active": false,
			"landing-page": {
				"status": null,
				"content-type": null,
				"checked": null,
				"result": null
			},
			"published": null,
			"created": "2018-11-08T10:45:19.000Z",
			"registered": null,
			"updated": "2018-11-08T10:45:19.000Z",
			"xml": null,
			"cache-key": "dois/10.5072/rd4t-1a5f7-2018-11-08T10:45:19Z"
		},
		"relationships": {
			"client": {
				"data": {
					"id": "demo.datacite",
					"type": "clients"
				}
			},
			"resource-type": {
				"data": null
			},
			"media": {
				"data": []
			}
		}
	},
	"included": [
		{
			"id": "demo.datacite",
			"type": "clients",
			"attributes": {
				"name": "DataCite Staff Demo Client",
				"symbol": "DEMO.DATACITE",
				"year": 2018,
				"contact-name": "DataCite Support",
				"contact-email": "support@datacite.org",
				"domains": "*",
				"url": null,
				"created": "2018-04-08T09:31:38.000Z",
				"updated": "2018-08-26T01:31:12.000Z",
				"is-active": true,
				"has-password": true
			},
			"relationships": {
				"provider": {
					"data": {
						"id": "demo",
						"type": "providers"
					}
				},
				"prefixes": {
					"data": [
						{
							"id": "10.5072",
							"type": "prefixes"
						},
						{
							"id": "10.70043",
							"type": "prefixes"
						}
					]
				}
			}
		}
	]
}
```


To register a `findable` DOI with URL and metadata. We must clarify that you metadata will need to be encoded in a specific standard. This standard is Base64. There are many way to achieve this in all programming languages (e.g. [python](https://docs.python.org/2/library/base64.html)). Once you metadata is enconded you will need to put it in a similar json file:

```json
{
	"data": {
		"type": "dois",
		"attributes": {
			"doi": "10.5072/rd4t-1a57",
			"event": "publish",
			"url": "https://www.datacite.org",
			"xml": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4KPHJlc291cmNlIHhtbG5zPSJodHRwOi8vZGF0YWNpdGUub3JnL3NjaGVtYS9rZXJuZWwtMyIgeG1sbnM6eHNpPSJodHRwOi8vd3d3LnczLm9yZy8yMDAxL1hNTFNjaGVtYS1pbnN0YW5jZSIgeHNpOnNjaGVtYUxvY2F0aW9uPSJodHRwOi8vZGF0YWNpdGUub3JnL3NjaGVtYS9rZXJuZWwtMyBodHRwOi8vc2NoZW1hLmRhdGFjaXRlLm9yZy9tZXRhL2tlcm5lbC0zL21ldGFkYXRhLnhzZCI+CiAgPGlkZW50aWZpZXIgaWRlbnRpZmllclR5cGU9IkRPSSI+MTAuMjYxOTMvMU5MT0ZZPC9pZGVudGlmaWVyPgogIDxjcmVhdG9ycz4KICAgIDxjcmVhdG9yPgogICAgICA8Y3JlYXRvck5hbWU+Um95IE1vcmdhbjwvY3JlYXRvck5hbWU+CiAgICA8L2NyZWF0b3I+CiAgPC9jcmVhdG9ycz4KICA8dGl0bGVzPgogICAgPHRpdGxlPkF1c3RyYWxpYW4gR2FsbHVwIFBvbGxzLCBTdXJ2ZXkgMTc1LCBGZWJydWFyeSAxMiwgMTk2NTwvdGl0bGU+CiAgPC90aXRsZXM+CiAgPHB1Ymxpc2hlcj5BREEgRGF0YXZlc"
		},
		"relationships": {
			"client": {
				"data": {
					"type": "clients",
					"id": "demo.datacite"
				}
			}
		}
	}
}
```

Finally you will need to make a call on this file, like this:

```shell
# POST to /dois
curl -X POST -H "Content-Type: application/vnd.api+json" --user YOUR_CLIENT_ID:YOUR_PASSWORD -d @my_metadata.json https://api.test.datacite.org/dois 
```

## Next

Woot! Now you know the basics of the DataCite REST API!

- Retrieving single items and List
- Querying
- Filtering
- Creating DOIs


Keep learning with the [API Reference](http://support.datacite.org/reference)!
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]