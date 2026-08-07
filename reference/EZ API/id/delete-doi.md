---
title: Delete DOI
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
A reserved DOI can be deleted by sending a DELETE request to the identifier's URL. We emphasize that only reserved identifiers may be deleted; see Identifier status. Authentication is required; only the identifier's owner and certain other users may delete the identifier (see Ownership model).
[block:code]
{
  "codes": [
    {
      "code": "⇒ DELETE /id/doi:10.5438/test9999 HTTP/1.1\n⇒ Host: ez.datacite.org\n\n⇐ HTTP/1.1 200 OK\n⇐ Content-Type: text/plain; charset=UTF-8\n⇐ Content-Length: 29\n⇐\n⇐ success: doi:/10.5438/test9999",
      "language": "text"
    }
  ]
}
[/block]
The return is a status line. Assuming success (see [Error handling](reference#section-error-handling)), the remainder of the status line echoes the canonical form of the identifier just deleted.