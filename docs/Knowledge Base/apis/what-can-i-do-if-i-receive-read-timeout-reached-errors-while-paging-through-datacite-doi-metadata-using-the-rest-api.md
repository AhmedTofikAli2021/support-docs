---
title: >-
  What can I do if I receive "read timeout reached" errors while paging through
  DataCite DOI metadata using the REST API?
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
Errors like the following may be returned when paginating through DataCite DOI metadata using the `/dois` REST API endpoint:

```json
{"status":400,"title":"read timeout reached"}
```

These errors often occur when retrieving a page containing unusually large DOI records. If you are using a `page[size]` URL parameter above the default 25, reduce the `page[size]` to 25 to retrieve the next page. For example, the following URL:

<https://api.datacite.org/dois?disable-facets=true&page[cursor]=MTQ3MDkwMjc2NzAwMCwxMC4xNTQ2OC9kbC56MjZhanU&page[size]=1000>

Would become: 

<https://api.datacite.org/dois?disable-facets=true&page[cursor]=MTQ3MDkwMjc2NzAwMCwxMC4xNTQ2OC9kbC56MjZhanU&page[size]=25>