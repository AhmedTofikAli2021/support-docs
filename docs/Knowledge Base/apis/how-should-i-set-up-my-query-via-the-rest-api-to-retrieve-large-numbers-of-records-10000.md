---
title: How do I query the REST API to retrieve large numbers of records (>10000)?
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
When using the DataCite REST API to retrieve lists of DOIs, the API response generates subsets (pages), the default being 25 records per page,  which can be changed with the page size query parameter, up to 1000 records per page, and a maximum of 10000 records. 

For larger numbers of records, the query should be set up using the cursor-based pagination, the cursor is a location within a set of data, to enable it you can set it with &page[cursor]=1, then follow the URLs the API gives you in the ‘links’ part of the response. 

Example

```shell
curl https://api.test.datacite.org/providers/caltech/dois?page[size]=1000
```
Use the returned "links.next" URL in the response for the next page:

```json 

"links": {
  "self":"https://api.test.datacite.org/providers/caltech/dois?page[size]=1000",
  "next":"https://api.test.datacite.org/dois?page%5Bnumber%5D=2&page%5Bsize%5D=1000&provider-id=caltech"}
}
```

You can read more about retrieving lists of DOIs [here](https://support.datacite.org/docs/pagination).