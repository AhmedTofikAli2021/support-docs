---
title: DataCite Event Data Changes
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
## What’s changing?

We are streamlining the data stored in [DataCite Event Data](doc:eventdata-guide). Event Data records represent relationships between DOIs, ORCID iDs, and ROR IDs, as well as usage statistics, like views and downloads. However, many of these records duplicate metadata that is the DataCite Metadata Store, which can be accessed via our other services—including the DataCite REST API. 

To improve the efficiency and performance of our services while bringing clarity to the purpose and scope of Event Data, we will remove most Event Data records which duplicate metadata from the DataCite Metadata Store, retaining only records that are used internally for DataCite services and/or contain information not sourced from DataCite DOI metadata.

Note that citations, views, and downloads in DataCite Commons and the DataCite REST API will continue to be gathered, counted, and represented in these services without adjustment or interruption. Learn more about [citations](doc:citations-and-references) and [usage](doc:views-and-downloads) in DataCite services.

These changes will take effect in Q3 and Q4 2026:

- In Q3 2026, we will _stop ingesting new events_ to Event Data that are no longer in scope (as defined below).
- In Q4 2026, we will _remove previously generated events_ from Event Data that are no longer in scope.

## What data will remain in scope for Event Data?

DataCite Event Data will continue to ingest and store events that are used internally for DataCite services. These include the events used to derive citation and reference counts, events for relationships between parts and versions, and events that record usage statistics.

The following events will stay in Event Data:

1. [Linking Events for Works](doc:eventdata-guide#linking-events) sourced from DataCite DOI metadata, where both works have DOIs and the relation is one of the 10 listed below:
   1. references
   2. cites
   3. is-cited-by
   4. is-referenced-by
   5. is-supplement-to
   6. is-supplemented-by
   7. is-part-of
   8. has-part
   9. has-version
   10. is-version-of
2. Linking Events sourced from other non-DataCite sources, including [Crossref’s data citations endpoint](https://www.crossref.org/documentation/retrieve-metadata/data-citations/) and zbMATH. These aren’t represented elsewhere in DataCite metadata.
3. All [Usage Events](doc:eventdata-guide#usage-events).

## What data will no longer be in Event Data?

The following events will be removed from Event Data:

1. [Linking Events for Works](doc:eventdata-guide#works) sourced from DataCite metadata, where:
   1. Both works have DOIs and the relation is not one of the 10 listed above for citations/references, parts, and versions.
   2. One work has a DOI and the other has a URL, with any relation.
2. [Linking Events for Authors](doc:eventdata-guide#authors) (relation-type-id  "is-authored-by") sourced from DataCite metadata. These record connections between DOIs and ORCID iDs, duplicating metadata from the Creator nameIdentifier property.
3. [Linking Events for Affiliations](doc:eventdata-guide#affiliations) (relation-type-id "is-authored-at"). These record connections between DOIs and ROR IDs, duplicating metadata from the Creator affiliationIdentifier property.
4. [Linking Events for Funders](doc:eventdata-guide#funders) (relation-type-id "is-funded-by"). These record connections between DOIs and Crossref Funder IDs, duplicating metadata from the FundingReference funderIdentifier property.

## What do I need to do?

If you register DOIs with DataCite, there is nothing you need to change. DataCite Event Data has always been automatically generated based on DataCite DOI metadata, so this change won’t have any impact on DOI registration workflows.

If you retrieve connection data from the `/events` endpoint, you can retrieve this data by querying the REST API `/dois` endpoint instead. We have included examples below showing how to retrieve connection metadata through the REST API. If you have questions about structuring REST API queries, please get in touch with us at [support@datacite.org.](mailto:support@datacite.org.)

## How can I access relationship metadata?

The DataCite REST API has filter parameters on the `/dois` endpoint that can be used to query RelatedIdentifier, nameIdentifier, affiliationIdentifier, and funderIdentifier metadata. The query parameter can also be used to search any metadata field.

### Connections between Works

Connections between works are asserted in the RelatedIdentifier property. All RelatedIdentifiers for a given DOI can be viewed in the individual DOI record. To search for connections to a given DOI asserted by other DOIs, you can query the RelatedIdentifiers field. For example:

- <https://api.datacite.org/dois?affiliation=true&publisher=true&query=relatedIdentifiers.relatedIdentifier:10.14454/qdd3-ps68>

This can be combined with a search for a specific relationType, for example:

- <https://api.datacite.org/dois?affiliation=true&publisher=true&query=relatedIdentifiers.relatedIdentifier:10.14454/qdd3-ps68%20AND%20relatedIdentifiers.relationType:IsDocumentedBy>

This searches for any DOI that includes the relatedIdentifier 10.14454/qdd3-ps68 and the relationType IsDocumentedBy.

- Note: For DOIs with multiple relatedIdentifiers, the relationType could be associated with a different relatedIdentifier in the same DOI record.

### Connections to Authors

Connections to authors with ORCID iDs are asserted in the nameIdentifier sub-property of Creator. All nameIdentifiers for a given DOI can be viewed in the individual DOI record. You can use the `user-id` parameter to search creators.nameIdentifiers.nameIdentifier for an ORCID iD. For example:

- <https://api.datacite.org/dois?affiliation=true&publisher=true&user-id=0000-0001-6133-4045>

### Connections to Affiliations

Connections to affiliations with ROR IDs are asserted in the affiliationIdentifier sub-property of affiliation. All affiliationIdentifiers for a given DOI can be viewed in the individual DOI record. You can use the `affiliation-id` parameter to search creators.affiliation.affiliationIdentifier and contributors.affiliation.affiliationIdentifier for a ROR ID. For example:

- <https://api.datacite.org/dois?affiliation=true&publisher=true&affiliation-id=https://ror.org/00jmfr291>

### Connections to Funders

Connections to funders with ROR IDs and Crossref Funder IDs are asserted in the funderIdentifier sub-property of FundingReference. All funderIdentifiers for a given DOI can be viewed in the individual DOI record. There are several parameters that support querying funderIdentifiers:

- `funded-by`: Search fundingReferences.funderIdentifier for a ROR ID. Results also include DOIs containing a Crossref Funder ID in fundingReferences.funderIdentifier corresponding to the ROR ID.
- `include-funder-child-organizations`: When the `funded-by=` parameter is set to a ROR ID and `include-funder-child-organizations=true`, the returned list of DOIs will be filtered to DataCite resources funded by the organization identified by the ROR ID as well as all of its child organizations. Child organizations include direct descendants as well as children of children.
- `funder-id`: Search fundingReferences.funderIdentifier for a Crossref Funder ID.