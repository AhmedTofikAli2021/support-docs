---
title: DataCite Metadata Schema 4.1
excerpt: ''
deprecated: false
hidden: true
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
  "title": "PDF is the version of record",
  "body": "The official home for the DataCite Metadata Schema is at https://schema.datacite.org, and the PDFs of the schema documentation found there are the versions of record. These pages on our support site are provided as a convenience. We try to duplicate the PDF as much as possible, but the PDF is the official version.\n\nCitation for the PDF version: DataCite Metadata Working Group. (2017). DataCite Metadata Schema Documentation for the Publication and Citation of Research Data. Version 4.1. DataCite e.V. http://doi.org/10.5438/0014."
}
[/block]
# The DataCite Consortium

Scholarly research is producing ever-increasing amounts of digital research data, and it depends on data to verify research findings, create new research, and share findings. In this context, what has been missing until recently, is a *persistent* approach to access, identification, sharing, and re-use of datasets. To address this need, the [DataCite](https://datacite.org) international consortium was founded in late 2009 with these three fundamental goals:

*   establish easier access to scientific research data on the Internet,
*   increase acceptance of research data as legitimate, citable contributions to the scientific record, and
* support data archiving that will permit results to be verified and re-purposed for future study.

Since its founding in 2009, DataCite has grown and now spans the globe from Europe and North America to Asia and Australia. The aim of DataCite is to provide domain agnostic services to benefit scholars in a wide range of disciplines.

Key to DataCite service is the concept of a long-term or *persistent* identifier. A persistent identifier is an association between a character string and a resource. Resources can be files, parts of files, persons, organisations, abstractions, etc. DataCite uses *Digital Object Identifiers* (DOIs). DOIs are administered by the [International DOI Foundation](http://www.doi.org).

# DataCite Community Participation

The Metadata Working Group would like to acknowledge the contributions to our work of many colleagues in our institutions who provided assistance of all kinds. Their help has been greatly appreciated. In addition, we are indebted to numerous individuals and organisations in the broader scholarly community who have taken an interest in this work. Because data citation and data management are evolving areas of concern, we look forward to continued interest. With this in mind, the Working Group provides an interactive discussion mechanism for DataCite members and clients to discuss the DataCite Metadata Schema and issues connected with metadata submitted to DataCite, as appropriate. Join the discussion at [https://schema.datacite.org].

# The Metadata Schema

The DataCite Metadata Schema is a list of core metadata properties chosen for an accurate and consistent identification of a resource for citation and retrieval purposes, along with recommended use instructions. The resource that is being identified can be of any kind, but it is typically a dataset. We use the term ‘dataset’ in its broadest sense. We mean it to include not only numerical data, but any other research objects in keeping with [DataCite's mission](https://www.datacite.org/mission.html). The metadata schema properties are presented and described in detail in [Properties Overview](doc:schema-properties-overview-v41). 

If this release of the metadata schema has a theme, it is support for software citation. The Working Group undertook this in response to increasing interest within the community, including the publication of the Force11 Software Citation Principles[(1)](#section-notes) as well as a set of guidelines[(2)](#section-notes) prepared by the UK Science and Technology Facilities Council for working with the DataCite schema. As we reviewed schema version 4.0, we found that very few actual schema changes were required, but substantial modifications needed to be made to the documentation to assist those registering DOIs for software. While the DataCite metadata schema now supports software registration, and provides properties to include version information for items being registered, it is not to be used as a version control or source code control system. There are many tools widely available that are ideally suited for that purpose. Instead, DataCite facilitates software discovery, sharing and citation.

A complete list of all changes in support of software citation is available as a special reference in [Version 4.1 Changes in Support of Software Citation](doc:schema-changes-software-citation-v41). In addition, we are providing a mapping of the Force11 Software Citation Principles’ metadata requirements to DataCite’s metadata schema. This is available as [FORCE11 Software Citation Principles Mapping](doc:schema-software-citation-principles-mapping-v41).

The remainder of the Version 4.1 changes is in response to requests from DataCite community members, people like you that have used the metadata schema and have imagined ways in which it might work better for their particular use case. We are indebted to everyone who has provided us with their feedback, allowing us to improve our service for the broader DataCite community.

For a list of all changes, see [Version 4.1 Updates](#section-version-4-1-updates).

Lastly, we continue to support openness and the future extensibility of the schema by collaborating with the Dublin Core Metadata Initiative (DCMI) [Science and Metadata Community (SAM)](http://www.dublincore.org/groups/sam/) to maintain a [Dublin Core Application Profile for the schema](https://schema.datacite.org/dc2ap/).

# Version 4.1 Updates

## Version 4.1 of the schema includes these changes:

- Allowing multiple polygons per GeoLocation
- Addition of new optional subproperties for polygon
  - inPolygonPoint
- Addition of new dateType “Other”
- Addition of new subproperty for Date
  - dateInformation
- Addition of a new resourceType "DataPaper"
- Addition of three new relationType pairs:
  - IsDescribedBy and Describes
  - HasVersion and IsVersionOf
  - IsRequiredBy and Requires
- Addition of a new optional attribute for creatorName and ContributorName:
  - nameType. Controlled list: personal, organizational
- Addition of a new optional attribute for relatedIdentifier
  - resourceTypeGeneral. Controlled list is identical to existing resourceTypeGeneral
attribute
- Addition of optional lang attribute to Rights property

## Version 4.1 of the documentation includes these changes:

- Change to the definition of Collection to encompass collections of one resourceType as well as those of mixed types.
- Inclusion of a reference to the Research Data Alliance (RDA)-recommended dynamic data citation approach in documentation in section 2.2, Citation.
- Change to the definition and examples of Size property to include duration as well as extent.
- Correction of the hierarchy of elements for Creator and Contributor.
- To enhance support for software citation, addition of 2 new appendices: one with a list of all the changes and explanatory notes; and one with Force11 mappings
- Changes and additions to these definitions, in support of software citation:
  - Identifier
  - Title
  - Publisher
  - Contributor
  - PublicationYear
  - resourceTypeGeneral (Service, Software)
  - relationType pairs (IsPartOf, HasPart, IsDocumentedBy, Documents, IsVariantFormOf, IsOriginalFormOf)
  - Version
  - Rights
  - Description (TechnicalInfo)

# Table of Contents
[Properties Overview](doc:schema-properties-overview-v41)
[Mandatory Properties](doc:schema-mandatory-properties-v41) 
[Recommended and Optional Metadata](doc:schema-optional-properties-v41)
[Earlier Version Update Notes](doc:schema-update-notes-v41) 
[Standard Values for Unknown Information](doc:schema-values-unknown-information-v41) 
[Version 4.1 Changes in Support of Software Citation](doc:schema-changes-software-citation-v41) 
[FORCE11 Software Citation Principles Mapping](doc:schema-software-citation-principles-mapping-v41) 
[XML Metadata Examples](doc:schema-metadata-examples-v41)
[block:api-header]
{
  "title": "Notes"
}
[/block]
1. Smith AM, Katz DS, Niemeyer KE, FORCE11 Software Citation Working Group. (2016) Software citation principles. PeerJ Computer Science 2:e86 https://doi.org/10.7717/peerj-cs.86
2. Gent, I., Jones, C., & Matthews, B. (2015). Guidelines for persistently identifying software using DataCite. Retrieved July 19, 2017, from http://purl.org/net/epubs/work/24058274