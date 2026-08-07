---
title: A crosswalk of the DataCite schema to RDA metadata standard for DMPs
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
The following examples break each element/section down into how you can map it to the RDA metadata standard for DMPs. The full JSON file showcasing relevant RDA DMP metadata elements can be found at the end for reference.

## Example DataCite DMP record

```xml
<?xml version="1.0"?>
<resource xmlns="http://datacite.org/schema/kernel-4"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://datacite.org/schema/kernel-4 http://schema.datacite.org/meta/kernel-4/metadata.xsd">
 <resourceType resourceTypeGeneral="Text">OutputManagementPlan
</resourceType>
 <identifier identifierType="DOI">10.12345/ABC123</identifier>
 <creators>
   <creator>
     <creatorName>Smith, John</creatorName>
     <nameIdentifier nameIdentifierScheme="ORCID"
                     schemeURI="http://orcid.org/">
       https://orcid.org/0000-0000-0000-000X
     </nameIdentifier>
     <affiliation affiliationIdentifier="https://ror.org/xxxxx"
                  affiliationIdentifierScheme="ROR">
       Generic University
     </affiliation>
   </creator>
 </creators>
 <titles>
   <title xml:lang="en-US">Lorem Ipsum</title>
 </titles>
 <publisher>Generic Repository</publisher>
 <publicationYear>2021</publicationYear>
 <contributors>
   <contributor contributorType="HostingInstitution">
     <contributorName>Generic Repository</contributorName>
     <nameIdentifier nameIdentifierScheme="ROR">https://ror.org/zzzzz</nameIdentifier>
   </contributor>
   <contributor contributorType="Producer">
     <contributorName>Generic University</contributorName>
     <nameIdentifier nameIdentifierScheme="ROR">https://ror.org/xxxxx</nameIdentifier>
   </contributor>
   <contributor contributorType="ProjectLeader">
     <contributorName>Doe PhD, Jane</contributorName>
     <nameIdentifier nameIdentifierScheme="ORCID"
                     schemeURI="http://orcid.org/">https://orcid.org/0000-0000-0000-000Y</nameIdentifier>
     <affiliation affiliationIdentifier="https://ror.org/yyyy"
                  affiliationIdentifierScheme="ROR">
       Example University
     </affiliation>
   </contributor>
 </contributors>
 <language>en</language>
 <relatedIdentifiers>
   <relatedIdentifier relationType="IsReferencedBy"
                     relatedIdentifierType="DOI">https://doi.org/10.0000/ABC12XY3</relatedIdentifier>
 </relatedIdentifiers>
 <descriptions>
   <description xml:lang="en"descriptionType="Abstract">
     Lorem Ipsum …
   </description>
 </descriptions>
 <fundingReferences>
   <fundingReference>
     <funderName>National Generic Funder</funderName>
     <funderIdentifier funderIdentifierType="Crossref Funder ID">https://doi.org/10.13039/000000000</funderIdentifier>
     <awardNumber awardURI="https://awards.example.org/123">123</awardNumber>
     <awardTitle>Lorem Ipsum</awardTitle>
   </fundingReference>
 </fundingReferences>
</resource>
```

## DataCite/RDA maDMP field mappings

Mapping each element/section of the DataCite schema to the equivalent RDA metadata standard for DMPs data.

### Resource Type

Datacite:

```xml
<resourceType resourceTypeGeneral="OutputManagementPlan">Data Management Plan</resourceType>
```

RDA metadata standard:  
No equivalent field; the entire record is wrapped in a field "dmp"

### Identifier

Datacite:

```xml
<identifier identifierType="DOI">10.12345/ABC123</identifier>
```

RDA metadata standard:

```json
"dmp_id": { "type":"doi", "identifier": "https://doi.org/10.0000/ABCD1234" },
```

### Titles

DataCite:

```xml
<titles>
  <title xml:lang="en-US">Lorem ipsum</title>
</titles>
```

RDA metadata standard:

- Note that the RDA standard allows for a single title entry. The language attribute can be derived from the `language` entry in the RDA standard.

```json
"title": "Lorem ipsum",
```

### Language

DataCite:

```xml
<language>en</language>
```

RDA metadata standard:

```json
"language": "eng"
```

### Publisher and Publication Year

DataCite

```xml
<publisher>My System</publisher>
<publicationYear>2021</publicationYear>
```

RDA metadata standard:  
\*Note: there is no equivalent for this in the RDA standard. Typically though the RDA `created` date’s year would match the year used in DataCite’s ‘publicationYear’ element. The DataCite Publisher would typically match the name of your system/repository.

```json
"created": "2021-03-09T20:49:42Z"
```

### Creators

DataCite:

```xml
<creators>
   <creator>
     <creatorName>Smith, John</creatorName>
     <nameIdentifier nameIdentifierScheme="ORCID" schemeURI="http://orcid.org/">
       https://orcid.org/0000-0000-0000-000X
     </nameIdentifier>
     <affiliation affiliationIdentifier="https://ror.org/xxxxx"
                  affiliationIdentifierScheme="ROR">Generic University</affiliation>
   </creator>
 </creators>
```

RDA metadata standard:

