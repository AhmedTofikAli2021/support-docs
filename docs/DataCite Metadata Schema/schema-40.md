---
title: DataCite Metadata Schema 4.0
excerpt: >-
  DataCite Metadata Working Group. (2016). DataCite Metadata Schema
  Documentation for the Publication and Citation of Research Data. Version 4.0.
  DataCite e.V. http://doi.org/10.5438/0013.
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
  "type": "danger",
  "body": "Note that this version of the schema is not backward compatible with previous schema versions. DataCite will provide ongoing support for the use of previous schema versions for a minimum of one year after the release of this version."
}
[/block]
Citation:

DataCite Metadata Working Group. (2016). DataCite Metadata Schema Documentation for the Publication and Citation of Research Data. Version 4.0. DataCite e.V. http://doi.org/10.5438/0012.

For notes in parentheses such as this (1), see the Notes section at the end of this document.
[block:api-header]
{
  "type": "basic",
  "title": "1. Introduction"
}
[/block]
## 1.1 The DataCite Consortium

Scholarly research is producing ever-increasing amounts of digital research data, and it depends on data to verify research findings, create new research, and share findings. In this context, what has been missing until recently, is a *persistent* approach to access, identification, sharing, and re-use of datasets. To address this need, the DataCite(1) international consortium was founded in late 2009 with these three fundamental goals:

*   establish easier access to scientific research data on the Internet,
*   increase acceptance of research data as legitimate, citable contributions to the scientific record, and
* support data archiving that will permit results to be verified and re-purposed for future study.

Since its founding in 2009, DataCite has grown and now spans the globe from Europe and North America to Asia and Australia. The aim of DataCite is to provide domain agnostic services to benefit scholars in a wide range of disciplines.

Key to DataCite service is the concept of a long-term or *persistent* identifier*.* A persistent identifier is an association between a character string and a resource. Resources can be files, parts of files, persons, organisations, abstractions, etc. DataCite uses *Digital Object Identifiers* (DOIs)(2) at the present time and is considering the use of other identifier schemes in the future. For this reason, the Metadata Schema has been designed with flexibility and extensibility in mind.

## 1.2 DataCite Community Participation

The Metadata Working Group would like to acknowledge the contributions to our work of many colleagues in our institutions who provided assistance of all kinds. Their help has been greatly appreciated. In addition, we are indebted to numerous individuals and organisations in the broader scholarly community who have taken an interest in this work. Because data citation and data management are evolving areas of concern, we look forward to continued interest. With this in mind, the Working Group provides an interactive discussion mechanism for DataCite members and clients to discuss the DataCite Metadata Schema and issues connected with metadata submitted to DataCite, as appropriate (3).  

## 1.3 The Metadata Schema

The DataCite Metadata Schema is a list of core metadata properties chosen for an accurate and consistent identification of a resource for citation and retrieval purposes, along with recommended use instructions. The resource that is being identified can be of any kind, but it is typically a dataset. We use the term ‘dataset’ in its broadest sense. We mean it to include not only numerical data, but any other research data outputs. The metadata schema properties are presented and described in detail in Section 2. 

In this release of the metadata schema, there are some larger changes. The most significant of these is resourceTypeGeneral property is now required. This change has been made to promote interoperability with DataCite partners such as ORCID, which in turn enhances the discoverability of research objects registered in the DataCite Metadata Store (MDS). 

A second major change is the addition of a new optional property to improve support for grant and funder information. The new property is called fundingReference, and it has subproperties for the funder name, award, and award information. This also means that the contributorType of “funder” is now deprecated.

Lastly, in this new version, the description of geographic locations is made to be both human and machine readable as well as more interoperable with external standards such as INSPIRE (4) and Dublin Core. This is accomplished by adding optional subproperties for directional metadata rather than relying on careful data entry.

Note that the three changes mentioned above are not backward compatible with previous schema versions. DataCite will provide ongoing support for the use of previous schema versions for a minimum of one year after the release of this version.

An additional significant change included in this release, is support for the optional provision of family name and given name along with creatorName as well as contributorName. We are introducing these subproperties to promote interoperability with ORCID and, generally, to provide the ability to generate citation-ready author names.

The remainder of the v. 4.0 changes are in response to requests from DataCite community members, people like you that have used the metadata schema and have imagined ways in which it might work better for their particular use case. We are indebted to everyone who has provided us with their feedback, allowing us to improve our service for the broader DataCite community.
For a list of all changes, see Section 1.4.

