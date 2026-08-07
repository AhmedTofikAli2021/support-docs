---
title: Can I delete or change my DOI name?
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
There are three [DataCite DOI states](doc:doi-states): Draft, Registered, and Findable. The state indicates whether the DOI is registered in the Global Handle System and whether the metadata is retrievable via the DataCite API. When a DataCite DOI is first published in Findable or Registered state, it is automatically registered in the external Handle System and cannot be deleted.

> 🚧 DOIs cannot be deleted
> 
> In both Findable and Registered states, a DOI cannot be deleted.

It is also important to note that the DOI name—the alphanumeric string that is the prefix and suffix—cannot be changed or edited.

> 📘 Suffixes cannot be changed
> 
> This is why we highly recommend avoiding the use of meaning in the suffix, as this cannot be changed if the meaning changes (e.g. acronyms).

It is best to avoid creating a situation in which a DOI needs to be removed. Adjusting workflows to make better use of Drafts could help with this.

Follow these steps to deactivate an erroneous DOI:

- Change the state of the erroneous DOI from Findable to Registered state. This means the DOI will not be found in DataCite Commons search results or Public API queries. Registered DOIs will continue to resolve.  
  Learn more about [DOI states](doc:doi-states).
- Update the URL of the erroneous DOI to a tombstone page. This can be your organization's own tombstone page or a generic one. Learn more about [tombstone pages](doc:tombstone-pages).