---
title: Is there a rate limit for making requests against the DataCite APIs?
excerpt: ''
deprecated: false
hidden: false
link:
  new_tab: false
  url: https://support.datacite.org/docs/rate-limit
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Rate limits

There is a top level hard limit imposed by DataCite's firewall of 3000 requests in a 5 minute window, based on IP address. There is also an upper limit for requests that come via doi.org [Content Negotiation](https://support.datacite.org/docs/datacite-content-resolver) of 1000 requests in a 5 minute window.

When placing requests to the test system, please do not exceed 750 requests per 5 minute window. See the [Test Accounts Policy](doc:test-accounts-policy) for more information.

## Sustained request rates

For large-scale DOI registrations and updates (around 100,000+ [POST](https://support.datacite.org/reference/post_dois) or [PUT](https://support.datacite.org/reference/put_dois-id) requests to the `/dois` endpoint in a single day), we recommend 300-500 requests in a 5 minute window. 

If you are planning a large number of DOI registrations or updates, please contact [support@datacite.org](mailto:support@datacite.org) for assistance.

> 📘 
> 
> It is helpful to ensure that your script has incremental backoffs in the case of failure (i.e., the delay in retrying a failed request gets longer each time).