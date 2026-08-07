---
title: Which metadata field in the DataCite schema captures the grant ID information?
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
The “awardURI” field in the DataCite metadata schema is the appropriate place to include a URI for a grant. 

Example: 

```xml
<awardNumber awardURI="http://cordis.europa.eu/project/rcn/100603_en.html”>284382></awardNumber>
```

The URI and award number don’t need to match. In the above example, the URI (not a DOI in this case) doesn't contain any part of the actual award number, but if you follow the link, you'll see that the "grant agreement ID" assigned by the EU is the “awardNumber” listed in the metadata.

More information:

[DataCite Metadata Schema](https://schema.datacite.org/)