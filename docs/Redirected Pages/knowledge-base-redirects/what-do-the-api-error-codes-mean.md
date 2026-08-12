---
title: I received an error code from the DataCite API, what does it mean?
excerpt: ''
deprecated: false
hidden: true
link:
  new_tab: false
  url: https://support.datacite.org/docs/api-error-codes
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## 4xx Client Error

400 Bad Request - Check the docs again and try to reproduce.
401 Unauthorized - Check your password.
403 Forbidden - Check your password or validate that you are updating a DOI/prefix/repository you have permissions for.
404 Not Found - The resource is not found, be it fetching a DOI/Repository/Member details.
405 Method Not Allowed - The http method on the request made is not supported. Check documentation.
422 Unprocessable Entity - Check the contents of your request, the system understood but it was unable to process it. For a DOI update this might be invalid URL or metadata is invalid.


##5xx Server Error

500 Internal Server Error - Try to reproduce and report steps that caused it.
502 Bad Gateway  - Most likely a temporary issue, try again.
503 Service Unavailable - Check our status page [status.datacite.org](https://status.datacite.org).
504 Gateway Timeout - Check our status page/releases [status.datacite.org](https://status.datacite.org).
[block:parameters]
{
  "data": {
    "h-0": "Error code",
    "h-1": "Message",
    "h-2": "Possible Solution",
    "h-3": "Example",
    "0-0": "400",
    "1-0": "401",
    "2-0": "403",
    "4-0": "405",
    "3-0": "404",
    "5-0": "422",
    "7-0": "502",
    "6-0": "500",
    "8-0": "503",
    "9-0": "504",
    "0-2": "Bad Request - Check the docs again and try to reproduce.",
    "1-2": "Unauthorized - Check your password.",
    "2-2": "Forbidden - Check your password or validate that you are updating a DOI/prefix/repository you have permissions for.",
    "3-2": "Not Found - The resource is not found e.g. it fetching a DOI/Repository/Member details.",
    "4-2": "Method Not Allowed - The http method on the request made is not supported. Check documentation.",
    "5-2": "Unprocessable Entity - Check the contents of your request, the system understood but it was unable to process it. For a DOI update this might be invalid URL or metadata is invalid.",
    "6-2": "Internal Server Error - Try to reproduce and report steps that caused it.",
    "7-2": "Bad Gateway  - Most likely a temporary issue, try again",
    "8-2": "Service Unavailable - Check our status page [status.datacite.org](https://status.datacite.org).",
    "9-2": "Gateway Timeout - Check our status page/releases [status.datacite.org](https://status.datacite.org).",
    "1-1": "Bad credentials.",
    "2-1": "You are not authorized to access this resource.",
    "3-1": "The resource you are looking for doesn't exist."
  },
  "cols": 4,
  "rows": 10
}
[/block]