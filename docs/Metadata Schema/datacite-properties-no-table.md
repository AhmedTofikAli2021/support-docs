---
title: DataCite Properties (no tables)
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
Table 3 provides a detailed description of the mandatory properties, which must be supplied with any initial metadata submission to DataCite, together with their sub-properties. If one of the required properties is unavailable, please use one of the standard (machine-recognizable) codes listed in Appendix 3, Table 11. In Table 4, the Recommended and Optional properties are described in detail. For an example of how to make a submission in XML format, please see the XML Examples provided on the DataCite Metadata Schema Repository<sup>10</sup> website.

Throughout this document, a naming convention has been used for all properties and sub-properties as follows: properties begin with a capital letter, whereas sub-properties begin with a lower case letter. If the name is a compound of more than one word, subsequent words begin with capital letters.<sup>11</sup>

As with Tables 1 and 2, Tables 3 and 4 use shading to identify the combined Mandatory and Recommended “super set” of properties and sub-properties that enhance the prospect that the resource’s metadata will be found, cited and linked.

The third column, Occurrence (Occ), indicates cardinality/quantity constraints for the properties as follows:
0-n = optional and repeatable
0-1 = optional, but not repeatable 1-n = required and repeatable
1 = required, but not repeatable

NOTE:
XML provides an xml:lang attribute<sup>12</sup> that can be used on the properties Title, Subject, Rights, and Description. This provides a way to describe the language used for the content of the specified properties. The schema provides a Language property to be used to describe the language of the resource.
[block:api-header]
{
  "title": "1     Identifier"
}
[/block]
**Occurence:** 1

**Definition: **
The Identifier is a unique string that identifies a resource. For software, determine whether the identifier is for a specific version of a piece of software, (per the Force11 Software Citation Principles<sup>13</sup>), or for all versions.

**Allowed values, examples, other constraints:** 
DOI (Digital Object Identifier) registered by a DataCite member. Format should be “10.1234/foo”
[block:api-header]
{
  "title": "1.1   identifierType"
}
[/block]
**Occurence:** 1

**Definition:** The type of Identifier. 

**Allowed values, examples, other constraints:** 
*Controlled List Value:*
DOI
[block:api-header]
{
  "title": "2     Creator"
}
[/block]
**Occurence:** 1-n

**Definition:** 
The main researchers involved in producing the data, or the authors of the publication, in priority order. To supply multiple creators, repeat this property.

**Allowed values, examples, other constraints:** 
May be a corporate/institutional or personal name. Note: DataCite infrastructure supports up to 8000-10000 names. For name lists above that size, consider attribution via linking to the related metadata.
[block:api-header]
{
  "title": "2.1   creatorName"
}
[/block]
**Occurence:** 1

**Definition:**
The full name of the creator.

**Allowed values, examples, other constraints:** 
Examples: Charpy, Antoine; Foo Data Center

Note: The personal name, format should be: family, given. Non- roman names may be transliterated according to the ALA-LC schemas<sup>14</sup>.