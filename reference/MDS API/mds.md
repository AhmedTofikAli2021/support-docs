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

- v.2: September 1, 2011
- v3: July 16, 2018

## Overview

The MDS (Metadata Store) API can be used to register and manage DOI names and associated metadata. The API requires authentication and is available to DataCite members and their repositories. The basic API endpoint is at `https://mds.datacite.org`, with the following three resource endpoints:

- `https://mds.datacite.org/doi`
- `https://mds.datacite.org/metadata`
- `https://mds.datacite.org/media`

## Authentication

All requests to the MDS API require authentication. For this reason, only traffic via a secure connection (HTTPS) is supported. The DataCite Metadata Store (MDS) uses  [HTTP Basic authentication](https://en.wikipedia.org/wiki/Basic_access_authentication). 

To start interacting with our DataCite Metadata Store (MDS) API you must request an account:

- If you are a DataCite Direct Member, DataCite will provide you a username and password.
- If you are a DataCite Consortium Organization, your Consortium Lead will provide you a username and password.

Remember that you will be allowed to register DOI names only under the prefixes that have been assigned to you using **Repository** account credentials. For more information, see [Accounts in DataCite](doc:datacite-account-types).

## API Response Codes

- `200 OK` - operation successful
- `201 OK` - content created
- `204 No Content` - DOI is known to MDS, but is not registered 
- `401 Unauthorized` - no login provided
- `403 Forbidden` - login problem or DOI belongs to another party
- `404 Not Found` - DOI does not exist in our database or you are not authorized with your username/password combination. Note that you may receive a 404 when using invalid credentials; this is to prevent security data leakage, i.e. showing to a potential attacker that the username is valid.
- `422 Unprocessable Entity` - metadata not validating against DataCite schema
- `500 Internal Server Error` - internal server error

## Testing

There are two ways you can test the MDS without registering a permanent DOI:

### Use the test MDS environment

This is the safest way to test the MDS. The test MDS at <https://mds.test.datacite.org> is available to all Direct Members and Consortium Organizations via your test account, which has different credentials than your production account. See our [Testing Guide](doc:testing-guide) for information about using the test system.

DOIs registered in the test MDS will not resolve using the doi.org proxy.  

### Use draft state

DOIs with registered metadata, but no URL registered, are a **draft** state, and can be deleted. Draft state is a good way to reserve an identifier for later use or to offer your repository platform users a way to reserve DOIs that are not yet live. Note that draft records will behave like any other DOI, but will not be registered in the Handle system, our search index, or any other DataCite service outside of DOI registration. See our documentation on [DOI States](doc:doi-states) for more information.

Please do not create Registered or Findable DOIs (see [DOI States](doc:doi-states) for explanations) in the production system as a means of testing your setup. These DOIs cannot be deleted and will count toward your DOI totals for the purposes of billing.