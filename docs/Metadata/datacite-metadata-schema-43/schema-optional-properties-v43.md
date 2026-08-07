---
title: DataCite Metadata Schema v4.3 Recommended and Optional Properties
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
# 6 Subject
[block:callout]
{
  "type": "success",
  "title": "Recommended for discovery"
}
[/block]
**Occurrence:** 0-n
**Definition:** Subject, keyword, classification code, or key phrase describing the resource.
**Allowed values, examples, other constraints:** Free text.

## 6.a subjectScheme
**Occurrence:** 0-1
**Definition: ** The name of the subject scheme or classification code or authority if one is used.
**Allowed values, examples, other constraints:** Free text.

## 6.b schemeURI
**Occurrence:** 0-1
**Definition: ** The URI of the subject identifier scheme.
**Allowed values, examples, other constraints:** 
Examples:
- http://id.loc.gov/authorities/subjects
- http://udcdata.info/ 

## 6.c valueURI
**Occurrence:** 0-1
**Definition: ** The URI of the subject term.
**Allowed values, examples, other constraints:** 
Examples:
- http://id.loc.gov/authorities/subjects/sh85026196
- http://udcdata.info/037278

# 7 Contributor
[block:callout]
{
  "type": "success",
  "title": "Recommended for discovery"
}
[/block]
**Occurrence:** 0-n
**Definition: ** The institution or person responsible for collecting, managing, distributing, or otherwise contributing to the development of the resource.
To supply multiple contributors, repeat this property.
For software, if there is an alternate entity that "holds, archives, publishes, prints, distributes, releases, issues, or produces" the code, use the contributorType "hostingInstitution" for the code repository.
**Allowed values, examples, other constraints:** Note: DataCite infrastructure supports up to between 8000- 10000 names. For name lists above that size, consider attribution via linking to the related metadata.
Examples: 
- Charpy, Antoine
- Foo Data Center

## 7.a contributorType
**Occurrence:** 1
**Definition: ** The type of contributor of the resource.
**Allowed values, examples, other constraints:** If Contributor is used, then contributorType is mandatory.

### Controlled List Values:

**ContactPerson**
Person with knowledge of how to access, troubleshoot, or otherwise field issues related to the resource. May also be “Point of Contact” in organisation that controls access to the resource, if that organisation is different from Publisher, Distributor, Data Manager.

**DataCollector**
Person/institution responsible for finding, gathering/collecting data under the guidelines of the author(s) or Principal Investigator (PI). May also use when crediting survey conductors, interviewers, event or condition observers, person responsible for monitoring key instrument data.

**DataCurator**
Person tasked with reviewing, enhancing, cleaning, or standardizing metadata and the associated data submitted for storage, use, and maintenance within a data centre or repository. While the “DataManager” is concerned with digital maintenance, the DataCurator’s role encompasses quality assurance focused on content and metadata. This includes checking whether the submitted dataset is complete, with all files and components as described by submitter, whether the metadata is standardized to appropriate systems and schema, whether specialized metadata is needed to add value and ensure access across disciplines, and determining how the metadata might map to search engines, database products, and automated feeds.

**DataManager**
Person (or organisation with a staff of data managers, such as a data centre) responsible for maintaining the finished resource. The work done by this person or organisation ensures that the resource is periodically “refreshed” in terms of software/hardware support, is kept available or is protected from unauthorized access, is stored in accordance with industry standards, and is handled in accordance with the records management requirements applicable to it.

**Distributor**
Institution tasked with responsibility to generate/disseminate copies of the resource in either electronic or print form. Works stored in more than one archive/repository may credit each as a distributor.

**Editor**
A person who oversees the details related to the publication format of the resource. Note: if the Editor is to be credited in place of multiple creators, the Editor’s name may be supplied as Creator, with “(Ed.)” appended to the name.

**HostingInstitution**
Typically, the organisation allowing the resource to be available on the internet through the provision of its hardware/software/operating support. May also be used for an organisation that stores the data offline. Often a data centre (if that data centre is not the “publisher” of the resource.)

**Producer**
Typically a person or organisation responsible for the artistry and form of a media product. In the data industry, this may be a company “producing” DVDs that package data for future dissemination by a distributor.

**ProjectLeader**
Person officially designated as head of project team or sub- project team instrumental in the work necessary to development of the resource. The Project Leader is not “removed” from the work that resulted in the resource; he or she remains intimately involved throughout the life of the particular project team.

**ProjectManager**
Person officially designated as manager of a project. Project may consist of one or many project teams and sub-teams. The manager of a project normally has more administrative responsibility than actual work involvement.

**ProjectMember**
Person on the membership list of a designated project/project team. This vocabulary may or may not indicate the quality, quantity, or substance of the person’s involvement.

**RegistrationAgency**
Institution/organisation officially appointed by a Registration Authority to handle specific tasks within a defined area of responsibility. DataCite is a Registration Agency for the International DOI Foundation (IDF). One of DataCite’s tasks is to assign DOI prefixes to the allocating agents who then assign the full, specific character string to data clients, provide metadata back to the DataCite registry, etc.

