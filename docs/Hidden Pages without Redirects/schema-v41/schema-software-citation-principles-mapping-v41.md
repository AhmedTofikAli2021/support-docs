---
title: DataCite Metadata Schema v4.1 FORCE11 Software Citation Principles Mapping
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: schema-metadata-examples-v41
      title: DataCite Metadata Schema v4.1 XML Metadata Examples
---
For full Software Citation Principles see:
Smith AM, Katz DS, Niemeyer KE, FORCE11 Software Citation Working Group. (2016) Software citation principles. PeerJ Computer Science 2:e86 https://doi.org/10.7717/peerj-cs.86
[block:parameters]
{
  "data": {
    "h-0": "FORCE11 Requirements",
    "h-1": "DataCite Schema v. 4.1",
    "h-2": "Comments",
    "0-0": "Unique identifier – recommend a DOI",
    "0-1": "Identifier\nwith identifierType ‘DOI’",
    "0-2": "For software a decision may need to be made about whether the ID is for a specific version of a piece of software (recommended by Force11 Software Citation Principles), for a piece of software i.e. all versions or for the latest version.",
    "1-0": "Software name",
    "1-1": "Title",
    "1-2": "May be the title of a dataset or the name of a piece of software.",
    "2-0": "Author",
    "2-1": "Creator",
    "2-2": "May include those responsible for software creation.",
    "3-0": "Contributor",
    "3-1": "Contributor",
    "3-2": "For software, if there is an alternate entity that “holds, archives, publishes, prints, distributes, releases, issues, or produces the code, use the contributorType “HostingInstitution” for the code repository.",
    "4-0": "Contributor role",
    "4-1": "contributorType",
    "4-2": "See Definition in contributorType Appendix: Distributor: Includes distribution of software.\nSee Example for HostingInstitution: Includes software or run code repositories.",
    "5-0": "Version number",
    "5-1": "Version",
    "5-2": "See Version example: Software engineering practice follows this approach of tracking changes and giving new version numbers.",
    "6-0": "Release date",
    "6-1": "PublicationYear",
    "6-2": "See definition:\nIn the case of resources such as software where there may be multiple releases in one year, other DataCite metadata or information such as the landing page should enable users to identify the newest one.",
    "7-0": "Location/repository",
    "7-1": "Publisher or Contributor/contributorType ‘HostingInstitution’",
    "7-2": "For software, use Publisher for Code Repository, following the data model. If there is an alternate entity that \"holds, archives, publishes, prints, distributes, releases, issues, or produces\" the code, use the contributorType \"hostingInstitution\" for the code repository.\"",
    "8-0": "Indexed citations\n(and links between software versions)",
    "8-1": "relationType +",
    "8-2": "RelationTypes of use for software.",
    "9-1": "HasVersion, IsVersionOf",
    "9-2": "HasVersion - The registered resource such as a software package or code repository has a versioned instance (indicates A has the instance B) e.g. it may be used to relate an un- versioned code repository to one of its specific software versions.\nIsVersionOf - The registered resource is an instance of a target resource (indicates that A is an instance of B) e.g. it may be used to relate a specific version of a software package to its software code repository.",
    "10-1": "IsNewVersionOf, IsPreviousVersionOf",
    "10-2": "IsNewVersionOf: can be used for “edition or software release etc.”\nIsPreviousVersionOf: can be used for “edition or software release etc.”",
    "11-1": "IsDerivedFrom, IsSourceOf",
    "11-2": "IsDerivedFrom and IsSourceOf: Can be used to denote software that is a fork of other software or is the origin of a fork.",
    "12-1": "IsPartOf,HasPart",
    "12-2": "IsPartOf and HasPart: may be used for individual software modules",
    "13-1": "IsDocumentedBy, Documents",
    "13-2": "IsDocumentedBy and Documents: e.g. points to software documentation",
    "14-1": "IsVariantFormOf, IsOriginalFormOf",
    "14-2": "IsVariantFormOf and IsOriginalFormOf: May be used for different software operating systems or compiler formats, for example. Indicates that A is a variant or different form or packaging of B.",
    "15-1": "IsRequiredBy, Requires",
    "15-2": "IsRequiredBy: the registered resource A is called by or is required by software resource B.\nRequires: the registered resource A calls or requires software resource B.",
    "16-0": "Software licenses",
    "16-1": "Rights",
    "16-2": "See example: May be used for software licenses.",
    "17-0": "Description",
    "17-1": "Description\n\nDescription with descriptionType ‘TechnicalInfo’\n\nDescription with descriptionType ‘Abstract’",
    "17-2": "TechnicalInfo: for software description, this may include a readme.text, and necessary environmental information (hardware, operational software, applications/programs) that cannot be described using other properties such as ‘Format/version’ or ‘Description/summary’",
    "18-0": "Keywords",
    "18-1": "Subject",
    "18-2": "Existing guidance applies: Subject, keyword, classification code, or key phrase describing the resource."
  },
  "cols": 3,
  "rows": 19
}
[/block]