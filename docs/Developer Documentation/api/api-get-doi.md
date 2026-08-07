---
title: Retrieving a single DOI
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: Retrieving a list of DOIs
  pages:
    - type: basic
      slug: api-get-lists
      title: Retrieving a list of DOIs
---
Almost any meaningful use of the DataCite REST API will involve some level of record retrieval. The responses from each of your requests fall into two basic categories: 

- Singleton: a single record
- List: a list of records

A **singleton** is a single result, i.e., the metadata for a specific DOI. This section of the guide covers singletons. The next section, [Retrieving a list of DOIs](doc:api-get-lists), will cover lists. 

## Request

Retrieve a single DOI via a GET request by replacing `{id}` in `https://api.test.datacite.org/dois/{id}` with the DOI name.

For example, retrieving the metadata record for the DOI `10.14454/FXWS-0523` from the command line with curl can be done by making a request to `https://api.datacite.org/dois/10.14454/FXWS-0523`:

```shell
# GET /dois
$ curl https://api.datacite.org/dois/10.14454/FXWS-0523
```

The [API Reference](ref:get_dois-id) provides example code for Node, Ruby, Javascript and Python.

## Response

The response would look like this:

```json
{
    "data": {
        "id": "10.14454/fxws-0523",
        "type": "dois",
        "attributes": {
            "doi": "10.14454/fxws-0523",
            "prefix": "10.14454",
            "suffix": "fxws-0523",
            "identifiers": [],
            "alternateIdentifiers": [],
            "creators": [
                {
                    "name": "DataCite Metadata Working Group",
                    "affiliation": [],
                    "nameIdentifiers": []
                }
            ],
            "titles": [
                {
                    "title": "DataCite Metadata Schema for the Publication and Citation of Research Data and Other Research Outputs v4.4"
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
            "language": null,
            "types": {
                "ris": "RPRT",
                "bibtex": "article",
                "citeproc": "article-journal",
                "schemaOrg": "ScholarlyArticle",
                "resourceType": "XSD code",
                "resourceTypeGeneral": "Text"
            },
            "relatedIdentifiers": [],
            "relatedItems": [],
            "sizes": [],
            "formats": [],
            "version": "4.4",
            "rightsList": [],
            "descriptions": [],
            "geoLocations": [],
            "fundingReferences": [],
            "xml": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4KPHJlc291cmNlIHhtbG5zOnhzaT0iaHR0cDovL3d3dy53My5vcmcvMjAwMS9YTUxTY2hlbWEtaW5zdGFuY2UiIHhtbG5zPSJodHRwOi8vZGF0YWNpdGUub3JnL3NjaGVtYS9rZXJuZWwtNCIgeHNpOnNjaGVtYUxvY2F0aW9uPSJodHRwOi8vZGF0YWNpdGUub3JnL3NjaGVtYS9rZXJuZWwtNCBodHRwOi8vc2NoZW1hLmRhdGFjaXRlLm9yZy9tZXRhL2tlcm5lbC00L21ldGFkYXRhLnhzZCI+CiAgPGlkZW50aWZpZXIgaWRlbnRpZmllclR5cGU9IkRPSSI+MTAuMTQ0NTQvRlhXUy0wNTIzPC9pZGVudGlmaWVyPgogIDxjcmVhdG9ycz4KICAgIDxjcmVhdG9yPgogICAgICA8Y3JlYXRvck5hbWU+RGF0YUNpdGUgTWV0YWRhdGEgV29ya2luZyBHcm91cDwvY3JlYXRvck5hbWU+CiAgICA8L2NyZWF0b3I+CiAgPC9jcmVhdG9ycz4KICA8dGl0bGVzPgogICAgPHRpdGxlPkRhdGFDaXRlIE1ldGFkYXRhIFNjaGVtYSBmb3IgdGhlIFB1YmxpY2F0aW9uIGFuZCBDaXRhdGlvbiBvZiBSZXNlYXJjaCBEYXRhIGFuZCBPdGhlciBSZXNlYXJjaCBPdXRwdXRzIHY0LjQ8L3RpdGxlPgogIDwvdGl0bGVzPgogIDxwdWJsaXNoZXI+RGF0YUNpdGU8L3B1Ymxpc2hlcj4KICA8cHVibGljYXRpb25ZZWFyPjIwMjE8L3B1YmxpY2F0aW9uWWVhcj4KICA8cmVzb3VyY2VUeXBlIHJlc291cmNlVHlwZUdlbmVyYWw9IlRleHQiPlhTRCBjb2RlPC9yZXNvdXJjZVR5cGU+CiAgPGNvbnRyaWJ1dG9ycz4KICAgIDxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IlByb2plY3RMZWFkZXIiPgogICAgICA8Y29udHJpYnV0b3JOYW1lPmRlIFNtYWVsZSwgTWFkZWxlaW5lPC9jb250cmlidXRvck5hbWU+CiAgICAgIDxnaXZlbk5hbWU+TWFkZWxlaW5lPC9naXZlbk5hbWU+CiAgICAgIDxmYW1pbHlOYW1lPmRlIFNtYWVsZTwvZmFtaWx5TmFtZT4KICAgICAgPG5hbWVJZGVudGlmaWVyIG5hbWVJZGVudGlmaWVyU2NoZW1lPSJPUkNJRCIgc2NoZW1lVVJJPSJodHRwczovL29yY2lkLm9yZyI+MDAwMC0wMDAzLTQxNDktODMxMTwvbmFtZUlkZW50aWZpZXI+CiAgICAgIDxhZmZpbGlhdGlvbiBhZmZpbGlhdGlvbklkZW50aWZpZXI9Imh0dHBzOi8vcm9yLm9yZy8wMmUyYzdrMDkiIGFmZmlsaWF0aW9uSWRlbnRpZmllclNjaGVtZT0iUk9SIj5EZWxmdCBVbml2ZXJzaXR5IG9mIFRlY2hub2xvZ3k8L2FmZmlsaWF0aW9uPgogICAgPC9jb250cmlidXRvcj4KICAgIDxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IlByb2plY3RMZWFkZXIiPgogICAgICA8Y29udHJpYnV0b3JOYW1lPkJlcm5hbCBNYXJ0acyBbmV6LCBJc2FiZWw8L2NvbnRyaWJ1dG9yTmFtZT4KICAgICAgPGdpdmVuTmFtZT5Jc2FiZWw8L2dpdmVuTmFtZT4KICAgICAgPGZhbWlseU5hbWU+QmVybmFsIE1hcnRpzIFuZXo8L2ZhbWlseU5hbWU+CiAgICAgIDxhZmZpbGlhdGlvbiBhZmZpbGlhdGlvbklkZW50aWZpZXI9Imh0dHBzOi8vcm9yLm9yZy8wMmdmYzd0NzIiIGFmZmlsaWF0aW9uSWRlbnRpZmllclNjaGVtZT0iUk9SIj5TcGFuaXNoIE5hdGlvbmFsIFJlc2VhcmNoIENvdW5jaWw8L2FmZmlsaWF0aW9uPgogICAgPC9jb250cmlidXRvcj4KICAgIDxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+CiAgICAgIDxjb250cmlidXRvck5hbWU+RGFzbGVyLCBSb2JpbjwvY29udHJpYnV0b3JOYW1lPgogICAgICA8Z2l2ZW5OYW1lPlJvYmluPC9naXZlbk5hbWU+CiAgICAgIDxmYW1pbHlOYW1lPkRhc2xlcjwvZmFtaWx5TmFtZT4KICAgICAgPG5hbWVJZGVudGlmaWVyIG5hbWVJZGVudGlmaWVyU2NoZW1lPSJPUkNJRCIgc2NoZW1lVVJJPSJodHRwczovL29yY2lkLm9yZyI+MDAwMC0wMDAyLTQ2OTUtNzg3NDwvbmFtZUlkZW50aWZpZXI+CiAgICAgIDxhZmZpbGlhdGlvbiBhZmZpbGlhdGlvbklkZW50aWZpZXI9Imh0dHBzOi8vcm9yLm9yZy8wNHd4bnNqODEiIGFmZmlsaWF0aW9uSWRlbnRpZmllclNjaGVtZT0iUk9SIj5EYXRhQ2l0ZTwvYWZmaWxpYXRpb24+CiAgICA8L2NvbnRyaWJ1dG9yPgogICAgPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iRWRpdG9yIj4KICAgICAgPGNvbnRyaWJ1dG9yTmFtZT5Bc2h0b24sIEphbjwvY29udHJpYnV0b3JOYW1lPgogICAgICA8Z2l2ZW5OYW1lPkphbjwvZ2l2ZW5OYW1lPgogICAgICA8ZmFtaWx5TmFtZT5Bc2h0b248L2ZhbWlseU5hbWU+CiAgICAgIDxhZmZpbGlhdGlvbiBhZmZpbGlhdGlvbklkZW50aWZpZXI9Imh0dHBzOi8vcm9yLm9yZy8wNWRoZThiNzEiIGFmZmlsaWF0aW9uSWRlbnRpZmllclNjaGVtZT0iUk9SIj5Ccml0aXNoIExpYnJhcnk8L2FmZmlsaWF0aW9uPgogICAgPC9jb250cmlidXRvcj4KICAgIDxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+CiAgICAgIDxjb250cmlidXRvck5hbWU+Um95LCBTb3BoaWU8L2NvbnRyaWJ1dG9yTmFtZT4KICAgICAgPGdpdmVuTmFtZT5Tb3BoaWU8L2dpdmVuTmFtZT4KICAgICAgPGZhbWlseU5hbWU+Um95PC9mYW1pbHlOYW1lPgogICAgICA8YWZmaWxpYXRpb24gYWZmaWxpYXRpb25JZGVudGlmaWVyPSJodHRwczovL3Jvci5vcmcvMDRtdGUxazA2IiBhZmZpbGlhdGlvbklkZW50aWZpZXJTY2hlbWU9IlJPUiI+TmF0aW9uYWwgUmVzZWFyY2ggQ291bmNpbCBDYW5hZGE8L2FmZmlsaWF0aW9uPgogICAgPC9jb250cmlidXRvcj4KICAgIDxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+CiAgICAgIDxjb250cmlidXRvck5hbWU+RmVubmVyLCBNYXJ0aW48L2NvbnRyaWJ1dG9yTmFtZT4KICAgICAgPGdpdmVuTmFtZT5NYXJ0aW48L2dpdmVuTmFtZT4KICAgICAgPGZhbWlseU5hbWU+RmVubmVyPC9mYW1pbHlOYW1lPgogICAgICA8bmFtZUlkZW50aWZpZXIgbmFtZUlkZW50aWZpZXJTY2hlbWU9Ik9SQ0lEIiBzY2hlbWVVUkk9Imh0dHBzOi8vb3JjaWQub3JnIj4wMDAwLTAwMDEtNjUyOC0yMDI3PC9uYW1lSWRlbnRpZmllcj4KICAgICAgPGFmZmlsaWF0aW9uIGFmZmlsaWF0aW9uSWRlbnRpZmllcj0iaHR0cHM6Ly9yb3Iub3JnLzA0d3huc2o4MSIgYWZmaWxpYXRpb25JZGVudGlmaWVyU2NoZW1lPSJST1IiPkRhdGFDaXRlPC9hZmZpbGlhdGlvbj4KICAgIDwvY29udHJpYnV0b3I+CiAgICA8Y29udHJpYnV0b3IgY29udHJpYnV0b3JUeXBlPSJFZGl0b3IiPgogICAgICA8Y29udHJpYnV0b3JOYW1lPkNoaWxvYW5lLCBMZW88L2NvbnRyaWJ1dG9yTmFtZT4KICAgICAgPGdpdmVuTmFtZT5MZW88L2dpdmVuTmFtZT4KICAgICAgPGZhbWlseU5hbWU+Q2hpbG9hbmU8L2ZhbWlseU5hbWU+CiAgICAgIDxhZmZpbGlhdGlvbj5Tb3V0aCBBZnJpY2FuIEVudmlyb25tZW50YWwgT2JzZXJ2YXRpb24gTmV0d29yazwvYWZmaWxpYXRpb24+CiAgICA8L2NvbnRyaWJ1dG9yPgogICAgPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iRWRpdG9yIj4KICAgICAgPGNvbnRyaWJ1dG9yTmFtZT5CdXJnZXIsIE1hcmxlZW48L2NvbnRyaWJ1dG9yTmFtZT4KICAgICAgPGdpdmVuTmFtZT5NYXJsZWVuPC9naXZlbk5hbWU+CiAgICAgIDxmYW1pbHlOYW1lPkJ1cmdlcjwvZmFtaWx5TmFtZT4KICAgICAgPGFmZmlsaWF0aW9uIGFmZmlsaWF0aW9uSWRlbnRpZmllcj0iaHR0cHM6Ly9yb3Iub3JnLzA0YWo0YzE4MSIgYWZmaWxpYXRpb25JZGVudGlmaWVyU2NoZW1lPSJST1IiPkdlcm1hbiBOYXRpb25hbCBMaWJyYXJ5IG9mIFNjaWVuY2UgYW5kIFRlY2hub2xvZ3k8L2FmZmlsaWF0aW9uPgogICAgPC9jb250cmlidXRvcj4KICAgIDxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+CiAgICAgIDxjb250cmlidXRvck5hbWU+WWFoaWEsIE1vaGFtZWQ8L2NvbnRyaWJ1dG9yTmFtZT4KICAgICAgPGdpdmVuTmFtZT5Nb2hhbWVkPC9naXZlbk5hbWU+CiAgICAgIDxmYW1pbHlOYW1lPllhaGlhPC9mYW1pbHlOYW1lPgogICAgICA8YWZmaWxpYXRpb24gYWZmaWxpYXRpb25JZGVudGlmaWVyPSJodHRwczovL3Jvci5vcmcvMDJtbjB2dDU3IiBhZmZpbGlhdGlvbklkZW50aWZpZXJTY2hlbWU9IlJPUiI+SW5zdGl0dXQgZGUgbCdJbmZvcm1hdGlvbiBTY2llbnRpZmlxdWUgZXQgVGVjaG5pcXVlPC9hZmZpbGlhdGlvbj4KICAgIDwvY29udHJpYnV0b3I+CiAgICA8Y29udHJpYnV0b3IgY29udHJpYnV0b3JUeXBlPSJFZGl0b3IiPgogICAgICA8Y29udHJpYnV0b3JOYW1lPlpvbGx5LCBMaXNhPC9jb250cmlidXRvck5hbWU+CiAgICAgIDxnaXZlbk5hbWU+TGlzYTwvZ2l2ZW5OYW1lPgogICAgICA8ZmFtaWx5TmFtZT5ab2xseTwvZmFtaWx5TmFtZT4KICAgICAgPGFmZmlsaWF0aW9uIGFmZmlsaWF0aW9uSWRlbnRpZmllcj0iaHR0cHM6Ly9yb3Iub3JnLzAzNWE2ODg2MyIgYWZmaWxpYXRpb25JZGVudGlmaWVyU2NoZW1lPSJST1IiPlVuaXRlZCBTdGF0ZXMgR2VvbG9naWNhbCBTdXJ2ZXk8L2FmZmlsaWF0aW9uPgogICAgPC9jb250cmlidXRvcj4KICAgIDxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+CiAgICAgIDxjb250cmlidXRvck5hbWU+SGFiZXJtYW5uLCBUZWQ8L2NvbnRyaWJ1dG9yTmFtZT4KICAgICAgPGdpdmVuTmFtZT5UZWQ8L2dpdmVuTmFtZT4KICAgICAgPGZhbWlseU5hbWU+SGFiZXJtYW5uPC9mYW1pbHlOYW1lPgogICAgICA8YWZmaWxpYXRpb24+TWV0YWRhdGEgR2FtZSBDaGFuZ2VyczwvYWZmaWxpYXRpb24+CiAgICA8L2NvbnRyaWJ1dG9yPgogICAgPGNvbnRyaWJ1dG9yIGNvbnRyaWJ1dG9yVHlwZT0iRWRpdG9yIj4KICAgICAgPGNvbnRyaWJ1dG9yTmFtZT5SYXVnaCwgQW5uZTwvY29udHJpYnV0b3JOYW1lPgogICAgICA8Z2l2ZW5OYW1lPkFubmU8L2dpdmVuTmFtZT4KICAgICAgPGZhbWlseU5hbWU+UmF1Z2g8L2ZhbWlseU5hbWU+CiAgICAgIDxhZmZpbGlhdGlvbiBhZmZpbGlhdGlvbklkZW50aWZpZXI9Imh0dHBzOi8vcm9yLm9yZy8wNDdzMmMyNTgiIGFmZmlsaWF0aW9uSWRlbnRpZmllclNjaGVtZT0iUk9SIj5Vbml2ZXJzaXR5IG9mIE1hcnlsYW5kLCBDb2xsZWdlIFBhcms8L2FmZmlsaWF0aW9uPgogICAgPC9jb250cmlidXRvcj4KICAgIDxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+CiAgICAgIDxjb250cmlidXRvck5hbWU+SWxpaywgVmlvbGV0YTwvY29udHJpYnV0b3JOYW1lPgogICAgICA8Z2l2ZW5OYW1lPlZpb2xldGE8L2dpdmVuTmFtZT4KICAgICAgPGZhbWlseU5hbWU+SWxpazwvZmFtaWx5TmFtZT4KICAgICAgPGFmZmlsaWF0aW9uIGFmZmlsaWF0aW9uSWRlbnRpZmllcj0iaHR0cHM6Ly9yb3Iub3JnLzAwaGo4czE3MiIgYWZmaWxpYXRpb25JZGVudGlmaWVyU2NoZW1lPSJST1IiPkNvbHVtYmlhIFVuaXZlcnNpdHk8L2FmZmlsaWF0aW9uPgogICAgPC9jb250cmlidXRvcj4KICAgIDxjb250cmlidXRvciBjb250cmlidXRvclR5cGU9IkVkaXRvciI+CiAgICAgIDxjb250cmlidXRvck5hbWU+Rm91bGdlciwgU2FtYW50aGE8L2NvbnRyaWJ1dG9yTmFtZT4KICAgICAgPGdpdmVuTmFtZT5TYW1hbnRoYTwvZ2l2ZW5OYW1lPgogICAgICA8ZmFtaWx5TmFtZT5Gb3VsZ2VyPC9mYW1pbHlOYW1lPgogICAgICA8YWZmaWxpYXRpb24gYWZmaWxpYXRpb25JZGVudGlmaWVyPSJodHRwczovL3Jvci5vcmcvMDVhMjhydzU4IiBhZmZpbGlhdGlvbklkZW50aWZpZXJTY2hlbWU9IlJPUiI+U3dpc3MgRmVkZXJhbCBJbnN0aXR1dGUgb2YgVGVjaG5vbG9neSBpbiBadXJpY2g8L2FmZmlsaWF0aW9uPgogICAgPC9jb250cmlidXRvcj4KICA8L2NvbnRyaWJ1dG9ycz4KICA8ZGF0ZXM+CiAgICA8ZGF0ZSBkYXRlVHlwZT0iSXNzdWVkIj4yMDIxPC9kYXRlPgogIDwvZGF0ZXM+CiAgPHZlcnNpb24+NC40PC92ZXJzaW9uPgo8L3Jlc291cmNlPg==",
            "url": "https://schema.datacite.org/meta/kernel-4.4/",
            "contentUrl": null,
            "metadataVersion": 1,
            "schemaVersion": "http://datacite.org/schema/kernel-4",
            "source": "fabricaForm",
            "isActive": true,
            "state": "findable",
            "reason": null,
            "viewCount": 0,
            "viewsOverTime": [],
            "downloadCount": 0,
            "downloadsOverTime": [],
            "referenceCount": 0,
            "citationCount": 1,
            "citationsOverTime": [
                {
                    "year": "2022",
                    "total": 1
                }
            ],
            "partCount": 0,
            "partOfCount": 0,
            "versionCount": 0,
            "versionOfCount": 0,
            "created": "2021-03-30T10:19:45.000Z",
            "registered": "2021-03-30T12:00:37.000Z",
            "published": "2021",
            "updated": "2021-03-30T12:00:37.000Z"
        },
        "relationships": {
            "client": {
                "data": {
                    "id": "datacite.datacite",
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
                    "id": "10.14454/fxws-0523",
                    "type": "media"
                }
            },
            "references": {
                "data": []
            },
            "citations": {
                "data": [
                    {
                        "id": "10.21105/joss.03824",
                        "type": "dois"
                    }
                ]
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

### What's in the response?

The REST API includes the complete DOI metadata record in JSON.

> 👍 
> 
> _Note: Affiliation identifiers (supported in Metadata Schema 4.3+) are not included in REST API responses by default. To include affiliation identifier details, add `&affiliation=true` to your queries. [See our FAQ for more information](https://support.datacite.org/docs/can-i-see-more-detailed-affiliation-information-in-the-rest-api)_

The list below provides a description of the additional fields that appear in the API response and provide extra information about the DOI. This information is different from the DOI metadata.

#### xml

The stored DataCite Metadata Schema XML encoded in Base64 format.

#### url

The landing page URL of the DOI.

#### contentUrl

An array of content URLs associated with the DOI.

#### metadataVersion

The version of the stored DataCite metadata, incremented once per update.

#### schemaVersion

The DataCite Metadata Schema version of the stored DOI metadata represented as a URL.

#### source

The system used to create the DOI. Values include:

| Value       | Source              |
| :---------- | :------------------ |
| mds         | MDS API             |
| api         | REST API            |
| fabricaForm | Fabrica Form        |
| fabrica     | Fabrica File Upload |
| ez          | EZ API              |

#### isActive

"true" if the DOI is in Findable state. Otherwise, "false".

#### state

The state of the DOI. Options are "findable", "registered", and "draft".

#### reason

Legacy attribute for EZID compatibility.

#### viewCount

Total views, pulled from Event Data.

#### downloadCount

Total downloads, pulled from Event Data.

#### referenceCount

Total references, pulled from Event Data.

#### citationCount

Total citations, pulled from Event Data.

#### partCount

Total number of parts, pulled from Event Data.

#### partOfCount

Total number of parents, pulled from Event Data.

#### versionCount"

Total number of versions, pulled from Event Data.

#### versionOfCount

Total number to which this DOI is a version, pulled from Event Data.

#### created

Creation date of the DOI record in iso8601.

#### registered

Date the DOI was registered in iso8601.

#### published

The issued date or publication year.

#### updated

Date the DOI record was updated in iso8601.

#### relationships

A dictionary containing relationships to other PIDs and DataCite data objects.

##### relationships.client.data.id

The repository ID of the holding repository

##### relationships.client.data.type

Always "clients".

##### relationships.provider.data.id

The Member or Consortium Organization ID of the associated repository.

##### relationships.provider.data.type"

Always "providers".

##### relationships.media

Legacy attribute for media support. An array of media as dictionaries.

##### relationships.references

An array of references as dictionaries.

##### relationships.references.data.id

The identifier of the reference.

##### relationships.references.data.type

The type of the reference identifier. Always "dois".

##### relationships.citations

An array of citations as dictionaries.

##### relationships.citations.data.id

The identifier of the citation.

##### relationships.citations.data.type

The type of the citation identifier. Always "dois".

##### relationships.parts

An array of parts as dictionaries.

##### relationships.parts.data.id

The identifier of the part.

##### relationships.parts.data.type

The type of the part identifier. Always "dois".

##### relationships.partOf

An array of parents as dictionaries.

##### relationships.partOf.data.id

The identifier of the parent.

##### relationships.partOf.data.type

The type of the parent identifier. Always "dois".

##### relationships.versions

An array of versions as dictionaries.

##### relationships.versions.data.id

The identifier of the version.

##### relationships.versions.data.type

The type of the version identifier. Always "dois".

##### relationships.versionOf

An array of objects to which this DOI is a version as dictionaries.

##### relationships.versionOf.data.id

The identifier of the object to which this DOI is a version.

##### relationships.versionOf.data.type

The type of the object to which this DOI is a version. Always "dois".