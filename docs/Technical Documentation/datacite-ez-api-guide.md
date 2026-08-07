---
title: DataCite EZ API Guide
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
## Purpose of the DataCite EZ API

The [DataCite EZ API](https://support.datacite.org/v1.1/reference#ez-api) was launched in March 2018 and allows users to register DataCite DOIs and associated metadata. The API is compatible with the [EZID API](https://ezid.cdlib.org/doc/apidoc.html) from the California Digital Library and is intended for previous users of that API. However, the [DataCite Metadata Store (MDS) API](doc:mds-2) is the default API for registering DataCite DOIs. The API requires authentication. To become a member, interested parties should contact [DataCite support](mailto:support@datacite.org).

To retrieve DOI metadata records users should use our [DataCite REST API](api.datacite.org), which provides better performance, better query options, and doesn't require authentication. 

## Authentication

All requests to the EZ API require authentication. For this reason, only traffic via a secure connection (HTTPS) is supported. The DataCite EZ API uses  [HTTP Basic authentication](https://en.wikipedia.org/wiki/Basic_access_authentication). 

To start interacting with our DataCite Metadata Store (MDS) API you must request an account:
* If you are a DataCite Provider, DataCite will provide you a username and password
* If you are a DataCite Client, your Provider will provide you a username and password
*  If you are not yet a DataCite Provider or Client, you can [obtain test credentials](doc:obtain-test-account)

Remember our accounts have basic security constraints:

* you will be allowed to register DOI names only under the prefixes that have been assigned to you
* your DOI names can only refer to URLs under host domains you control
* you must use your Client account for registering doi's providers can not register DOI's
* usernames must be passed in lowercase

## How to Use

The DataCite EZ API can be used directly by making HTTP requests with packages such as [cURL](https://curl.haxx.se/docs/manpage.html). Besides using the API directly there are a number of wrappers for the API that you can install to create DataCite DOIs. Please review the documentation of the respective package for installation instructions, and make sure you point your client to https://ez.datacite.org instead of https://ezid.cdlib.org.

* **EZID** (Python) - https://ezid.cdlib.org/doc/apidoc.html#python-command-line-tool
* **EZID Client** (Ruby) - https://github.com/duke-libraries/ezid-client
* **EZID-PHP** (PHP) - https://github.com/olendorf/ezid-php

## DataCite MetaData Profile
The EZ API supports the deposition of metadata in DataCite XML format followin the [DataCite metadata schema](http://schema.datacite.org/). This must be passed to the API via the ANVL format, i.e. with proper escaping of new lines and colons (which have special meaning in ANVL). For example:

```xml

_target: https%3A//example.org/abc
<?xml version="1.0" encoding="UTF-8"?>%0A<resource xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://datacite.org/schema/kernel-4" xsi:schemaLocation="http://datacite.org/schema/kernel-4 %0A " target="_blank" rel="noopener noreferrer">http://schema.datacite.org/meta/kernel-4/metadata.xsd">%0A  <identifier identifierType="DOI">10.33516/F8X6-9F20</identifier>%0A  <creators>%0A    <creator>%0A      <creatorName>Test User</creatorName>%0A    </creator>%0A  </creators>%0A  <titles>%0A    <title>Aqueous geochemistry of Louisiana marshes, May 2015 – October 2016</title>%0A  </titles>%0A  <publisher>Harte Research Institute</publisher>%0A  <publicationYear>2018</publicationYear>%0A  <resourceType resourceTypeGeneral="Dataset">CreativeWork</resourceType>%0A  <dates>%0A    <date dateType="Issued">2018</date>%0A  </dates>%0A  <version/>%0A</resource>%0A

```

### Resource types
When specifying the DataCite metadata profile it is important you send the correct resource type for the DOI you are registering, in some cases third party libraries (as above) may put defaults that are invalid e.g. "Book"

## Example cURL request

Using cURL it is easiest to create a data file e.g. "payload.txt" and in that put your ANVL formatted request (see above).
You can then make a call like
```curl --user xxx:xxx -X POST -H 'Content-Type: text/plain' --data-binary @payload.txt https://ez.test.datacite.org/shoulder/doi:10.5072```

[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]