Lastly, in order to support openness and future extensibility of the schema, a collaboration between DataCite and the Dublin Core Metadata Initiative (DCMI) Science and Metadata Community (SAM) (5) has produced a version of the v. 3.1 schema in a Dublin Core Application Profile format which is currently out for review and comment via a dedicated Google forum (6). The profile is made available in conjunction with the Metadata Working Group’s DataCite in RDF work which is also nearing completion.

## 1.4 Version 4.0 Update

Version 4.0 of the schema includes these changes:

- Allowing more than one nameIdentifier per creator or contributor
- Addition of new optional subproperties for creatorName and contributorName
  - familyName
  - givenName
- Addition of new titleType "Other"
- Addition of new subproperty for subjectScheme
  - subjectScheme
    - valueURI
- Changing resourceTypeGeneral from optional to mandatory
- Addition of a new relatedIdentifierType option "IGSN"

- Addition of a new descriptionType &quot;TechnicalInfo&quot;

- Addition of a new subproperty for GeoLocation "geoLocationPolygon"
- Changing the definition of the existing GeoLocation sub properties (geoLocationPoint, and geoLocationBox)

- Addition of a new property: FundingReference, with subproperties
  - funderName
  - funderIdentifier
    - funderIdentifierType
  - awardNumber
  - awardURI
  - awardTitle
- Deprecation of contributorType "funder"; (as a result of adding the new property "FundingReference")

Version 4.0 of the documentation includes these changes:

- Provision of a link to guidelines for how to write the ORCID ID (See properties 2.2.1 and 7.3.1 nameIdentifierScheme)
- Adjustment of the instructions for resourceTypeGeneral option "collection" (See Appendix 1, Table 7)

Note that, while the property resourceType has been relocated in the documentation to the mandatory property section, it retains its original numbering (10).
[block:api-header]
{
  "type": "basic",
  "title": "2. DataCite Metadata Properties"
}
[/block]
## 2.1 Overview

The properties of the DataCite Metadata Schema are presented in this section. More detailed descriptions of the properties, and their related sub-properties, are provided in Section 2.3. 

There are three different levels of obligation for the metadata properties:

* Mandatory (M) properties must be provided,
* Recommended (R ) properties are optional, but strongly recommended for interoperability and 
* Optional (O) properties are optional and provide richer description. 

Those clients who wish to enhance the prospects that their metadata will be found, cited and linked to original research are strongly encouraged to submit the Recommended as well as Mandatory set of properties. Together, the Mandatory and Recommended set of properties and their sub-properties are especially valuable to information seekers and added-service providers, such as indexers. The Metadata Working Group members strongly urge the inclusion of metadata identified as Recommended for the purpose of achieving greater exposure for the resource’s metadata record, and therefore, the underlying research itself. 

The properties listed in Table 1 have the obligation level Mandatory, and must be supplied when submitting DataCite metadata. The properties listed in Table 2 have one of the obligation levels Recommended or Optional, and may be supplied when submitting DataCite metadata. 

The prospect that a resource's metadata will be found, cited and linked is enhanced by using the combined Mandatory and Recommended "super set" of properties and sub-properties. These are highlighted in Tables 1 and 2, as shown in the example below.
[block:parameters]
{
  "data": {
    "h-0": "ID",
    "h-1": "DataCite-Property",
    "h-2": "Occ",
    "h-3": "Definition",
    "h-4": "Allowed values, examples, other constraints",
    "0-0": "6",
    "0-1": "Subject",
    "0-2": "0-n",
    "0-3": "Subject, keyword, classification code, or key phrase describing the resource.",
    "0-4": "Free text."
  },
  "cols": 5,
  "rows": 1
}
[/block]
Of the Recommended set of properties, the most important to use is the **Description** property, together with the Recommended sub-properties descriptionType ="Abstract" (see Section 2.3 and property 17). Appendix 1 includes detailed descriptions of controlled list values, using the same shading to indicate those values that are especially important for information seekers and added-service providers. It cannot be emphasized enough how valuable an Abstract is to other scholars in finding the resource and then determining whether or not the resource, once found, is worth investigating further, re-using or validating.

