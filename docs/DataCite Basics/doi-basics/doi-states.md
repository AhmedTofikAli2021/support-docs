---
title: DOI States
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
In DataCite systems, a record will have one of three “states”: Findable DOI, Registered DOI, or Draft record.  These states indicate:

- Whether the DOI name has been registered in the global [Handle System](doc:doi-persistence#dois-and-the-handle-system) 
- Whether the metadata is openly available and indexed in DataCite’s APIs and DataCite Commons

| State      | Registered in global Handle System | Publicly available metadata |
| :--------- | :--------------------------------- | :-------------------------- |
| Findable   | :white_check_mark:                 | :white_check_mark:          |
| Registered | :white_check_mark:                 | :x:                         |
| Draft      | :x: (can be deleted)               | :x:                         |

## Findable DOIs

Findable DOIs are registered within the global Handle System. 

Metadata for Findable DOIs is openly available and indexed in DataCite’s APIs and DataCite Commons.

Findable DOIs may be updated to Registered DOIs, which hides the metadata from publicly availability. This is useful in  [cases where a DOI is created by mistake or content is retracted](doc:doi-persistence#what-if-a-doi-is-created-by-mistake-or-the-content-is-retracted) . Findable DOIs may not be returned to the Draft state and can’t be deleted.

## Registered DOIs

Registered DOIs are registered with the global Handle System. 

However, metadata for Registered DOIs is not openly available: they are not findable in DataCite Commons and are not retrievable via the [Public API](doc:api#public-api-no-authentication). Authenticated users can access metadata for Registered DOIs via the [Member API](doc:api#member-api-requires-authentication).

Registered DOIs may be updated to Findable DOIs, making the metadata publicly available. Registered DOIs may not be returned to the Draft state and can’t be deleted.

> 🚧 Privacy
> 
> Registered DOI metadata can be seen by authenticated users via the [Member API](doc:api#member-api-requires-authentication).

## Draft records

Draft records are not yet registered within the global Handle System, which means the identifier can be deleted. Draft records require only the identifier number in order to be created or saved. It is not necessary to enter a valid URL or valid metadata when creating a Draft. 

Draft records will only be retrieved if the user is logged in to Fabrica or if an API query is authenticated; they are not public facing records. You may use this state to reserve an identifier number without other services or resolvers knowing about its existence.

> ❗️ A note on publishing
> 
> Draft records are not DOIs because they are not registered in the global Handle System and can be deleted. We strongly recommend you avoid using draft state records in publications and other published content. Update the state to Findable or Registered before using the DOI name.

Draft state may be updated to either Registered or Findable. Registered and Findable DOIs may not be returned to the Draft state, which means that changing the state of a Draft is final. Drafts remain until the owner either deletes them or converts them to another state. 

> 🚧 Privacy
> 
> Draft state metadata can be seen by authenticated users via the [Member API](doc:api#member-api-requires-authentication).

## Metadata retrieval and DOI states

The REST API can be used with authentication (the Member API) and without authentication (the Public API). (See [Member vs. Public API](doc:api#member-vs-public-api) for more information).

By default, the Member API will return records with any of the three states: Findable, Registered, or Draft. These results can be filter by using the `state` parameter to only include certain states. For example, `state=findable,registered` will  exclude Draft records.

The Public API will only return records in Findable state (equivalent results to `state=findable`in the Member API).