---
title: Can I see more detailed affiliation information in the REST API?
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
DataCite added support for affiliation identifiers in Metadata Schema 4.3, released August 2019. This information is not visible in the JSON REST API to avoid breaking changes that could cause problems with existing API integrations. Please add the query parameter `&affiliation=true` to your REST API queries to see additional affiliation information such as the affiliation identifier.