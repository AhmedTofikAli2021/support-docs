---
title: What characters should I use in the suffix of my DOI?
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
The easiest and recommended option is to use a randomly generated suffix. The auto-generated DOI strings use a-z, 0-9. They avoid i, l, o as they are easily mixed up with 0, 1. We group the suffix into blocks of 4, separated by a hyphen. You can generate a random suffix in both Fabrica and the API and your DOI will look something like this **10.5438/9te8-5h68**.

If you choose not to use this option then remember:

1. The DOI suffix must be unique within each prefix. The optimum length of a DOI suffix is 6–10 characters. 

2. Only use a-z (lowercase), 0-9 and - in a DOI suffix. Other characters might have special meaning or will be escaped.

3. Avoid human-readable information in a DOI suffix because any meaning may change over time. Further advice on DOI syntax:


DataCite [blog post](https://blog.datacite.org/cool-dois/)
Crossref [blog post](https://www.crossref.org/blog/dois-and-matching-regular-expressions/)
Reserved characters in [Elasticsearch](doc:why-is-my-doi-name-not-retrieved-with-a-search-in-fabrica)
Technical implementation for [generating random DOI strings](https://github.com/datacite/base32-url)
[block:callout]
{
  "type": "info",
  "title": "Auto-generate a suffix",
  "body": "**The auto-generate DOI name functionality means the DOI suffix is generated automatically and will look something like this 10.15138/33bv-s284.**"
}
[/block]