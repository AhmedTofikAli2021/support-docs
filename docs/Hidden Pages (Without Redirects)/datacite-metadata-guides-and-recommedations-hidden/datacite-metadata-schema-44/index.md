---
title: DataCite Metadata Schema 4.4
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
  "body": "The official home for the DataCite Metadata Schema is at https://schema.datacite.org, and the PDFs of the schema documentation found there are the versions of record. These pages on our support site are provided as a convenience. We try to duplicate the PDF as much as possible, but the PDF is the official version. \n\nCitation:\nDataCite Metadata Working Group. (2021). DataCite Metadata Schema Documentation for the Publication and Citation of Research Data and Other Research Outputs. Version 4.4. DataCite e.V. \n[https://doi.org/10.14454/3w3z-sa82](https://doi.org/10.14454/3w3z-sa82)"
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

The DataCite Metadata Schema is a list of core metadata properties chosen for an accurate and consistent identification of a resource for citation and retrieval purposes, along with recommended use instructions. The resource that is being identified can be of any kind, but it is typically a dataset. We use the term ‘dataset’ in its broadest sense. We mean it to include not only numerical data, but any other research objects in keeping with [DataCite's mission](https://www.datacite.org/mission.html). The metadata schema properties are presented and described in detail in [Properties Overview](doc:datacite-metadata-schema-v44-properties-overview). 

While DataCite’s Metadata Schema has been expanded with each new version, it is, nevertheless, intended to be generic to the broadest range of research datasets, rather than customized to the needs of any particular discipline. DataCite metadata primarily supports citation and discovery of data; it is not intended to supplant or replace the discipline or community specific metadata that fully describes the data, and that is vital for understanding and reuse.

DataCite clients are strongly encouraged to provide metadata in English whenever possible, and in addition to any other language that may be required by the funder or hosting organization. The DataCite metadata schema supports language attributes for core properties.

This release of this metadata schema contains support of organizational identifiers, like ROR IDs. Including ROR IDs in metadata will enable more efficient discovery and tracking of publications by institutions and is making unambiguous affiliation information widely and freely available. 

The remainder of the Version 4.4 changes is in response to requests from DataCite community members, people like you that have used the metadata schema and have imagined ways in which it might work better for their particular use case. We are indebted to everyone who has provided us with their feedback, allowing us to improve our service for the broader DataCite community.

For a list of all changes, see [Version 4.4 Update](doc:datacite-metadata-schema-v44-earlier-version-update-notes).

The DataCite Metadata Schema is a list of core metadata properties chosen for accurate and consistent identification of a resource for citation and retrieval purposes, with recommended use instructions in the documentation. The resource that is being identified can be of any kind, but it is typically a dataset. We use the term ‘dataset’ in its broadest sense. We mean it to include not only numerical data, but any other research objects in keeping with DataCite’s mission. The metadata schema properties are presented and described in detail in the section DataCite Metadata Properties in this document.

While DataCite’s Metadata Schema has been expanded with each new version, it is nevertheless intended to be generic to the broadest range of research datasets, rather than customized to the needs of any particular discipline. DataCite metadata primarily supports citation and discovery of data; it is not intended to supplant or replace the discipline- or community-specific metadata that fully describes the data and is vital for understanding and reuse. DataCite clients are strongly encouraged to provide metadata in English whenever possible, in addition to any other language that may be required by the funder or hosting organization. 

The DataCite Metadata Schema supports language attributes for core properties. This release of the Metadata Schema contains better support for textual publications. Important changes are the addition of specific resource types such as journal, journal article, dissertation, etc., and also includes computational notebook and peer review, so that these types can be better identified. Also, a new property, relatedItem, is introduced which contains information about a resource related to the one being registered, e.g., a journal article, conference paper, or a book series. It can be used to describe a text citation where relatedIdentifier cannot be used because the related resource does not have an identifier. The remainder of the Version 4.4 changes are in response to requests from DataCite community members, people like you that have used the metadata schema and have imagined ways in which it might work better for their particular use cases. We are indebted to everyone who has provided us with their feedback, allowing us to improve our service for the broader DataCite community.


Lastly, we continue to support openness and the future extensibility of the schema by collaborating with the Dublin Core Metadata Initiative (DCMI) Science and Metadata Community (SAM)4 to maintain a DataCite to Dublin Core crosswalk, available at [DataCite Metadata Schema](https://schema.datacite.org/meta/kernel-4.4/). 

## Version 4.4 Update

Version 4.4 of the schema includes these changes:

● Addition of the new subproperty “classificationCode” in the Subject property.
● Addition of new values to the resourceTypeGeneral property:

○ Book
○ BookChapter
○ ComputationalNotebook
○ ConferencePaper
○ ConferenceProceeding
○ Dissertation
○ Journal
○ JournalArticle
○ OutputsManagementPlan
○ PeerReview
○ Preprint
○ Report
○ Standard

● Addition of a new relationType: “isPublishedIn” (indicates that A is published in B)
● Addition of a new relatedItem property, with subproperties to contain specific details for
containing publication information previously encoded in a description field with
descriptionType=”SeriesInformation” (for example, to define the journal name,
volume, and page number for an article resource). Subproperties:

○ relationType
○ relatedItemType
○ relatedItemIdentifier
○ relatedItemIdentifierType
○ creator
○ title
○ publicationYear
○ volume
○ issue
○ number
○ firstPage
○ lastPage
○ publisher
○ edition

DataCite Metadata Schema V 4.4 6

○ contributor

Major Documentation changes:

● The title of this document has changed to: DataCite Metadata Schema Documentation for the
Publication and Citation for Research Data and Other Research Outputs.
● Following community feedback and suggestions, this version includes further clarification as
regards the following contributorTypes: DataManager, DataCurator, ResearchGroup, and
HostingInstitution.

# Table of Contents
[Properties Overview](doc:datacite-metadata-schema-v44-properties-overview)
[Mandatory Properties](doc:datacite-metadata-schema-v44-mandatory-properties) 
[Recommended and Optional Metadata](doc:datacite-metadata-schema-v44-recommended-and-optional-properties)
[Earlier Version Update Notes](doc:datacite-metadata-schema-v44-earlier-version-update-notes) 
[Standard Values for Unknown Information](doc:datacite-metadata-schema-v44-standard-values-for-unknown-information) 
[Changes in Support of Software Citation (introduced in v4.1)](doc:schema-changes-software-citation) 
[FORCE11 Software Citation Principles Mapping (introduced in v4.1)](doc:schema-software-citation-principles-mapping) 
[XML Metadata Examples](doc:datacite-metadata-schema-v44-xml-metadata-examples)
[Dublic Core Mappings](https://schema.datacite.org/meta/kernel-4.4/doc/DataCite_DublinCore_Mapping.pdf)