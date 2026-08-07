---
title: Connecting to Organizations
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
There are several places where organizations can be included in DataCite DOI metadata.

- **Affiliations: **Creators and contributors have an affiliation sub-property. This property has an optional affiliationIdentifier attribute for organizational identifiers (e.g. ROR IDs). 
- **Creators and contributors:** In cases where an organization is itself a creator or contributor, the nameIdentifier sub-property can be used to include an organizational identifier.
- **Funders:** The fundingReference property is used for funding organizations. This property has an optional sub-property funderIdentifier for an appropriate identifier (e.g. Crossref Funder ID, ROR ID).
- **Publisher:** The publisher property has an optional publisherIdentifier sub-property that can be used to include an organizational identifier (e.g. a ROR ID). 

## Examples

Creator with affiliationIdentifier:

```xml
<creator>
  <creatorName nameType="Personal">Garcia, Sofia</creatorName>
  <givenName>Sofia</givenName>
  <familyName>Garcia</familyName>
  <nameIdentifier schemeURI="https://orcid.org/" nameIdentifierScheme="ORCID">0000-0001-5727-2427</nameIdentifier>
  <affiliation affiliationIdentifier="https://ror.org/03efmqc40" affiliationIdentifierScheme="ROR" SchemeURI="https://ror.org">Arizona State University</affiliation>
</creator>
```

Contributor with nameIdentifier for organization:

```xml
<contributor contributorType="RegistrationAgency">
  <contributorName nameType="Organizational">DataCite</contributorName>
  <nameIdentifier schemeURI="https://ror.org/" nameIdentifierScheme="ROR">https://ror.org/04wxnsj81</nameIdentifier>
</contributor>
```

FundingReference with funderIdentifier:

```xml
<fundingReference>
  <funderName>European Commission</funderName>
  <funderIdentifier funderIdentifierType="Crossref Funder ID">https://doi.org/10.13039/501100000780</funderIdentifier>
  <awardNumber awardURI="https://cordis.europa.eu/project/rcn/100180_en.html">282625</awardNumber>
  <awardTitle>MOTivational strength of ecosystem services and alternative ways to express the value of BIOdiversity</awardTitle>
</fundingReference>
```

Publisher with publisherIdentifier:

```xml
  <publisher publisherIdentifier="https://ror.org/04wxnsj81" publisherIdentifierScheme="ROR" schemeURI="https://ror.org/">DataCite</publisher>
```