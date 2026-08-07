---
title: What formats can I use to submit my metadata and how do I do it?
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
You can send DOI metadata to DataCite in different formats including:DataCite XML, schema.org in JSON-LD, Crossref Unixref, Citeproc JSON, RIS, BibTeX. If you use DOI Fabrica to create DOIs, you can upload your metadata in any of the above formats using the [file upload](doc:fabrica-create-doi-file-upload) functionality. If you use the REST API to create DOIs, as an alternative to providing metadata attributes directly in JSON, you can also provide your metadata in any of the above formats by following these steps:

1.) Base64 encode your metadata
2.). Include this in the XML attribute in the payload you send to the REST API. Top tip: You can also base64 encode a URL that points to a webpage with embedded schema.org, or a DOI from Crossref, e.g. https://doi.org/10.7554/ elife.01567. Here is an example payload (the full base64 encoded metadata is not shown):

```json
{
 "data": {
   "id": "10.5438/0012",
   "type": "dois",
   "attributes": {
     "event": "publish",
     "doi": "10.5438/0012",
     "url": "https://schema.datacite.org/ meta/kernel-4.0/index.html",
     "xml": "PD94bWwgdmVyc2lvbj0iMS4wIiBlb­mNvZGluZz0iVVRGLTgiPz4NCjxyZX­NvdXJjZSB4bWxucz0iaHR0…….."
 }
}
```

More information can be found here:

¨ [Creating a DOI with the REST API](doc:api-create-dois)

¨ [DataCite Metadata Schema](https://schema.datacite.org)

¨ [Create a DOI using the File Upload](fabrica-create-doi-file-upload)