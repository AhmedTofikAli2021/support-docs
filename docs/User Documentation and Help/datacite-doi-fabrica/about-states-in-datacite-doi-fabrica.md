---
title: About States in DataCite DOI Fabrica
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
When registering DOIs in DOI Fabrica, you must select a state for the DOI. There are currently three states available.
[block:api-header]
{
  "title": "Draft DOIs"
}
[/block]
Draft DOIs can be deleted, and they don't require a valid URL or valid metadata. Draft DOIs are known only to DOI Fabrica. You may use this state to reserve a DOI within DOI Fabrica without other services or resolvers knowing about its existence.  

Draft DOIs may be updated to either Registered or Findable DOIs. Registered and Findable DOIs may not be returned to the Draft state, which means that changing the state of a Draft DOI is final.
[block:api-header]
{
  "title": "Registered DOIs"
}
[/block]
Registered DOIs are registered with the global handle system, but they are not indexed in DataCite Search. This state maps to "is_active=false" in the DataCite Metadata Store. 

Registered DOIs may be updated to Findable DOIs, at which point they will be indexed in DataCite Search. Registered DOIs may not be returned to the Draft state.
[block:api-header]
{
  "title": "Findable DOIs"
}
[/block]
Findable DOIs are registered with the global handle system just like Registered DOIs, but they are also indexed in DataCite Search. This state maps to "is_active=true" in the DataCite Metadata Store.

Findable DOIs may be updated to Registered DOIs. This means that they will no longer be indexed by DataCite Search.