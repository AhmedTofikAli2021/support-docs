---
title: Can I use the REST API to obtain DOI registration statistics?
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
The REST API allows you to retrieve DOI registration statistics. 

Examples:

Use the following query to retrieve all the clients of e.g Texas Digital Library https://api.datacite.org/clients/totals?provider-id=tdl&state=findable 

The query can be extended to filter out the draft DOIs by specifying the "state" e.g. https://api.datacite.org/clients/totals?provider-id=tdl&state=findable

Read more about setting up queries with the REST API [here](https:// support.datacite.org/docs/ api-queries).