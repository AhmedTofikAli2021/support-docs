---
title: When should I use IsIdenticalTo?
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
You can connect your DOIs to other identifiers using the [relatedIdentifier](https://datacite-metadata-schema.readthedocs.io/en/4.7/properties/relatedidentifier/) metadata property. The relatedIdentifier property is always  accompanied by a [relationType](https://datacite-metadata-schema.readthedocs.io/en/4.7/properties/relatedidentifier/#b-relationtype) which describes the relationship between the two identifiers.

The [IsIdenticalTo](https://datacite-metadata-schema.readthedocs.io/en/4.7/appendices/appendix-1/relationType/#isidenticalto) relationType can be used when there are two DOIs for the exact same research output. The most common reasons for this are:

1.)  A group of resources have been moved from one platform to another (we always suggested it is best to avoid duplication by also [migrating the DOIs and updating the landing pages](https://support.datacite.org/docs/is-it-possible-to-update-the-url-landing-pages-of-dois)).

2.)  The same content is intentionally stored in two different locations (different landing pages on different platforms).

The metadata of both DOIs can be updated to indicate that there is an identical version of the resource as follows:

**DOI 1** IsIdenticalTo **DOI 2 **

Metadata for DOI 1, connecting to DOI 2 

```xml
<identifier>10.17596/hcqn-2w70</identifier>
<relatedIdentifiers>
        <relatedIdentifier relatedIdentifierType="DOI" relationType="IsIdenticalTo" resourceTypeGeneral="Dataset">10.17596/xc1g-pq91</relatedIdentifier>
    </relatedIdentifiers>
```

**DOI 2** IsIdenticalTo **DOI 1**

Metadata for DOI 2, connecting to DOI 1

```xml
<identifier>10.17596/xc1g-pq91</identifier>
<relatedIdentifiers>
        <relatedIdentifier relatedIdentifierType="DOI" relationType="IsIdenticalTo" resourceTypeGeneral="Dataset">10.17596/hcqn-2w70</relatedIdentifier>
    </relatedIdentifiers>
```

More information about the [DataCite Metadata Schema](https://schema.datacite.org/).

See also [Connecting different versions, formats and more with Related Identifiers](https://support.datacite.org/docs/connecting-versions-with-related-identifiers)