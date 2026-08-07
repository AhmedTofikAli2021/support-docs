---
title: Connecting Research Outputs (SCHOLIX)
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
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/47f5c62-Screen_Shot_2017-01-02_at_10.45.22.png",
        "Screen Shot 2017-01-02 at 10.45.22.png",
        1830,
        876,
        "#1d1d1d"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "SCHOLIX: A Framework for Scholarly Link eXchange"
}
[/block]
The Scholix initiative is a high level interoperability framework for exchanging information about the links between scholarly literature and data. It aims to build an open information ecosystem to understand systematically what data underpins literature and what literature references data.
[block:api-header]
{
  "type": "basic",
  "title": "Related identifiers"
}
[/block]
The DataCite Metadata Schema supports the `relatedIdentifier` property. It is used to connect an object to other related resources. The identifiers used by this property must be globally unique.

`relatedIdentifierType` is a mandatory subproperty with a controlled list of supported unique identifiers: ARK, arXiv, bibcode, DOI, EAN13, EISSN, Handle, IGSN, ISBN, ISSN, ISTC, LISSN, LSID, PMID, PURL, UPC, URL and URN.

`relationType` describes the relationship of the resource being registered with a DOI and the related resource. It is also a mandatory subproperty with a controlled list of relations: IsCitedBy, Cites, IsSupplementTo, IsSupplementedBy, IsContinuedBy, Continues, HasMetadata, IsMetadataFor, IsNewVersionOf, IsPreviousVersionOf, IsPartOf, HasPart, IsReferencedBy, References, IsDocumentedBy, Documents, IsCompiledBy, Compiles, IsVariantFormOf, IsOriginalFormOf, IsIdenticalTo, IsReviewedBy, Reviews, IsDerivedFrom and IsSourceOf.

This is an example of a `relatedIdentifier` for extra metadata in a URL:
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifiers>\n   <relatedIdentifier relatedIdentifierType=\"URL\" \n                      relatedMetadataScheme=\"ISA-Tab\" \n                      relationType=\"HasMetadata\" \n                      schemeType=\"Text\"   \n                      schemeURI=\"http://isatab.sourceforge.net/docs/ISA-TAB_release-candidate-1_v1.0_24nov08.pdf\">\n      http://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE18695\n   </relatedIdentifier>\n</relatedIdentifiers>",
      "language": "text"
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Authors and contributors"
}
[/block]
`creators` and `contributors` are also properties of the DataCite Metadata Schema. In version 4.0 of the Schema, we introduced improvements to make them more flexible.

DataCite encourages all its users to provide the names of the creators and contributors making use of the `familyName` and `givenName` when available.

`nameIdentifier` is also particularly important in order to connect research outputs. It connects the authors of a given object to their ORCID or ISNI records and enables services such as ORCID Auto-Update.
[block:code]
{
  "codes": [
    {
      "code": "<creators>\n   <creator>\n      <creatorName>Miller, Elizabeth</creatorName>\n      <givenName>Elizabeth</givenName>\n      <familyName>Miller</familyName>\n      <nameIdentifier schemeURI=\"http://orcid.org/\"\n                      nameIdentifierScheme=\"ORCID\">\n         0000-0001-5000-0007</nameIdentifier>\n      <affiliation>DataCite</affiliation>\n   </creator>\n</creators>",
      "language": "text"
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Funding information"
}
[/block]
`FundingReference` is a property of the DataCite Metadata Schema where you can include information about financial support (funding) for the resource being registered. It is a best practice to supply funding information when financial support has been received.

The subproperties `funderName`, `funderIdentifier` and `funderIdentifierType` (controlled) identify the funding body; while `awardNumber`, `awardURI` and `awardTitle` identify the grant or project details.
[block:code]
{
  "codes": [
    {
      "code": "<FundingReference>\n   <funderName>\n      Gordon and Betty Moore Foundation\n   </funderName>\n   <funderIdentifier>\n      https://doi.org/10.13039/100000936\n   </funderIdentifier>\n   <funderIdentifierType>\n      Crossref Funder\n   </funderIdentifierType>  \n   <awardNumber>\n      GBMF3859.01\n   </awardNumber>\n   <awardURI>\n      https://www.moore.org/grants/list/GBMF3859.01\n   </awardURI>\n   <awardTitle>\n      Socioenvironmental Monitoring of the Amazon Basin and Xingu\n   </awardTitle>\n</FundingReference>",
      "language": "text"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]