---
title: DataCite Properties custom page
fullscreen: false
hidden: true
metadata:
  title: ''
  description: ''
---
[block:parameters]
{
  "data": {
    "h-0": "ID",
    "h-1": "DataCite-Property",
    "h-2": "Occ",
    "h-3": "Definition",
    "h-4": "Allowed values, examples, other contraints",
    "0-0": "1",
    "0-1": "Identifier",
    "0-2": "1",
    "0-3": "The Identifier is a unique\nstring that identifies a resource. For software, determine whether the identifier is for a specific version of a piece of software, (per the Force11 Software Citation Principles13), or for all versions.",
    "0-4": "DOI (Digital Object Identifier) registered by a DataCite member. Format should be “10.1234/foo”",
    "1-0": "1.1",
    "1-1": "identifierType",
    "1-2": "1",
    "1-3": "The type of Identifier.",
    "1-4": "*Controlled List Value:*\nDOI",
    "2-0": "2",
    "2-1": "Creator",
    "2-2": "1-n",
    "2-3": "The main researchers involved in producing the data, or the authors of the publication, in priority order. To supply multiple creators, repeat this property.",
    "2-4": "May be a corporate/institutional or personal name. Note: DataCite infrastructure supports up to 8000-10000 names. For name lists above that size, consider attribution via linking to the related metadata.",
    "3-0": "2.1",
    "3-1": "creatorName",
    "3-2": "1",
    "3-3": "The full name of the creator.",
    "3-4": "Examples: Charpy, Antoine; Foo\nData Center\nNote: The personal name, format should be: family, given. Non- roman names may be transliterated according to the ALA-LC schemas<sup>14</sup>."
  },
  "cols": 5,
  "rows": 4
}
[/block]