---
title: Get Metadata for DOI
excerpt: This request returns metadata for a given DOI.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Metadata can be retrieved for any existing identifier; no authentication is required. Simply issue a GET request to the identifier's URL.

```
⇒ GET /id/doi:10.5438/test9999 HTTP/1.1
⇒ Host: ez.datacite.org

⇐ HTTP/1.1 200 OK
⇐ Content-Type: text/plain; charset=UTF-8
⇐ Content-Length: 208
⇐
⇐ success: doi:10.5438/test9999
⇐ _created: 1300812337
⇐ _updated: 1300913550
⇐ _target: http://www.gutenberg.org/ebooks/7178
⇐ _profile: datacite
```

The first line of the response body is a status line. Assuming success, the remainder of the status line echoes the canonical form of the requested identifier.

The remaining lines are metadata element name/value pairs serialized per ANVL rules; see Request & response bodies above. The order of elements is undefined. Element names beginning with an underscore ("_", U+005F) are reserved for use by the system; their meanings are described in Internal metadata below. Some elements may be drawn from citation metadata standards; see Metadata profiles.