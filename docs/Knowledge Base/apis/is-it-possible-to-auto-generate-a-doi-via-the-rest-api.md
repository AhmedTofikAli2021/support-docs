---
title: Is it possible to auto-generate a DOI via the REST API?
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
To do this you need to include your prefix in the body of the payload without a DOI and send a POST request to https:// api.test.datacite.org/dois endpoint (or production). The below example shows the body of the payload required to autogenerate a suffix for a draft state metadata:

```
{
  "data": {
    "type": "dois",
    "attributes": {
      "prefix": "10.5438",
      "creators": [{
        "name": "example"
      }],
      "titles": [{
        "title": "This is an example"
      }],
      "publisher": "DataCite",
      "publicationYear": 2019,
      "types": {
        "resourceTypeGeneral"­: "Text"
      },
      "url": "https://example.org"
    }
  }
}
```

More information [here](https://support.datacite.org/docs/api-create-dois).