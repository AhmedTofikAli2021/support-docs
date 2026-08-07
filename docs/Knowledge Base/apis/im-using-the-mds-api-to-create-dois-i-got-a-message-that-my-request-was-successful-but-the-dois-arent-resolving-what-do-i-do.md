---
title: >-
  My request to create a DOI with MDS API was successful, but the DOIs aren’t
  resolving. What do I do?
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
Remember that it takes 2 calls to the MDS API to successfully create a resolvable DOI. One call submits metadata for the DOI, while the other call submits the URL and triggers the DOI registration in the handle server. 

If your application is only making one call, you’re missing a piece of the process. See the MDS API documentation [here](https://support.datacite.org/docs/mds-api-guide) . 

If you are successfully making 2 calls to the MDS API, then something else is wrong.