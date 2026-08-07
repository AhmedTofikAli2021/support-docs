---
title: Testing Guide
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
Test accounts allow users to try out DataCite services in a safe sandbox environment. A test account allows you to configure your systems to automatically register and manage DOIs via one of our APIs or to try out the latest functionality in Fabrica without the risk of creating live DOIs. 

The following sections describe how to get started with testing DataCite services. 

- [Get a test account](doc:getting-a-test-account)
- [Create a repository in Fabrica Test](doc:create-a-client-in-fabrica-test)

> 📘 
> 
> The test system uses a test handle server. Test DOIs resolve via this test handle server. DOIs  created in the test system aren’t real and don’t resolve using the global handle system via <https://doi.org.> They look like this: <https://handle.test.datacite.org/10.17596/w76y-4s92>

## About the test system

DataCite maintains test instances of its services. These test instances can be identified by the word "test" in their URL. These test services are:

- Fabrica (<https://doi.test.datacite.org>)
- REST API (<https://api.test.datacite.org>)
- MDS API (<https://mds.test.datacite.org>)

In other words, the test account credentials will allow you to test creating and managing DOIs manually in a web-based platform (Fabrica), and the same set of credentials will allow you to test your own applications and integrations that call one of DataCite's APIs. 

## Who can have a test account?

Current DataCite Members and Repositories can have test accounts, as can potential new Members. For more information, refer to our [Test Accounts Policy](doc:test-accounts-policy).

## Using the test system

The test system should be used to try out Fabrica and test applications and integrations using DataCite APIs. Because the test system is not built to support the same amount of requests as our production systems, the test system should not be used as a mirror for production application and integration requests. 

Your test applications and integrations may be populated with production data. In these cases, please ensure that your systems are not making requests for production DOIs in the test system.