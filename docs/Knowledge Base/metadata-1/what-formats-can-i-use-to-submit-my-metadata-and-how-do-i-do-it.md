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
You can send DOI metadata to DataCite in different formats including: DataCite XML, schema.org in JSON-LD, Crossref Unixref, Citeproc JSON, RIS, and BibTeX. If you use Fabrica to create DOIs, you can upload your metadata in any of the above formats using the [File Upload](doc:fabrica-create-doi-file-upload) functionality. If you use the REST API to create DOIs, as an alternative to providing metadata attributes directly in JSON, you can also provide your metadata in any of the above formats by following these steps:

1. Base64 encode the metadata.
2. Include the base64-encoded value in the "xml" attribute of the payload you send to the REST API. Here is an example payload (the full base64 encoded metadata is not shown):

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

You can also base64 encode a URL that points to a webpage with embedded schema.org metadata or a DOI from Crossref. For example, for URL <https://doi.org/10.7554/elife.01567>, the REST API request would look like the following:

```json
{
    "data": {
        "type": "dois",
        "attributes": {
            "prefix": "10.5438",
            "event":"publish",
            "xml":"aHR0cHM6Ly9kb2kub3JnLzEwLjc1NTQvZWxpZmUuMDE1Njc="
        }
    }
}
```

More information can be found here:

- [Creating a DOI with the REST API](doc:api-create-dois)

- [DataCite Metadata Schema](https://schema.datacite.org)

- [Create a DOI using the File Upload](fabrica-create-doi-file-upload)