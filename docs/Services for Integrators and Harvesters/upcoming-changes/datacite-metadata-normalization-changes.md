---
title: DataCite Metadata Normalization Changes
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
## What changed

Previously, when metadata was submitted to DataCite to register or update a DOI, DataCite applied isolated changes (or "normalizations") to some submitted metadata fields, particularly when converting submitted XML metadata to JSON for appearance in REST API responses. These behaviors caused confusion for some users and are no longer aligned with our approach to metadata submission.

The normalizations outlined below are now phased out. These changes took effect in **Q2 2026**.

## What do I need to do?

You don’t need to change anything about how you are submitting metadata, and all valid API calls to the MDS API and REST API will remain valid. The appearance of certain metadata may change slightly in REST API responses for new and updated DOIs according to the changes described below.

## What normalizations are phased out?

The following normalizations are now removed:

[block:parameters]
{
  "data": {
    "h-0": "Affected submission methods",
    "h-1": "Deprecated behavior",
    "0-0": "MDS API/XML",
    "0-1": "If there is not already a Date with dateType \"Issued\", one is inserted into the REST API response using the submitted PublicationYear value. XML metadata is not modified.",
    "1-0": "MDS API/XML",
    "1-1": "Creator and Contributor name, givenName, and familyName metadata is interpreted to normalize the name value and populate the nameType value in the REST API response. XML metadata is not modified.",
    "2-0": "MDS API/XML  \nREST API",
    "2-1": "When a subject can be matched to a term from the [OECD’s Fields of Science (FOS) vocabulary](https://web-archive.oecd.org/2012-06-15/138575-38235147.pdf), a subject with the FOS term is inserted into the REST API response. XML metadata is not modified."
  },
  "cols": 2,
  "rows": 3,
  "align": [
    "left",
    "left"
  ]
}
[/block]


## Are there other normalizations still in place?

Yes. The following normalizations will remain in place pending ongoing assessment:

[block:parameters]
{
  "data": {
    "h-0": "Affected submission methods",
    "h-1": "Normalization behavior",
    "0-0": "MDS API/XML  \nREST API",
    "0-1": "Three-letter language codes (ISO 639-3) are updated to two-letter codes (ISO 639-1) when an exact match is available. Country codes are also removed. For more information, see: [Why do the language codes in the metadata change?](doc:why-do-the-language-codes-in-the-metadata-change)",
    "1-0": "MDS API/XML  \nREST API",
    "1-1": "If the Rights name, rightsURI, or rightsIdentifier matches a license in SPDX, we add the corresponding rightsUri, rightsIdentifier, rightsIdentifierScheme, and schemeUri values",
    "2-0": "MDS API/XML  \nREST API",
    "2-1": "If an AlternateIdentifier has alternateIdentifierType \"DOI\", the AlternateIdentifier will be removed. Identical resources that are both identified by DOIs can be linked using [a RelatedIdentifier with relationType \"IsIdenticalTo\"](https://datacite-metadata-schema.readthedocs.io/en/4.6/appendices/appendix-1/relationType/#isidenticalto). (Note: In the REST API, [the `alternateIdentifiers` attribute is the same as the `identifiers` attribute](doc:what-is-the-identifiers-attribute-in-the-rest-api) .) "
  },
  "cols": 2,
  "rows": 3,
  "align": [
    "left",
    "left"
  ]
}
[/block]


> 👍 
> 
> We’d love your feedback on either maintaining or removing these normalizations. Contact [support@datacite.org](mailto:support@datacite.org) and let us know what you think!