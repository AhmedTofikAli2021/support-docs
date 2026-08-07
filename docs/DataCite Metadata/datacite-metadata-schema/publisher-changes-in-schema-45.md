---
title: Schema 4.5 Publisher Changes
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
Schema 4.5 added three new sub-properties to the Publisher property:

- publisherIdentifier
- publisherIdentifierScheme
- schemeUri

Adding publisher identifiers necessitated some changes to our APIs and services which accept and return JSON.

## DataCite REST API

### Creating and updating DOIs

The REST API has been modified to accept an object with these attributes when [creating](https://support.datacite.org/docs/api-create-dois) or [updating](https://support.datacite.org/docs/updating-metadata-with-the-rest-api) a DOI:

```json
"publisher":  
  {  
    "name": "DataCite",  
    "schemeUri": "https://ror.org",  
    "publisherIdentifier": "https://ror.org/04wxnsj81",  
    "publisherIdentifierScheme": "ROR",  
    "lang": "en"
  }
```

To ensure this change is backward-compatible, the REST API continues to accept a single string value for publisher:

```json
"publisher": "DataCite"
```

Repositories submitting JSON metadata via the REST API may use either the new structure or a string value—the REST API will accept either.

The XML structure is shown in the [DataCite Metadata Schema documentation for the Publisher property](https://datacite-metadata-schema.readthedocs.io/en/4.5/properties/publisher/).

### Retrieving a single DOI or a list of DOIs

For metadata retrieval via the DataCite REST API `/dois` endpoint, a URL parameter `publisher` is required to include publisher identifiers in the response. For example:

`https://api.datacite.org/dois/10.14454/g8e5-6293?publisher=true`

`https://api.datacite.org/dois?publisher=true`

REST API responses without the `publisher=true` parameter do not include publisher identifiers. For more information, see [Can I see more detailed affiliation and publisher information in the REST API?](doc:can-i-see-more-detailed-affiliation-information-in-the-rest-api)

## DataCite Content Negotiation and GraphQL API

> 🚧 
> 
> The changes to DataCite Content Negotiation and the DataCite GraphQL API to support the new publisher attributes are not backward-compatible. Updates may be required to existing integrations. For assistance, please contact us at [support@datacite.org](mailto:support@datacite.org).

### DataCite Content Negotiation

All [DataCite Content Negotiation](doc:datacite-content-resolver) requests for the content types `application/vnd.datacite.datacite+json` and `application/vnd.datacite.datacite+xml` will include publisher identifiers as of **February 27, 2024.** This includes:

- Content negotiation requests to `https://doi.org`
- [Link-based content-type requests](https://support.datacite.org/docs/datacite-content-resolver#link-based-content-type-requests)  to `https://data.crosscite.org` 
- Link-based content-type requests to the DataCite REST API using the syntax `https://api.datacite.org/application/vnd.datacite.datacite+json/{doi}`

Consequently, content negotiation requests with content type `application/vnd.datacite.datacite+json` will  return the publisher value as an object (see above) rather than a string as of **February 27, 2024.**

### DataCite GraphQL API

The GraphQL type **Work** and its derivatives will support publisher identifiers as of **February 27, 2024**. This includes:

- Audiovisual
- Book
- BookChapter
- Collection
- ConferencePaper
- DataManagementPlan
- DataPaper
- Dataset
- Dissertation
- Event
- Image
- Instrument
- InteractiveResource
- JournalArticle
- Model
- Other
- PeerReview
- PhysicalObject
- Preprint
- Publication
- Service
- Software
- Sound
- Workflow

Consequently, GraphQL queries containing publisher types will need to be modified to support the publisher object structure. For example, a query currently structured like this:

```graphql
{
  works(query: "climate change") {
    nodes {
      doi
      publisher
    }
  }
}

```

Will need to be changed to the following to query the same publisher metadata as of **February 27, 2024**:

```graphql
{
  works(query: "climate change") {
    nodes {
      doi
      publisher {
        name
      }
    }
  }
}
```

Additionally, the JSON returned will reflect the queried publisher object structure.