---
title: DataCite Metadata Schema v4.1 Mandatory Properties
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: schema-optional-properties-v41
      title: DataCite Metadata Schema v4.1 Recommended and Optional Properties
---
[block:callout]
{
  "type": "success",
  "title": "Recommended for discovery",
  "body": "All of the mandatory properties are recommended for discovery."
}
[/block]
# 1 Identifier
**Occurrence:** 1
**Definition: ** The Identifier is a unique string that identifies a resource. For software, determine whether the identifier is for a specific version of a piece of software, (per the Force11 Software Citation Principles[(1)](#section-notes), or for all versions.
**Allowed values, examples, other constraints:** DOI (Digital Object Identifier) registered by a DataCite member. Format should be “10.1234/foo”

## 1.1 identifierType
**Occurrence:** 1
**Definition: ** The type of Identifier.
**Allowed values, examples, other constraints:** Controlled List Value: DOI

# 2 Creator
**Occurrence:** 1-n
**Definition: ** The main researchers involved in producing the data, or the authors of the publication, in priority order. To supply multiple creators, repeat this property.
**Allowed values, examples, other constraints:** May be a corporate/institutional or personal name. 

Note: DataCite infrastructure supports up to 8000-10000 names. For name lists above that size, consider attribution via linking to the related metadata.

## 2.1 creatorName
**Occurrence:** 1
**Definition: ** The full name of the creator.
**Allowed values, examples, other constraints:** 
Examples: 
- Charpy, Antoine
- Foo Data Center

Note: The personal name format should be: family, given. Non-Roman names may be transliterated according to the [ALA-LC schemas](http://www.loc.gov/catdir/cpso/roman.html).

## 2.1.1 nameType
**Occurrence:** 0-1
**Definition: ** The type of name
**Allowed values, examples, other constraints:** 
Controlled List Values:
- Organizational
- Personal

## 2.2 givenName
**Occurrence:** 0-1
**Definition: ** The personal or first name of the creator.
**Allowed values, examples, other constraints:** 
Examples based on the 2.1 names: 
- Antoine
- Mae

## 2.3 familyName
**Occurrence:** 0-1
**Definition: ** The surname or last name of the creator.
**Allowed values, examples, other constraints:** 
Examples based on the 2.1 names: 
- Charpy
- Jemison

## 2.4 nameIdentifier
**Occurrence:** 0-n
**Definition: ** Uniquely identifies an individual or legal entity, according to various schemas.
**Allowed values, examples, other constraints:** The format is dependent upon schema.

## 2.4.1 nameIdentifierScheme
**Occurrence:** 1
**Definition: ** The name of the name identifier schema.
**Allowed values, examples, other constraints:** If nameIdentifier is used, nameIdentifierScheme is mandatory.
Examples: 
- [ORCID](http://orcid.org/). When entering an ORCID, follow [these style guidelines](http://support.orcid.org/knowledgebase/articles/116780-structure-of-the-orcid-identifier)
- [ISNI](http://www.isni.org/)

## 2.4.2 schemeURI
**Occurrence:** 0-1
**Definition: ** The URI of the name identifier schema.
**Allowed values, examples, other constraints:** 
Examples:
- http://www.isni.org
- http://orcid.org

## 2.5 affiliation
**Occurrence:** 0-n
**Definition: ** The organizational or institutional affiliation of the creator.
**Allowed values, examples, other constraints:** Free text.

# 3 Title
**Occurrence:** 1-n
**Definition: ** A name or title by which a resource is known. May be the title of a dataset or the name of a piece of software.
**Allowed values, examples, other constraints:** Free text.

## 3.1 titleType
**Occurrence:** 0-1
**Definition: ** The type of Title.
**Allowed values, examples, other constraints:** 
Controlled List Values:
- AlternativeTitle
- Subtitle
- TranslatedTitle
- Other

# 4 Publisher
**Occurrence:** 1
**Definition: ** The name of the entity that holds, archives, publishes prints, distributes, releases, issues, or produces the resource. This property will be used to formulate the citation, so consider the prominence of the role. For software, use Publisher for the code repository. If there is an entity other than a code repository, that "holds, archives, publishes, prints, distributes, releases, issues, or produces" the code, use the property Contributor/contributorType/ hostingInstitution for the code repository.
**Allowed values, examples, other constraints:** 
Examples:
- World Data Center for Climate (WDCC)
- GeoForschungsZentrum Potsdam (GFZ)
- Geological Institute
- University of Tokyo
- GitHub

# 5 PublicationYear
**Occurrence:** 1
**Definition: ** The year when the data was or will be made publicly available. 
**Allowed values, examples, other constraints:** YYYY
- If the date of public availability cannot be determined, use the date of registration.
- If an embargo period has been in effect, use the date when the embargo period ends.
- In the case of datasets, "publish" is understood to mean making the data available on a specific date to the community of researchers.
- In the case of resources such as software or dynamic data where there may be multiple releases in one year, include the Date/dateType/dateInformation property and sub-properties to provide more information about the publication or release date details.
- If there is no standard publication year value, use the date that would be preferred from a citation perspective.

*In the case of a digitised version of a physical object*

If the DOI is being used to identify a digitised version of an original item, the recommended approach is to supply the PublicationYear for the digital version and not the original object.

The Title field may be used to convey the approximate or known date of the original object. Other metadata properties available for additional date information about the object include: Subject and Description. However, only Title will be part of the citation.

Here are two examples of citations using dates or date information in the titles.

>Schmidt, S., Andersen, V., Belviso, S., & Marty, J.-C. (2002). Dissolved and particulate thorium 234 concentration at time series station DYFAMED from date 1995-05-07 (Data set). PANGAEA - Data Publisher for Earth & Environmental Science. https://doi.org/10.1594/pangaea.183607

>Tape, K. D. (2015). Aerial Images of Alaska’s Arctic Coastal Plain; 1948-1949. U.S. Geological Survey. (Image). https://doi.org/10.5066/f79021tb

# 10 ResourceType
**Occurrence:** 1
**Definition: ** A description of the resource.
**Allowed values, examples, other constraints:** The format is open, but the preferred format is a single term of some detail so that a pair can be formed with the sub-property.
Text formats can be free-text OR terms from the [CASRAI Publications resource type list](http://dictionary.casrai.org/Output_Types).
Examples:
- Dataset/Census Data, where 'Dataset' is resourceTypeGeneral value and 'Census Data' is ResourceType value.
- Text/Conference Abstract, where 'Text' is
resourceTypeGeneral value and 'Conference Abstract' is resourceType value aligned with CASRAI Publications term.

## 10.1 resourceTypeGeneral
**Occurrence:** 1
**Definition: ** The general type of a resource.
**Allowed values, examples, other constraints:** 
Controlled List Values:
[block:callout]
{
  "type": "info",
  "title": "Correspondence with Dublin Core",
  "body": "Where there is direct correspondence with the Dublin Core Metadata, DataCite definitions have borrowed liberally from the DCMI definitions. See: http://dublincore.org/documents/dcmi-terms/index.shtml"
}
[/block]
**Audiovisual**
A series of visual representations imparting an impression of motion when shown in succession. May or may not include sound. May be used for films, video, etc. 

Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.17608/K6.AUCKLAND.4620790.V1

Suggested Dublin Core mapping: MovingImage

**Collection**
An aggregation of resources, which may encompass collections of one resourceType as well as those of mixed types. A collection is described as a group; its parts may also be separately described.

Example: A collection of samples, or various files making up a report.
https://data.datacite.org/application/vnd.datacite.datacite+xml/10.5284/1001038

Suggested Dublin Core mapping: Collection

**DataPaper**
A factual and objective publication with a focused intent to identify and describe specific data, sets of data, or data collections to facilitate discoverability. A data paper describes data provenance and methodologies used in the gathering, processing, organizing, and representing the data.

Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.15470/5a5kni

Suggested Dublin Core mapping: Text

**Dataset**
Data encoded in a defined structure. Data file or files.
Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.1594/PANGAEA.804876

Suggested Dublin Core mapping: Dataset

**Event**
A non-persistent, time- based occurrence.

Usage: Descriptive information and/or content that is the basis for discovery of the purpose, location, duration, and responsible agents associated with an event such as a webcast or convention.

Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.7269/P3RN35SZ

Suggested Dublin Core mapping: Event

**Image** 
A visual representation other than text.

Usage: Digitised or born digital images, drawings or photographs.

Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.6083/M4QN65C5

Suggested Dublin Core mapping: Image, StillImage

**InteractiveResource** 
A resource requiring interaction from the user to be understood, executed, or experienced.

Usage: Training modules, files that require use of a viewer (e.g., Flash), or query/response portals.

Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.7269/P3TB14TR

Suggested Dublin Core mapping: InteractiveResource

**Model** 
An abstract, conceptual, graphical, mathematical or visualization model that represents empirical objects, phenomena, or physical processes.

Usage: Modelled descriptions of, for example, different aspects of languages or a molecular biology reaction chain.

Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.5285/4D866CD2-C907-4CE2-B070-084CA9779DC2

**PhysicalObject** 
An inanimate, three-dimensional object or substance.

Usage: Artifacts, specimens.

Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.7299/X78052RB

Suggested Dublin Core mapping: PhysicalObject

**Service**
An organized system of apparatus, appliances, staff, etc., for supplying some function(s) required by end users.

Usage: Data management service, or long-term preservation service.

Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.21938/3I01ISNUCODNH1ZJBCVUWA

Suggested Dublin Core mapping: Service

**Software**
A computer program in source code (text) or compiled form. Use this type for all software components supporting scholarly research.

Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.4225/03/5954F738EE5AA

Suggested Dublin Core mapping: Software

**Sound**
A resource primarily intended to be heard, such as an audio recording. 

Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.7282/T3J67F05

Suggested Dublin Core mapping: Sound

**Text**
A resource consisting primarily of words for reading.

Combine “Text” with free-text or terms from the [CASRAI Publications resource type list](http://dictionary.casrai.org/Output_Types).

Usage: Grey literature, lab notes, accompanying materials.

Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.5682/9786065914018

Suggested Dublin Core mapping: Text

**Workflow**
A structured series of steps which can be executed to produce a final outcome, allowing users a means to specify and enact their work in a more reproducible manner.

Usage: Computational workflows involving sequential operations made on data by wrapped software and may be specified in a format belonging to a workflow management system, such as Taverna (http://www.taverna.org.uk/). An education module on workflows prepared by DataONE is available at http://www.dataone.org/sites/all/documents/L10_AnalysisWorkflows.pptx

**Other**
If selected, supply a value for ResourceType.

#Guidance for handling missing mandatory property values

If providing values for any of the mandatory properties presents a difficulty, use of standard machine-recognizable codes is strongly advised. A set of the codes is provided in [DataCite Metadata Schema v4.1 Standard Values for Unknown Information](doc:schema-values-unknown-information-v41). However, we recommend that you consider the resulting effect on the citation created from the metadata provided.

Here is an example of a citation that uses machine-readable substitutions for all but one of the required metadata properties. Obviously the more metadata that is supplied, the more information is conveyed. Note that is a demonstration DOI and not an actual identifier, so the link will not work.

>(:unkn)(9999):(:none).(:null).Dataset. [http://doi.org/10.5072/FK2JW8C992](http://doi.org/10.5072/FK2JW8C992)
[block:api-header]
{
  "title": "Notes"
}
[/block]
1. Smith AM, Katz DS, Niemeyer KE, FORCE11 Software Citation Working Group. (2016) Software citation principles. PeerJ Computer Science 2:e86 https://doi.org/10.7717/peerj-cs.86