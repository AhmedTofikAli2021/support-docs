---
title: >-
  How do I update my DOIs to metadata schema version 4 with the DataCite REST
  API?
excerpt: ''
deprecated: false
hidden: true
link:
  new_tab: false
  url: https://support.datacite.org/docs/updating-from-schema-3-to-schema-4
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
To update DOIs from an older version to schema 4 with the REST API you should specify an explicit update to version 4 for your DOIs using the attribute field "schemaVersion".

Example:
[block:code]
{
  "codes": [
    {
      "code": "{\n\n  \"data\": {\n\n   \"id\": \"10.0138/1f84-ta02\",\n\n   \"type\": \"dois\",\n\n   \"attributes\": {\n\n    \"doi\": \"10.0138/1f84-ta02\",\n\n    \"schemaVersion\": \"http://datacite.org/schema/kernel-4\"\n\n  }\n\n }\n\n}",
      "language": "json"
    }
  ]
}
[/block]

Remember that the existing DOI metadata, and any updates, must be compatible with schema 4 as outlined in the [DataCite metadata schema documentation](schema.datacite.org).