---
title: >-
  What is the recommended format for including nameIdentifiers in the DataCite
  metadata?
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
The DataCite metadata schema defines a nameIdentifier as: “uniquely identifying an individual or legal entity, according to various schemes.” ORCID, ISNI, and ROR IDs are all types of nameIdentifiers. They provide information to distinguish who the “creator” or “contributor” is. Including a nameIdentifier in the DOI metadata can also connect the DOI directly to the creator/contributor of the resource.

Although other formats are technically permitted, we recommend including the full URL link of the nameIdentifier as seen below in XML:
[block:code]
{
  "codes": [
    {
      "code": "<nameIdentifier nameIdentifierScheme=\"ORCID\" schemeURI=\"https://orcid.org\">https://orcid.org/0000-0001-5727-2427</nameIdentifier>",
      "language": "xml"
    }
  ]
}
[/block]
And in JSON the nameIdentifier information is formatted like this:
[block:code]
{
  "codes": [
    {
      "code": "     \"nameIdentifiers\": [\n        {\n          \"schemeUri\": \"https://orcid.org\",\n          \"nameIdentifier\": \"https://orcid.org/0000-0001-5727-2427\",\n          \"nameIdentifierScheme\": \"ORCID\"\n        }\n",
      "language": "json"
    }
  ]
}
[/block]
You can include nameIdentifiers when you [register a DOI with the Fabrica Form](doi:create-a-doi-via-form).

Learn more about other types of identifiers that can be included in the metadata in the [DataCite metadata schema](http://schema.datacite.org/).