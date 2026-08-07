---
title: DataCite Properties (default)
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
  "title": "Table 3: Expanded DataCite Mandatory Properties"
}
[/block]

[block:parameters]
{
  "data": {
    "h-0": "ID",
    "h-1": "DataCite Property",
    "h-2": "Occ",
    "h-3": "Definition",
    "h-4": "Allowed values, examples, other constraints",
    "1-0": "1.1",
    "1-1": "identifierType",
    "1-2": "1",
    "1-3": "The type of identifier.",
    "1-4": "*Controlled List Value:*\nDOI",
    "0-0": "1",
    "0-1": "Identifier",
    "0-2": "1",
    "0-3": "The Identifier is a unique\nstring that identifies a resource. For software, determine whether the identifier is for a specific version of a piece of software, (per the Force11 Software Citation Principles<sup>13</sup>), or for all versions.",
    "0-4": "DOI (Digital Object Identifier)\nregistered by a DataCite member. Format should be “10.1234/foo”",
    "2-0": "2",
    "2-1": "Creator",
    "2-2": "1-n",
    "2-3": "The main researchers involved in producing the data, or the authors of the publication, in priority order. To supply multiple creators, repeat this property.",
    "2-4": "May be a corporate/institutional or personal name. Note: DataCite infrastructure supports up to 8000-10000 names. For name lists above that size, consider attribution via linking to the related metadata.",
    "3-0": "2.1",
    "3-1": "creatorName",
    "3-2": "1",
    "3-3": "The full name of the creator.",
    "3-4": "Examples: Charpy, Antoine; Foo\nData Center\nNote: The personal name, format should be: family, given. Non- roman names may be transliterated according to the ALA-LC schemas<sup>14</sup>.",
    "4-0": "2.1.1",
    "4-1": "nameType",
    "4-2": "0-1",
    "4-3": "The type of name.",
    "4-4": "Controlled List Values:\nOrganizational \nPersonal",
    "5-0": "2.2",
    "5-1": "givenName",
    "5-2": "0-1",
    "5-3": "The personal or first name of the creator.",
    "5-4": "Examples based on the 2.1 names: Antoine; Mae",
    "6-0": "2.3",
    "6-1": "familyName",
    "6-2": "0-1",
    "6-3": "The surname or last name of the creator.",
    "6-4": "Examples based on the 2.1 names:\nCharpy; Jemison",
    "7-0": "2.4",
    "7-1": "nameIdentifier",
    "7-2": "0-n",
    "7-3": "Uniquely identifies an individual or legal entity, according to various schemas.",
    "7-4": "The format is dependent upon schema.",
    "8-0": "2.4.1",
    "8-1": "nameIdentifierScheme",
    "8-2": "1",
    "8-3": "The name of the name identifier schema.",
    "8-4": "If nameIdentifier is used, nameIdentifierScheme is mandatory.\nExamples: ORCID<sup>15</sup>, ISNI<sup>16</sup>",
    "9-0": "2.4.2",
    "9-1": "schemeUI",
    "9-2": "0-1",
    "9-3": "The URL of the name identifier schema.",
    "9-4": "Examples: \nhttp://www.isni.org http://orcid.org",
    "10-0": "2.5",
    "10-1": "affiliation",
    "10-2": "0-n",
    "10-3": "The organizational or institutional affiliation of the creator.",
    "10-4": "Free text.",
    "11-0": "3",
    "11-1": "Title",
    "11-2": "1-n",
    "11-3": "A name or title by which a resource is known. May be the title of a dataset or the name of a piece of software.",
    "11-4": "Free text.",
    "12-0": "3.1",
    "12-1": "titleType",
    "12-2": "0-1",
    "12-3": "The type of Title.",
    "12-4": "*Controlled List Values:*\nAlternativeTitle Subtitle TranslatedTitle\nOther"
  },
  "cols": 5,
  "rows": 13
}
[/block]

[block:api-header]
{
  "title": "Footnotes"
}
[/block]
13. Smith AM, Katz DS, Niemeyer KE, FORCE11 Software Citation Working Group. (2016) Software citation principles. PeerJ Computer Science 2:e86 https://doi.org/10.7717/peerj-cs.86
14. http://www.loc.gov/catdir/cpso/roman.html
15. http://orcid.org/. When entering an ORCID, follow these style guidelines: http://support.orcid.org/knowledgebase/articles/116780-structure-of-the-orcid-identifier
16. http://www.isni.org/