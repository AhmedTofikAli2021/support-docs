---
title: How do I update the DataCite XML metadata to a newer schema version?
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
If some of your DOIs are using schema version 2 or 3 you should update them. If you are working with XML metadata you can update the schema version header as shown below:
[block:code]
{
  "codes": [
    {
      "code": "<resource xmlns:xsi=\"http://www.w3.org/2001/XMLSchemainstance\"xmlns=\"http://datacite.org/schema/kernel4\"xsi:schemaLocation=\"http://datate.org/schema/kernel-4 http://schema.datacite.org/meta/kernel-4.4/metadata.xsd\">",
      "language": "text"
    }
  ]
}
[/block]
Breaking changes can occur in major schema version updates, e.g. from version 3 to version 4, so this upgrade needs some time to investigate and test before proceeding. Minor schema upgrades, e.g. from 4.3 to 4.4, will never have breaking changes, and are always safe to upgrade to. If you have an integration, contact your service provider to find out if it's possible to update to the latest schema version. You can find all information related to the DataCite schema in the guide at
[schema.datacite.org](schema.datacite.org).