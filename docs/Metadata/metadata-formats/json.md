---
title: JSON
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
Will there be a 4.4. version of the JSON Schema? There is an issue in Github asking about 4.4 but no one has responded for several months: https://github.com/datacite/schema/issues/99.
Is the DataCite Github repo the official place to get the latest version of the JSON schemas? We retrieved the current version of 4.3 from the Github repo (https://github.com/datacite/schema/tree/master/source/json/kernel-4.3). I do not see the JSON schema linked anywhere else from the DataCite website or API docs or https://schema.datacite.org/ even though it seems that the REST API now depends on it. We have noticed at least one schema discrepancy (publicationYear is returned as an int and not a string) so we are curious if we are not using the most up to date version. Also there are additional fields mixed into the attributes section of the data payload send to create/update requests for the DataCite API that are not part of the schema we have (prefix, doi, url, event) and I’m not sure if that is just a design choice or something missing from our version of the schema.
Is Identifier a required field? The 4.3 JSON schema lists the identifiers field as required, but I am unable to update it for any of our DOIs. The DataCite API appears to ignore my data. It also lets me create public DOIs without this field. E.g., I have tried to update the DOI 10.23658/zw5n-tf24 using the forms in the DOI API reference (https://support.datacite.org/reference/dois-2) and the identifier data never shows up. This doesn’t appear to keep us from making a DOI public, but it’s a bit confusing.
What is the fractional second precision supported by DataCite for dates? We have noticed in the DataCite Fabrica “Update DOI” form that if our DOIs contain microsecond precision (e.g. “2020-11-06T21:37:33.000123Z“ the form claims there is an error. In python the standard way to format the fractional part of a second for a datetime object is microseconds. The DataCite schema refers users to the W3C note on datetime (https://www.w3.org/TR/NOTE-datetime) but that note says that adopters must state the min/max precision for the second fraction, which I can’t find in the DataCite Metadata Schema Documentation. Is millisecond precision the max supported by DataCite?

Answer

The JSON Schema version of the metadata was never officially released and therefore for 4.3 it hasn't been updated to 4.4, I've raised this with our representive for the Metadata WG to discuss what the plan is around providing a JSON Schema version of the metadata. It is likely there will be a 4.4 version but there is no immediate plans for this. Furthermore the DataCite services do not explicitly support the JSON Schema documents as valid metadata formats.

The REST API does not depend on the JSON Schema, the REST API allows you to update metadata attributes using JSON, however this is different to the explicit JSON Schema (even if there may be some similarities). The attributes that appear via the REST API are a json representation of what is defined via the XML / documentation on schema.datacite.org. This is why you are noticing differences because they are not linked. The additional attributes that appear are also not nescessarily metadata attributes, but instead additional attributes related to the DataCite view of the DOI, i.e. you mentioned event, this is a good example as this is used to handle the transition between states of a DOI, but these are part of the service not related to the metadata.

It is also entirely possible to use the REST API without specifying the metadata attributes as json and instead sending a complete metadata document via the "xml" attribute.

Identifier is a required field in the DataCite metadata schema (https://schema.datacite.org) however as this must match the DOI it is not possible to change this once set against a DOI. i.e. you can't have a different identifier than the one used for the DOI.


Yes you're right fractional parts are supported and as per the documentation in the schema the valid formats for dates defined as:

YYYY,YYYY-MM-DD, YYYY-MM-DDThh:mm:ssTZD or any other format or level of granularity described in W3CDTF. Use RKMS-ISO8601 standard for depicting date ranges.
Which includes fractional as the W3CDTF accepts this like your example of 2020-11-06T21:37:33.000123Z

I can put the metadata in with the value directly via XML, however this data only appears there, it looks like the data we are parsing is not parsing the fractional part correctly. I've raised a bug for us to look into it https://github.com/datacite/datacite/issues/1361, the workaround for now would be to put the fractional part via XML (you can do this in fabrica via file upload).