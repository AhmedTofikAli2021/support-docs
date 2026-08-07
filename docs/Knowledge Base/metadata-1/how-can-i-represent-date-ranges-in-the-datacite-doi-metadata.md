---
title: How can I represent date ranges   in the DataCite DOI metadata?
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
The DataCite Date property can be used for different dates relevant to the work that the DOI is being assigned to.

This property accepts date ranges according to RKMS-ISO8601, which separates the start and end dates with a slash. For example, the metadata you would need to include for a date range with the dateType Valid:

<dates>

```
 <date dateType="Valid">2025-01-01/2025-12-31</date>
```

</dates>

<br />

More information about the [DataCite Metadata Schema](https://schema.datacite.org/).