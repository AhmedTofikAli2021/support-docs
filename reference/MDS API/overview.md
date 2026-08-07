---
title: MDS API
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
## Version History

* v.2: September 1, 2011
* v3: July 16, 2018

## Overview

The MDS (Metadata Store) API can be used to register and manage DOI names and associated metadata. The API requires authentication and is available to DataCite providers and their clients. The basic API endpoint is at `https://mds.datacite.org`, with the following three resource endpoints:

* `https://mds.datacite.org/doi`
* `https://mds.datacite.org/metadata`
* `https://mds.datacite.org/media`

## Authentication

All requests to the MDS API require authentication. For this reason, only traffic via a secure connection (HTTPS) is supported. The DataCite Metadata Store (MDS) uses  [HTTP Basic authentication](https://en.wikipedia.org/wiki/Basic_access_authentication). 

To start interacting with our DataCite Metadata Store (MDS) API you must request an account:
* If you are a DataCite Provider, DataCite will provide you a username and password
* If you are a DataCite Client, your Provider will provide you a username and password
*  If you are not yet a DataCite Provider or Client, you can [obtain a demo account](doc:demo-account)

Remember that you will be allowed to register DOI names only under the prefixes that have been assigned to you.

## API Response Codes

* `200 OK` - operation successful
* `201 OK` - content created
* `204 No Content` - DOI is known to MDS, but is not registered 
* `401 Unauthorized` - no login
* `403 Forbidden` - login problem or DOI belongs to another party
* `404 Not Found` - DOI does not exist in our database
* `422 Unprocessable Entity` - metadata not validating against DataCite schema
* `500 Internal Server Error` - internal server error

## Testing
There are three ways you can test the MDS without registering a permanent DOI:

## Use draft DOIs
DOIs with registered metadata, but no URL registered, are in **draft** state, and can be deleted. Read more about DOI states [here](https://support.datacite.org/docs/doi-states). Note that draft DOIs will behave like any other DOI, but will not be registered in the Handle system, our Search index, or any other DataCite service outside of DOI registration. 

### Use demo DOIs with prefix 10.5072
The special demo prefix **10.5072** is available to all clients. All DOIs with this prefix are draft DOIs. In addition, these DOIs can not be transitioned to other DOI states, and are automatically deleted after 30 days. All demo accounts use only the demo prefix.

### Use the test MDS
The test MDS at [https://mds.test.datacite.org](https://mds.test.datacite.org) is available to all providers and clients, but special registration is necessary. Please contact [DataCite Support](mailto:support@datacite.org}. DOIs registered in the test MDS will not resolve using the doi.org proxy. 

Your own prefixes should not be used for testing DOIs in the production MDS service.