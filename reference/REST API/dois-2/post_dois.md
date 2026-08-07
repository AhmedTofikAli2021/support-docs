---
title: Add a new DOI.
excerpt: ''
api:
  file: rest-api.json
  operationId: post_dois
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
### Support Documentation

- [Creating DOIs with the REST API](doc:api-create-dois)

When creating a new DOI, you can either:

- specify the full DOI name (prefix/suffix) in the `"doi"` attribute
- [randomly generate the suffix](https://support.datacite.org/docs/api-create-dois#auto-generate-a-suffix-or-specify-a-suffix) by including `"prefix"` and omitting `"doi"`