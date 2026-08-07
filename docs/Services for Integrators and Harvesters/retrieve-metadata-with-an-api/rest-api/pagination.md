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
## What is pagination?

Pagination is a mechanism to split API query results into discrete subsections, or pages. This offers an efficient way to handle moving through a large result set of data.

The default page size is 25 records. If the list of records in a response is longer than 25, a subset (page) of the whole response is returned. Page size can be changed using the `page[size]` query parameter (allowed values in range 0-1000).

There are two methods to retrieve multi-page responses: page number-based pagination and cursor-based pagination.

### Method 1: Page number (up to 10,000 records)

Paginate using the `page[number]` query parameter, starting with 1. This is the default if no `page[number]` or `page[cursor]` is specified. **You can retrieve up to 10,000 records (400 pages with the default of 25 records per page) using this method**. The sort order can be specified using the sort query parameter.

This example query retrieves the first 1,000 records:

```shell
curl "https://api.datacite.org/dois?provider-id=caltech&page[size]=1000"
```

To retrieve subsequent records, increment the page number using the page[number] parameter:

```shell
curl "https://api.datacite.org/dois?provider-id=caltech&page[size]=1000&page[number]=2"
```

The query for the next page is also provided in the "links.next" URL in the response:

```json

"links": {
  "self":"https://api.datacite.org/dois?provider-id=caltech&page[size]=1000",
  "next":"https://api.datacite.org/dois?page%5Bnumber%5D=2&page%5Bsize%5D=1000&provider-id=caltech"
}
```

The "meta" object in the response includes:

```json

"meta": {
  "total":36409,
  "totalPages":10,
  "page":1
}
```

Only the first 10,000 records (10 x 1000 per page) can be retrieved.

### Method 2: Cursor

Cursor-based pagination has no limitations on the number of records that can be retrieved.

Paginate using the `page[cursor]` query parameter. Use `page[cursor]=1` to retrieve the first page.

This example query retrieves the first 1,000 records (the sort order is always created ascending): 

```shell
curl "https://api.datacite.org/dois?provider-id=caltech&page[cursor]=1&page[size]=1000"
```

To retrieve subsequent records, use the returned "links.next" URL in the response for the next page:

```json

"links": {
  "self":"https://api.datacite.org/dois?provider-id=caltech&page[cursor]=1&page[size]=1000",
  "next":"https://api.datacite.org/dois?page%5Bcursor%5D=MTQ5NjQzNDE5MDAwMCwxMC43OTA3L3o5dngwZGt2&page%5Bsize%5D=1000&provider-id=caltech"
}
```

This URL includes a token that must be used to retrieve subsequent pages. Do not increment the `page[cursor]` parameter manually.

The "meta" object in the response includes:

```json

"meta": {
  "total": 36409,
  "totalPages": 37
}
```

All records (37 x 1000 per page) can be retrieved.