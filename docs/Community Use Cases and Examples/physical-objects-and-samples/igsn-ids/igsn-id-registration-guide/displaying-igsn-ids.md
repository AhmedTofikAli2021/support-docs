---
title: Displaying IGSN IDs
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
## IGSN ID long display form

Like DOIs, the canonical form of an IGSN ID is a complete `https://doi.org/` URL using the form:

```
https://doi.org/10.21384/AU1234
```

Clear context should be included to indicate that it is an IGSN ID. See [DataCite DOI Display Guidelines](doc:datacite-doi-display-guidelines) for more information about displaying IGSN IDs as `https://doi.org/`links.

## IGSN ID short display form

IGSN IDs are sometimes displayed in locations where a complete `https://doi.org/`URL is not appropriate. In these cases, IGSN IDs should be displayed with only the DOI prefix and suffix or, if necessary, only the suffix. 

- Preferred: The DOI prefix and suffix (e.g., `igsn:10.21384/AU1234`)
- Alternate: Only the suffix (e.g., `igsn:AU1234`) 

Note that the short display form should be typically preceded by an `igsn:` tag to specify that it is an IGSN ID. However, in cases where IGSN IDs are already clearly denoted, such as in the column header of a data table, the preceding `igsn:` tag may be excluded from the short display form.  

## Hyperlinking IGSN IDs

Where possible, all representations of IGSN IDs should be hyperlinked with the IGSN ID’s complete DOI link.

## IGSN IDs in metadata

IGSN IDs encoded in metadata should contain the IGSN ID’s complete DOI URL. This includes IGSN IDs entered in DataCite Metadata Schema properties such as `relatedIdentifier`.

## QR codes

QR codes for IGSN IDs should contain the complete DOI URL. For example, <https://doi.org/10.21384/AU1234>

If a QR code is applied to a sample or its container, the label should also display the IGSN ID short display form in a human-readable way.

> 👍 
> 
> Display guidance may be updated in the future as best practices are refined in agreement with the publishing community.