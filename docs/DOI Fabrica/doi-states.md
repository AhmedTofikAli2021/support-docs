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
When registering DOIs in DOI Fabrica, you must select a state for the DOI. There are currently three states available. 
[block:api-header]
{
  "title": "Draft DOIs"
}
[/block]
Draft DOIs can be deleted, and they require only the DOI itself in order to be created or saved. In other words, you do not need to enter a valid URL or valid metadata when creating Draft DOIs. Draft DOIs are known only to DOI Fabrica. You may use this state to reserve a DOI within DOI Fabrica without other services or resolvers knowing about its existence.  

Draft DOIs may be updated to either Registered or Findable DOIs. Registered and Findable DOIs may not be returned to the Draft state, which means that changing the state of a Draft DOI is final.

Draft DOIs using the test prefix (10.5072) are automatically deleted from our production systems after 30 days. Draft DOIs with other prefixes remain until the DOI owner either deletes them or converts them to another state. 
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
[block:api-header]
{
  "title": "DOI States Outside of Fabrica"
}
[/block]
DOI states were introduced when DataCite DOI Fabrica was launched, so the Fabrica service understands all states natively. Other DataCite services can also make use of states, but currently only in a limited way. 

The [MDS API](doc:mds-api-guide) doesn't directly understand state, but you can change a DOI from Findable to Registered by using the `delete DOI` API call. You cannot currently create Draft DOIs using the MDS API. 

The EZ API understands all DOI states, but it uses the EZID terms. 
[block:parameters]
{
  "data": {
    "h-0": "EZID State Term",
    "h-1": "Equivalent DataCite State Term",
    "0-0": "Reserved",
    "0-1": "Draft",
    "1-0": "Unavailable",
    "1-1": "Registered",
    "2-0": "Public",
    "2-1": "Findable"
  },
  "cols": 2,
  "rows": 3
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Would you like to know more?",
  "body": "If you have any questions, requests or ideas please [contact us.](doc:how-to-contact-datacite)"
}
[/block]