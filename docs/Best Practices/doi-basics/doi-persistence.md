---
title: DOI Persistence
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
DOIs are persistent identifiers (PIDs), which means that they are intended to be a permanent means of identifying and accessing a particular research output or resource. DOIs cannot be deleted.

## DOIs and the Handle System

The [DOI Foundation](https://www.doi.org/) governs the Digital Object Identifier (DOI) system. The DOI System offers DOI identifier / resolution services through the [Handle System](https://www.dona.net/handle-system), which meets the functional requirements defined by [ISO 26324](https://www.iso.org/standard/81599.html).

- The Handle System technology is used for the resolution part of the DOI System.
- The Handle System was developed by [CNRI](https://www.cnri.reston.va.us/) and is currently administered and maintained by the [DONA Foundation](https://www.dona.net/index).
- This handle infrastructure provides a reliable way of managing digital objects.

DOI Registration Agencies, including DataCite, make a commitment to  work with the DOI Foundation to guarantee persistence. [Read more about the Registration Agencies’ commitments](https://www.doi.org/the-community/existing-registration-agencies).

Resources:

[What is a DOI](https://www.doi.org/the-identifier/what-is-a-doi/)  
[The DOI handbook](https://www.doi.org/doi-handbook/HTML/index.html)  
[DOI Resolution Protocol Specification](https://www.dona.net/sites/default/files/2022-06/DO-IRPV3.0--2022-06-30.pdf)  
[Prefixes](https://support.datacite.org/docs/prefixes)

## Deactivate a DOI

There are three [DataCite DOI states](https://support.datacite.org/docs/doi-states): Draft, Registered, and Findable. The state indicates whether the DOI is registered in the Global Handle System and whether the metadata is retrievable via the DataCite API.  When a DataCite DOI is first published in Findable or Registered state, it is automatically registered in the external Handle System and cannot be deleted. 

> 🚧 DOIs cannot be deleted
> 
> In both Findable and Registered states, a DOI cannot be deleted.

It is also important to note that the DOI name—the alphanumeric string that is the prefix and suffix—cannot be changed or edited. 

> 📘 Suffixes cannot be changed
> 
> This is why we highly recommend avoiding the use of meaning in the suffix, as this cannot be changed if the meaning changes (e.g. acronyms).

## What if a DOI is created by mistake or the content is retracted?

If a DOI is registered in error, or the content that the DOI points to is deleted or retracted, then DataCite Repositories can follow these steps to deactivate and archive a DOI:

- **Change the state of the erroneous DOI from Findable to Registered state.** This means the DOI will not be found in DataCite Commons search results or Public API queries. Registered DOIs will continue to resolve.  
  Learn more about [DOI states](doc:doi-states).
- **Update the URL of the erroneous DOI to a tombstone page**. This can be your organization's own tombstone page or a generic one. Learn more about [tombstone pages](doc:tombstone-pages).