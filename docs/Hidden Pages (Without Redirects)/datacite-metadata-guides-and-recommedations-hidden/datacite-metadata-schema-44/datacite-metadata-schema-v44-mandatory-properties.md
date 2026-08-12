---
title: DataCite Metadata Schema v4.4 Mandatory Properties
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
  "type": "success",
  "title": "Recommended for discovery",
  "body": "All of the mandatory properties are recommended for discovery."
}
[/block]
# 1 Identifier
**Occurrence:** 1
**Definition: ** The Identifier is a unique string that identifies a resource. For software, determine whether the identifier is for a specific version of a piece of software, (per the Force11 Software Citation Principles[(1)](#section-notes), or for all versions.
**Allowed values, examples, other constraints:** DOI (Digital Object Identifier) registered by a DataCite member. Format should be “10.1234/foo”

## 1.a identifierType
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

## 2.1.a nameType
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

## 2.4.a nameIdentifierScheme
**Occurrence:** 1
**Definition: ** The name of the name identifier schema.
**Allowed values, examples, other constraints:** If nameIdentifier is used, nameIdentifierScheme is mandatory.
Examples: 
- [ORCID](http://orcid.org/). When entering an ORCID, follow [these style guidelines](https://support.orcid.org/hc/en-us/articles/360006897674-Structure-of-the-ORCID-Identifier)
- [ISNI](http://www.isni.org/)
- [ROR](https://ror.org/)
- [GRID](https://www.grid.ac/)

## 2.4.b schemeURI
**Occurrence:** 0-1
**Definition: ** The URI of the name identifier schema.
**Allowed values, examples, other constraints:** 
Examples:
- http://www.isni.org
- http://orcid.org
- https://ror.org/
- https://www.grid.ac/

## 2.5 affiliation
**Occurrence:** 0-n
**Definition: ** The organizational or institutional affiliation of the creator.
**Allowed values, examples, other constraints:** Free text. The creator's nameType may be Organizational or Personal. In case of an organizational creator, e.g. a research group, you can add here the name of the formal institution to which the creator belongs.

## 2.5.a affiliationIdentifier
**Occurrence:** 0-n
**Definition:** Uniquely identifies the organizational affiliation of the creator. 
**Allowed values, examples, other constraints:** The format is dependent upon schema. 
Examples: 
- https://ror.org/04aj4c181
- grid.461819.3

## 2.5.b affiliationIdentifierScheme
**Occurrence:** 1
**Definition:** The name of the affiliation identifier schema. 
**Allowed values, examples, other constraints:** If affiliationIdentifier is used, affiliationIdentifierScheme is mandatory. 
Examples:
- ROR
- GRID

## 2.5.c schemeURI
**Occurrence:** 1
**Definition:** The URI of the affiliation identifier schema. 
**Allowed values, examples, other constraints:** 
Examples:
- http://www.isni.org/
- http://orcid.org
- https://ror.org/
- https://www.grid.ac/

# 3 Title
**Occurrence:** 1-n
**Definition: ** A name or title by which a resource is known. May be the title of a dataset or the name of a piece of software.
**Allowed values, examples, other constraints:** Free text.

## 3.a titleType
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
The text format is free-text.
Examples:
- Dataset/Census Data, where 'Dataset' is resourceTypeGeneral value and 'Census Data' is ResourceType value.
- Text/Conference Abstract, where 'Text' is
resourceTypeGeneral value and 'Conference Abstract' is resourceType value aligned with CASRAI Publications term.

## 10.a resourceTypeGeneral
**Occurrence:** 1
**Definition: ** The general type of a resource.
**Allowed values, examples, other constraints:** 
Controlled List Values:

  * Audiovisual
  * Book
  * BookChapter
  * Collection
  * ComputationalNotebook
  * ConferencePaper
  * ConferenceProceeding
  * DataPaper
  * Dataset
  * Dissertation
  * Event
  * Image
  * InteractiveResource
  * Journal
  * JournalArticle
  * Model
  * OutputManagementPlan
  * PeerReview
  * PhysicalObject
  * Preprint
  * Report
  * Service
  * Software
  * Sound
  * Standard
  * Text
  * Workflow
  * Other 
[block:callout]
{
  "type": "info",
  "body": "Where there is direct correspondence with the Dublin Core Metadata, DataCite definitions have borrowed liberally from the DCMI definitions. See: http://dublincore.org/documents/dcmi-terms/index.shtml",
  "title": "Correspondence with Dublin Core"
}
[/block]
#PublicationYear—Additional guidance

PublicationYear : the year when the data was or will be made publicly available. In the case of datasets, "publish" is understood to mean making the data available on a specific date to the community of researchers.
- If that date cannot be determined, use the date of registration.
- If an embargo period has been in effect, use the date when the embargo period ends.
- If there is no standard publication year value, use the date that would be preferred from a
citation perspective.
- In the case of resources such as software or dynamic data where there may be multiple releases
in one year, include the Date/dateType/dateInformation property and sub-properties to provide
more information about the publication or release date details.

#In the case of a digitised version of a physical object

If the DOI is being used to identify a digitised version of an original item, the recommended approach is to supply the PublicationYear for the digital version and not the original object. The Title field may be used to convey the approximate or known date of the original object. Other metadata properties available for additional date information about the object include: Subject and Description. However, only Title will be part of the citation.

Here are two examples of citations using dates or date information in the titles.

- Schmidt, S., Andersen, V., Belviso, S., & Marty, J.-C. (2002). Dissolved and particulate thorium 234
concentration at time series station DYFAMED from date 1995-05-07 (Data set). PANGAEA - Data
Publisher for Earth & Environmental Science. https://doi.org/10.1594/pangaea.183607

- Tape, K. D. (2015). Aerial Images of Alaska’s Arctic Coastal Plain; 1948-1949. U.S. Geological Survey.
(Image). https://doi.org/10.5066/f79021tb

#Guidance for handling missing mandatory property values

If providing values for any of the mandatory properties presents a difficulty, use of standard machine-recognizable codes is strongly advised. A set of the codes is provided in [DataCite Metadata Schema v4.4 Standard Values for Unknown Information](doc:datacite-metadata-schema-v44-standard-values-for-unknown-information). However, we recommend that you consider the resulting effect on the citation created from the metadata provided.

Here is an example of a citation that uses machine-readable substitutions for all but one of the required metadata properties. Obviously the more metadata that is supplied, the more information is conveyed. Note that is a demonstration DOI and not an actual identifier, so the link will not work.

>:unkn 9999: :none. :null. Dataset. http://doi.org/10.5072/FK2JW8C992