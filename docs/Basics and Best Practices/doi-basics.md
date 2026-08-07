---
title: DOI Basics
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
[block:api-header]
{
  "type": "basic",
  "title": "What is a DOI?"
}
[/block]
From the [DOI Handbook](http://doi.org):

> DOI is an acronym for "digital object identifier", meaning a "digital identifier of an object". A DOI name is an identifier (not a location) of an entity on digital networks. It provides a system for persistent and actionable identification and interoperable exchange of managed information on digital networks. A DOI name can be assigned to any entity — physical, digital or abstract — primarily for sharing with an interested user community or managing as intellectual property. The DOI system is designed for interoperability; that is to use, or work with, existing identifier and metadata schemes.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a7f9e1d-d.png",
        "d.png",
        250,
        250,
        "#fbb425"
      ],
      "caption": "DOI Foundation Logo"
    }
  ]
}
[/block]
DOIs are an example of [Persistent Identifiers](https://en.wikipedia.org/wiki/Persistent_identifier) (PIDs). DOIs have been adopted by the scholarly communication community as, almost, the 'default' identifier for publications. In the last years, they have been adopted as identifiers for data publication, enabling data citation and reuse.

DOI names are provided by DataCite and other DOI registration agencies, coordinated by the International DOI Foundation ([IDF](https://www.doi.org)). Out of the currently 10 DOI registration agencies, most of them assign DOI names to scholarly content. [Crossref](http://crossref.org) is the largest DOI registration agency.

A DOI name is divided into three parts, separated by the first two slashes ('/'):
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eb3f38c-doi-parts.png",
        "doi-parts.png",
        600,
        125,
        "#767676"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Proxy"
}
[/block]
The proxy is not part of the DOI specification, but almost all scholarly DOIs that users encounter today will be expressed as HTTP URLs. DataCite therefore recommends in the [DOI display guidelines](doc:datacite-doi-display-guidelines) that all DOIs are displayed as permanent URLs, consistent with the recommendations of other DOI registration agencies, e.g. the [Crossref DOI display guidelines](https://www.crossref.org/display-guidelines/). 

When the DOI system was originally designed, it was thought that the DOI protocol would become widely used, but that clearly has not happened and displaying DOIs as doi:10.5281/ZENODO.31780 is therefore no longer recommended.
[block:api-header]
{
  "title": "Prefix"
}
[/block]
A DOI prefix always starts with '10.' and continues with a number (e.g. '10.1234' or '10.20865'). The DOI prefix is used as a namespace so that DOIs are globally unique without requiring global coordination for every new identifier. Prefixes in the handle system and therefore all DOIs prefixes are numbers without any semantic meaning. One lesson learned with persistent identifiers is that adding meaning to the identifier (e.g. by using a prefix with the name of the data repository) is always dangerous, because – despite best intentions – all names can change over time.

Since the DOI prefix is a namespace to keep DOIs globally unique, there is usually no need for multiple prefixes for one organization managing DOI assignment. The tricky part is that these responsibilities can change, e.g. when an organization manages multiple repositories and one of them is migrated to another organization. It, therefore, makes sense to consider assigning one prefix per list of resources that always stay together, e.g. a repository. It is possible that one prefix is managed by multiple organizations (as long as they use the same DOI registration agency), but that makes DOI management more complex.
[block:api-header]
{
  "title": "Suffix"
}
[/block]
The suffix for a DOI can be (almost) any string. This provides great flexibility, e.g. when migrating existing identifiers to the DOI system. This flexibility unfortunately not always works well in the web context, as the list of characters allowed in a URL is limited. A good example of this are SICIs ([Serial Item and Contribution Identifier](https://en.wikipedia.org/wiki/Serial_Item_and_Contribution_Identifier)), they were defined in 1996 before the DOI system was implemented, and could then be migrated to DOIs. Unfortunately they can contain many characters that are problematic in a URL or make it difficult to validate the DOI, as in `https://doi.org/10.1002/(sici)1099-1409(199908/10)3:6/7<672::aid-jpp192>3.0.co;2-8`. A Crossref [blog post](http://blog.crossref.org/2015/08/doi-regular-expressions.html) by Andrew Gilmartin gives a good overview about the characters found in DOIs and suggests the following regular expression to check for valid DOIs:
[block:code]
{
  "codes": [
    {
      "code": "/^10.\\d{4,9}/[-._;()/:A-Z0-9]+$/i",
      "language": "text"
    }
  ]
}
[/block]
SICIs demonstrate two other pitfalls:

* they contain semantic information (ISSN, volume, number, etc.) that may change over time, and
* they are long, difficult to transcribe, with characters not allowed in URLs, and not very human-readable.

Semantic information might also lead users to expect certain functionalities. A common pattern that we see at DataCite is to include information about the version or parent in the suffix, e.g. [https://doi.org/10.6084/M9.FIGSHARE.3501629.V1](https://doi.org/10.6084/M9.FIGSHARE.3501629.V1) or [https://doi.org/10.5061/DRYAD.0SN63/7](https://doi.org/10.5061/DRYAD.0SN63/7). While the decision on what to put into the suffix is up to each data center, we should make sure users don’t think that these are functionalities of the DOI system (e.g. that adding .V2 to any DOI name will resolve to version 2 of that resource).

Another issue to keep in mind when assigning suffixes is that DOIs – in contrast to HTTP URIs – are case-insensitive, https://doi.org/10.5281/ZENODO.31780 and https://doi.org/10.5281/zenodo.31780 are the same DOI. All DOIs are converted to upper case upon registration and DOI resolution, but DOIs are not consistently displayed in such a way.
[block:api-header]
{
  "type": "basic",
  "title": "DOIs for research data"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f836793-Screen_Shot_2017-01-02_at_10.59.50.png",
        "Screen Shot 2017-01-02 at 10.59.50.png",
        1850,
        898,
        "#dad3d4"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "More information!"
}
[/block]
Learn more about DOIs:

* [Official DOI Handbook](http://www.doi.org/hb.html)
* [The ANDS guide to DOIs](http://www.ands.org.au/guides/doi)
* [Wikipedia article](https://en.wikipedia.org/wiki/Digital_object_identifier)
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]