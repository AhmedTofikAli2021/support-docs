---
title: How can I harvest XML metadata with DataCite APIs?
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
There are two ways to harvest XML metadata using DataCite APIs.

[The OAI-PMH Service](doc:datacite-oai-pmh) :

This DataCite service exposes metadata stored in the DataCite Metadata Store (MDS) using the Open Archives Initiative Protocol for Metadata Harvesting ([OAI-PMH](http://www.openarchives.org/pmh/)). You can retrieve records via OAI-PMH in several formats, including 1) the [OAI DataCite (oai_datacite)](doc:datacite-oai-pmh#oai-datacite-oai_datacite) metadata format which was established for the dissemination of DataCite records using OAI-PMH and 2) the [DataCite Direct (datacite)](doc:datacite-oai-pmh#datacite-direct-datacite) format, which contains only the original DataCite metadata without additions or alterations.

[The DataCite REST API](doc:api):

When [retrieving a list of DOIs](doc:api-get-lists), the REST API supports several parameters that can be used to refine, sort, and change the presentation of the results. You can use [additional parameters](doc:api-queries#selecting-which-metadata-fields-to-retrieve) to control the results returned by the DataCite REST API. To retrieve the XML version of the metadata in your REST API response, include the &detail=true parameter in your requests:

<https://api.datacite.org/dois?client-id=datacite.datacite&detail=true> 

With &detail=true, each result will contain a base64-encoded XML version of the metadata in the xml attribute.

> 📘 
> 
> If you want to retrieve XML metadata for a single DOI you can use the[ REST API](doc:api-get-doi), [OAI-PMH](doc:datacite-oai-pmh) and [DataCite Content Negotiation Service](doc:datacite-content-resolver).