---
title: How do I search for a DOI  in DataCite Commons?
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
[DataCite Commons](doc:datacite-commons) describes works, people, organizations, and repositories, as well as their connections. There are a few ways to search for a specific DOI. Start in the “Works” tab. The search interface in DataCite Commons is based on [Elasticsearch query string queries](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html#query-string-syntax).

If you know the DOI name, you can search with the identifier; for example, 10.7936/5bc9-0k33:

<https://commons.datacite.org/doi.org?query=10.7936%2F5bc9-0k33>

## Why is my DOI not found when I search in DataCite Commons?

DataCite's services use the Elasticsearch index. The kind of queries used in Elasticsearch (query_string_query) have the following reserved characters (which means they need to be treated differently in your query)

## Elasticsearch reserved characters:

```text
+ - = && || > < ! ( ) { } [ ] ^ " ~ * ? : \ / .
```

If any these characters is part of your query, you should **escape with a leading backslash.**

## Example 1: escape with a leading backslash

```text
10.2314/kxp\:1738669661
```

Run the [query in DataCite Commons](https://commons.datacite.org/doi.org?query=10.2314%2Fkxp%5C%3A1738669661).

However, don’t escape if the reserved character is an operator, e.g. the example below the colon is used to indicate a particular field.

## Example 2: don’t escape if the reserved character is an operator

```text
doi:10.2314/KXP\:1738669661
```

Run this [query in DataCite Commons](https://commons.datacite.org/doi.org?query=doi%3A10.2314%2FKXP%5C%3A1738669661).

Finally, remember that different search indexes will have different reserved characters.