**RegistrationAuthority**
A standards-setting body from which Registration Agencies obtain official recognition and guidance. The IDF serves as the Registration Authority for the International Standards Organisation (ISO) in the area/domain of Digital Object Identifiers.

**RelatedPerson**
A person without a specifically defined role in the development of the resource, but who is someone the author wishes to recognize. This person could be an author’s intellectual mentor, a person providing intellectual leadership in the discipline or subject domain, etc.

**Researcher**
A person involved in analyzing data or the results of an experiment or formal study. May indicate an intern or assistant to one of the authors who helped with research but who was not so “key” as to be listed as an author. Should be a person, not an institution. Note that a person involved in the gathering of data would fall under the contributorType “DataCollector.” The researcher may find additional data online and correlate it to the data collected for the experiment or study, for example.

**ResearchGroup**
Typically refers to a group of individuals with a lab, department, or division; the group has a particular, defined focus of activity. May operate at a narrower level of scope; may or may not hold less administrative responsibility than a project team.

**RightsHolder**
Person or institution owning or managing property rights, including intellectual property rights over the resource.

**Sponsor**
Person or organisation that issued a contract or under the auspices of which a work has been written, printed, published, developed, etc. Includes organisations that provide in-kind support, through donation, provision of people or a facility or instrumentation necessary for the development of the resource, etc.

**Supervisor**
Designated administrator over one or more groups/teams working to produce a resource or over one or more steps of a development process.

**WorkPackageLeader**
A Work Package is a recognized data product, not all of which is included in publication. The package, instead, may include notes, discarded documents, etc. The Work Package Leader is responsible for ensuring the comprehensive contents, versioning, and availability of the Work Package during the development of the resource.

**Other**
Any person or institution making a significant contribution to the development and/or maintenance of the resource, but whose contribution does not “fit” other controlled vocabulary for contributorType. Could be a photographer, artist, or writer whose contribution helped to publicize the resource (as opposed to creating it), a reviewer of the resource, someone providing administrative services to the author (such as depositing updates into an online repository, analysing usage, etc.), or one of many other roles.

