---
title: DataCite Metadata Schema 4.2
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
  "title": "PDF is the version of record",
  "body": "The official home for the DataCite Metadata Schema is at https://schema.datacite.org, and the PDFs of the schema documentation found there are the versions of record. These pages on our support site are provided as a convenience. We try to duplicate the PDF as much as possible, but the PDF is the official version.\n\nCitation for the PDF version: DataCite Metadata Working Group. (2019). DataCite Metadata Schema Documentation for the Publication and Citation of Research Data. Version 4.2. DataCite e.V. https://doi.org/10.5438/bmjt-bx77."
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

The Metadata Working Group would like to acknowledge the contributions to our work of many colleagues in our institutions who provided assistance of all kinds. Their help has been greatly appreciated. In addition, we are indebted to numerous individuals and organisations in the broader scholarly community who have taken an interest in this work. Because data citation and data management are evolving areas of concern, we look forward to continued interest. With this in mind, the Working Group provides an interactive discussion mechanism for DataCite members and clients to discuss the DataCite Metadata Schema and issues connected with metadata submitted to DataCite, as appropriate. 

# The Metadata Schema

The DataCite Metadata Schema is a list of core metadata properties chosen for an accurate and consistent identification of a resource for citation and retrieval purposes, along with recommended use instructions. The resource that is being identified can be of any kind, but it is typically a dataset. We use the term ‘dataset’ in its broadest sense. We mean it to include not only numerical data, but any other research objects in keeping with [DataCite's mission](https://www.datacite.org/mission.html). The metadata schema properties are presented and described in detail in [Properties Overview](doc:schema-properties-overview-v41). 

While DataCite’s Metadata Schema has been expanded with each new version, it is, nevertheless, intended to be generic to the broadest range of research datasets, rather than customized to the needs of any particular discipline. DataCite metadata primarily supports citation and discovery of data; it is not intended to supplant or replace the discipline or community specific metadata that fully describes the data, and that is vital for understanding and reuse.

DataCite clients are strongly encouraged to provide metadata in English whenever possible, and in addition to any other language that may be required by the funder or hosting organization. The DataCite metadata schema supports language attributes for core properties.

This release of the metadata schema contains a few changes to the schema and some general improvements to the documentation. A larger change is the extension of the Rights property to enable users to provide more structural metadata on the licence identifier.

The remainder of the Version 4.2 changes is in response to requests from DataCite community members, people like you that have used the metadata schema and have imagined ways in which it might work better for their particular use case. We are indebted to everyone who has provided us with their feedback, allowing us to improve our service for the broader DataCite community.

For a list of all changes, see [Version 4.2 Update](#section-version-4-2-update).

Lastly, we continue to support openness and the future extensibility of the schema by collaborating with the Dublin Core Metadata Initiative (DCMI) [Science and Metadata Community (SAM)](http://www.dublincore.org/groups/sam/) to maintain a [Dublin Core Application Profile for the schema](https://schema.datacite.org/dc2ap/).

# Version 4.2 Update
## Version 4.2 of the schema includes these changes:
- Addition of new dateType “Withdrawn”
- Addition of new relationType pair: IsObsoletedBy and Obsoletes
- Addition of new relatedIdentifierType “w3id”
- Addition of new subproperties for Rights:
   - rightsIdentifier
   - rightsIdentifierScheme 
   - schemeURI
- Addition of the XML language attribute to the properties Creator, Contributor and Publisher for organizational names.

## Version 4.2 of the documentation includes these changes:
- Addition of “data management plan” and “conference paper” as examples to the description of resourceTypeGeneral “Text” (see Appendix 1, Table 7).
- Addition of a usage note to the relationType pair “Compiles/IsCompiledBy” (see Appendix 1, Table 9).
- Addition of a reference to the DataCite Event Data service to the description of the relatedIdentifier property.
- Addition of subproperty “resourceTypeGeneral” to relatedIdentifier.
- Notes on the coverage and scope of the metadata schema, and the preferred language in which
the metadata should be provided.

# Table of Contents
[Properties Overview](doc:schema-properties-overview-v42)
[Mandatory Properties](doc:schema-mandatory-properties-v42) 
[Recommended and Optional Metadata](doc:schema-optional-properties-v42)
[Earlier Version Update Notes](doc:schema-update-notes-v42) 
[Standard Values for Unknown Information](doc:schema-values-unknown-information-v42) 
[Changes in Support of Software Citation (introduced in v4.1)](doc:schema-changes-software-citation-v41) 
[FORCE11 Software Citation Principles Mapping (introduced in v4.1)](doc:schema-software-citation-principles-mapping-v41) 
[XML Metadata Examples](doc:schema-metadata-examples-v42)
[block:api-header]
{
  "title": "Notes"
}
[/block]
1. Smith AM, Katz DS, Niemeyer KE, FORCE11 Software Citation Working Group. (2016) Software citation principles. PeerJ Computer Science 2:e86 https://doi.org/10.7717/peerj-cs.86
2. Gent, I., Jones, C., & Matthews, B. (2015). Guidelines for persistently identifying software using DataCite. Retrieved July 19, 2017, from http://purl.org/net/epubs/work/24058274