---
title: DataCite OAI-PMH Guide
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
Access the DataCite OAI-PMH service here: [https://oai.datacite.org](https://oai.datacite.org) 
[block:api-header]
{
  "title": "What is this service?"
}
[/block]
This DataCite service exposes metadata stored in the DataCite Metadata
Store (MDS) using the Open Archives Initiative Protocol for Metadata Harvesting ([OAI-PMH](http://www.openarchives.org/pmh/)).
[block:api-header]
{
  "title": "Who can use this service?"
}
[/block]
This service is open to everyone and is meant to be accessed by OAI-PMH
compliant harvesters or any application that issues OAI-PMH requests.
The service base address is **`https://oai.datacite.org/oai`** and the
service identifier is available [here](https://oai.datacite.org/oai?verb=Identify).
[block:api-header]
{
  "title": "What is OAI-PMH?"
}
[/block]
In brief, [OAI-PMH] provides a set of services that enables exposure and
harvesting of repository metadata. The protocol is comprised of six
verbs that specify the service being invoked, they are:

-   **Identify** - used to retrieve information about the repository.
-   **ListIdentifiers** - used to retrieve record headers from the
    repository.
-   **ListRecords** - used to harvest full records from the repository.
-   **ListSets** - used to retrieve the set structure of the repository.
-   **ListMetadataFormats** - lists available metadata formats that the
    repository can disseminate.
-   **GetRecord** - used to retrieve an individual record from the
    repository.

Selective harvesting can be performed by the use of accompanying
parameters. Available parameters are:

-   **identifier** - specifies a specific record identifier.
-   **metadataPrefix** - specifies the metadata format that the records
    will be returned in.
-   **set** - specifies the set that returned records must belong to.
-   **from** - specifies that records returned must have been
    created/update/deleted on or after this date.
-   **until** - specifies that records returned must have been
    created/update/deleted on or before this date.
-   **resumptionToken** - a token previously provided by the server to
    resume a request where it last left off.

The verbs and parameters can be combined to issue requests to the
service such as:

- [`https://oai.datacite.org/oai?verb=Identify`](https://oai.datacite.org/oai?verb=Identify)
- [`https://oai.datacite.org/oai?verb=ListIdentifiers&metadataPrefix=oai_dc`](https://oai.datacite.org/oai?verb=ListIdentifiers&metadataPrefix=oai_dc)
- [`https://oai.datacite.org/oai?verb=ListRecords&from=2011-06-01T00:00:00Z&metadataPrefix=oai_dc`](https://oai.datacite.org/oai?verb=ListRecords&from=2011-06-01T00:00:00Z&metadataPrefix=oai_dc)

For more details on the protocol, its implementation, and uses please
visit the [OAI-PMH web site](http://www.openarchives.org/pmh/).
[block:api-header]
{
  "title": "Available Metadata Formats"
}
[/block]
The DataCite OAI-PMH Data Provider is able to disseminate records in the
following formats:

### OAI Dublin Core (oai_dc)

As a minimum requirement for OAI-PMH compliance, metadata must be made
available in the OAI Dublin Core format. For more information please see
the [OAI-PMH web site](http://www.openarchives.org/OAI/openarchivesprotocol.html#dublincore).

### OAI DataCite (oai_datacite)

This metadata format has been specifically established for the
dissemination of DataCite records using OAI-PMH. In addition to the
original DataCite metadata, this format contains several other elements
describing the version of the metadata and the registering data center.
For more information about this format and its schema please see the
[Datacite OAI schema page](doc:oai-pmh-schema-documentation).

### DataCite Direct (datacite)

This metadata format contains only the original DataCite metadata
without additions or alterations. Because there are multiple versions of
DataCite metadata in the MDS, there is no one schema that they will all
adhere to. Therefore the schema for this format does **not** exist and
metadata will **not** validate against it. Please note that this format
is **not** OAI-PMH version 2.0 compliant for the previously stated
reasons.
[block:api-header]
{
  "title": "Set Structure"
}
[/block]
Each DataCite member and data center is represented by a set in the repository.
Therefore it is easy to harvest all available metadata for a particular member
or data center.

### Arbitrary Queries

You can use custom query search queries in your setspec. Therefore the
query string must be base64url encoded, see [RFC 4648](https://tools.ietf.org/html/rfc4648#section-5), and
appended to any normal setspec or the empty string separated by a tilde
(`~`).

### Examples

The query structure is documented here: https://support.datacite.org/docs/api-queries

- **API query string**: [`types.resourceTypeGeneral%3ADataset`](https://oai.datacite.org/oai?verb=ListRecords&metadataPrefix=oai_datacite&set=~dHlwZXMucmVzb3VyY2VUeXBlR2VuZXJhbCUzQURhdGFzZXQ=)
- **base64url**: [`~dHlwZXMucmVzb3VyY2VUeXBlR2VuZXJhbCUzQURhdGFzZXQ=`](https://oai.datacite.org/oai?verb=ListRecords&metadataPrefix=oai_datacite&set=~dHlwZXMucmVzb3VyY2VUeXBlR2VuZXJhbCUzQURhdGFzZXQ=)
- **set name member**: [`TIB~dHlwZXMucmVzb3VyY2VUeXBlR2VuZXJhbCUzQURhdGFzZXQ=`](https://oai.datacite.org/oai?verb=ListRecords&metadataPrefix=oai_datacite&set=TIB~dHlwZXMucmVzb3VyY2VUeXBlR2VuZXJhbCUzQURhdGFzZXQ=)
- **set name data center**: [`TIB.GFZ~dHlwZXMucmVzb3VyY2VUeXBlR2VuZXJhbCUzQURhdGFzZXQ=`](https://oai.datacite.org/oai?verb=ListRecords&metadataPrefix=oai_datacite&set=TIB.GFZ~dHlwZXMucmVzb3VyY2VUeXBlR2VuZXJhbCUzQURhdGFzZXQ=)
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]