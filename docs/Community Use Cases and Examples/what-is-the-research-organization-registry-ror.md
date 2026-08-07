---
title: Research Organization Registry (ROR)
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
The [Research Organization Registry (ROR)](https://ror.org/) is a global, community-led registry of open persistent identifiers for research and funding organizations. ROR makes it easy for anyone or any system to disambiguate institution names and connect research organizations to researchers and research outputs. The Research Organization Registry (ROR) includes IDs and metadata for more than 120,000 organizations and counting. Registry data is CC0 and openly available via a search interface, REST API, and data dump. Registry updates are curated through a community process and released approximately  once a month. There is no cost to use ROR data or add an organization to the registry. 

If your organization does not already have a ROR ID, you can [submit a request to suggest a new record](https://docs.google.com/forms/d/e/1FAIpQLSdJYaMTCwS7muuTa-B_CnAtCSkKzt19lkirAKG4u7umH9Nosg/viewform).

## How do DataCite and ROR work together?

ROR is operated as a collaborative initiative by [California Digital Library](https://cdlib.org/), [Crossref](https://www.crossref.org/), and [DataCite](https://datacite.org/). The three ROR governing organizations collectively assume and share responsibility for ROR governance, operations, resourcing, and decision-making. Read more about [ROR Governance](https://ror.org/about/#governance).

### DataCite Metadata Schema

ROR IDs can be included in DataCite DOI metadata in the following sub-properties:

- Publisher: [4.a publisherIdentifier](https://datacite-metadata-schema.readthedocs.io/en/4/properties/publisher/#a-publisheridentifier)
- Creator: [2.5.a affiliationIdentifier](https://datacite-metadata-schema.readthedocs.io/en/4/properties/creator/#a-affiliationidentifier) and [2.4 nameIdentifier](https://datacite-metadata-schema.readthedocs.io/en/4/properties/creator/#nameidentifier) (for organizational creators)
- Contributor: [7.5.a affiliationIdentifier](https://datacite-metadata-schema.readthedocs.io/en/4/properties/contributor/#a-affiliationidentifier) and [7.4 nameIdentifier](https://datacite-metadata-schema.readthedocs.io/en/4/properties/contributor/#nameidentifier) (for organizational contributors)
- FundingReference: [19.2 funderIdentifier](https://datacite-metadata-schema.readthedocs.io/en/4/properties/fundingreference/#funderidentifier)

Example of a ROR ID in the affiliationIdentifier of the Creator:

```xml
<creators>
    <creator>
        <creatorName nameType="Organizational">DataCite</creatorName>
        <affiliation affiliationIdentifier="https://ror.org/04wxnsj81" affiliationIdentifierScheme="ROR" schemeURI="https://ror.org">DataCite</affiliation>
    </creator>
</creators>
```

### DataCite Fabrica

#### Fabrica Form:

When you register a DOI in DataCite Fabrica using the [form](doc:fabrica-doi-form), both the Publisher and Affiliation properties include a look-up function which auto-populates the ROR ID:

#### Fabrica Organization Profile:

DataCite Members, Consortium Leads and Consortium Organizations should include their ROR ID in the account profile in DataCite Fabrica. This will ensure that all DOIs registered by this account will be automatically connected to corresponding organization profile (from ROR)  in DataCite Commons.  To do this, use the lookup in the **Organization Identifier** field in the [settings](doc:fabrica-settings) in Fabrica:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/75fb7ca4d0294f7396ec8853172b2fb2d5289ca0f76889b7a5d47fad3e8ab8d2-Screenshot_2026-07-27_at_11.48.26.png",
        "",
        "Organization Identifier field in Fabrica organization profile"
      ],
      "align": "center"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a3c608527a6e08efd5789a0680a22814fe869153d6fe44e97e4ab9538d9815c-Screenshot_2026-07-27_at_11.49.27.png",
        "",
        "ROR ID in orgnization identifier field"
      ],
      "align": "center"
    }
  ]
}
[/block]


### DataCite Commons

The [Organizations tab in DataCite Commons](https://commons.datacite.org/ror.org) connects to ROR’s API to import organization records from the registry. Research organization profiles in DataCite Commons are connected to the works (DOIs) registered by the organization when:

- The ROR ID is included in the DataCite metadata - best practice for creating complete metadata, improving visibility and connecting research to the affiliated organizations, publishers and funders.
- The ROR ID is included in the Fabrica profile - this automates the connection between DOIs registered by a DataCite Member in DataCite and the organizational profile from ROR in DataCite Commons, but is secondary to creating rich and complete metadata.

Find out more about connection metadata and [Connecting to Organizations](https://support.datacite.org/docs/connecting-to-organizations).