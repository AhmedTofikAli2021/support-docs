---
title: Tracking metadata provenance
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
[block:callout]
{
  "type": "info",
  "body": "Provenance is information about entities, activities, and people involved in producing a piece of data or thing, which can be used to form assessments about its quality, reliability or trustworthiness.",
  "title": "Provenance definition according to the Prov Data Model (PROV-DM)"
}
[/block]
Metadata provenance is describing the history of a particular DOI metadata record, i.e. what changes were made when and by whom. This information is stored and provided via an API for all DOI registrations since March 10, 2019. The following provenance information is available via a new `/activities` [REST API endpoint](https://support.datacite.org/reference/activities):
[block:parameters]
{
  "data": {
    "0-0": "prov:wasGeneratedBy",
    "1-0": "prov:generatedAtTime",
    "2-0": "prov:wasDerivedFrom",
    "3-0": "prov:wasAttributedTo",
    "4-0": "action",
    "5-0": "version",
    "6-0": "changes",
    "4-1": "can be either create, update or delete.",
    "5-1": "version number for the DOI record.",
    "3-1": "The Repository or Member account responsible for the changes.",
    "2-1": "The DOI for which the changes are being tracked.",
    "1-1": "Timestamp of the activity.",
    "0-1": "The unique identifier of the activity making changes to a DOI.",
    "6-1": "An object with the properties that changed as keys and an array with the actual changes as values"
  },
  "cols": 2,
  "rows": 7
}
[/block]
This new provenance API addresses the following use cases:

##  What changes have been made to a particular DOI?

The activities API exposes all changes made to a particular DOI, e.g. `https://api.datacite.org/dois/10.5438/jwvf-8a66/activities`. This DOI is for a post on the DataCite blog, and we can see that some changes were made after the initial publication of the blog post, and we can see what was changed when and by whom. One change is for example described in `https://api.datacite.org/activities/851d725b-d7c8-41cf-90b3-22466d8b1927`: 

```
"data": {
  "id": "a61d0947-e836-4f9c-b19d-cec558438eae",
  "type": "activities",
  "attributes": {
    "prov:wasGeneratedBy": "https://api.datacite.org/activities/a61d0947-e836-4f9c-b19d-cec558438eae",
    "prov:generatedAtTime": "2019-03-28T20:58:22.251Z",
    "prov:wasDerivedFrom": "https://doi.org/10.5438/jwvf-8a66",
    "prov:wasAttributedTo": "https://api.datacite.org/providers/admin",
    "action": "update",
    "version": 5,
    "changes": {
      "types": [{
          "ris": "RPRT",
          "bibtex": "article",
          "citeproc": "article-journal",
          "schemaOrg": "ScholarlyArticle",
          "resourceType": "BlogPosting",
          "resourceTypeGeneral": "Text"
        },
        {
          "ris": "GEN",
          "bibtex": "article",
          "citeproc": "post-weblog",
          "schemaOrg": "BlogPosting",
          "resourceTypeGeneral": "Text"
        }
      ],
      "related_identifiers": [
        [{
          "relationType": "IsPartOf",
          "relatedIdentifier": "10.5438/0000-00ss",
          "resourceTypeGeneral": "Text",
          "relatedIdentifierType": "DOI"
        }],
        [{
            "relationType": "IsPartOf",
            "relatedIdentifier": "10.5438/0000-00ss",
            "resourceTypeGeneral": "Text",
            "relatedIdentifierType": "DOI"
          },
          {
            "relationType": "References",
            "relatedIdentifier": "10.5438/s6d3-k860",
            "relatedIdentifierType": "DOI"
          },
          {
            "relationType": "References",
            "relatedIdentifier": "10.25490/a97f-egyk",
            "relatedIdentifierType": "DOI"
          },
          {
            "relationType": "References",
            "relatedIdentifier": "10.5281/zenodo.2548643",
            "relatedIdentifierType": "DOI"
          },
          {
            "relationType": "References",
            "relatedIdentifier": "10.5438/pre3-2f25",
            "relatedIdentifierType": "DOI"
          },
          {
            "relationType": "References",
            "relatedIdentifier": "10.5281/zenodo.2600275",
            "relatedIdentifierType": "DOI"
          }
        ]
      ]
    }
  }
```
This activity record describes an update of the related identifier information, sent by the DataCite admin `https://api.datacite.org/providers/admin` account on 28 March 2019. A total of five references were added to the blog post.

## Which DOIs were affected by a particular change?

The activities API also supports queries, allowing the search for particular changes (see [API reference](https://support.datacite.org/reference/activities) for details). For example:

```
https://api.datacite.org/activities?query=changes.url:https*
```

This query returns all activities where the URL was changed to an HTTPS URL. We can also query for all updates by a given account, on a given day, etc.



**This work was funded as part of the FREYA project. The FREYA project has received funding from the European Union’s Horizon 2020 research and innovation programme under grant agreement No 777523.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d5c4d09-Screen_Shot_2020-04-09_at_14.05.39.png",
        "Screen Shot 2020-04-09 at 14.05.39.png",
        200,
        120,
        "#f0f3ef"
      ]
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8eb07cb-Screen_Shot_2020-04-09_at_14.10.22.png",
        "Screen Shot 2020-04-09 at 14.10.22.png",
        200,
        134,
        "#133b92"
      ]
    }
  ]
}
[/block]