---
title: How can I detect removed records, including retractions, with the REST API?
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
When a DOI is [created by mistake or content is retracted](doc:doi-persistence#what-if-a-doi-is-created-by-mistake-or-the-content-is-retracted), this is represented by a change in the [DOI state](doc:doi-states) from Findable to Registered. 

When harvesting metadata records from DataCite using the [Public API](https://support.datacite.org/docs/api#public-api-no-authentication) (no authentication), only DOIs in Findable state are available. If a DOI has changed state from Findable to Registered, it will no longer be part of the response from the Public API.

To detect state changes, we recommend using the [Member API](https://support.datacite.org/docs/api#member-api-requires-authentication) by authenticating with your Member, Consortium Organization, or Repository account credentials. Harvesters can then use the `state` filter to retrieve DOIs in `registered` state. 

For example, the following authenticated request retrieves all DOIs in Registered state (`state=registered`, sorted by most to least recently updated (`sort=-updated`):

```curl
curl -X GET -H "Content-Type: application/vnd.api+json" --user YOUR_ACCOUNT_ID:YOUR_PASSWORD https://api.datacite.org/dois?disable-facets=true&sort=-updated&publisher=true&affiliation=true&state=registered
```