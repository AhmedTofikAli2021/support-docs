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
[DataCite Commons](doc:datacite-commons) describes works, people, organizations, and repositories, as well as their connections. There are a few ways to search for a specific DOI. Start in the “Works” tab. The search interface in DataCite Commons is based on [OpenSearch query string queries](https://opensearch.org/docs/latest/query-dsl/full-text/query-string/).

If you know the DOI name, you can search with the identifier; for example, 10.7936/5bc9-0k33:

<https://commons.datacite.org/doi.org?query=10.7936%2F5bc9-0k33>

## Why is my DOI not found when I search in DataCite Commons?

DataCite Commons queries use the [the OpenSearch query string query syntax](https://docs.opensearch.org/docs/latest/query-dsl/full-text/query-string/). These kinds of queries have the following reserved characters, which means they need to be treated differently in your query:

### OpenSearch reserved characters:

```text
+ - = && || > < ! ( ) { } [ ] ^ " ~ * ? : \ / .
```

If any these characters is part of your DOI name search, you should **add quotation marks around the DOI name** or **escape the reserved characters with a leading backslash**:

### Option 1: Add quotation marks around the DOI name

Search with the DOI name enclosed by quotation marks to search for the exact DOI name string. OpenSearch reserved characters will be treated as part of the search string rather than as query operators.

```
"10.21938/W:hWbPah3wBabuqewQULTA"
```

Run this [query in DataCite Commons](https://commons.datacite.org/?query=%2210.21938%2FW%3AhWbPah3wBabuqewQULTA%22)

### Option 2: Escape the reserved characters with a leading backslash

Escape OpenSearch reserved characters with a leading backslash to make sure they are not interpreted as query operators. In this case, quotations should not be used. 

```text
10.2314/kxp\:1738669661
```

Run the [query in DataCite Commons](https://commons.datacite.org/doi.org?query=10.2314%2Fkxp%5C%3A1738669661).

> 📘 
> 
> Don't escape reserved characters when they are intended as an operator in your query. For example, in the query below, the first colon is an operator used to indicate a particular field and is not escaped while the second colon is in the DOI name and must be escaped:
> 
> ```
> doi:10.2314/KXP\:1738669661
> ```
> 
> Run this [query in DataCite Commons](https://commons.datacite.org/doi.org?query=doi%3A10.2314%2FKXP%5C%3A1738669661).