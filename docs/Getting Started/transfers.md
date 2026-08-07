---
title: Transferring DOIs and Prefixes
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
This guide provides information about managing DOIs in DOI Fabrica. For general information about DataCite membership please see our [website](https://datacite.org/become.html).

Information about DataCite Consortia and their Consortium Organizations, Direct Members, and their Repositories needs to be maintained and updated in DOI Fabrica -- this information is used by the Fabrica application and to determine Member Fees. 

There are specific occasions when a Repository will need to move their prefix(es) and DOIs to a new Repository under a different member. This is especially relevant for Repositories that already exist within the DataCite system and either upgrade to Direct Members or join a Consortium. Those Repositories will then need to migrate their account and DOIs under the new member.

Repositories play a central role in DataCite’s structure. The process of moving prefix(es) and DOIs from one Repository to another is called a "transfer".  These are the steps for a successful transfer: 

##1. Repository environment set up in Fabrica##
  * A new repository environment is set up by the Direct Member or by the Consortium Organization.
  * An automated email is generated to inform you that the new repository environment is available.
  

##2. Contact Support##

**For Direct Members**
  * Contact DataCite [support@datacite.org](mailto:support@datacite.org) to request the transfer.
  * Make sure you know which prefixes will be transferred to which repository environment and supply the following information in your message to DataCite support. 



Old Repository [ID: DATACITE]
New Repository ID: [DATACITE.DATACITE]
Prefix: [10.7000]
Number of DOIs: [165]


**For Consortium Members**


The steps are the same as for Direct Members, but the Consortium Lead contacts [support@datacite.org](mailto:support@datacite.org) with the following information for all of their Consortium Organizations.

Old Repository [ID: DATACITE]
New Repository ID: [DATACITE.DATACITE]
Prefix: [10.7000]
Number of DOIs: [165]
[block:callout]
{
  "type": "info",
  "body": "Prefixes cannot be shared between repositories!"
}
[/block]
##3. Schedule##
Once you have sent the required information to support@datacite.org, DataCite, together with you, will schedule a time and date for the transfer of the prefix(es) and DOIs to the new Repository. Make sure that all relevant parties agree to and are aware of the transfer and copied on the message to DataCite. 

##4. Transfer##
  * DataCite transfers the prefix(es) and DOIs and DataCite alerts the relevant parties that the transfer is complete.
  * The Direct Member or Consortium confirms that everything is OK from their side.
  * Update the authentication credentials for your API integration 
  

Please see the [Transfer FAQ](doc:transfers-1) for more guidance