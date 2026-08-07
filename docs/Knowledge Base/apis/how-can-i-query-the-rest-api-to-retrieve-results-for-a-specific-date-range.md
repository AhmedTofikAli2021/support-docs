---
title: >-
  How can I query the REST API to retrieve results for a specific date or date
  range?
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
### Filter using date parameters

There are three date parameters available in the REST API: `registered`,`created`, `published`.  Using these parameters, you can filter for DOIs from a specific year. For example:

```shell
curl "https://api.datacite.org/dois?registered=2025"
```

```shell
curl "https://api.datacite.org/dois?published=2020"
```

You can include up to 10 years, separated by a comma. For example:

```shell
curl "https://api.datacite.org/dois?created=2021,2022,2023'
```

For more information about how these dates are defined, see [What is the difference between the "created", "registered" and "published" date in the DataCite REST API?](doc:what-is-the-difference-between-the-created-and-registered-date-in-the-datacite-rest-api) 

### Search dates in the query string

For more specific date ranges, you can build a query string within the `query` parameter to search the date fields `registered`, `created`, and `updated`. 

For example, to search DOIs updated from 2023-01-01 to 2023-03-31, include `updated:[2023-01-01 TO 2023-03-31]` in the query:

```shell
curl "https://api.datacite.org/dois?query=updated:[2023-01-01%20TO%202023-03-31]"
```