---
title: >-
  How do I set up a query with the DataCite API to search the metadata catalogue
  for affiliation information?
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
You can use the DataCite [REST API](doc:api) to find DOIs which include specific affiliation metadata, for example, the name or nameIdentifier of your organization. Make sure to add the URL parameter &affiliation=true to your REST API requests to see additional affiliation information:

To search for the creator affiliation name you can set up a basic query like this (using " to enclose the name):

creators.affiliation.name:”University of Kentucky”

<https://api.datacite.org/dois?query=creators.affiliation.name:%22University%20of%20Kentucky%22*&affiliation=true>

You can also search for the records that include the nameIdentifier of your organization:

Use the query parameter to search any nameIdentifiers  (e.g. ROR, GRID, ISNI), in this example the ROR ID of the [University of Kentucky](https://ror.org/02k3smh20):

creators.affiliation.affiliationIdentifier:"<https://ror.org/02k3smh20"&affiliation=true> 

<https://api.datacite.org/dois?query=creators.affiliation.affiliationIdentifier:"https://ror.org/02k3smh20"&affiliation=true>

For ROR IDs, there is also the option to use a filter. This is faster and more efficient than using the query parameter. The filter will normalise the ROR ID, so you can use both of the different formats of the ROR ID below and get the same results:

affiliation-id=<https://ror.org/02k3smh20&affiliation=true>  
<https://api.datacite.org/dois?affiliation-id=https://ror.org/02k3smh20&affiliation=true>  

2. affiliation-id=02k3smh20&affiliation=true

<https://api.datacite.org/dois?affiliation-id=02k3smh20&affiliation=true>  

The filter will also search the contributors as well as the creators.

Learn more about [queries and filtering with the REST API](doc:api-queries).