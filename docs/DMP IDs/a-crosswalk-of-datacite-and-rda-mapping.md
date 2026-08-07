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
The following examples break each element/section down into how you can map it to the RDA metadata standard for DMPs. The full RDA JSON file (well just the relevant parts) can be found at the end for reference.

## Example DataCite DMP record
[block:code]
{
  "codes": [
    {
      "code": "<?xml version=\"1.0\"?>\n<resource xmlns=\"http://datacite.org/schema/kernel-4\"\n         xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\"\n         xsi:schemaLocation=\"http://datacite.org/schema/kernel-4 http://schema.datacite.org/meta/kernel-4/metadata.xsd\">\n <resourceType resourceTypeGeneral=\"Text\">OutputManagementPlan\n</resourceType>\n <identifier identifierType=\"DOI\">10.12345/ABC123</identifier>\n <creators>\n   <creator>\n     <creatorName>Smith, John</creatorName>\n     <nameIdentifier nameIdentifierScheme=\"ORCID\"\n                     schemeURI=\"http://orcid.org/\">\n       https://orcid.org/0000-0000-0000-000X\n     </nameIdentifier>\n     <affiliation affiliationIdentifier=\"https://ror.org/xxxxx\"\n                  affiliationIdentifierScheme=\"ROR\">\n       Generic University\n     </affiliation>\n   </creator>\n </creators>\n <titles>\n   <title xml:lang=\"en-US\">Lorem Ipsum</title>\n </titles>\n <publisher>Generic Repository</publisher>\n <publicationYear>2021</publicationYear>\n <contributors>\n   <contributor contributorType=\"HostingInstitution\">\n     <contributorName>Generic Repository</contributorName>\n     <nameIdentifier nameIdentifierScheme=\"ROR\">https://ror.org/zzzzz</nameIdentifier>\n   </contributor>\n   <contributor contributorType=\"Producer\">\n     <contributorName>Generic University</contributorName>\n     <nameIdentifier nameIdentifierScheme=\"ROR\">https://ror.org/xxxxx</nameIdentifier>\n   </contributor>\n   <contributor contributorType=\"ProjectLeader\">\n     <contributorName>Doe PhD, Jane</contributorName>\n     <nameIdentifier nameIdentifierScheme=\"ORCID\"\n                     schemeURI=\"http://orcid.org/\">https://orcid.org/0000-0000-0000-000Y</nameIdentifier>\n     <affiliation affiliationIdentifier=\"https://ror.org/yyyy\"\n                  affiliationIdentifierScheme=\"ROR\">\n       Example University\n     </affiliation>\n   </contributor>\n </contributors>\n <language>en</language>\n <relatedIdentifiers>\n   <relatedIdentifier relationType=\"IsReferencedBy\"\n                     relatedIdentifierType=\"DOI\">https://doi.org/10.0000/ABC12XY3</relatedIdentifier>\n </relatedIdentifiers>\n <descriptions>\n   <description xml:lang=\"en\"descriptionType=\"Abstract\">\n     Lorem Ipsum …\n   </description>\n </descriptions>\n <fundingReferences>\n   <fundingReference>\n     <funderName>National Generic Funder</funderName>\n     <funderIdentifier funderIdentifierType=\"Crossref Funder ID\">https://doi.org/10.13039/000000000</funderIdentifier>\n     <awardNumber awardURI=\"https://awards.example.org/123\">123</awardNumber>\n     <awardTitle>Lorem Ipsum</awardTitle>\n   </fundingReference>\n </fundingReferences>\n</resource>",
      "language": "xml"
    }
  ]
}
[/block]
## DataCite/RDA maDMP field mappings

Mapping each element/section of the DataCite schema to the equivalent RDA metadata standard for DMPs data.

### Resource Type
Datacite:
[block:code]
{
  "codes": [
    {
      "code": "<resourceType resourceTypeGeneral=\"OutputManagementPlan\">Data Management Plan</resourceType>",
      "language": "xml"
    }
  ]
}
[/block]
RDA metadata standard:
No equivalent field; the entire record is wrapped in a field "dmp"

### Identifier

Datacite:
[block:code]
{
  "codes": [
    {
      "code": "<identifier identifierType=\"DOI\">10.12345/ABC123</identifier>",
      "language": "xml"
    }
  ]
}
[/block]
RDA metadata standard:
[block:code]
{
  "codes": [
    {
      "code": "\"dmp_id\": { \"type\":\"doi\", \"identifier\": \"https://doi.org/10.0000/ABCD1234\" },",
      "language": "xml"
    }
  ]
}
[/block]
### Titles

