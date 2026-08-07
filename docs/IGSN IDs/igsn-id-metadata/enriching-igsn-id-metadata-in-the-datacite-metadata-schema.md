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

If additional information about your samples becomes available, you should update your IGSN ID metadata or URLs no matter their [DOI state](https://support.datacite.org/docs/doi-states). The [REST API](https://support.datacite.org/docs/updating-metadata-with-the-rest-api), [MDS API](https://support.datacite.org/docs/mds-api-guide), and [Fabrica](https://support.datacite.org/docs/fabrica-update-doi) can be used to modify IGSN ID metadata and URLs. 

## Placeholder and sensitive metadata

IGSN IDs may be registered for physical samples that do not yet have public metadata; for example, samples that have not yet been cataloged or samples that have embargoed information. 

The DataCite Metadata Schema provides a set of standard values that may be used when mandatory property values are not available for various reasons. Please see Appendix 3 and Table 11 of the DataCite Metadata Schema 4.4 documentation for more information about these values. Example standard values for unknown information include “:unac” for “temporarily inaccessible” and “:unav” for “value unavailable, possibly unknown.”

IGSN IDs in the Registered state will not appear in DataCite discovery systems. However, IGSN ID metadata in any state, including Draft and Registered state, will be visible to other authenticated DataCite Members using the Member API. Thus, IGSN ID metadata should not contain private or sensitive information. See [DOI States](doc:doi-states). 

## Building relationships between IGSN IDs and other resources that use PIDs

IGSN ID relationship metadata unambiguously links samples with related datasets, publications, researchers, institutions, and external metadata, as well as parent samples (including features-of-interest) and derived children.

Relationships among IGSN IDs and with other resources that use PIDs can be encoded in the DataCite Metadata Schema and represented in the [PID Graph](https://support.datacite.org/docs/datacite-graphql-api-guide#the-pid-graph). A subset of these relationships are represented in DataCite APIs, as well as in [DataCite Commons](https://commons.datacite.org/). 

The `relatedIdentifier` property in the [DataCite Metadata Schema](https://schema.datacite.org/) can be used to build relationships among IGSN IDs and with other resources that use PIDs. Relationships entered using the `relatedIdentifier` property create [Event Data](https://support.datacite.org/docs/eventdata-guide) and a selection of Event Data relation types—including citation, reference, part, and version relationships—are represented in DataCite APIs and Commons. See [Connecting to Works](doc:connecting-to-works) for more information.

> 👍 
> 
> Relationships to other IGSN IDs registered with DataCite services should use `relatedIdentifierType` `DOI`. 

## Linking to custom metadata

Your institution may maintain metadata about your samples in schemata specific to your institution, discipline, or samples community. We recommend that you link to this external metadata using the `relatedIdentifier` property with a “HasMetadata” `relationType` attribute. If you are pointing to a web-hosted metadata file, the `relatedIdentifierType` “URL” will likely be appropriate. The `relatedMetadataScheme` attribute can be used to specify the name of the metadata scheme. See the [DataCite Metadata Schema](https://schema.datacite.org/).

```
```