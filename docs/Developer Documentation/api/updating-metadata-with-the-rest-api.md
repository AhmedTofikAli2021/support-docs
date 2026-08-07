---
title: Updating Metadata with the Rest API
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
With the REST API you can update a DOI either in full or partially via the attributes you specify. This is handled by the HTTP verb PUT and still ensuring you follow a JSON:API document structure for your request payload.

Below is an example of how to partially update metadata using the REST API, in this case the relatedIdentifier.

First we define our JSON Payload:

```json
{
    "data": {
        "attributes": {
            "relatedIdentifiers": [
                {
                    "relatedIdentifier": "https://doi.org/10.xxxx/xxxxx",
                    "relatedIdentifierType": "DOI",
                    "relationType": "References",
                    "resourceTypeGeneral": "Dataset"
                }
            ]
        }
    }
}
```

To submit this using curl, we'll use the following command, first:
* Replacing `YOUR_REPOSITORY_ID:YOUR_PASSWORD` with your DataCite repository credentials.
* Replacing `my_doi_update.json` with the file you've saved the metadata in.
* Replacing :id with the DOI you wish to update e.g.  https://api.test.datacite.org/dois/10.5072/1234

```shell
# PUT /dois/:id

$ curl -X PUT -H "Content-Type: application/vnd.api+json" --user YOUR_REPOSITORY_ID:YOUR_PASSWORD -d @my_doi_update.json https://api.test.datacite.org/dois/:id
```

More information about updating DOI metadata via the REST API can be found in the [reference API](https://support.datacite.org/reference/dois-2#put_dois-id).