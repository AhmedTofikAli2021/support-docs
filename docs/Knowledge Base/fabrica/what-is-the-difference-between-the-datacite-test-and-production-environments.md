---
title: What is the difference between the DataCite test and production environments?
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
The DataCite test and production environments are completely separate. You will need separate credentials to access each environment. The test environment mirrors production and includes all of the same functionalities so DataCite members can test workflows and integrations. **The test environment works like a sandbox and nothing you do in the test environment will ever go live in production.**

## Will test DOIs resolve?
Yes. The test system uses DataCite's own test handle server which means the DOI resolves to the landing page stored in the metadata. In production, once a DOI is in "Registered" or "Findable" state, it is registered in the global handle server and cannot be deleted.

A test DOI: https://handle.stage.datacite.org/10.80253/135539
A real DOI: https://doi.org/10.25923/9z8r-6h70

##Will test DOIs remain in the test system?
We ensure that the test system works for testing purposes. However, we cannot guarantee the integrity of the metadata stored there. For this reason, the test environment should never be part of any production workflows.

## How do I get a test account?
If you are a DataCite member or potential member, you should contact us to request a test account  [support@datacite.org](mailto:support@datacite.org). If your organization is part of a DataCite Consortium, please contact your Consortium lead.

## Does the test environment contain the same data as production?
No. It only contains repositories, prefixes and DOIs that have been added by organizations testing their applications and workflows. This data is completely separate from the production environment. 

More detailed information about testing is available [here](doc:testing-guide).