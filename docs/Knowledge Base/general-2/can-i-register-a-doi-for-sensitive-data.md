---
title: Can I register a DOI for sensitive data?
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
It is possible to assign DOIs to sensitive data. However, there are a few things to keep in mind in the context of what is possible within the DataCite DOI system.  Each repository needs to determine the best solution for the resources they handle.

The DataCite DOI registration policy states:

_DOIs must resolve to a publicly available landing page. The underlying content does not need to be publicly available but the metadata must be open._

As long as you can provide a publicly available landing page and the mandatory DataCite metadata properties, you can register a DOI. You can control whether or not the DOI metadata is publicly available using the [DOI state](doc:doi-states).

- Findable state: The DOI metadata  will be indexed in DataCite APIs and DataCite Commons.
- Registered state: The DOI metadata will not be publicly available. However, Registered state DOI metadata can be retrieved via the Member API, so it is not fully restricted. Sensitive metadata should not be included in the DataCite metadata.

The [FAIR-IMPACT Project](https://www.fair-impact.eu/) has published a set of [User guidelines on EOSC PID implementation](https://zenodo.org/records/15081434) which includes the use of PIDs with sensitive data.