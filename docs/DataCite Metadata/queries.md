---
title: Search DOI Metadata with Queries
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
DataCite services support searching DOI metadata according to OpenSearch [query string syntax](https://opensearch.org/docs/latest/query-dsl/full-text/query-string/). This guide contains examples to get you started with querying DataCite DOI metadata.

The same query string syntax is used for:

- The `query` parameter of the [DataCite REST API](doc:api)
- The [Works search in DataCite Commons](doc:works-in-datacite-commons)
- [Arbitrary queries](https://support.datacite.org/docs/datacite-oai-pmh#arbitrary-queries) (base64-encoded) in the [DataCite OAI-PMH service](doc:datacite-oai-pmh) 

## Construct a query string

A query string can be used to search DOI metadata, as well as other administrative information associated with the DOI.

### Specify the field to search

A specific metadata field can be provided in the query. For example:

- `publicationYear:2016` ([REST API](https://api.datacite.org/dois?query=publicationYear:2016)) ([Commons](https://commons.datacite.org/?query=publicationYear%3A2016))
- `publisher:DataCite` ([REST API](https://api.datacite.org/dois?query=publisher:DataCite)) ([Commons](https://commons.datacite.org/?query=publisher%3ADataCite))

Nested fields are joined by a `.`. For example:

- `creators.nameIdentifiers.nameIdentifierScheme:ORCID` ([REST API](https://api.datacite.org/dois?query=creators.nameIdentifiers.nameIdentifierScheme:ORCID)) ([Commons](https://commons.datacite.org/?query=creators.nameIdentifiers.nameIdentifierScheme%3AORCID))
- `titles.title:"CrowdoMeter Tweets"` ([REST API](https://api.datacite.org/dois?query=titles.title:%22CrowdoMeter%20Tweets%22)) ([Commons](https://commons.datacite.org/?query=titles.title%3A%22CrowdoMeter+Tweets%22))

For a complete list of fields, see [Supported fields](doc:queries#supported-fields) below.

When a field is _not_ specified, the query by default searches commonly queried fields (including title, creator name, creator nameIdentifier, publisher, description, subject, and relatedIdentifier). For example:

- `climate` ([REST API](https://api.datacite.org/dois?query=climate)) ([Commons](https://commons.datacite.org/?query=climate))

### Wildcards

The wildcards `*` and `?` are supported. `*` matches zero or more characters and `?` matches any single character. For example:

- `creators.nameIdentifiers.nameIdentifier:*` ([REST API](https://api.datacite.org/dois?query=creators.nameIdentifiers.nameIdentifier:*)) ([Commons](https://commons.datacite.org/?query=creators.nameIdentifiers.nameIdentifier%3A*))
- `subjects.subject:robot*` ([REST API](https://api.datacite.org/dois?query=subjects.subject:robot*)) ([Commons](https://commons.datacite.org/?query=subjects.subject%3Arobot*))

### Exact match searches

Enclose the query in quotations `" "`  to search for exact matches only. For example:

- `creators.affiliation.name:"Oklahoma State University"` ([REST API](<https://api.datacite.org/dois?affiliation=true&query=creators.affiliation.name:"Oklahoma State University">)) ([Commons](https://commons.datacite.org/?query=creators.affiliation.name%3A%22Oklahoma+State+University%22))

### Boolean operators

By default, all terms are optional, as long as one term matches. Use `+` or `-` to specify terms that have to match or not match, respectively. For example, to search for DOIs containing both "climate" and "change" in the title field:

- `titles.title:(climate +change)`  ([REST API](https://api.datacite.org/dois?query=titles.title:(climate%20+change))) ([Commons](https://commons.datacite.org/?query=titles.title%3A%28climate+%2Bchange%29))

The boolean operators `AND`, `OR` and `NOT` (case-sensitive) are also supported. For example:

- `types.resourceTypeGeneral:Software AND types.resourceType:XML` ([REST API](https://api.datacite.org/dois?query=types.resourceTypeGeneral:Software%20AND%20types.resourceType:XML)) ([Commons](https://commons.datacite.org/?query=types.resourceTypeGeneral%3ASoftware+AND+types.resourceType%3AXML))
- `types.resourceTypeGeneral:Preprint OR types.resourceType:Preprint` ([REST API](https://api.datacite.org/dois?query=types.resourceTypeGeneral:Preprint%20OR%20types.resourceType:Preprint)) ([Commons](https://commons.datacite.org/?query=types.resourceTypeGeneral%3APreprint+OR+types.resourceType%3APreprint))
- `publicationYear:2026 AND NOT types.resourceTypeGeneral:Dataset` ([REST API](https://api.datacite.org/dois?query=publicationYear:2026%20AND%20NOT%20types.resourceTypeGeneral:Dataset)) ([Commons](https://commons.datacite.org/?query=publicationYear%3A2026+AND+NOT+types.resourceTypeGeneral%3ADataset))

When multiple operators are used together, use parentheses to combine them. For example:

- `publicationYear:2016 AND types.resourceTypeGeneral:(Preprint OR JournalArticle)` ([REST API](https://api.datacite.org/dois?query=publicationYear:2016%20AND%20types.resourceTypeGeneral:(Preprint%20OR%20JournalArticle))) ([Commons](https://commons.datacite.org/?query=publicationYear%3A2016+AND+types.resourceTypeGeneral%3A%28Preprint+OR+JournalArticle%29))
- `(titles.title:(climate AND change) OR descriptions.description:(climate AND change)) AND (publicationYear:2023)` ([REST API](https://api.datacite.org/dois?query=(titles.title:(climate%20AND%20change)%20OR%20descriptions.description:(climate%20AND%20change))%20AND%20(publicationYear:2023))) ([Commons](https://commons.datacite.org/?query=%28titles.title%3A%28climate+AND+change%29+OR+descriptions.description%3A%28climate+AND+change%29%29+AND+%28publicationYear%3A2023%29))

## Supported fields

### Metadata fields

Nested fields use the same structure as in the "attributes" section of the [REST API response for a DOI metadata record](doc:api-get-doi#response). You can also refer to the [DataCite XML to JSON mapping](doc:datacite-xml-to-json-mapping) for a full list of how DataCite metadata is represented in JSON.

- creators
  - creators.name
  - creators.lang
  - creators.nameType
  - creators.givenName
  - creators.familyName
  - creators.nameIdentifiers
    - creators.nameIdentifiers.nameIdentifier
    - creators.nameIdentifiers.nameIdentifierScheme
    - creators.nameIdentifiers.schemeUri
  - creators.affiliation
    - creators.affiliation.name
    - creators.affiliation.affiliationIdentifier
    - creators.affiliation.affiliationIdentifierScheme
    - creators.affiliation.schemeUri
- titles
  - titles.title
  - titles.lang
  - titles.titleType
- publisher
  - publisher.name
  - publisher.publisherIdentifier
  - publisher.publisherIdentifierScheme
  - publisher.schemeUri
  - publisher.lang
- publicationYear
- subjects
  - subjects.subject
  - subjects.subjectScheme
  - subjects.schemeUri
  - subjects.valueUri
  - subjects.classificationCode
  - subjects.lang
- contributors
  - contributors.contributorType
  - contributors.name
  - contributors.lang
  - contributors.nameType
  - contributors.givenName
  - contributors.familyName
  - contributors.nameIdentifiers
    - contributors.nameIdentifiers.nameIdentifier
    - contributors.nameIdentifiers.nameIdentifierScheme
    - contributors.nameIdentifiers.schemeUri
  - contributors.affiliation
    - contributors.affiliation.name
    - contributors.affiliation.affiliationIdentifier
    - contributors.affiliation.affiliationIdentifierScheme
    - contributors.affiliation.schemeUri
- dates
  - dates.date
  - dates.dateType
  - dates.dateInformation
- language
- types
  - types.resourceType
  - types.resourceTypeGeneral
  - relatedIdentifiers.relationTypeInformation
- alternateIdentifiers (or identifiers)
  - alternateIdentifiers.alternateIdentifier (or identifiers.identifier)
  - alternateIdentifiers.alternateIdentifierType (or identifiers.identifierType)
- relatedIdentifiers
  - relatedIdentifiers.relatedIdentifier
  - relatedIdentifiers.relatedIdentifierType
  - relatedIdentifiers.relationType
  - relatedIdentifiers.relatedMetadataScheme
  - relatedIdentifiers.schemeUri
  - relatedIdentifiers.schemeType
  - relatedIdentifiers.resourceTypeGeneral
- sizes
- formats
- version
- rightsList
  - rightsList.rights
  - rightsList.lang
  - rightsList.rightsUri
  - rightsList.rightsIdentifier
  - rightsList.rightsIdentifierScheme
  - rightsList.schemeUri
- descriptions
  - descriptions.description
  - descriptions.lang
  - descriptions.descriptionType
- geoLocations
  - geoLocations.geoLocationPoint
    - geoLocations.geoLocationPoint.pointLongitude
    - geoLocations.geoLocationPoint.pointLatitude
  - geoLocations.geoLocationBox
    - geoLocations.geoLocationBox.westBoundLongitude
    - geoLocations.geoLocationBox.eastBoundLongitude
    - geoLocations.geoLocationBox.southBoundLatitude
    - geoLocations.geoLocationBox.northBoundLatitude
  - geoLocations.geoLocationPlace
  - geoLocations.geoLocationPolygon
    - geoLocations.geoLocationPolygon.polygonPoint
      - geoLocations.geoLocationPolygon.polygonPoint.pointLongitude
      - geoLocations.geoLocationPolygon.polygonPoint.pointLatitude
    - geoLocations.geoLocationPolygon.inPolygonPoint
      - geoLocations.geoLocationPolygon.inPolygonPoint.pointLongitude
      - geoLocations.geoLocationPolygon.inPolygonPoint.pointLatitude
- fundingReferences
  - fundingReferences.funderName
  - fundingReferences.funderIdentifier
  - fundingReferences.funderIdentifierType
  - fundingReferences.schemeUri
  - fundingReferences.awardNumber
  - fundingReferences.awardUri
  - fundingReferences.awardTitle
- relatedItems
  - relatedItems.relatedItemType
  - relatedItems.relationType
  - relatedItems.relationTypeInformation
  - relatedItems.relatedItemIdentifier
    - relatedItems.relatedItemIdentifier.relatedItemIdentifier
    - relatedItems.relatedItemIdentifier.relatedItemIdentifierType
    - relatedItems.relatedItemIdentifier.relatedMetadataScheme
    - relatedItems.relatedItemIdentifier.schemeURI
    - relatedItems.relatedItemIdentifier.schemeType
  - relatedItems.creators
    - relatedItems.creators.name
    - relatedItems.creators.nameType
    - relatedItems.creators.givenName
    - relatedItems.creators.familyName
  - relatedItems.titles
    - relatedItems.titles.title
    - relatedItems.titles.lang
    - relatedItems.titles.titleType
  - relatedItems.publicationYear
  - relatedItems.volume
  - relatedItems.issue
  - relatedItems.number
  - relatedItems.numberType
  - relatedItems.firstPage
  - relatedItems.lastPage
  - relatedItems.publisher
  - relatedItems.edition
  - relatedItems.contributors
    - relatedItems.contributors.contributorType
    - relatedItems.contributors.name
    - relatedItems.contributors.nameType
    - relatedItems.contributors.givenName
    - relatedItems.contributors.familyName

### Additional fields

In addition to the metadata fields above, the following fields are searchable as part of the query string:

| Field         | Notes                                                                                 |
| :------------ | :------------------------------------------------------------------------------------ |
| prefix        | The DOI prefix.                                                                       |
| suffix        | The DOI suffix.                                                                       |
| url           | The landing page URL of the DOI.                                                      |
| schemaVersion | The DataCite Metadata Schema version of the stored DOI metadata represented as a URL. |
| created       | Creation date of the DOI record.                                                      |
| registered    | Registration date of the DOI record.                                                  |
| updated       | Last updated date of the DOI record.                                                  |