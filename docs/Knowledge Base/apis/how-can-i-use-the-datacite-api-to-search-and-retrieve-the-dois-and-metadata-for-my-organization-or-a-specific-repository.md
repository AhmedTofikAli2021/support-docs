---
title: >-
  How can I use the DataCite API to search and   retrieve the DOIs and metadata
  for my organization or a specific repository?
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
The [DataCite REST API](doc:api) is a good solution for quickly and easily retrieving lists of DOIs and the associated metadata. To search for a specific organization or repository, you will need to know the ID of the account. You can then apply [filter](doc:api-queries#applying-filter-parameters) parameters as follows (you can use a tool like '[Postman](https://www.postman.com/)', curl from the command line, or just your browser to run these queries):

For example:  
Member ID: cern  
Parameter: provider-id  
<https://api.datacite.org/dois?provider-id=cern>

Repository ID: cern.zenodo  
Parameter: client-id  
<https://api.datacite.org/dois?client-id=cern.zenodo&page[cursor]=1&page[size]=1000>

Notice that the second query includes cursor-based pagination to page through a results set that exceeds 10,000 results.

You can also search DOI metadata using the 'query' parameter. A basic query to search for DOI metadata records with a specific publication year looks like this:

<https://api.datacite.org/dois?query=publicationYear:2024> 

You can apply a filter parameter and combine it with the query parameter as follows:

<https://api.datacite.org/dois?client-id=cern.zenodo&query=publicationYear:2024>

There is lots of information in the recently updated guide about [queries and filtering](doc:api-queries#applying-filter-parameters)!