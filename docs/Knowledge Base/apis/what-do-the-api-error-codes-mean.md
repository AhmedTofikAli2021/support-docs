---
title: I received an error code from the DataCite API, what does it mean?
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
## 4xx Client Error

400 Bad Request - Check the docs again and try to reproduce
401 Unauthorized - Check your password
403 Forbidden - Check your password or validate that you are updating a DOI/prefix/repository you have permissions for
404 Not Found - The resource is not found, be it fetching a DOI/Repository/Member details
405 Method Not Allowed - The http method on the request made is not supported. Check documentation.
422 Unprocessable Entity - Check the contents of your request, the system understood but it was unable to process it. For a DOI update this might be invalid URL or metadata is invalid.


##5xx Server Error

500 Internal Server Error - Try to reproduce and report steps that caused it
502 Bad Gateway  - Most likely a temporary issue, try again
503 Service Unavailable - Check our status page [status.datacite.org](https://status.datacite.org)
504 Gateway Timeout - Check our status page/releases [status.datacite.org](https://status.datacite.org)