DataCite:
[block:code]
{
  "codes": [
    {
      "code": "<titles>\n  <title xml:lang=\"en-US\">Lorem ipsum</title>\n</titles>",
      "language": "xml"
    }
  ]
}
[/block]

RDA metadata standard:
* Note that the RDA standard allows for a single title entry. The language attribute can be derived from the `language` entry in the RDA standard.
[block:code]
{
  "codes": [
    {
      "code": "\"title\": \"Lorem ipsum\",",
      "language": "xml"
    }
  ]
}
[/block]
### Language

DataCite:
[block:code]
{
  "codes": [
    {
      "code": "<language>en</language>",
      "language": "xml"
    }
  ]
}
[/block]
RDA metadata standard:
[block:code]
{
  "codes": [
    {
      "code": "\"language\": \"eng\"",
      "language": "xml"
    }
  ]
}
[/block]
### Publisher and Publication Year

DataCite
[block:code]
{
  "codes": [
    {
      "code": "<publisher>My System</publisher>\n<publicationYear>2021</publicationYear>",
      "language": "xml"
    }
  ]
}
[/block]
RDA metadata standard:
*Note: there is no equivalent for this in the RDA standard. Typically though the RDA `created` date’s year would match the year used in DataCite’s ‘publicationYear’ element. The DataCite Publisher would typically match the name of your system/repository.
[block:code]
{
  "codes": [
    {
      "code": "\"created\": \"2021-03-09T20:49:42Z\"",
      "language": "xml"
    }
  ]
}
[/block]
### Creators

DataCite:
[block:code]
{
  "codes": [
    {
      "code": "<creators>\n   <creator>\n     <creatorName>Smith, John</creatorName>\n     <nameIdentifier nameIdentifierScheme=\"ORCID\" schemeURI=\"http://orcid.org/\">\n       https://orcid.org/0000-0000-0000-000X\n     </nameIdentifier>\n     <affiliation affiliationIdentifier=\"https://ror.org/xxxxx\"\n                  affiliationIdentifierScheme=\"ROR\">Generic University</affiliation>\n   </creator>\n </creators>",
      "language": "xml"
    }
  ]
}
[/block]
RDA metadata standard:
[block:code]
{
  "codes": [
    {
      "code": "\"contact\":{\n  \"name\": \"Smith, John\",\n  \"affiliation\": {\n    \"name\": \"Generic University\",\n    \"affiliation_id\": { \"type\": \"ror\", \"identifier\": \"https://ror.org/xxxxx\" }\n  },\n  \"contact_id\": { \"type\": \"orcid\", \"identifier\": \"https://orcid.org/0000-0000-0000-000X\" }\n},",
      "language": "xml"
    }
  ]
}
[/block]
### Contributors

DataCite:
[block:code]
{
  "codes": [
    {
      "code": "<contributors>\n  <contributor contributorType=\"HostingInstitution\">\n    <contributorName>Repository X</contributorName>\n    <nameIdentifier nameIdentifierScheme=\"ROR\">https://ror.org/zzzzz</nameIdentifier>\n  </contributor>\n  <contributor contributorType=\"Producer\">\n    <contributorName>Example University</contributorName>\n    <nameIdentifier nameIdentifierScheme=\"ROR\">https://ror.org/yyyyy</nameIdentifier>\n  </contributor>\n  <contributor contributorType=\"ProjectLeader\">\n    <contributorName>Doe PhD, Jane</contributorName>\n    <nameIdentifier nameIdentifierScheme=\"ORCID\" schemeURI=\"http://orcid.org/\">\n      https://orcid.org/0000-0000-0000-000Y</nameIdentifier>\n     <affiliation affiliationIdentifier=\"https://ror.org/yyyyy\"\n                  affiliationIdentifierScheme=\"ROR\">Example University</affiliation>\n  </contributor>\n</contributors>\n",
      "language": "xml"
    }
  ]
}
[/block]
RDA metadata standard:
* Note: the contributors defined in the RDA standard should be passed through to the DataCite contributors section along with the following 2 additional contributor types:
      * HostingInstitution - It is good practice to identify the system/repository that will be providing the 
        landing page for this DMP ID.
       * Producer - The institution(s) responsible for the ownership of the DMP. People can change 
        institutions over time so this allows us to record the provenance directly.

[block:code]
{
  "codes": [
    {
      "code": "\"contributor\": [\n  {\n    \"name\": \"Doe PhD, Jane\",\n    \"role\": [\"http://credit.niso.org/contributor-roles/investigation\"],\n    \"affiliation\": {\n      \"name\": \"Example University\",\n      \"affiliation_id\": { \"type\": \"ror\", \"identifier\": \"https://ror.org/yyyyy\" }\n    },\n    \"contributor_id\": { \n      \"type\": \"orcid\", \n      \"identifier\": \"https://orcid.org/0000-0000-0000-000Y\" \n    }\n  }\n]",
      "language": "xml"
    }
  ]
}
[/block]
### Funding

