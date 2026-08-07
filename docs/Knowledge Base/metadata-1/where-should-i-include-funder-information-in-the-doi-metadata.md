---
title: Where should I include funder information in the DOI metadata?
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
If the resource being published received grant funding from a funder e.g FP7,  this information can be included in the DOI metadata in the fundingReferences section.

Example:
[block:code]
{
  "codes": [
    {
      "code": "<fundingReferences>\n<fundingReference>\n<funderName>Seventh FrameworkProgramme</funderName><funderIdentifier funderIdentifierType=\"Crossref FunderID\" schemeURI=<http://doi.org/\">http://dx.doi.org/10.13039/100011102</funderIdentifier>\n<awardNumber awardURI=\"<http://cordis.europa.eu/project/rcn/100180_en.html\"282625/\nawardNumber>\n<awardTitle>MOTivational strength ofecosystem services and alternativeways to express the value ofBIOdiversity</awardTitle>\n</fundingReference>\n</fundingReferences>",
      "language": "text"
    }
  ]
}
[/block]
In this case the funderIdentifier DOI is the Crossref Funder ID. Some funders may have multiple identifiers. The DOI is for FP7, and there is a different DOI for H2020, and there will be for Horizon
Europe. 

You can look them up [here](https://search.crossref.org/funding).