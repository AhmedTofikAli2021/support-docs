---
title: Can I add/update DOI metadata with the REST API?
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
The REST API allows you to update DOI metadata either in full or partially via the attributes you specify. This is handled by the HTTP verb PUT and still ensures you follow a JSON:API document structure for your request payload.

Example:

```shell
curl -X PUT -H "Content-Type: application/vnd.api+json" --user YOUR_REPOSITORY_ID:YOUR_PASSWORD -d @my_doi_update.json https://api.test.datacite.org/dois/:id
```

You will need to define the JSON payload and replace my_doi_update.json wih the metadata file and :id with the DOI you wish to update, e.g. `https://api.test.datacite.org/dois/10.xxxx/xxxx`.

More information can be found here: [Updating DOIs with the REST API](doc:updating-metadata-with-the-rest-api).