---
title: Is there a rate limit for making requests against the DataCite APIs?
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
The current status is that we do not impose per account rate limits. However, there is a top level hard limit imposed by DataCite's firewall which is based on IP address, and this is around 3000 requests in a 5 minute window. There is also an upper limit for requests that come via doi.org Content Negotiation of 1000 requests in a 5 minute window.

More information about the [DataCite API](doc:api) and [Content Negotiation](doc:datacite-content-resolver)