DataCite:
[block:code]
{
  "codes": [
    {
      "code": "<fundingReferences>\n  <fundingReference>\n    <funderName>National Generic Funder</funderName>\n    <funderIdentifier funderIdentifierType=\"Crossref Funder ID\">\n      https://doi.org/10.13039/00000000\n    </funderIdentifier>\n    <awardNumber awardURI=\"https://awards.example.org/123\">\n      123\n    </awardNumber>\n    <awardTitle>Lorem Ipsum</awardTitle>\n  </fundingReference>\n</fundingReferences>",
      "language": "xml"
    }
  ]
}
[/block]
RDA metadata standard:
Note: that the RDA standard does not provide a way to convey a name/title for the award so we just repeat the title of the DMP here
[block:code]
{
  "codes": [
    {
      "code": "\"project\": [\n  {\n    \"funding\": [\n      {\n        \"name\": \"National Generic Funder\",\n        \"funder_id\": { \"type\": \"fundref\", \"identifier\": \"https://doi.org/10.13039/000000000\" },\n        \"grant_id\": { \"type\": \"url\", \"identifier\": \"http://awards.example.org/123\" },\n      }\n   ]\n }\n]",
      "language": "xml"
    }
  ]
}
[/block]
### Related Identifiers

Datacite:
[block:code]
{
  "codes": [
    {
      "code": "<relatedIdentifiers>\n  <relatedIdentifier relationType=\"IsReferencedBy\"\n                      relatedIdentifierType=\"URL\">\n    https://doi.org/10.00000/ABC12XY3\n     </relatedIdentifier>\n</relatedIdentifiers>",
      "language": "xml"
    }
  ]
}
[/block]
RDA metadata standard:
Note: that this is an extension to the RDA metadata standard. There is conversation about supporting this in the future. We are handling this way until it is officially supported.
[block:code]
{
  "codes": [
    {
      "code": "\"dmproadmap_related_identifiers\":[\n  { \n    \"type\": \"doi\", \n    \"descriptor\": \"is_referenced_by\", \n    \"identifier\": \"https://doi.org/10.00000/ABC12XY3\" \n  }\n]\n",
      "language": "xml"
    }
  ]
}
[/block]
## Full RDA JSON maDAMP example
[block:code]
{
  "codes": [
    {
      "code": "{\n \"dmp\": {\n   \"title\": \"Lorem ipsum\",\n   \"description\": \"Lorem ipsum est ...\",\n   \"created\": \"2021-03-09T20:49:42Z\",\n   \"language\": \"eng\",\n   \"dmp_id\": { \"type\":\"doi\", \"identifier\": \"https://doi.org/10.0000/ABCD1234\" },\n   \"contact\":{\n     \"name\": \"Smith, John\",\n     \"affiliation\": {\n       \"name\": \"Generic University\",\n       \"affiliation_id\": { \"type\": \"ror\", \"identifier\": \"https://ror.org/xxxxx\" }\n     },\n     \"contact_id\": { \"type\": \"orcid\", \"identifier\": \"https://orcid.org/0000-0000-0000-000X\" }\n   },\n   \"contributor\": [\n     {\n       \"name\": \"Doe PhD, Jane\",\n       \"role\": [\"http://credit.niso.org/contributor-roles/investigation\"],\n       \"affiliation\": {\n         \"name\": \"Example University\",\n         \"affiliation_id\": { \"type\": \"ror\", \"identifier\": \"https://ror.org/yyyyy\" }\n       },\n       \"contributor_id\": { \"type\": \"orcid\", \"identifier\": \"https://orcid.org/0000-0000-0000-000Y\" }\n     }\n   ],\n   \"project\": [\n     {\n       \"funding\": [{\n         \"name\": \"National Generic Funder\",\n         \"funder_id\": { \"type\": \"fundref\", \"identifier\": \"https://doi.org/10.13039/000000000\" },\n         \"grant_id\": { \"type\": \"url\", \"identifier\": \"http://awards.example.org/123\" },\n       }]\n     }\n   ],\n   \"dmproadmap_related_identifiers\":[\n     { \"type\": \"doi\", \"descriptor\": \"is_referenced_by\", \"identifier\": \"10.00000/ZZ99X0\" }\n   ]\n }\n}",
      "language": "json"
    }
  ]
}
[/block]