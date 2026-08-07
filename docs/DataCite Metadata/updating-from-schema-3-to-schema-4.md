---
title: Updating from Schema 3 to Schema 4
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
DataCite is preparing to remove support for Version 3 of the DataCite Metadata Schema—also known as “Schema 3”. Schema 3 was first released in 2013 ([version 3.0](https://schema.datacite.org/meta/kernel-3.0/)), and last updated in 2014 ([version 3.1](https://schema.datacite.org/meta/kernel-3.1/)).

As of **January 1, 2025**, DataCite Members and Consortium Organizations will be required to use [Schema 4](https://schema.datacite.org/meta/kernel-4/)—i.e., versions 4.0 through 4.5 and any subsequent minor versions—to register DOIs and update DOI metadata.

This guide addresses what will happen to existing DOIs registered using Schema 3 and how DataCite users can prepare for this change.

***

## What will change when DataCite removes support for Schema 3

### What happens to existing DOIs with Schema 3 metadata?

- **Existing DOIs with Schema 3 metadata will continue to resolve.** When a major version of the DataCite Metadata Schema is deprecated, there is no change to DOI resolution.
- **Existing DOIs with Schema 3 metadata will remain part of the DataCite Metadata Store.** There will be no change to retrieving and searching DOIs with Schema 3 metadata in the DataCite’s APIs and services. This includes the DataCite REST API, DataCite GraphQL API, DataCite OAI-PMH service, and DataCite Commons.

### My repository is using Schema 3 for DOI registration. Can we continue to register new DOIs?

Once Schema 3 is deprecated, repositories must send DataCite metadata that is valid under Schema 4 to register new DOIs. 

- **MDS API users:** The MDS API will only accept DataCite XML that is valid under Schema 4.
- **REST API users:** A small number of REST API users submit DataCite XML through the `xml` attribute, which accepts base64-encoded DataCite XML. Similar to the MDS API, this will only accept Schema 4 metadata once Schema 3 is deprecated. The majority of REST API users submit DataCite JSON, which is already in Schema 4.
- **Fabrica users:** The Fabrica File Upload will only accept Schema 4 metadata once Schema 3 is deprecated.

### My repository has previously registered DOIs using Schema 3. After Schema 3 is retired, can we still update these DOIs?

Once Schema 3 is deprecated, existing DOIs with Schema 3 metadata may only be updated using Schema 4. If an update is sent to DataCite with Schema 3 metadata, it will not be accepted.

***

## What repositories using Schema 3 need to change to switch to Schema 4

As of January 1, 2025, repositories will need to create new DOIs using Schema 4 and submit metadata updates using Schema 4.

### What are the critical differences between Schema 3 and Schema 4?

Schema 4 introduced two breaking changes:

- The  `resourceType` property was changed from optional to mandatory. This property has `resourceTypeGeneral` as a mandatory attribute.
- The `contributorType` "Funder" was deprecated. This concept was replaced with the `FundingReference` property.

### What else has changed between Schema 3 and Schema 4?

Between Schema 3 and Schema 4, several new properties, sub-properties, and controlled list values have been added to the DataCite Metadata Schema. As of minor version 4.5, the following changes are available in Schema 4:

**New metadata properties and sub-properties:**

- Property: `FundingReference`
- Property: `RelatedItem`
- Sub-properties for:

  - Creator and Contributor:
    - `givenName` and `familyName`
    - `nameType`
    - affiliation sub-properties:
      - `affiliationIdentifier`
      - `affiliationIdentifierScheme`
      - `schemeURI`
  - Publisher:
    - `publisherIdentifier`
    - `publisherIdentifierScheme`
    - `schemeURI`
  - Subject:
    - `valueUri`
    - `classificationCode`
  - Date:
    - `dateInformation`
  - RelatedIdentifier:
    - `resourceTypeGeneral`
  - Rights:
    - `rightsIdentifier`
    - `rightsIdentifierScheme`
    - `schemeURI`
  - GeoLocation:
    - `geoLocationPolygon`

  **New controlled list values:**

  - dateType
    - Other
    - Withdrawn
  - descriptionType
    - TechnicalInfo
    - relatedIdentifierType
    - IGSN
    - w3id
  - relationType
    - HasVersion / IsVersionOf
    - IsRequiredBy / Requires
    - IsDescribedBy / Describes
    - IsObsoletedBy / Obsoletes
    - IsPublishedIn
    - IsCollectedBy / Collects
  - resourceTypeGeneral
    - Book
    - BookChapter
    - ComputationalNotebook
    - ConferencePaper
    - ConferenceProceeding
    - DataPaper
    - Dissertation
    - Instrument
    - Journal
    - JournalArticle
    - OutputManagementPlan
    - PeerReview
    - Preprint
    - Report
    - Standard
    - StudyRegistration
  - titleType
    - Other

### Where can I find examples of Schema 4 metadata?

Examples are available at <https://schema.datacite.org/meta/kernel-4/>. 

### How can I identify DOIs from my repository that use Schema 3?

To identify Schema 3 DOIs in your repository, you can use the REST API and filter DOI results by `client-id` and `schema-version` using the request below. Replace the `client-id` "abcd.efgh" with your Repository account ID:

`https://api.datacite.org/dois?client-id=abcd.efgh&schema-version=3`

You can also filter by a Direct Member or Consortium Organization (`provider-id` parameter) or by a Consortium ( `consortium-id`) parameter. See [Queries and filtering: Filtering List Responses](doc:api-queries#filtering-list-responses) for additional filter paramters.

### How can I identify Schema 3 DOIs from my repository that are missing resourceTypeGeneral or use the contributorType "Funder"?

To retrieve Schema 3 DOIs from your repository that are missing resourceTypeGeneral, use the request below (changing the `client-id`):

 `https://api.datacite.org/dois?client-id=abcd.efgh&schema-version=3&query=NOT resourceTypeGeneral:*`

To retrieve Schema 3 DOIs from your repository that use the contributorType "Funder", use the request below (changing the `client-id`):

 `https://api.datacite.org/dois?client-id=abcd.efgh&schema-version=3&query=contributors.contributorType:Funder`

***

## How to submit Schema 4 metadata

### What needs to change in the XML metadata to transition DOIs from Schema 3 to Schema 4?

#### Specify Kernel 4

1. The XML record should indicate kernel-4 in the `resource` element:

```xml
<resource xmlns="http://datacite.org/schema/kernel-4" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://datacite.org/schema/kernel-4 http://schema.datacite.org/meta/kernel-4/metadata.xsd">
```

kernel-4 will always represent the latest minor version of Schema 4. Note that it is also possible to specify a minor version, e.g., kernel-4.4. However, because all minor versions are backward compatible, we recommend specifying kernel-4 to stay up-to-date with the latest changes.

> 👍 
> 
> When submitting XML metadata, we recommend specifying the major version (kernel-4). This enables you to always take advantage of the latest minor version changes. All minor versions are backward compatible.

#### Include resourceType / resourceTypeGeneral

The record must include—or be updated to include—the `resourceType` property with the `resourceTypeGeneral` attribute. For example:

```xml
<resourceType resourceTypeGeneral="Dataset">Census Data</resourceType>
```

It is possible to include `resourceTypeGeneral` only without specifying a free text `resourceType`. For example:

```xml
<resourceType resourceTypeGeneral="JournalArticle"/>
```

#### Move Contributors with contributorType "Funder" to FundingReference

The record must not use the `contributorType` "Funder". This information can be moved to the `FundingReference` property, which was introduced in Schema 4.0. This property has sub-properties for the `funderName`, `funderIdentifier`, `awardNumber`, and `awardTitle`.

```xml
<fundingReferences>
  <fundingReference>
    <funderName>European Commission</funderName>
    <funderIdentifier funderIdentifierType="Crossref Funder ID">https://doi.org/10.13039/501100000780</funderIdentifier>
    <awardNumber awardURI="https://cordis.europa.eu/project/rcn/100603_en.html">284382</awardNumber>
    <awardTitle>Institutionalizing global genetic-resource commons. Global Strategies for accessing and using essential public knowledge assets in the life sciences</awardTitle>
  </fundingReference>
<fundingReferences>
```

### How do I check if my XML metadata is valid under Schema 4?

Schema 4 XML metadata is validated with the kernel-4 XSD file: <https://schema.datacite.org/meta/kernel-4/metadata.xsd>. This always refers to the latest minor version of Schema 4.

### Can I update Schema 3 DOIs to Schema 4 using JSON with the DataCite REST API?

When updating a Schema 3 DOI to Schema 4, you can [make a PUT request to update the DOI](https://support.datacite.org/reference/put_dois-id) with the REST API. This request should include the following attributes.

#### Include schemaVersion to trigger the update to Schema 4

Include the `schemaVersion` attribute, set to "<http://datacite.org/schema/kernel-4">. While this is not required for new DOI registrations or to update DOIs that already use Schema 4, this is necessary to trigger the update from Schema 3 to Schema 4.

#### Add a resourceTypeGeneral if not already present

If not already present in the record, include the required metadata property `resourceTypeGeneral` (part of `types` in JSON).

```json
{  
  "data": {  
    "id": "10.21384/1f84-ta02",  
    "type": "dois",  
    "attributes": {  
      "doi": "10.21384/1f84-ta02",  
      "types": {  
        "resourceTypeGeneral": "JournalArticle"  
      },  
      "schemaVersion": "http://datacite.org/schema/kernel-4"  
    }  
  }  
}
```

#### Move Contributors with contributorType "Funder" to fundingReferences

If any existing Contributors use `contributorType` “Funder”, they should be migrated to `fundingReferences`. To avoid data loss, provide both the `contributors` property (with all non-Funder contributors) and the `fundingReferences` property.

```json
{  
  "data": {  
    "id": "10.21384/1f84-ta02",  
    "type": "dois",  
    "attributes": {  
      "doi": "10.21384/1f84-ta02",  
      "types": {  
        "resourceTypeGeneral": "JournalArticle"  
      },  
      "contributors": [  
        {  
          "name": "Garcia, Sofia",  
          "contributorType": "ProjectLeader",  
        }  
      ],
      "fundingReferences": [  
        {  
          "funderName": "National Science Foundation",  
          "funderIdentifier": "https://ror.org/021nxhr62",  
          "funderIdentifierType": "ROR"  
        }  
      ],
      "schemaVersion": "http://datacite.org/schema/kernel-4"
    } 
}
```

### Can I update Schema 3 DOIs to Schema 4 using the Fabrica form?

Updating a Schema 3 DOI using the [Fabrica form](doc:create-a-doi-via-form) will update the DOI to Schema 4. A warning will appear at the top of the page for Schema 3 DOIs:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9c3ba63-Screen_Shot_2023-12-08_at_08.57.44.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


If the metadata is not compatible with Schema 4, an error message will appear at the bottom of the page: 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8714d5b-Screen_Shot_2023-12-08_at_08.57.39.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


To save the DOI using Schema 4, add  `resourceTypeGeneral` and remove any Contributors with `contributorType` "Funder".

***

## How DataCite will support users through this transition period

To ensure all DataCite users have enough time to prepare for this change, this information will be shared with all DataCite Members, including Direct Members and Consortium Leads.

We will also individually contact Direct Members and Consortium Leads who actively used Schema 3 in 2023 to register or update at least 100 DOIs. Because existing Schema 3 DOIs will continue to resolve and be searchable, our priority is ensuring that active Schema 3 users transition to Schema 4 as soon as possible. 

Regardless of how many DOIs you have registered using Schema 3, we encourage you to reach out to us at [support@datacite.org](mailto:support@datacite.org) for assistance with transitioning to Schema 4. Consortium Organizations should contact their Consortium Leads for assistance.