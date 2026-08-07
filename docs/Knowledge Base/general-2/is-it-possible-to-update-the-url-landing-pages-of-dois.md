---
title: Is it possible to update the URL landing pages of DOIs?
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
[DOI landing pages ](doc:landing-pages)(and DOI metadata) can be updated at any time after the initial registration. DOIs always resolve to a landing page which provides a way to access the resource being shared with a DOI, for example, a link to download a dataset. It also provides other information about the resource. It’s important to make sure that your landing pages are maintained and do not generate errors.

Landing pages can be updated using any of the normal methods for creating and updating DOIs, including [DataCite Fabrica](doc:fabrica-doi-form), the [DataCite REST API](doc:api) or an integration from a [Registered Service Provider](doc:service-provider-software-integrations).

To update only the URLs of the DOIs in a batch process with the DataCite REST API, you will need a script to iterate over the list of DOIs and execute a [PUT call](https://support.datacite.org/reference/put_dois-id) over each item.

The metadata you will need to include can be limited to the new URL address, e.g:

```text
{"data": {  
0.7282/t37zhk-y459",  
"dois",  
tes": {  
<https://example.org">  
```

For any DataCite Member switching repository platforms or CRIS systems, our recommendation is to update the landing pages of any existing DOIs to point to the same resource on the new platform. This means you don’t need to create duplicate DOIs when you move your resources.

[Updating DOIs with the REST API](doc:updating-metadata-with-the-rest-api)