## 7.1 contributorName
**Occurrence:** 1
**Definition: ** The full name of the contributor.
**Allowed values, examples, other constraints:** If Contributor is used, then
contributorName is mandatory.
Examples: 
- Patel, Emily
- ABC Foundation
The personal name format may be: family, given. Non- roman names should be transliterated according to the [ALA-LC schemas](http://www.loc.gov/catdir/cpso/roman.html).

### 7.1.a nameType
**Occurrence:** 0-1
**Definition: ** The type of name
**Allowed values, examples, other constraints:** 

### Controlled List Values:
- Organizational 
- Personal (default)

## 7.2 givenName
**Occurrence:** 0-1
**Definition: ** The personal or first name of the contributor.
**Allowed values, examples, other constraints:** 
Examples based on the 7.2 names: 
- Emily

## 7.3 familyName
**Occurrence:** 0-1
**Definition: ** The surname or last name of the contributor.
**Allowed values, examples, other constraints:** 
Example based on the 7.2 names: 
- Patel

## 7.4 nameIdentifier
**Occurrence:** 0-n
**Definition: ** Uniquely identifies an individual or legal entity, according to various schemes.
**Allowed values, examples, other constraints:** The format is dependent upon scheme.

### 7.4.a nameIdentifierScheme
**Occurrence:** 1
**Definition: ** The name of the name identifier
scheme.
**Allowed values, examples, other constraints:** If nameIdentifier is used,
nameIdentifierScheme is mandatory.
Examples:
- [ORCID](http://orcid.org/) When entering an ORCID, follow [these style guidelines](http://support.orcid.org/knowledgebase/articles/116780-structure-of-the-orcid-identifier)
- [ISNI](http://www.isni.org/)
- [ROR](https://ror.org/)
- [GRID](http://www.grid.ac/)

### 7.4.b schemeURI
**Occurrence:** 0-1
**Definition: ** The URI of the name identifier scheme.
**Allowed values, examples, other constraints:** 
Examples:
- http://www.isni.org 
- http://orcid.org
- https://ror.org/
- https://www.grid.ac/

## 7.5 affiliation
**Occurrence:** 0-n
**Definition: ** The organizational or institutional affiliation of the contributor.
**Allowed values, examples, other constraints:** Free text. The contributor's nameType may be Organizational or Personal. In case of an organizational contributor e.g. a research group, you can add here the name of the formal institution to which the contributor belongs.

## 7.5.a affiliationIdentifier
**Occurrence:** 0-n
**Definition:** Uniquely identifies the organizational affiliation of the conributor. 
**Allowed values, examples, other constraints:** The format is dependent upon schema. 
Examples:
- https://ror.org/041j4c181
- grid.461819.3

## 7.5.b affiliationIdentifierScheme
**Occurrence:** 1
**Definition:** Name of the affiliation identifier schema. 
**Allowed values, examples, other constraints:** If affiliationIdentifier is used, affiliationIdentifierScheme is mandatory.
Examples:
- ROR
- GRID

## 7.5.c schemeURI
**Occurrence:** 0-1
**Definition:** URI of the affiliation identifier schema. 
**Allowed values, examples, other constraints:** 
Examples:
- http://www.isni.org/
- https://orcid.org/
- https://ror.org/

# 8 Date
[block:callout]
{
  "type": "success",
  "title": "Recommended for discovery"
}
[/block]
**Occurrence:** 0-n
**Definition: ** Different dates relevant to the work.
**Allowed values, examples, other constraints:** 
- YYYY
- YYYY-MM-DD
- YYYY-MM-DDThh:mm:ssTZD 
- or any other format or level of granularity described in [W3CDTF](http://www.w3.org/TR/NOTE-datetime). Use the [RKMS-ISO8601 standard](http://www.ukoln.ac.uk/metadata/dcmi/collection-RKMS-ISO8601/) for depicting date ranges. 
Example: 
- 2004-03-02/2005-06-02
Years before 0000 must be prefixed with a - sign, e.g. -0054 to indicate 55 BC.

## 8.a dateType
**Occurrence:** 1
**Definition: ** The type of date.
**Allowed values, examples, other constraints:** If Date is used, dateType is
mandatory.

### Controlled List Values:
[block:callout]
{
  "type": "success",
  "title": "Recommended values for discovery",
  "body": "Created, Submitted"
}
[/block]
**Accepted**
The date that the publisher accepted the resource into their system.
To indicate the start of an embargo period, use Submitted or Accepted, as appropriate.
     
**Available**
The date the resource is made publicly available. May be a range.
To indicate the end of an embargo period, use Available.
      
**Copyrighted**
The specific, documented date at which the resource receives a copyrighted status, if applicable.
      
**Collected**
The date or date range in which the resource content was collected.
To indicate precise or particular timeframes in which research was conducted.
       
**Created**
The date the resource itself was put together; this could refer to a timeframe in ancient history, be a date range or a single date for a final component, e.g., the finalized file with all of the data.
*Recommended for discovery.*
      
**Issued**
The date that the resource is published or distributed e.g. to a data centre
     
**Submitted**
The date the creator submits the resource to the publisher. This could be different from Accepted if the publisher then applies a selection process. To indicate the start of an embargo period, use Submitted or Accepted, as appropriate.
*Recommended for discovery.*

**Updated**
The date of the last update to the resource, when the resource is being added to. May be a range.

**Valid**
The date or date range during which the dataset or resource is accurate.

**Withdrawn**
The date the resource is removed. It's good practice to indicate the reason for retraction of withdrawal in the `descriptionType`. 

**Other**

## 8.b dateInformation
**Occurrence:** 0-1
**Definition: ** Specific information about the date, if appropriate.
**Allowed values, examples, other constraints:** Free text
May be used to provide more information about the publication, release or collection date details, for example. May also be used to clarify dates in ancient history. 
Examples:
- 55 BC
- 55 BCE

# 9 Language
**Occurrence:** 0-1
**Definition: ** The primary language of the resource.
**Allowed values, examples, other constraints:** Allowed values are taken from IETF BCP 47, ISO 639-1 language codes.
Examples: 
- en
- de
- fr

# 11 AlternateIdentifier
**Occurrence:** 0-n
**Definition: ** An identifier or identifiers other than the primary Identifier applied to the resource being registered. This may be any alphanumeric string which is unique within its domain of issue. May be used for local identifiers. AlternateIdentifier should be used for another identifier of the same instance (same location, same file).
**Allowed values, examples, other constraints:** Free text.
Example: 
- E-GEOD-34814

## 11.a alternateIdentifierType
**Occurrence:** 1
**Definition: ** The type of the AlternateIdentifier.
**Allowed values, examples, other constraints:** Free text. 
If AlternateIdentifier is used, alternateIdentifierType is mandatory. For the above example, the alternateIdentifierType would be “A local accession number”

# 12 RelatedIdentifier
[block:callout]
{
  "type": "success",
  "title": "Recommended for discovery"
}
[/block]
**Occurrence:** 0-n
**Definition: ** Identifiers of related resources.
These must be globally unique identifiers.
**Allowed values, examples, other constraints:** Free text. Use this property to indicate subsets of properties, as appropriate. Note: [DataCite Event Data](doc:eventdata-guide) collects all references to related resources based on the RelatedIdentifier property.

## 12.a relatedIdentifierType
**Occurrence:** 1
**Definition: ** The type of the RelatedIdentifier
**Allowed values, examples, other constraints:** If RelatedIdentifier is used, relatedIdentifierType is mandatory.

### Controlled List Values:

**ARK**
Archival Resource Key
URL designed to support long-term access to information objects. In general, ARK syntax is of the form (brackets indicate [optional] elements): 
[http://NMA/] ark:/NAAN/Name [Qualifier]
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"ARK\" relationType=\"IsCitedBy\">ark:/13030/tqb3kh97gh8w </relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**arXiv**
arXiv identifier
arXiv.org is a repository of preprints of scientific papers in the fields of mathematics, physics, astronomy, computer science, quantitative biology, statistics, and quantitative finance.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=”arXiv” relationType=”IsCitedBy”>arXiv:0706.0001 </relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**bibcode**
Astrophysics Data System bibliographic codes; a standardized 19 character identifier according to the syntax yyyyjjjjjvvvvmppppa. See [description](http://info-uri.info/registry/OAIHandler?verb=GetRecord&metadataPrefix=reg&identifier=info:bibcode/) 
Note: bibcodes can be resolved via http://adsabs.harvard.edu/abs/bibcode
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"bibcode\" relationType=\"IsCitedBy\"> 2014Wthr...69...72C </relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**DOI**
Digital Object Identifier; a character string used to uniquely identify an object. A DOI name is divided into two parts, a prefix and a suffix, separated by a slash.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=”IsSupplementTo”> 10.1016/j.epsl.2011.11.037 </relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**EAN13**
European Article Number, now renamed International Article Number, but retaining the original acronym, is a 13-digit barcoding standard which is a superset of the original 12-digit Universal Product Code (UPC) system.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"EAN13” relationType=”Cites”>9783468111242 </relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**EISSN**
Electronic International Standard Serial Number; ISSN used to identify periodicals in electronic form (eISSN or e- ISSN).
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"eISSN” relationType=”Cites”>1562-6865 </relatedIdenfifier>",
      "language": "xml"
    }
  ]
}
[/block]
**Handle** 
A handle is an abstract reference to a resource.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"Handle\" relationType=\"References\">10013/epic.10033 </relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**IGSN**
International Geo Sample Number; a 9-digit alphanumeric code that uniquely identifies samples from our natural environment and related sampling features.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"IGSN\" relationType=\"References\">IECUR0097 </relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**ISBN**
International Standard Book Number; a unique numeric book identifier. There are 2 formats: a 10-digit ISBN format and a 13-digit ISBN.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier><relatedIdentifier relatedIdentifierType=\"ISBN\" relationType=\"IsPartOf\">978-3-905673-82-1 </relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**ISSN**
International Standard Serial Number; a unique 8-digit number used to identify a print or electronic periodical publication.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"ISSN\" relationType=\"IsPartOf\">0077-5606 </relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**ISTC**
International Standard Text Code; a unique “number” assigned to a textual work. An ISTC consists of 16 numbers and/or letters.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"ISTC” relationType=”Cites”>0A9 2002 12B4A105 7 </relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**LISSN**
The linking ISSN or ISSN-L enables collocation or linking among different media versions of a continuing resource.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"LISSN” relationType=”Cites”>1188-1534</relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**LSID**
Life Science Identifiers; a unique identifier for data in the Life Science domain. Format: urn:lsid:authority:namespace:identifier:revision
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"LSID” relationType=”Cites”> urn:lsid:ubio.org:namebank:11815</relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**PMID**
PubMed identifier; a unique number assigned to each PubMed record.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"PMID” relationType=”IsReferencedBy”>12082125</relatedId entifier>",
      "language": "xml"
    }
  ]
}
[/block]
**PURL**
Persistent Uniform Resource Locator. A PURL has three parts: (1) a protocol, (2) a resolver address, and (3) a name.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"PURL” relationType=”Cites”> http://purl.oclc.org/foo/bar</relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**UPC**
Universal Product Code is a barcode symbology used for tracking trade items in stores. Its most common form, the UPC-A, consists of 12 numerical digits.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"UPC” relationType=”Cites”> 123456789999</relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**URL**
Uniform Resource Locator, also known as web address, is a specific character string that constitutes a reference to a resource. The syntax is: schema://domain:port/path?query_string#fragment_id
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"URL” relationType=”IsCitedBy”>http://www.heatflow.und.edu/i ndex2.html</relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**URN**
Uniform Resource Name; is a unique and persistent identifier of an electronic document. The syntax is: urn:<NID>:<NSS> The leading urn: sequence is case-insensitive, <NID> is the namespace identifier, <NSS> is the namespace-specific string.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"URN\" relationType=”IsSupplementTo”>urn:nbn:de:101:1- 201102033592</relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**w3id**
Permanent identifier for Web applications. Mostly used to publish vocabularies and ontologies. The letters 'w3' stand for "World Wide Web".
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"w3id\" relationType=\"IsCitedBy\">https://w3id.org/games/spec/coil#Coil_Bomb_Die_Of_Age</relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
## 12.b relationType
**Occurrence:** 1
**Definition: ** Description of the relationship of the resource being registered (A) and the related resource (B).
**Allowed values, examples, other constraints:** If RelatedIdentifier is used,
relationType is mandatory.

### Controlled List Values:
[block:callout]
{
  "type": "success",
  "title": "Recommended values for discovery",
  "body": "IsCitedBy, Cites, IsSupplementTo, IsSupplementedBy, IsPartOf, HasPart"
}
[/block]
**IsCitedBy**
Indicates that B includes A in a citation 
*Recommended for discovery.*
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\"relationType=\"IsCited By\">10.4232/10.ASEAS-5.2-1 </relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**Cites**
Indicates that A includes B in a citation 
*Recommended for discovery.*
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"ISBN” relationType=\"Cites“>0761964312 </relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**IsSupplementTo**
Indicates that A is a supplement to B 
*Recommended for discovery.*
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"URN\" relationType=\"IsSupplementTo\">urn:nbn:de:0168-ssoar- 13172 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsSupplementedBy**
Indicates that B is a supplement to A 
*Recommended for discovery.*
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"PMID\" relationType=\"IsSupplementedBy\">16911322/ </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsContinuedBy**
Indicates A is continued by the work B 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"URN\" relationType=\"IsContinuedBy\">urn:nbn:de:bsz:21-opus- 4967 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**Continues**
Indicates A is a continuation of the work B 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"URN\" relationType=\"Continues\">urn:nbn:de:bsz:21-opus-4966 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsDescribedBy**
Indicates A is described by B 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"IsDescribedBy\">10.1038/sdata.2016.123</relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**Describes**
Indicates A describes B 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"Describes\">10.6084/m9.figshare.c.3288407</relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**HasMetadata**
Indicates resource A has additional metadata B 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"HasMetadata\" relatedMetadataSchema=\"DDI-L\" schemeURI=\"http://www.ddialliance.org/Specification/DDI- Lifecycle/3.1/XMLSchema/instance.xsd\">10.1234/567890</relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsMetadataFor**
Indicates additional metadata A for a resource B 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"IsMetadataFor “relatedMetadataSchema=\"DDI-L\" schemeURI=\"http://www.ddialliance.org/Specification/DDI- Lifecycle/3.1/XMLSchema/instance.xsd\">10.1234/567891</relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**HasVersion**
Indicates A has a version (B) 
The registered resource such as a software package or code repository has a versioned instance (indicates A has the instance B) e.g. it may be used to relate an un-versioned code repository to one of its specific software versions. 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"HasVersion\">10.5281/ZENODO.832053 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsVersionOf**
Indicates A is a version of B 
The registered resource is an instance of a target resource (indicates that A is an instance of B) e.g. it may be used to relate a specific version of a software package to its software code repository. 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"IsVersionOf\">10.5281/ZENODO.832054 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsNewVersionOf**
Indicates A is a new edition of B, where the new edition has been modified or updated.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"IsNewVersionOf\">10.5438/0005 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsPreviousVersionOf**
Indicates A is a previous edition of B 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"IsPreviousVersionOf\">10.5438/0007 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsPartOf**
Indicates A is a portion of B; may be used for elements of a series 
Primarily this relation is applied to container-contained type relationships. 
Note: May be used for individual software modules; note that code repository-to-version relationships should be modeled using IsVersionOf and HasVersion 
*Recommended for discovery.* 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"IsPartOf\">10.5281/zenodo.754312 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**HasPart**
Indicates A includes the part B 
Primarily this relation is applied to container-contained type relationships. 
Note: May be used for individual software modules; note that code repository-to-version relationships should be modeled using IsVersionOf and HasVersion 
*Recommended for discovery.*
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"URL\" relationType=\"HasPart\">https://zenodo.org/record/16564/files/dune-stuff-LSSC_15.zip</relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsReferencedBy**
Indicates A is used as a source of information by B 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"URL\" relationType=\"IsReferencedBy\">http://www.testpubl.de </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**References**
Indicates B is used as a source of information for A 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"URN\" relationType=\"References\">urn:nbn:de:bsz:21-opus- 963</relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsDocumentedBy**
Indicates B is documentation about/explaining A; e.g. points to software documentation 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"URL\" relationType=\"IsDocumentedBy\">http://tobias-lib.uni-tuebingen.de/volltexte/2000/96/ </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**Documents**
Indicates A is documentation about B; e.g. points to software documentation 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"Documents\">10.1234/7836 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsCompiledBy**
Indicates B is used to compile or create A. Note: May be used for software and text, as a compiler can be a computer program or a person. 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"URL\" relationType=\"isCompiledBy\">http://d- nb.info/gnd/4513749-3 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**Compiles**
Indicates B is the result of a compile or creation event using A. Note: May be used for software and text, as a compiler can be a computer program or a person. 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"URN\" relationType=\"Compiles\">urn:nbn:de:bsz:21-opus-963 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsVariantFormOf**
Indicates A is a variant or different form of B.
Use for a different form of one thing. 
May be used for different software operating systems or compiler formats, for example. 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"IsVariantFormOf\">10.1234/8675 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsOriginalFormOf**
Indicates A is the original form of B.
May be used for different software operating systems or compiler formats, for example. 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"IsOriginalFormOf\">10.1234/9035 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsIdenticalTo**
Indicates that A is identical to B, for use when there is a need to register two separate instances of the same resource.
IsIdenticalTo should be used for a resource that is the same as the registered resource but is saved in another location, maybe another institution. 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"URL\" relationType=\"IsIdenticalTo\">http://oac.cdlib.org/findaid/ar k:/13030/c8r78fzq </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsReviewedBy**
Indicates that A is reviewed by B 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"IsReviewedBy\">10.5256/F1000RESEARCH.4288.R4745 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**Reviews**
Indicates that A is a review of B
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"Reviews\">10.12688/f1000research.4001.1</relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsDerivedFrom**
Indicates B is a source upon which A is based.
IsDerivedFrom should be used for a resource that is a derivative of an original resource. 
In this example, the dataset is derived from a larger dataset and data values have been manipulated from their original state. 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"IsDerivedFrom\">10.6078/M7DZ067C </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsSourceOf**
Indicates A is a source upon which B is based.
IsSourceOf is the original resource from which a derivative resource was created. 
In this example, this is the original dataset without value manipulation, and the source of the derived dataset.
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"URL\" relationType=\"IsSourceOf\"> http://opencontext.org/projects/81204AF8-127C-4686-E9B0- 1202C3A47959 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**IsRequiredBy**
Indicates A is required by B.
Note: May be used to indicate software dependencies. 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"IsRequiredBy\">10.1234/8675 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**Requires**
Indicates A requires B.
Note: May be used to indicate software dependencies. 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"Requires\">10.1234/8675 </relatedIdentifier> ",
      "language": "xml"
    }
  ]
}
[/block]
**Obsoletes**
Indicates A replaces B. 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"Obsoletes\">10.5438/0007</relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
**IsObsoletedBy**
Indicates A is replaced by B. 
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"IsObsoletedBy\">10.5438/0005</relatedIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
## 12.c relatedMetadataScheme
**Occurrence:** 0-1
**Definition: ** The name of the scheme.
**Allowed values, examples, other constraints:** Use only with this relation pair: (HasMetadata/ IsMetadataFor)
See [relationType](#section-12-2-relationtype) for example.

## 12.d schemeURI
**Occurrence:** 0-1
**Definition: ** The URI of the relatedMetadataScheme.
**Allowed values, examples, other constraints:** Use only with this relation pair: (HasMetadata/ IsMetadataFor)
See [relationType](#section-12-2-relationtype) for example.

## 12.e schemeType
**Occurrence:** 0-1
**Definition: ** The type of the relatedMetadataScheme, linked with the schemeURI.
**Allowed values, examples, other constraints:** Use only with this relation pair: (HasMetadata/ IsMetadataFor)
Examples: 
- XSD
- DDT
- Turtle

## 12.f resourceTypeGeneral
**Occurrence:** 0-1
**Definition:** The general type of the related resource.
**Allowed values, examples, other constraints:** Use the controlled list values as stated in 10.1.

# 13 Size  
**Occurrence:** 0-n
**Definition:** Size (e.g. bytes, pages, inches, etc.) or duration (extent), e.g. hours, minutes, days, etc., of a resource.
**Allowed values, examples, other constraints:** Free text.
Examples: 
- "15 pages"
- "6 MB"
- “45 minutes”

# 14 Format 
**Occurrence:** 0-n
**Definition:** Technical format of the resource.
**Allowed values, examples, other constraints:** Free text.
Use file extension or MIME type where possible, e.g., PDF, XML, MPG or application/pdf, text/xml, video/mpeg.

# 15 Version 
**Occurrence:** 0-1
**Definition:** The version number of the resource.
**Allowed values, examples, other constraints:**
- Suggested practice: track major_version.minor_version.
- Register a new identifier for a major version change.
- Individual stewards need to determine which are major vs. minor versions. Based on the work of the Earth Science Information Partners (ESIP). For more guidance, see:
http://wiki.esipfed.org/index.php/Interagency_Data_Stewardship/Citations/provider_guidelines#Note_on_Versioning_and_Locators
- Software engineering practice follows this approach of tracking changes and giving new version numbers.
- May be used in conjunction with properties 11 and 12 ([AlternateIdentifier](#section-11-alternateidentifier)) and [RelatedIdentifier](#section-12-relatedidentifier)) to indicate various information updates.
- May be used in conjunction with property 17 ([Description](#section-17-description)) to indicate the nature and file/record range of version.

# 16 Rights 
**Occurrence:** 0-n
**Definition:** Any rights information for this resource. The property may be repeated to record complex rights characteristics.
**Allowed values, examples, other constraints:** Free text.
- Provide a rights management statement for the resource or reference a service providing such information. Include embargo information if applicable.
- Use the complete title of a license and include version information if applicable.
- May be used for software licenses.
Examples:
- Creative Commons Attribution 3.0 Germany License
- [Apache License](http://www.apache.org/licenses/), Version 2.0

## 16.a rightsURI 
**Occurrence:** 0-1
**Definition:** The URI of the license.
**Allowed values, examples, other constraints:**
Example:
- http://creativecommons.org/licenses/by/3.0/de/deed.en

## 16.b rightsIdentifier
**Occurrence:** 0-1
**Definition:** A short, standardized version of the license name.
**Allowed values, examples, other constraints:** Note: It's suggested to use the identifiers from the [SPDX license list](https://spdx.org/licenses)
Example:
- CC-BY-3.0

### 16.c rightsIdentifierScheme
**Occurrence:** 0-1
**Definition:** The name of the scheme. 
**Allowed values, examples, other constraints:** 
Example:
- SPDX

### 16.d schemeURI
**Occurrence:** 0-1
**Definition:** The URI of the rightsIdentifierScheme.
**Allowed values, examples, other constraints:** 
Example:
- https://spdx.org/licenses

# 17 Description 
[block:callout]
{
  "type": "success",
  "title": "Recommended for discovery"
}
[/block]
**Occurrence:** 0-n
**Definition:** All additional information that does not fit in any of the other categories. May be used for technical information.
**Allowed values, examples, other constraints:** Free text. It is a best practice to supply a description.

## 17.a descriptionType 
**Occurrence:** 1
**Definition:** The type of the Description.
**Allowed values, examples, other constraints:** If Description is used, descriptionType is mandatory.

### Controlled List Values:
[block:callout]
{
  "type": "success",
  "title": "Recommended values for discovery",
  "body": "Abstract, Methods"
}
[/block]
**Abstract**
A brief description of the resource and the context in which the resource was created. 
Recommended for discovery. 
Use `<br>` to indicate a line break for improved rendering of multiple paragraphs, but otherwise no html markup. 
Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.1594/PANGAEA.771774 

**Methods**
The methodology employed for the study or research. 
Recommended for discovery. 
Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.6078/D1K01X 

**SeriesInformation**
Information about a repeating series, such as volume, issue, number. 
For use with grey literature. If providing an ISSN, use property 12 ([RelatedIdentifier](#section-12-relatedidentifier)), relatedIdentifierType=ISSN. For dataset series, use property 12 ([RelatedIdentifier](#section-12-relatedidentifier)) and describe the relationships with isPartOf or HasPart. 
Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.4229/23RDEUPVSEC2008-5CO.8.3 

**TableOfContents**
A listing of the Table of Contents. 
Use `<br>` to indicate a line break for improved rendering of multiple paragraphs, but otherwise no html markup. 
Example: https://data.datacite.org/application/vnd.datacite.datacite+xml/10.5678/LCRS/FOR816.CIT.1031 

**TechnicalInfo**
Detailed information that may be associated with design, implementation, operation, use, and/or maintenance of a process or system. 
For software description, this may include the contents of a readme.txt, and necessary environmental information (hardware, operational software, applications/programs with version information, a human-readable synopsis of software purpose) that cannot be described using other properties (e.g. Language (software)). For other uses, this can include specific and detailed information as necessary and appropriate. 

**Other**
Other description information that does not fit into an existing category. 
Use for any other description type. 

# 18 GeoLocation 
[block:callout]
{
  "type": "success",
  "title": "Recommended for discovery"
}
[/block]
**Occurrence:** 0-n
**Definition:** Spatial region or named place where the data was gathered or about which the data is focused.
**Allowed values, examples, other constraints:** Repeat this property to indicate several different locations.

## 18.1 geoLocationPoint 
**Occurrence:** 0-1
**Definition:** A point location in space.
**Allowed values, examples, other constraints:** A point contains a single longitude-latitude pair.
Use WGS 84 (World Geodetic System) coordinates. Use only decimal numbers for coordinates. Longitudes are - 180 to 180 (0 is Greenwich, negative numbers are west, positive numbers are east), Latitudes are -90 to 90 (0 is the equator; negative numbers are south, positive numbers north).
Example: -67.302

### 18.1.1 pointLongitude 
**Occurrence:** 1
**Definition:** Longitudinal dimension of point.
**Allowed values, examples, other constraints:** If geolocationPoint is used, pointLongitude is mandatory. Longitude of the geographic point expressed in decimal degrees (positive east). 
Domain: -180 <= pointLongitude <= 180
  
### 18.1.2 pointLatitude 
**Occurrence:** 1
**Definition:** Latitudinal dimension of point.
**Allowed values, examples, other constraints:** If geolocationPoint is used, pointLatitude is mandatory. Latitude of the geographic point expressed in decimal degrees (positive north)
Example: 31.233
Domain: -90<= pointLatitude <= 90

## 18.2 geoLocationBox 
**Occurrence:** 0-1
**Definition:** The spatial limits of a box.
**Allowed values, examples, other constraints:** A box is defined by two geographic points. Left low corner and right upper corner. Each point is defined by its longitude and latitude. A polygon that crosses the anti-meridian (i.e. the 180th meridian) can be represented by cutting it into two polygons such that neither crosses the anti-meridian.

### 18.2.1 westBoundLongitude 
**Occurrence:** 1
**Definition:** Western longitudinal dimension of box.
**Allowed values, examples, other constraints:** If geolocationBox is used westBoundLongitude is mandatory. Longitude of the geographic point expressed in decimal degrees (positive east). 
Domain: -180.00 ≤ westBoundLongitude ≤ 180.00

### 18.2.2 eastBoundLongitude 
**Occurrence:** 1 
**Definition:** Eastern longitudinal dimension of box.
**Allowed values, examples, other constraints:** If geolocationBox is used eastBoundLongitude is mandatory. Longitude of the geographic point expressed in decimal degrees (positive east)
Domain: -180.00 ≤ eastBoundLongitude ≤ 180.00

### 18.2.3 southBoundLatitude 
**Occurrence:** 1
**Definition:** Southern latitudinal dimension of box.
**Allowed values, examples, other constraints:** If geolocationBox is used southBoundLatitude is mandatory. Latitude of the geographic point expressed in decimal degrees (positive north).
Domain: -90.00 ≤ southBoundingLatitude ≤ 90.00

### 18.2.4 northBoundLatitude 
**Occurrence:** 1
**Definition:** Northern latitudinal dimension of box.
**Allowed values, examples, other constraints:** If geolocationBox is used northBoundLatitude is mandatory. Latitude of the geographic point expressed in decimal degrees (positive north).
Domain: -90.00 ≤ northBoundingLatitude ≤ 90.00

## 18.3 geoLocationPlace 
**Occurrence:** 0-1
**Definition:** Description of a geographic location
**Allowed values, examples, other constraints:** Free text. Use to describe a geographic location.

## 18.4 geoLocationPolygon 
**Occurrence:** 0-n 
**Definition:** A drawn polygon area, defined by a set of points and lines connecting the points in a closed chain.
**Allowed values, examples, other constraints:** A polygon is delimited by geographic points. Each point is defined by a longitudelatitude pair. The last point should be the same as the first point.

### 18.4.1 polygonPoint 
**Occurrence:** 4-n
**Definition:** A point location in a polygon.
**Allowed values, examples, other constraints:** If geoLocationPolygon is used, polygonPoint must be used as well. There must be at least 4 non-aligned points to make a closed curve, with the last point described the same as the first point.
  
### 18.4.1.1 pointLongitude 
**Occurrence:** 1
**Definition:** Longitudinal dimension of point.
**Allowed values, examples, other constraints:** If polygonPoint is used pointLongitude is mandatory. Longitude of the geographic point expressed in decimal degrees (positive east).
Domain: -180 <= pointLongitude <= 180

### 18.4.1.2 pointLatitude 
**Occurrence:** 1 
**Definition:** Latitudinal dimension of point.
**Allowed values, examples, other constraints:** If polygonPoint is used pointLatitude is mandatory. Latitude of the geographic point expressed in decimal degrees (positive north).
Domain: -90 <= pointLatitude <= 90

### 18.4.2 inPolygonPoint
**Occurrence:** 0-1 
**Definition:** For any bound area that is larger than half the earth, define a (random) point inside.
**Allowed values, examples, other constraints:** inPolygonPoint is only necessary to indicate the "inside" of the polygon if the polygon is larger than half the earth. Otherwise the smallest of the two areas bounded by the polygon will be used.

### 18.4.2.1 pointLongitude 
**Occurrence:** 1
**Definition:** Longitudinal dimension of point.
**Allowed values, examples, other constraints:** If inPolygonPoint is used pointLongitude is mandatory. Longitude of the geographic point expressed in decimal degrees (positive east). 
  
### 18.4.2.2 pointLatitude 
**Occurrence:** 1 
**Definition:** Latitudinal dimension of point.
**Allowed values, examples, other constraints:** If inPolygonPoint is used, pointLatitude is mandatory. Latitude of the geographic point expressed in decimal degrees (positive north).
 
# 19 FundingReference 
**Occurrence:** 0-n
**Definition:** Information about financial support (funding) for the resource being registered.
**Allowed values, examples, other constraints:** It is a best practice to supply funding information when financial support has been received.

## 19.1 funderName 
**Occurrence:** 1 
**Definition:** Name of the funding provider.
**Allowed values, examples, other constraints:**
Example: 
- Gordon and Betty Moore Foundation

## 19.2 funderIdentifier 
**Occurence:** 0-1 
**Definition:** Uniquely identifies a funding entity, according to various types.
**Allowed values, examples, other constraints:**
Example:
- https://doi.org/10.13039/100000936

### 19.2.a funderIdentifierType 
**Occurrence:** 0-1
**Definition:** The type of the funderIdentifier.
**Allowed values, examples, other constraints:**
Controlled List Values:
- Crossref Funder ID. The FundRef service is now called “[Open Funder Registry](https://www.crossref.org/services/funder-registry/)”  and Crossref Funder ID is the new name for a Fundref identifier.
- GRID
- ISNI
- ROR
- Other

## 19.2.b SchemeURI
**Occurrence:** 0-1
**Definition:** The URI of the funder identifier schema. 
**Allowed values, examples, other constraints:**
Examples:
- https://www.crossref.org/services/funder-registry/
- https://ror.org/

## 19.3 awardNumber 
**Occurrence:** 0-1
**Definition:** The code assigned by the funder to a sponsored award (grant).
**Allowed values, examples, other contraints:**
Example:
- GBMF3859.01

### 19.3.a awardURI 
**Occurrence:** 0-1
**Definition:** The URI leading to a page provided by the funder for more information about the award (grant).
**Allowed values, examples, other contraints:**
Example:
- https://www.moore.org/grants/list/GBMF3859.01

## 19.4 awardTitle 
**Occurrence:** 0-1 
**Definition:** The human readable title or name of the award (grant).
**Allowed values, examples, other contraints:**
Example:
- Socioenvironmental Monitoring of the Amazon Basin and Xingu