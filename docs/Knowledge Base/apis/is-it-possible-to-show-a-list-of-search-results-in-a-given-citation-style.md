---
title: Is it possible to show a list of search results in a given citation style?
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
This is possible with the REST API, but, at the moment, it is not a feature of DataCite Search. The REST API offers numerous options for searching, querying, and filtering. You can find more information on our webpage. 

If you would like to retrieve the results in a given citation style you need to include

“/text/x-bibliography” in the URL and &style= and &language= to your query as shown in the example below:

https://api.datacite.org/dois/ text/x-bibliography?query=%22german+internet+panel%22&data-center-id=gesis.gesis&style=apa&la­nguage=de