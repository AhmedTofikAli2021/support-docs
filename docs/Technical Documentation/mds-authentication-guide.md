---
title: Metadata Store (MDS) Authentication Guide
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
All requests to the MDS API require authentication. For this reason, only traffic via a secure connection (HTTPS) is supported. The DataCite Metadata Store (MDS) uses  [HTTP Basic authentication](https://en.wikipedia.org/wiki/Basic_access_authentication). 

To start interacting with our DataCite Metadata Store (MDS) API you must request an account:
* If you are a DataCite Member, DataCite will provide you a username and password
* If you are a DataCite User, your Allocating Member will provide you a username and password
*  If you are not yet a DataCite Member or User, you can [obtain test credentials to our sandbox](doc:obtain-test-account)

Remember our accounts have basic security constraints:

* you will be allowed to register DOI names only under the prefixes that have been assigned to you
* your DOI names can only refer to URLs under host domains you control
* depending on your Allocating Member, you may or may not have an unlimited number of DOIs available. You can negotiate your quota with your Allocating Member

[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]