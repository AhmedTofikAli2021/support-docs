---
title: Which API should I use?
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
DataCite currently maintains several APIs. 
[block:api-header]
{
  "title": "REST API"
}
[/block]
The DataCite REST API is available for use by anyone. It allows you to retrieve metadata for DOIs. It does NOT allow you to create, update, or delete DOIs. 

See the [DataCite REST API Guide](doc:api) 
[block:api-header]
{
  "title": "MDS API"
}
[/block]
The DataCite MDS API is available for use only by DataCite Members. It allows members to create, update, and (in the case of Draft DOIs) delete DOIs. 

See the [DataCite MDS API Guide](doc:mds-api-guide) 
[block:api-header]
{
  "title": "EZ API"
}
[/block]
The DataCite EZ API is available for use only by DataCite Members. It was specially designed to mimic some of the capabilities of the API provided by EZID, in order to better support Members transitioning from EZID to DataCite. It allows members to create, update, and (in the case of Draft DOIs) delete DOIs. 

See the [DataCite EZ API Guide](doc:datacite-ez-api-guide) 
[block:api-header]
{
  "title": "EventData API"
}
[/block]
The DataCite EventData API is available for use by anyone. It enables you to query for "events" around DOIs, such as citations or updated relations with other persistent identifiers.

See the [EventData API Guide](doc:eventdata-apis) 
[block:api-header]
{
  "title": "OAI-PMH API"
}
[/block]
The DataCite OAI-PMH API is available for use by anyone using an OAI-PMH compliant harvester or an application that issues OAI-PMH requests. It allows you to retrieve metadata about DOIs in an OAI-PMH compliant way. It does NOT allow you to create, update, or delete DOIs. 

The OAI-PMH API is intended primarily for bulk harvesting. Most metadata requests will be better served by the REST API. We recommend using the REST API unless you have a specific need for OAI-PMH compliant requests. 

See the [DataCite OAI-PMH Guide](doc:datacite-oai-pmh)