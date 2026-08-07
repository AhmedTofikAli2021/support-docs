---
title: Retrieving a random sample of DOIs
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
Being able to select random results is useful for both testing and sampling. You can use the `random` parameter to retrieve a set of random results. For example, the following would select 10 random works from among all DataCite records:

```shell
$ curl https://api.datacite.org/dois?random=true&page[size]=10
```

The random parameter can be combined with any kind of query, for example:

```shell
$ curl https://api.datacite.org/dois?query=climate%20change&random=true&page[size]=10
```

Note that when you use the random parameter, the `page[number]` and `sort` parameters are ignored. The `page[size]` parameter can be any number between 1 and 1000. A `page[size]` \< 100 is recommended for performance.

### Sample Group

Samples can be grouped:

```shell
$ curl https://api.datacite.org/dois?sample=10&sample-group=client&page[size]=20
```

This query will retrieve 10 samples per client, for 20 clients. Allowed parameters for `sample-group` are `client`, `provider` and `resource-type`.