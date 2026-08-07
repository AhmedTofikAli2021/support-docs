---
title: Pagination
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
## What is Pagination?

Pagination describes a process whereby API query results are divided up into discrete subsections. This offers an efficient way to handle moving through a large result set of data.
 
If the list of records in a response is longer than 25 DOIs, a subset (page) of the whole response is returned. By default up to 25 records are returned at a time, this can be changed using the ```page[size]``` query parameter (allowed values in range 0-1000).

Links to the current and next page are provided in a ```links``` object in the API response. Use these links to retrieve all pages by one of two methods: page number-based pagination and cursor-based pagination.

### Page number

Paginate using the ```page[number]``` query parameter, starting with 1. This is the default if no ```page[number]``` or ```page[cursor]``` is specified. You can retrieve up to 10,000 records (400 pages with the default of 25 records per page) using this method. The sort order can be specified using the sort query parameter.

```shell
curl https://api.test.datacite.org/providers/caltech/dois?page[size]=1000
```
Then use the returned "links.next" URL in the response for the next page:

```json 

"links": {
  "self":"https://api.test.datacite.org/providers/caltech/dois?page[size]=1000",
  "next":"https://api.test.datacite.org/dois?page%5Bnumber%5D=2&page%5Bsize%5D=1000&provider-id=caltech"}
}
```


The "meta" object in the response includes:
```json

"meta": {
  "total":16322,
  "totalPages":10,
  "page":1
}

```

Only the first 10,000 records (10 x 1000 per page) can be retrieved.

###Cursor

Cursor-based pagination has no limitations on the number of records that can be retrieved. Paginate using the ```page[cursor]``` query parameter. Use ```page[cursor]=1``` to retrieve the first page, and then use the URL for the next page from the links object in the API response to retrieve the remaining pages. The sort order is always created ascending.

Retrieve all the metadata for a provider e.g caltech

```shell
curl https://api.test.datacite.org/providers/caltech/dois?page[cursor]=1&page[size]=1000
```

Then use the returned "links.next" URL in the response for the next page:


```json

"links": {
  "self":"https://api.test.datacite.org/providers/caltech/dois?page[cursor]=1&page[size]=1000",
  "next":"https://api.test.datacite.org/dois?page%5Bcursor%5D=1542256252000&page%5Bsize%5D=1000&provider-id=caltech"}
}
```

The "meta" object in the response includes:

```json

"meta": {
  "total":16322,
  "totalPages":17,
  "page":1
}
```

All records (17 x 1000 per page) can be retrieved.