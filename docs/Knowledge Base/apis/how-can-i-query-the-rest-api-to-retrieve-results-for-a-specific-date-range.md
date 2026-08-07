---
title: How can I query the REST API to retrieve results for a specific date range?
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
You can run a query for a specific date range, using, for example, the date the DOI was “created” or the date it was “updated”. Below is an example of a query for a specific date range including pagination: 

```json
https://api.datacite.org/dois?query=created:[2020-01-01%20TO%202020-01-05]&page[number]=1&page[size]=1000
```

If your results set is very large, you will need to use the cursor based pagination, more information [here](doc:pagination#section-cursor).