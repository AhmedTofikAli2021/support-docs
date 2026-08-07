---
title: Test Accounts Policy
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
## The Test System

DataCite’s test environment mirrors the functionality of the production environment and enables DOIs registration via a test handle server so test DOIs will resolve in the same way as live DOIs. However, the DataCite test system works like a sandbox and is completely [separate from the production system](doc:what-is-the-difference-between-the-datacite-test-and-production-environments), with a different set of credentials and prefixes. A [DataCite test account](doc:https://support.datacite.org/docs/testing-guide) is intended to allow new and potential members and integrators to try out the functionalities of the DataCite web interface ([Fabrica](doc:doi-fabrica)) and the APIs ([REST](doc:api) and [MDS](doc:mds-api-guide)). New and potential members and integrators  may use the test system to; test a new integration, practice using the functionalities in Fabrica and learn more about the account structure. The test system is not built to support the same amount of requests as the production system; it should never be used as part of any production application or integration requests. DOIs created in the test system cannot be transferred to production. 


## Test Accounts

**Members**
DataCite provides test accounts to all Direct Members and Consortium Leads. Consortium Leads may provide test accounts to Consortium Organizations on behalf of DataCite.

DataCite Direct Members, Consortium Leads, and Consortium Organizations may be assigned different Account IDs on the test system than on the production system. Prefix assignment also happens separately on the test system; as a result, test repository accounts will have different prefixes. The test system cannot be accessed using production system credentials (or vice versa).

**Prospective members **
DataCite may also provide test accounts to prospective Direct Members and Consortium Leads. Consortium Leads may provide test accounts to prospective Consortium Organizations.


**Integrators and other users**
DataCite may provide test accounts to those building DOI registration integrations with our APIs (including DataCite Service Providers), upon request.
[block:callout]
{
  "type": "info",
  "body": "DataCite provides test accounts to prospective members and integrators to give the organization the opportunity to evaluate whether they're interested in a DataCite membership. The test account will be active for 6 months. If the organization does not apply for membership within that period, DataCite will reach out to discuss next steps. If the organization decides not to join DataCite, the test account will be deactivated."
}
[/block]
## Test DOIs

**Test DOIs cannot be deleted unless in Draft state**
Like DOIs in the production system, test DOIs in Registered or Findable state cannot be deleted. Test DOIs in Draft state can be deleted since they have not yet been registered in the test handle server. 

**Persistence of test handles **
Unlike DOIs in the production system, test DOIs registered in the test system are not real DOIs and should not be considered persistent. Test handles registered in the test handle server (for example, https://handle.stage.datacite.org/10.82206/ah2m-dw44) are not guaranteed to resolve indefinitely. 

## Test System Misuse

**Misuse of the test system**
Requests for production DOIs and other resources should not be sent to the test system. Duplicate requests should not be sent to both the test system and the production system. The test system should not be used to validate production requests unless temporarily testing an application or integration. Requests in excess of 750 requests per 5 minutes is considered misuse of the test system. 

**Consequences for misuse** 
If a test account is being misused, DataCite may warn the System Email and available Technical Contact(s) associated with the account of a potential deactivation. If DataCite does not receive a response to the warning, DataCite may deactivate misused accounts until the account contacts confirm a change to their usage. If misuse is causing degraded service performance for other users, DataCite may deactivate the misused account before receiving a response.