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
There are two ways you can test the MDS without registering a permanent DOI:

### Use the test MDS environment
This is the safest way to test the MDS. The test MDS at [https://mds.test.datacite.org](https://mds.test.datacite.org) is available to all providers and clients via your test account, which has different credentials than your production account. See our [Testing Guide](doc:testing-guide) for information about registering a test account.

DOIs registered in the test MDS will not resolve using the doi.org proxy.  

## Use draft DOIs
DOIs with registered metadata, but no URL registered, are in **draft** state, and can be deleted. Draft DOIs are a good way to reserve DOIs for later use or to offer your repository platform users a way to create DOIs that are not yet live. Read more about DOI states [here](doc:doi-states). Note that draft DOIs will behave like any other DOI, but will not be registered in the Handle system, our Search index, or any other DataCite service outside of DOI registration. 

Please do not create Registered or Findable DOIs (see [DOI States](doc:doi-states) for explanations) in the production system as a means of testing your setup. These DOIs cannot be deleted and will count toward your DOI totals for the purposes of billing.