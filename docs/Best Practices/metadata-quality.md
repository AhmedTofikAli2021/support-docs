---
title: Metadata Quality
excerpt: Best Practices
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
[block:api-header]
{
  "type": "basic",
  "title": "Metadata Properties"
}
[/block]
The DataCite Metadata Schema is a list of core metadata properties chosen for an accurate and consistent identification of a resource for citation and retrieval purposes, along with recommended use instructions.The Metadata Schema has three different levels of obligation for its metadata properties:

* Mandatory: these properties must be provided, otherwise the DataCite DOI will not be minted or updated
* Recommended: these properties are optional, but strongly recommended for interoperability
* Optional: these properties are optional but provide a richer description of the object

To enhance the prospects of an object with a DataCite DOI to be found, cited and linked to original research, DataCite strongly encourages to submit as much metadata as the service is aware of and has permission to share.
[block:api-header]
{
  "type": "basic",
  "title": "Mandatory Properties"
}
[/block]
Mandatory and Recommended properties and sub‐properties are especially valuable to information seekers and added‐service providers, such as indexers. The DataCite Metadata Working Group members strongly urge the inclusion of metadata identified as Recommended for the purpose of achieving greater exposure for the resource’s metadata record, and therefore, the underlying research itself. 

| Mandatory Properties | Details |
| :-------------: |
| Identifier | with mandatory type sub‐property |
| Creator | with optional name identifier and affiliation sub-properties |
| Title | with optional type sub‐properties |
| Publisher | |
| PublicationYear | |
| ResourceType | with mandatory general type description sub-property |
[block:api-header]
{
  "type": "basic",
  "title": "Recommended Properties"
}
[/block]
| Recommended Properties | Details |
| :-------------: |
| Subject | with scheme sub‐property |
| Contributor | with type, name identifier, and affiliation sub‐properties |
| Date | with type sub‐property |
| RelatedIdentifier | with type and relation type sub‐properties |
| Description | with type sub‐property |
| GeoLocation | with point, box, and polygon sub‐properties |
[block:api-header]
{
  "type": "basic",
  "title": "Optional Properties"
}
[/block]
| Optional Properties | Details |
| :-------------: |
| Language | |
| AlternateIdentifier | with type sub‐property |
| Size | |
| Format | |
| Version | |
| Rights | |
| FundingReference | with name, identifier, and award related sub‐properties |