### Table 1: DataCite Mandatory Properties
[block:parameters]
{
  "data": {
    "h-0": "ID",
    "h-1": "Property",
    "h-2": "Obligation",
    "0-0": "1",
    "1-0": "2",
    "2-0": "3",
    "3-0": "4",
    "4-0": "5",
    "5-0": "10",
    "0-1": "Identifier (with mandatory type sub-property)",
    "1-1": "Creator (with optional name identifier and affiliation sub-properties)",
    "2-1": "Title (with optional type sub-properties)",
    "3-1": "Publisher",
    "4-1": "PublicationYear",
    "5-1": "ResourceType (with mandatory general type description sub-property)",
    "0-2": "M",
    "1-2": "M",
    "2-2": "M",
    "3-2": "M",
    "4-2": "M",
    "5-2": "M"
  },
  "cols": 3,
  "rows": 6
}
[/block]
### Table 2: DataCite Recommended and Optional Properties
[block:parameters]
{
  "data": {
    "h-0": "ID",
    "h-1": "Property",
    "h-2": "Obligation",
    "0-0": "6",
    "1-0": "7",
    "2-0": "8",
    "3-0": "9",
    "0-1": "Subject (with scheme sub-property)",
    "1-1": "Contributor (with type, name identifier, and affiliation sub-properties)",
    "2-1": "Date (with type sub-property)",
    "3-1": "Language",
    "4-0": "11",
    "5-0": "12",
    "6-0": "13",
    "7-0": "14",
    "8-0": "15",
    "9-0": "16",
    "4-1": "AlternateIdentifier (with type sub-property)",
    "5-1": "RelatedIdentifier (with type and relation type sub-properties)",
    "6-1": "Size",
    "7-1": "Format",
    "8-1": "Version",
    "9-1": "Rights",
    "10-0": "17",
    "11-0": "18",
    "0-2": "R",
    "1-2": "R",
    "2-2": "R",
    "3-2": "O",
    "4-2": "O",
    "5-2": "R",
    "6-2": "O",
    "7-2": "O",
    "8-2": "O",
    "9-2": "O",
    "10-1": "Description (with type sub-property)",
    "11-1": "GeoLocation (with point, box and polygon sub-properties)",
    "12-1": "FundingReference (with name, identifier, and award related sub-properties)",
    "12-0": "19",
    "10-2": "R",
    "11-2": "R",
    "12-2": "0"
  },
  "cols": 3,
  "rows": 13
}
[/block]
## 2.2 Citation

Because many users of this schema are members of a variety of academic disciplines, DataCite remains discipline-agnostic concerning matters pertaining to academic style sheet requirements. Therefore, DataCite encourages rather than requires a particular citation format (7). In keeping with this approach, the following is the preferred format for rendering a DataCite citation for human readers using the first five properties of the schema:

> Creator (PublicationYear): Title. Publisher. Identifier 

It may also be desirable to include information from two optional properties, Version and ResourceType (as appropriate). If so, the preferred form is as follows: 

> Creator (PublicationYear): Title. Version. Publisher. ResourceType. Identifier

For citation purposes, DataCite prefers that DOI names are displayed as linkable, permanent URLs. The Identifier may appear in its original format. If the original format is chosen, be sure to include the characters “doi:" pre-pended to the Identifier as in “doi:10.1234/abc.” 

For resources that do not have a standard publication year value, DataCite suggests that PublicationYear should include the date that is preferred for use in a citation.

Here are several examples:
* Irino, T; Tada, R (2009): Chemical and mineral compositions of sediments from ODP Site 127-797. V. 2.1. Geological Institute, University of Tokyo. http://doi.org/10.1594/PANGAEA.726855 
* Geofon operator (2009): GEFON event gfz2009kciu (NW Balkan Region). GeoForschungsZentrum Potsdam (GFZ). http://doi.org/10.1594/GFZ.GEOFON.gfz2009kciu 
* Denhard, Michael (2009): dphase_mpeps: MicroPEPS LAF-Ensemble run by DWD for the MAP D-PHASE project. World Data Center for Climate. Dataset. http://doi.org/10.1594/WDCC/dphase_mpeps 

A special note regarding citation of dynamic datasets: 

For datasets that are continuously and rapidly updated, there are special challenges both in citation and preservation. For citation, three approaches are possible:
1. Cite a specific slice (the set of updates to the dataset made during a particular period of time or to a particular area of the dataset);
2. Cite a specific snap-shot (a copy of the entire dataset made at a specific time);
3. Cite the continuously updated dataset, but add an Access Date and Time to the citation.

Note that a "slice" and "snap-shot" are versions of the dataset and require unique identifiers. The third option is controversial, because it necessarily means that following the citation does not result in observation of the resource as cited.

## 2.3 DataCite Properties

