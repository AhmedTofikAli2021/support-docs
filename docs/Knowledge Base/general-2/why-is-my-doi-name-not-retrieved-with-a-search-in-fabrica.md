---
title: Why is my DOI name not retrieved with a search in DataCite Commons?
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
DataCite's services use the Elasticsearch index. The kind of queries used in Elasticsearch (query_string_query) have the following reserved characters (which means they need to be treated differently in your query)

## Elasticsearch reserved characters: 
[block:code]
{
  "codes": [
    {
      "code": "+ - = && || > < ! ( ) { } [ ] ^ \" ~ * ? : \\ / . ",
      "language": "text"
    }
  ]
}
[/block]
If any these characters is part of your query, you should **escape with a leading backslash.**

## Example 1: escape with a leading backslash
[block:code]
{
  "codes": [
    {
      "code": "10.2314/kxp\\:1738669661",
      "language": "text"
    }
  ]
}
[/block]
Run the [query in DataCite Commons](https://commons.datacite.org/doi.org?query=10.2314%2Fkxp%5C%3A1738669661).

However, don’t escape if the reserved character is an operator, e.g. the example below the colon is used to indicate a particular field.

## Example 2: don’t escape if the reserved character is an operator
[block:code]
{
  "codes": [
    {
      "code": "doi:10.2314/KXP\\:1738669661",
      "language": "text"
    }
  ]
}
[/block]
Run this [query in DataCite Commons](https://commons.datacite.org/doi.org?query=doi%3A10.2314%2FKXP%5C%3A1738669661).

Finally, remember that different search indexes will have different reserved characters.