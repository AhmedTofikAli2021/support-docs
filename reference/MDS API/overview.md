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

## Overview

The MDS (Metadata Store) API can me use to register and manage DOI names and associated metadata. The API requires authentication and is available to DataCite members and their data centers. The basic API endpoint is at `https://mds.datacite.org`, with the following three resource endpoints:

* `https://mds.datacite.org/doi`
* `https://mds.datacite.org/metadata`
* `https://mds.datacite.org/media`

## Authentication

All requests to the MDS API require authentication. For this reason, only traffic via a secure connection (HTTPS) is supported. The DataCite Metadata Store (MDS) uses  [HTTP Basic authentication](https://en.wikipedia.org/wiki/Basic_access_authentication). 

To start interacting with our DataCite Metadata Store (MDS) API you must request an account:
* If you are a DataCite Member, DataCite will provide you a username and password
* If you are a DataCite User, your Allocating Member will provide you a username and password
*  If you are not yet a DataCite Member or User, you can [obtain test credentials to our sandbox](doc:obtain-test-account)

Remember our accounts have basic security constraints:

* you will be allowed to register DOI names only under the prefixes that have been assigned to you
* your DOI names can only refer to URLs under host domains you control
* depending on your Allocating Member, you may or may not have an unlimited number of DOIs available. You can negotiate your quota with your Allocating Member

## API Response Codes

* `200 OK` - operation successful
* `201 OK` - content created
* `204 No Content` - DOI is known to MDS, but is not registered (or not resolvable e.g. due to handle’s latency)
* `401 Unauthorized` - no login
* `403` - login problem or DOI belongs to another party
* `404 Not Found` - DOI does not exist in our database
* `500 Internal Server Error` - server internal error, try later and if problem persists please contact us

## Testing
There are three ways you can test the MDS without registering a permanent DOI:

### Use the test MDS
The test MDS at [https://mds.test.datacite.org](https://mds.test.datacite.org) is available to all members and users. DOIs registered in the test MDS will not resolve using the doi.org proxy. 

### Use the testMode query parameter
Each API call can have an optional `testMode` query parameter. If set to “true” or “1”, e.g. `POST /doi?testMode=true`, the request will not change the database nor will the DOI handle be registered or updated.

### Use the test prefix 10.5072
The special test prefix **10.5072** is available to all data centers. Please use it for all your testing DOIs. Note that DOIs with test prefix will behave like any other DOI, e.g. they can be normally resolved. They will *not* be exposed in services like search and OAI, though. 

Your own prefixes should not be used for testing DOIs in the production MDS service.