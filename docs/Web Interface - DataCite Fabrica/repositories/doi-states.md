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
When registering metadata you must select a state. There are currently three states available. 

## Draft record

Draft state means the identifier can be deleted. They require only the identifier number in order to be created or saved. It is not necessary to enter a valid URL or valid metadata when creating a Draft. Drafts records will only be retrieved if the user is logged in to Fabrica or if an API query is authenticated, they are not public facing records. You may use this state to reserve an identifier number within without other services or resolvers knowing about its existence.  

> ❗️ A note on publishing
> 
> Draft records are not DOIs because they are not registered in the global handle server and can be deleted. We strongly recommend you avoid using draft state records in publications and other published content. Update the state to registered or findable before using the DOI name.

Draft state may be updated to either Registered or Findable. Registered and Findable DOIs may not be returned to the Draft state, which means that changing the state of a Draft is final. Drafts remain until the owner either deletes them or converts them to another state. 

> 🚧 Privacy
> 
> Draft state metadata can be seen by other DataCite Members via the Member API.

## Registered DOI Name

Registered DOIs are registered with the global handle system, but they are not indexed in DataCite Commons and are no longer available via the [Public API](https://support.datacite.org/docs/api#member-vs-public-api). This state maps to "is_active=false" in the DataCite Metadata Store. 

Registered DOIs may be updated to Findable DOIs, at which point they will be indexed in DataCite Commons. Registered DOIs may not be returned to the Draft state.

> 🚧 Privacy
> 
> Registered DOI metadata can be seen by other DataCite Members via the Member API.

## Findable DOI Name

Findable DOIs are registered with the global handle system just like Registered DOIs, but they are also indexed in DataCite Commons and therefore in the DataCite APIs. This state maps to "is_active=true" in the DataCite Metadata Store.

Findable DOIs may be updated to Registered DOIs. This means that they will no longer be indexed by DataCite Commons.

## DOI States Outside of Fabrica

DOI states were introduced when DataCite DOI Fabrica was launched, so the Fabrica service understands all states natively. Both the [REST API](doc:api) and [MDS API](doc:mds-api-guide) allow you to change a DOI from Findable to Registered by using an API call.

> 📘 Would you like to know more?
> 
> If you have any questions, requests or ideas please [contact us.](doc:how-to-contact-datacite)