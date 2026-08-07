---
title: Physical Objects and Samples
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
DOIs can be assigned to physical objects, samples and substances using the [resourceTypeGeneral: PhysicalObject](https://datacite-metadata-schema.readthedocs.io/en/4/appendices/appendix-1/resourceTypeGeneral/#physicalobject). Some examples include artifacts, specimens, material samples, and features-of-interest of any size. 

Below is an example of XML metadata for a DOI with the resourceTypeGeneral: PhysicalObject:

```xml PhysicalObject
<resourceType resourceTypeGeneral="PhysicalObject">Individual Sample</resourceType>
```

An IGSN ID is a globally unique and persistent identifier for physical samples. The core purpose of the IGSN ID is to enable transparent and traceable connections between research activities and objects, including samples, collections, instruments, grants, data, publications, people, and organizations. Learn more about [assigning IGSN IDs](doc:igsn-ids).