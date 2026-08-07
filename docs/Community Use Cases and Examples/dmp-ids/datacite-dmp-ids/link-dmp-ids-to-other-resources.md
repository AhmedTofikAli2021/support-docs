---
title: Link DMP IDs to other resources
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
The metadata associated with the DMP ID can be used to link it to related datasets and publications, the people involved, organizations, and funders. There are a few places where linking metadata can be added:
 
RelatedIdentifiers (e.g. DOIs)  using the "citations" relationship types.
[block:code]
{
  "codes": [
    {
      "code": " <relatedIdentifiers>\n        <relatedIdentifier relatedIdentifierType=\"DOI\" relationType=\"IsCitedBy\" resourceTypeGeneral=\"JournalArticle\">10.0158/4z9r-b441</relatedIdentifier>\n    </relatedIdentifiers>",
      "language": "xml"
    }
  ]
}
[/block]
Creators and Contributors with their affiliations (e.g. ORCID iD + ROR iD) 
[block:code]
{
  "codes": [
    {
      "code": "   <creators>\n        <creator>\n            <creatorName nameType=\"Personal\">Carberry, Josiah</creatorName>\n            <givenName>Josiah</givenName>\n            <familyName>Carberry</familyName>\n            <nameIdentifier nameIdentifierScheme=\"ORCID\" schemeURI=\"https://orcid.org\">https://orcid.org/0000-0002-1028-6941</nameIdentifier>\n            <affiliation affiliationIdentifier=\"https://ror.org/02qz8b764\" affiliationIdentifierScheme=\"ROR\" schemeURI=\"https://ror.org\">Cold Spring Harbor Laboratory</affiliation>\n        </creator>\n    </creators>",
      "language": "xml"
    }
  ]
}
[/block]
Contributors can be of three types: *ProjectLeader*, *Producer*, *DataCurator* 
[block:code]
{
  "codes": [
    {
      "code": "<contributors>\n<contributor contributorType=\"ProjectLeader\">\n<contributorName>Starr, Joan</contributorName>\n<givenName>Joan</givenName>\n<familyName>Starr</familyName>\n<nameIdentifier schemeURI=\"https://orcid.org/\" nameIdentifierScheme=\"ORCID\">0000-0002-7285-027X</nameIdentifier>\n<affiliation>California Digital Library</affiliation>\n</contributor>\n</contributors>",
      "language": "xml"
    }
  ]
}
[/block]
Funders (e.g. FunderIDs) 
[block:code]
{
  "codes": [
    {
      "code": " <fundingReferences>\n        <fundingReference>\n            <funderName>National Science Foundation</funderName>\n            <funderIdentifier funderIdentifierType=\"Crossref Funder ID\">https://doi.org/10.13039/100000001</funderIdentifier>\n            <awardNumber awardURI=\"https://www.nsf.gov/awardsearch/showAward?AWD_ID=1745675&amp;HistoricalAwards=false\">1745675</awardNumber>\n            <awardTitle>DMP Roadmap: Making Data Management Plans Actionable</awardTitle>\n        </fundingReference>\n    </fundingReferences>",
      "language": "xml"
    }
  ]
}
[/block]