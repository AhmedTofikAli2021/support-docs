---
title: Mint DOI
excerpt: >-
  Will register a new DOI, but instead of supplying a complete identifier, the
  client specifies only a partial namespace (shoulder).
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Minting an identifier is the same as creating an identifier, but instead of supplying a complete identifier, the client specifies only a namespace (or "shoulder") that forms the first part of the identifier's suffix, and the service generates an opaque, random string for the full identifier suffix. An identifier can be minted by sending a POST request to the URL https://ez.datacite.org/shoulder/myshoulder where `myshoulder` is the desired namespace. 

```
⇒ POST /shoulder/doi:10.5072 HTTP/1.1
⇒ Host: ez.datacite.org
⇒ Content-Type: text/plain; charset=UTF-8
⇒ Content-Length: 30
⇒
⇒ _target: https://ez.datacite.org/
⇒ _status: reserved

⇐ HTTP/1.1 201 CREATED
⇐ Content-Type: text/plain; charset=UTF-8
⇐ Content-Length: 29
⇐
⇐ success: doi:10.5072/testc9cz3dh0
```

Aside from specifying a complete identifier versus specifying a shoulder only, the create and mint operations operate identically. Authentication is required to mint an identifier; namespace permission is required, and prefixes can be viewed in the DOI Fabrica service under the Prefixes tab. The request and response bodies are identical.

The service automatically embeds the newly-minted identifier in certain types of uploaded metadata. See Metadata profiles for when this is performed.