Table 3 provides a detailed description of the mandatory properties, which *must* be supplied with any initial metadata submission to DataCite, together with their sub-properties. **If one of the required properties is unavailable** , please use one of the standard (machine-recognizable) codes listed in Appendix 3, Table 11. In Table 4, the Recommended and Optional properties are described in detail. For an example of how to make a submission in XML format, please see the [XML Examples](https://schema.datacite.org/meta/kernel-4.0/) provided on the DataCite Metadata Schema Repository(8) website.

Throughout this document, a naming convention has been used for all properties and sub-properties as follows: properties begin with a capital letter, whereas sub-properties begin with a lower case letter. If the name is a compound of more than one word, subsequent words begin with capital letters.(9)

As with Tables 1 and 2,Tables 3 and 4 use shading to identify the combined Mandatory and Recommended "super set" of properties and sub-properties that enhance the prospect that the resource's metadata will be found, cited and linked.

The third column, Occurrence (Occ), indicates cardinality/quantity constraints for the properties as follows:

0-n = optional and repeatable
0-1 = optional, but not repeatable
1-n = required and repeatable
1 = required, but not repeatable

NOTE:
XML provides an xml:lang attribute (10) that can be used on the properties Title, Subject and Description. This provides a way to describe the language used for the content of the specified properties. The schema provides a Language property to be used to describe the language of the resource.

### Table 3: Expanded DataCite Mandatory Properties
[block:parameters]
{
  "data": {
    "h-0": "ID",
    "h-1": "DataCite-Property",
    "h-2": "Occ",
    "h-3": "Definition",
    "h-4": "Allowed values, examples, other constraints",
    "0-3": "The Identifier is a unique string that identifies a resource.",
    "0-0": "1",
    "0-1": "Identifier",
    "0-2": "1",
    "0-4": "DOI (Digital Object Identifier) registered by a DataCite member. Format should be 10.1234/foo or 10.12345/foo",
    "1-0": "1.1",
    "1-1": "identifierType",
    "1-2": "1",
    "1-4": "Controlled List Value: DOI",
    "1-3": "The type of Identifier.",
    "2-0": "2",
    "3-0": "2.1",
    "4-0": "2.1.1",
    "2-1": "Creator",
    "3-1": "creatorName",
    "2-2": "1-n",
    "3-2": "1",
    "4-1": "familyName",
    "5-0": "2.1.2",
    "5-1": "givenName",
    "4-2": "0-1",
    "5-2": "0-1",
    "2-3": "The main researchers involved in producing the data, or the authors of the publication, in priority order.",
    "3-3": "The name of the creator.",
    "4-3": "The surname or last name of the creator.",
    "5-3": "The personal or first name of the creator.",
    "2-4": "May be a corporate/institutional or personal name. Note: DataCite infrastructure supports up to 8000-10000 names. For name lists above that size, consider attribution via linking to the related metadata.",
    "3-4": "Examples: Charpy, Antoine; Jemison, Mae\nThe personal name format should be: family, given. Non-roman names may be transliterated according to the ALA-LC schemes (11).",
    "4-4": "Examples based on the 2.1 names: Charpy; Jemison",
    "5-4": "Examples based on the 2.1 names: Antoine; Mae",
    "6-0": "2.2",
    "7-0": "2.2.1",
    "8-0": "2.2.1",
    "6-1": "nameIdentifier",
    "7-1": "nameIdentifierScheme",
    "8-1": "schemeURI",
    "6-2": "0-n",
    "7-2": "1",
    "8-2": "0-1",
    "6-3": "Uniquely identifies an individual or legal entity, according to various schemes.",
    "7-3": "The name of the name identifier scheme.",
    "8-3": "The URI of the name identifier scheme.",
    "8-4": "Examples: [http://www.isni.org](http://www.isni.org) [http:/orcid.org](http://orcid.org)",
    "7-4": "If nameIdentifier is used, nameIdentifierScheme is mandatory.\nExamples: ORCID (12), \nISNI (13)",
    "6-4": "The format is dependent upon scheme.",
    "9-0": "2.3",
    "10-0": "3",
    "11-0": "3.1",
    "12-0": "4",
    "13-0": "5",
    "14-0": "10",
    "15-0": "10.1",
    "15-1": "resourceTypeGeneral",
    "14-1": "ResourceType",
    "13-1": "PublicationYear",
    "12-1": "Publisher",
    "10-1": "Title",
    "11-1": "titleType",
    "9-1": "affiliation",
    "9-2": "0-n",
    "9-3": "The organisational or institutional affiliation of the creator.",
    "10-2": "1-n",
    "10-3": "A name or title by which a resource is known.",
    "11-3": "The type of Title.",
    "11-2": "0-1",
    "10-4": "Free text.",
    "9-4": "Free text.",
    "11-4": "Controlled List Values:_\nAlternativeTitle\nSubtitle\nTranslatedTitleOther",
    "12-2": "1",
    "12-3": "The name of the entity that holds, archives, publishes prints, distributes, releases, issues, or produces the resource. This property will be used to formulate the citation, so consider the prominence of the role.",
    "12-4": "Examples: World Data Center for Climate (WDCC); GeoForschungsZentrum Potsdam (GFZ); Geological Institute, University of Tokyo",
    "13-2": "1",
    "13-3": "The year when the data was or will be made publicly available.",
    "13-4": "YYYY\nIf an embargo period has been in effect, use the date when the embargo period ends.In the case of datasets, \"publish;\" is understood to mean making the data available on a specific date to the community of researchers. If there is no standard publication year value, use the date that would be preferred from a citation perspective.",
    "14-2": "1",
    "15-2": "1",
    "14-3": "A description of the resource.",
    "14-4": "The format is open, but the preferred format is a single term of some detail so that a pair can be formed with the sub-property.\nText formats can be free-text OR terms from the CASRAI Publications resource type list. (14)\nExamples: \nDataset/Census Data, where \"Dataset\" is resourceTypeGeneral value and \"Census Data\" is ResourceType value.\nText/Conference Abstract, where \"Text\" is resourceTypeGeneral value and \"Conference Abstract\" is resourceType value aligned with CASRAI Publications term.",
    "15-3": "The general type of a resource.",
    "15-4": "Controlled List Values:\nAudiovisual\nCollection\nDataset\nEvent\nImage\nInteractiveResource\nModel\nPhysicalObject\nService\nSoftware\nSound\nText (15)\nWorkflow \nOther \nSee Appendix for definitions and examples."
  },
  "cols": 5,
  "rows": 16
}
[/block]
*PublicationYear: Additional guidance*

PublicationYear : the year when the data was or will be made publicly available. In the case of datasets, "publish" is understood to mean making the data available on a specific date to the community of researchers.

- If that date cannot be determined, use the date of registration.
- If an embargo period has been in effect, use the date when the embargo period ends.
- If there is no standard publication year value, use the date that would be preferred from a citation perspective.

*In the case of a digitised version of a physical object*

If the DOI is being used to identify a digitised version of an original item, the recommended approach is to supply the PublicationYear for the digital version and not the original object.

The Title field may be used to convey the approximate or known date of the original object. Other metadata properties available for additional date information about the object include: Subject and Description. However, only Title will be part of the citation.

Here are two examples of citations using dates or date information in the titles.

Shaked, Edith; (2015): Map by the German military, dated January 20, 1942 - date of the Wannsee Conference; Unpublished. [http://doi.org/10.13140/RG.2.1.4448.8405](http://doi.org/10.13140/RG.2.1.4448.8405)

Ketchell, Shelly D; (2005): Re-locating Japanese Canadian history: sugar beet farms as carceral sites in Alberta and Manitoba, February 1942-January 1943. The University of British Columbia.   [http://doi.org/10.14288/1.0099801](http://doi.org/10.14288/1.0099801%20)

*Guidance for handling missing mandatory property values*

If the completion of any of the mandatory properties presents a difficulty, use of standard machine-recognizable codes is strongly advised. A set of the codes is provided in Appendix 3, Table 11. However, we recommend that you consider the resulting effect on the citation created from the metadata provided.

Here is an example of a citation that uses machine-readable substitutions for all but one of the required metadata properties. Obviously the more metadata that is supplied, the more information is conveyed. Note that is a demonstration DOI and not an actual identifier, so the link will not work.

(:unkn)(9999):(:none).(:null).Dataset. [http://doi.org/10.5072/FK2JW8C992](http://doi.org/10.5072/FK2JW8C992)

### Table 4: Expanded DataCite Recommended and Optional Properties--IN PROGRESS
[block:parameters]
{
  "data": {
    "h-0": "ID",
    "h-1": "DataCite-Property",
    "h-2": "Occ",
    "h-3": "Definition",
    "h-4": "Allowed values, examples, other constraints",
    "0-0": "6",
    "1-0": "6.1",
    "2-0": "6.2",
    "3-0": "6.3",
    "4-0": "7",
    "0-1": "Subject",
    "1-1": "subjectScheme",
    "2-1": "schemeURI",
    "3-1": "valueURI",
    "4-1": "Contributor",
    "0-2": "0-n",
    "1-2": "0-1",
    "2-2": "0-1",
    "3-2": "0-1",
    "4-2": "0-n",
    "0-3": "Subject, keyword, classification code, or key phrase describing the resource",
    "1-3": "The name of the subject scheme or classification code or authority if one is used.",
    "3-3": "The URI of the subject term.",
    "2-3": "The URI of the subject identifier scheme.",
    "2-4": "Examples: [http://id.loc.gov/authorities/subjects](http://id.loc.gov/authorities/subjects)  [http://udcdata.info/](http://udcdata.info/)",
    "0-4": "Free text.",
    "1-4": "Free text.",
    "3-4": "Example(s) [http://id.loc.gov/authorities/subjects/sh85026196](http://id.loc.gov/authorities/subjects/sh85026196) [http://udcdata.info/037278](http://udcdata.info/037278)",
    "4-3": "The institution or person responsible for collecting, managing, distributing, or otherwise contributing to the development of the resource.",
    "4-4": "Note: DataCite infrastructure supports up to between 8000-10000 names. For name lists above that size, consider attribution via linking to the related metadata.",
    "5-1": "contributorType",
    "5-0": "7.1",
    "6-0": "7.2",
    "7-0": "7.2.1",
    "8-0": "7.2.2",
    "9-0": "7.3",
    "6-1": "contributorName",
    "7-1": "familyName",
    "8-1": "givenName",
    "9-1": "nameIdentifier",
    "9-2": "0-n",
    "9-3": "Uniquely identifies an individual or legal entity, according to various schemes.",
    "5-2": "1",
    "6-2": "1",
    "7-2": "0-1",
    "8-2": "0-1",
    "5-3": "The type of contributor of the resource.",
    "6-3": "The name of the contributor.",
    "7-3": "The surname or last name of the contributor.",
    "8-3": "The personal or first name of the contributor.",
    "5-4": "If Contributor is used, then contributorType is mandatory.\nControlled List Values:\nContactPerson \nDataCollector\nDataCurator \nDataManager \nDistributor\nEditor\nHostingInstitution\nProducer\nProjectLeader\nProjectManager\nProjectMember\nRegistrationAgency\nRegistrationAuthority\nRelatedPerson\nResearcher\nResearchGroup\nRightsHolder\nSponsor\nSupervisor\nWorkPackageLeader\nOther \nSee Appendix for definitions.",
    "6-4": "If Contributor is used, then contributorName is mandatory.\nExamples: Patel, Emily; Nyugen, John\nThe personal name format may be: family, given. Non-roman names should be transliterated according to the ALA-LC schemes (16).",
    "7-4": "The surname or last name of the contributor. \nExamples based on the 7.2 names: Patel; Nyugen",
    "8-4": "The personal or first name of the contributor. \nExamples based on the 7.2 names: Emily; John",
    "9-4": "The format is dependent upon scheme.",
    "11-4": "Examples: [http://www.isni.org](http://www.isni.org)   [http://orcid.org](http://orcid.org) [http://www.crossref.org/fundref/](http://www.crossref.org/fundref/)",
    "11-0": "7.3.2",
    "12-0": "7.4",
    "13-0": "8",
    "14-0": "8.1",
    "15-0": "9",
    "16-0": "11",
    "11-1": "schemeURI",
    "12-1": "affiliation",
    "13-1": "Date",
    "14-1": "dateType",
    "15-1": "Language",
    "16-1": "AlternateIdentifier",
    "11-2": "0-1",
    "12-2": "0-n",
    "13-2": "0-n",
    "16-2": "0-n",
    "15-2": "0-1",
    "14-2": "1",
    "12-3": "The organisational or institutional affiliation of the contributor.",
    "12-4": "Free text.",
    "11-3": "The URI of the name identifier scheme.",
    "13-3": "Different dates relevant to the work.",
    "14-3": "The type of date.",
    "15-3": "The primary language of the resource.",
    "16-3": "An identifier or identifiers other than the primary Identifier applied to the resource being registered. This may be any alphanumeric string which is unique within its domain of issue. May be used for local identifiers. AlternateIdentifier should be used for another identifier of the same instance (same location, same file).",
    "10-0": "7.3.1",
    "10-1": "nameIdentifierScheme",
    "10-2": "1",
    "10-3": "The name of the name identifier scheme.",
    "10-4": "If nameIdentifier is used, nameIdentifierScheme is mandatory.\nExamples:\nORCID (17), \nISNI (18)",
    "13-4": "YYYY,YYYY-MM-DD, YYYY-MM-DDThh:mm:ssTZD or any other format or level of granularity described in W3CDTF. (19) Use RKMS-ISO860120 standard for depicting date ranges.\nExample: 2004-03-02/2005-06-02",
    "14-4": "If Date is used, dateType is mandatory.\nControlled List Values:\nAccepted\nAvailable\nCopyrighted\nCollected\nCreated\nIssued\nSubmitted\nUpdated\nValid\nSee Appendix for definitions and recommendations.",
    "15-4": "Allowed values are taken from IETF BCP 47, ISO 639-1 language codes.\nExamples: en, de, fr",
    "16-4": "Free text.\nExample:E-GEOD-34814",
    "17-0": "11.1",
    "18-0": "12",
    "19-0": "12.1",
    "20-0": "12.2",
    "21-0": "12.3",
    "22-0": "12.4",
    "23-0": "12.5",
    "24-0": "13",
    "25-0": "14",
    "26-0": "15",
    "27-0": "16",
    "28-0": "16.1",
    "29-0": "17",
    "30-0": "17.1",
    "31-0": "18",
    "32-0": "18.1",
    "33-0": "18.1.1",
    "34-0": "18.1.2",
    "35-0": "18.2",
    "36-0": "18.2.1",
    "37-0": "18.2.2",
    "38-0": "18.2.3",
    "39-0": "18.2.4",
    "40-0": "18.3",
    "41-0": "18.4",
    "42-0": "18.4.1",
    "43-0": "18.4.1.1",
    "44-0": "18.4.1.2",
    "45-0": "19",
    "46-0": "19.1",
    "47-0": "19.2",
    "49-0": "19.3",
    "50-0": "19.3.1",
    "51-0": "19.4",
    "51-1": "awardTitle",
    "50-1": "awardURI",
    "49-1": "awardNumber",
    "47-1": "funderIdentifier",
    "46-1": "funderName",
    "48-0": "19.2.1",
    "48-1": "funderIdentifierType",
    "45-1": "FundingReference",
    "44-1": "pointLatitude",
    "43-1": "pointLongitude",
    "42-1": "polygonPoint",
    "41-1": "geoLocationPolygon",
    "40-1": "geoLocationPlace",
    "39-1": "northBoundLatitude",
    "38-1": "souththBoundLatitude",
    "37-1": "eastBoundLatitude",
    "36-1": "westBoundLatitude",
    "35-1": "geoLocationBox",
    "34-1": "pointLatitude",
    "33-1": "pointLongitude",
    "32-1": "geoLocationPoint",
    "31-1": "GeoLocation",
    "30-1": "descriptionType",
    "29-1": "Description",
    "17-1": "alternateIdentifierType",
    "18-1": "RelatedIdentifier",
    "19-1": "relatedIdentifierType",
    "20-1": "relationType",
    "21-1": "relatedMetadataScheme",
    "22-1": "schemeURI",
    "23-1": "schemeType",
    "24-1": "Size",
    "25-1": "Format",
    "26-1": "Version",
    "27-1": "Rights",
    "28-1": "rightsURI"
  },
  "cols": 5,
  "rows": 52
}
[/block]

[block:api-header]
{
  "title": "3. XML Example"
}
[/block]
Examples for various resource types and special cases can be found at http://schema.datacite.org/meta/kernel-4/index.html.
[block:api-header]
{
  "type": "basic",
  "title": "4. XML Schema"
}
[/block]
The XML Schema is available here: http://schema.datacite.org/meta/kernel-4/metadata.xsd

```
> DataCite Metadata Working Group; (2016): DataCite Metadata Schema for the Publication and Citation of Research Data v4.0; DataCite e.V.. http://doi.org/10.5438/0013
```

Note that the schema and this documentation will always have the same version number. Each subsequent version of the schema will be at this same location using an address composed in the same manner, that is: http://schema.datacite.org/meta/kernel-versionnumber/metadata.xsd. Earlier versions will continue to be available at their previous locations for backward compatibility.
[block:api-header]
{
  "title": "Appendix 1: Controlled List Definitions--placeholder"
}
[/block]

[block:api-header]
{
  "title": "Appendix 2: Earlier Version Update Notes--placeholder"
}
[/block]

[block:api-header]
{
  "title": "Appendix 3: Additional Information"
}
[/block]
###Table 11: Standard values for unknown information
[block:parameters]
{
  "data": {
    "h-0": "Code",
    "h-1": "Value",
    "0-0": "(:unac)",
    "0-1": "temporarily inaccessible",
    "1-0": "(:unal)",
    "2-0": "(:unap)",
    "3-0": "(:unas)",
    "1-1": "unallowed, suppressed intentionally",
    "2-1": "not applicable, makes no sense",
    "3-1": "value unassigned (e.g., Untitled)",
    "4-0": "(:unav)",
    "5-0": "(:unkn)",
    "6-0": "(:none)",
    "7-0": "(:null)",
    "8-0": "(:tba)",
    "9-0": "(:etal)",
    "4-1": "value unavailable, possibly unknown",
    "5-1": "known to be unknown (e.g., Anonymous, Inconnue)",
    "6-1": "never had a value, never will",
    "7-1": "explicitly and meaningfully empty",
    "8-1": "to be assigned or announced late",
    "9-1": "too numerous to list (et alia"
  },
  "cols": 2,
  "rows": 10
}
[/block]

[block:api-header]
{
  "title": "Notes"
}
[/block]
1. http://schema.datacite.org/    
2. DOIs are administered by the International DOI Foundation, http://www.doi.org/ 
3. Join the discussion here: schema.datacite.org.
4.  http://inspire-geoportal.ec.europa.eu/ 
5. For more information on DCMI SAM, see http://wiki.dublincore.org/index.php/DCMI_Science_And_Metadata. 
6. The Application Profile forum is available here: https://groups.google.com/a/datacite.org/forum/#!forum/dc2map 
7.  In collaboration with CrossRef, DataCite has created a DOI Citation Formatter Service available at http://crosscite.org/citeproc/. The user can choose from more than 500 different citation formats in 45 different languages.
8.  http://schema.datacite.org/ 
9. This convention is known as “camelCase.” https://en.wikipedia.org/wiki/CamelCase 
10. Allowed values IETF BCP 47, ISO 639-1 language codes, e.g. en, de, fr
11. http://www.loc.gov/catdir/cpso/roman.html
12. http://orcid.org/.  When entering an ORCID, follow these style guidelines: http://support.orcid.org/knowledgebase/articles/116780-structure-of-the-orcid-identifier 
13. http://www.isni.org/
14. http://dictionary.casrai.org/Output_Types 
15. Combine “Text” with free-text or terms from the CASRAI Publications resource type list found here: http://dictionary.casrai.org/Output_Types 
16. http://www.loc.gov/catdir/cpso/roman.html
17. http://orcid.org/ When entering an ORCID, follow these style guidelines: http://support.orcid.org/knowledgebase/articles/116780-structure-of-the-orcid-identifier 
18. http://www.isni.org/
19. http://www.w3.org/TR/NOTE-datetime
20. The standard is documented here: http://www.ukoln.ac.uk/metadata/dcmi/collection-RKMS-ISO8601/ 
21. Based on the work of the Earth Science Information Partners (ESIP). For more guidance, see: http://wiki.esipfed.org/index.php/Interagency_Data_Stewardship/Citations/provider_guidelines#Note_on_Versioning_and_Locators
22. Use WGS 84 (World Geodetic System) coordinates. Use only decimal numbers for coordinates. Longitudes are -180 to 180 (0 is Greenwich, negative numbers are west, positive numbers are east), Latitudes are -90 to 90 (0 is the equator; negative numbers are south, positive numbers north).
23. The FundRef service is now called “Open Funder Registry” (http://fundref.org/fundingdata/registry.html) and Crossref Funder ID is the new name for a Fundref identifier.
24. Where there is direct correspondence with the Dublin Core Metadata, DataCite definitions have borrowed liberally from the DCMI definitions. See: http://dublincore.org/documents/dcmi-terms/index.shtml
25. An education module on workflows prepared by DataONE is available at http://www.dataone.org/sites/all/documents/L10_AnalysisWorkflows.pptx
26. Two additional schema code level changes are the allowance of keeping optional wrapper elements empty and the allowance of arbitrary ordering of elements (by removal of <xs:sequence>).
27. The standard is documented here: http://www.ukoln.ac.uk/metadata/dcmi/collection-RKMS-ISO8601/ 
28. Allowed values IETF BCP 47, ISO 639-1 language codes, e.g. en, de, fr