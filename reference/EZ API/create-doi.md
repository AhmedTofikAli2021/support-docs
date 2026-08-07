---
title: Create DOI
excerpt: >-
  Will register a new DOI if the specified DOI doesn’t exist. Will not update an
  existing DOI, but will return an error.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
An identifier can be "created" by sending a PUT request to the identifier's URL. Here, identifier creation means establishing a record of the identifier (to be successful, no such record can already exist). Authentication is required, and the user must have permission to create DOIs using the DOI prefix. Users can view the prefixes available to them by visiting the DOI Fabrica service and navigating to the Prefixes tab.

A request body is optional; if present, it defines the identifier's starting metadata. There are no restrictions on what metadata elements can be submitted, but a convention has been established for naming metadata elements, and the service has built-in support for certain sets of metadata elements; see Metadata profiles. A few of the internal service metadata elements may be set; see Internal metadata.

```
⇒ PUT /id/doi:10.5072/test9999 HTTP/1.1
⇒ Host: ez.datacite.org
⇒ Content-Type: text/plain; charset=UTF-8
⇒ Content-Length: 30
⇒
⇒ _target: https://ez.datacite.org/
⇒ _status: reserved

⇐ HTTP/1.1 201 CREATED
⇐ Content-Type: text/plain; charset=UTF-8
⇐ Content-Length: 27
⇐
⇐ success: doi:/10.5072/test9999
```

The return is a status line. If a DOI was created successfully, the normalized form of the identifier is returned as shown above.