---
title: Versioning
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
DOI metadata can be updated. This includes the content underlying the DOI, correcting small errors e.g. typos or adding a new file. This means small changes don't always require a new DOI.  Individual stewards need to determine which are major vs. minor versions

## If there is a minor change to the content being shared:

If you are not registering a new DOI you may still update the metadata for the the version property (property 15) and increment the minor version number. This allows you to indicate what version “of the resource” is being described. These changes will be captured in the provenance API e.g. https://api.datacite.org/dois/10.21406/abpa.2017.5.1.50/activities (only for DOIs registered since March 2019).

## If there is a major change to the content being shared:

Our schema documentations recommends that a new DOI should be assigned when there is a new major version of the resource you are sharing. We recommend adding a relatedIdentifier with the relationType as follows: 

new relationType pair (HasVersion, IsVersionOf)

**HasVersion** : The registered resource such as a software package or code repository has a versioned instance (indicates A has the instance B) e.g. it may be used to relate an un-versioned code repository to one of its specific software versions.

```
<relatedIdentifier
relatedIdentifierType="DOI"
relationType="HasVersion">10.5281/ZENODO.832053
</relatedIdentifier>
```

**IsVersionOf **: The registered resource is an instance of a target resource (indicates that A is an instance of B) e.g. it may be used to relate a specific version of a software package to its software code repository.

```
<relatedIdentifier
relatedIdentifierType="DOI"
relationType="IsVersionOf">10.5281/ZENODO.832054
</relatedIdentifier>
```

##Related Resources:

The [RDA versioning work group](https://www.rd-alliance.org/groups/data-versioning-wg) is also a good place for resources.