```json
"contact":{
  "name": "Smith, John",
  "affiliation": {
    "name": "Generic University",
    "affiliation_id": { "type": "ror", "identifier": "https://ror.org/xxxxx" }
  },
  "contact_id": { "type": "orcid", "identifier": "https://orcid.org/0000-0000-0000-000X" }
},
```

### Contributors

DataCite:

```xml
<contributors>
  <contributor contributorType="HostingInstitution">
    <contributorName>Repository X</contributorName>
    <nameIdentifier nameIdentifierScheme="ROR">https://ror.org/zzzzz</nameIdentifier>
  </contributor>
  <contributor contributorType="Producer">
    <contributorName>Example University</contributorName>
    <nameIdentifier nameIdentifierScheme="ROR">https://ror.org/yyyyy</nameIdentifier>
  </contributor>
  <contributor contributorType="ProjectLeader">
    <contributorName>Doe PhD, Jane</contributorName>
    <nameIdentifier nameIdentifierScheme="ORCID" schemeURI="http://orcid.org/">
      https://orcid.org/0000-0000-0000-000Y</nameIdentifier>
     <affiliation affiliationIdentifier="https://ror.org/yyyyy"
                  affiliationIdentifierScheme="ROR">Example University</affiliation>
  </contributor>
</contributors>
```

RDA metadata standard:

- Note: the contributors defined in the RDA standard should be passed through to the DataCite contributors section along with the following 2 additional contributor types:  
      _ HostingInstitution - It is good practice to identify the system/repository that will be providing the  
        landing page for this DMP ID.  
       _ Producer - The institution(s) responsible for the ownership of the DMP. People can change  
        institutions over time so this allows us to record the provenance directly.

```json
"contributor": [
  {
    "name": "Doe PhD, Jane",
    "role": ["http://credit.niso.org/contributor-roles/investigation"],
    "affiliation": {
      "name": "Example University",
      "affiliation_id": { "type": "ror", "identifier": "https://ror.org/yyyyy" }
    },
    "contributor_id": { 
      "type": "orcid", 
      "identifier": "https://orcid.org/0000-0000-0000-000Y" 
    }
  }
]
```

### Funding

DataCite:

```xml
<fundingReferences>
  <fundingReference>
    <funderName>National Generic Funder</funderName>
    <funderIdentifier funderIdentifierType="Crossref Funder ID">
      https://doi.org/10.13039/00000000
    </funderIdentifier>
    <awardNumber awardURI="https://awards.example.org/123">
      123
    </awardNumber>
    <awardTitle>Lorem Ipsum</awardTitle>
  </fundingReference>
</fundingReferences>
```

RDA metadata standard:  
Note: that the RDA standard does not provide a way to convey a name/title for the award so we just repeat the title of the DMP here

```json
"project": [
  {
    "funding": [
      {
        "name": "National Generic Funder",
        "funder_id": { "type": "fundref", "identifier": "https://doi.org/10.13039/000000000" },
        "grant_id": { "type": "url", "identifier": "http://awards.example.org/123" },
      }
   ]
 }
]
```

### Related Identifiers

Datacite:

```xml
<relatedIdentifiers>
  <relatedIdentifier relationType="IsReferencedBy"
                      relatedIdentifierType="URL">
    https://doi.org/10.00000/ABC12XY3
     </relatedIdentifier>
</relatedIdentifiers>
```

RDA metadata standard:  
Note: that this is an extension to the RDA metadata standard. There is conversation about supporting this in the future. We are handling this way until it is officially supported.

```json
"dmproadmap_related_identifiers":[
  { 
    "type": "doi", 
    "descriptor": "is_referenced_by", 
    "identifier": "https://doi.org/10.00000/ABC12XY3" 
  }
]
```

## Full RDA JSON maDAMP example

```json
{
 "dmp": {
   "title": "Lorem ipsum",
   "description": "Lorem ipsum est ...",
   "created": "2021-03-09T20:49:42Z",
   "language": "eng",
   "dmp_id": { "type":"doi", "identifier": "https://doi.org/10.0000/ABCD1234" },
   "contact":{
     "name": "Smith, John",
     "affiliation": {
       "name": "Generic University",
       "affiliation_id": { "type": "ror", "identifier": "https://ror.org/xxxxx" }
     },
     "contact_id": { "type": "orcid", "identifier": "https://orcid.org/0000-0000-0000-000X" }
   },
   "contributor": [
     {
       "name": "Doe PhD, Jane",
       "role": ["http://credit.niso.org/contributor-roles/investigation"],
       "affiliation": {
         "name": "Example University",
         "affiliation_id": { "type": "ror", "identifier": "https://ror.org/yyyyy" }
       },
       "contributor_id": { "type": "orcid", "identifier": "https://orcid.org/0000-0000-0000-000Y" }
     }
   ],
   "project": [
     {
       "funding": [{
         "name": "National Generic Funder",
         "funder_id": { "type": "fundref", "identifier": "https://doi.org/10.13039/000000000" },
         "grant_id": { "type": "url", "identifier": "http://awards.example.org/123" },
       }]
     }
   ],
   "dmproadmap_related_identifiers":[
     { "type": "doi", "descriptor": "is_referenced_by", "identifier": "10.00000/ZZ99X0" }
   ]
 }
}
```