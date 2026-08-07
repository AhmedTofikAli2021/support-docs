---
title: Enriching IGSN ID metadata in the DataCite Metadata Schema
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
As with other research outputs, metadata plays a critical role in describing and connecting IGSN IDs to maximize discoverability and reuse. DataCite encourages the following metadata best practices for enriching IGSN ID metadata in the [DataCite Metadata Schema](https://schema.datacite.org/). 

## Populating DataCite Metadata Schema properties

In addition to the properties listed in the [IGSN ID Metadata Recommendations](doc:igsn-id-metadata-recommendations), we recommend that you populate as many of the [DataCite Metadata Schema](https://schema.datacite.org/) properties as possible using your local samples metadata and database fields. This will help to improve the discoverability of your IGSN IDs. 

## Updating IGSN ID metadata over time

IGSN ID metadata can be collected and enriched throughout every stage of the samples workflow, from planning and collection through to repository ingest and publication. Principal Investigators, analysts, curators, and repository managers are encouraged to enrich sample metadata throughout the workflow processes and over time, using metadata from field-based tools, analytical systems, and local samples databases.

If additional information about your samples becomes available, you should update your IGSN ID metadata or URLs no matter their [DOI state](doc:doi-states). The [REST API](doc:updating-metadata-with-the-rest-api), [MDS API](doc:mds-api-guide), and [Fabrica](doc:fabrica-update-doi) can be used to modify IGSN ID metadata and URLs. 

## Placeholder and sensitive metadata

IGSN IDs may be registered for physical samples that do not yet have public metadata; for example, samples that have not yet been cataloged or samples that have embargoed information. 

The DataCite Metadata Schema provides a set of standard values that may be used when mandatory property values are not available for various reasons. Please see Appendix 3 and Table 11 of the DataCite Metadata Schema 4.4 documentation for more information about these values. Example standard values for unknown information include “:unac” for “temporarily inaccessible” and “:unav” for “value unavailable, possibly unknown.”

IGSN IDs in the Registered state will not appear in DataCite discovery systems. However, IGSN ID metadata in any state, including Draft and Registered state, will be visible to other authenticated DataCite Members using the Member API. Thus, IGSN ID metadata should not contain private or sensitive information. See [DOI States](doc:doi-states). 

## Building relationships between IGSN IDs and other resources that use PIDs

IGSN ID relationship metadata unambiguously links samples with related datasets, publications, researchers, institutions, and external metadata, as well as parent samples (including features-of-interest) and derived children.

Relationships among IGSN IDs and with other resources that use PIDs can be encoded in the DataCite Metadata Schema and represented in the [PID Graph](doc:datacite-graphql-api-guide#the-pid-graph). A subset of these relationships are represented in DataCite APIs, as well as in [DataCite Commons](doc:datacite-commons). 

The `relatedIdentifier` property in the DataCite Metadata Schema can be used to build relationships among IGSN IDs and with other resources that use PIDs. Relationships entered using the `relatedIdentifier` property create [Event Data](doc:eventdata-guide) and a selection of Event Data relation types—including citation, reference, part, and version relationships—are represented in DataCite APIs and Commons. See [Connecting to Works](doc:connecting-to-works) for more information.

> 👍 
> 
> Relationships to other IGSN IDs registered with DataCite services should use `relatedIdentifierType` `DOI`.

## Linking to custom metadata

Your institution may maintain metadata about your samples in schemata specific to your institution, discipline, or samples community. We recommend that you link to this external metadata using the `relatedIdentifier` property with a “HasMetadata” `relationType` attribute. If you are pointing to a web-hosted metadata file, the `relatedIdentifierType` “URL” will likely be appropriate. The `relatedMetadataScheme` attribute can be used to specify the name of the metadata scheme. 

## Operationalizing the CARE Principles: Local Contexts Notices and Labels

It is important that material sample management aligns with the [CARE (Collective benefit, Authority to control, Responsibility, Ethics) Principles for Indigenous Data Governance](https://www.gida-global.org/care). The CARE Principles may be operationalized by applying Local Contexts’ Traditional Knowledge or Biocultural [Notices](https://localcontexts.org/notice) and [Labels](https://localcontexts.org/labels) via the [Local Contexts Hub](https://localcontexts.org/tk-label-hub/). If a sample has been assigned with a Notice or Label, this can be included in its IGSN ID metadata using the `Rights` property of the DataCite Metadata Schema. See [Using the Rights property for Notices and Labels](doc:local-contexts-notices-and-labels#using-the-rights-property-for-notices-and-labels) for more information.

Notes:

1. In most cases, when a Local Contexts community applies a Label, any Notices are removed. It is therefore recommended that a sample’s IGSN ID metadata in DataCite be updated when new Notices or Labels are applied or existing ones modified. This can be checked through the Local Contexts API.
2. When connecting an IGSN ID to a [RAiD](https://raid.org/) via `relatedIdentifier` metadata, the [RAiD vocabulary](https://vocabs.ardc.edu.au/viewById/682) associated with RAiD metadata properties contains controlled lists for Notices and Labels. In this case, Notices and Labels should be included in the RAiD metadata rather than the IGSN ID metadata; otherwise, they should be included in the IGSN ID metadata of the uppermost parent sample.

To learn more about repository guidance for implementing the CARE Principles, please see the following papers:

- [O’Brien et al. 2020. Earth Science Data Repositories: Implementing the CARE Principles. Data Science Journal, 19(43)](https://doi.org/10.5334/dsj-2024-037)
- [Carroll et al. 2021. Operationalizing the CARE and FAIR Principles for Indigenous Data Futures. Scientific Data, 8(1)](https://doi.org/10.1038/s41597-021-00892-0)

See also [this blog post](https://doi.org/10.5438/dpxc-bm32), which discusses the grounding of Indigenous Rights in DataCite metadata.