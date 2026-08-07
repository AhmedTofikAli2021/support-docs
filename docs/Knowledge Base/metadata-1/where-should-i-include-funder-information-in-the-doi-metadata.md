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
If the resource being published received grant funding from a funder e.g The Seventh Framework Programme (European Union),  this information can be included in the DOI metadata in the fundingReferences section.

Example:

```xml
<fundingReferences>
<fundingReference>
  <funderName>Seventh FrameworkProgramme</funderName>
  <funderIdentifier funderIdentifierType="Crossref Funder ID" schemeURI="http://doi.org/">http://doi.org/10.13039/100011102</funderIdentifier>
  <awardNumber awardURI="http://cordis.europa.eu/project/rcn/100180_en.html">282625</awardNumber>
  <awardTitle>MOTivational strength ofecosystem services and alternativeways to express the value ofBIOdiversity</awardTitle>
</fundingReference>
</fundingReferences>
```

In this case the funderIdentifier DOI is the Crossref Funder ID. Some funders may have multiple identifiers. For example the European Union has numerous funding mechanisms each with a separate DOI.

You can look them up [here](https://search.crossref.org/funding).