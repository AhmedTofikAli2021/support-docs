---
title: >-
  Can I use the same credentials to register a DOI with both the API and
  Fabrica?
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
In DataCite systems, if you want to create or update a DOI and metadata you need to use your repository account. The same repository account credentials and prefix will be used to register DOIs with both the [DataCite Fabrica](doc:doi-fabrica) web interface and the [API](doc:api).

The repository account ID is a string of characters separated by a dot, for example: XVDU.USIMS. The first part of the repository ID corresponds to the ID of the parent organization (i.e., the related Direct Member or Consortium Organization at the time the repository was created) and the second part is unique to the repository account. Each repository has one prefix. Remember that test and production accounts are different.