---
title: Modify DOI
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
An identifier's metadata can be modified by sending a POST request to the identifier's URL. Authentication is required; only the identifier's owner and certain other users may modify the identifier (see Ownership model below).

Metadata elements are operated on individually. If the identifier already has a value for a metadata element included in the request body, the value is overwritten, otherwise, the element and its value are added. Only a few of the reserved metadata elements may be modified; see Internal metadata.

```
⇒ POST /id/doi:10.5438/test9999 HTTP/1.1
⇒ Host: ez.datacite.org
⇒ Content-Type: text/plain; charset=UTF-8
⇒ Content-Length: 30
⇒
⇒ _target: https://ez.datacite.org/

⇐ HTTP/1.1 200 OK
⇐ Content-Type: text/plain; charset=UTF-8
⇐ Content-Length: 29
⇐
⇐ success: doi:10.5438/test9999
```

The return is a status line. Assuming success (see [Error handling](reference#section-error-handling)), the remainder of the status line echoes the canonical form of the identifier in question.

To delete a metadata element, set its value to an empty string.