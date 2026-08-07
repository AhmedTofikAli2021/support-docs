---
title: Field Descriptions for Repository Settings (old version)
excerpt: ''
deprecated: false
hidden: true
link:
  new_tab: false
  url: https://support.datacite.org/docs/fields-repository-settings
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
[block:api-header]
{
  "title": "Client ID"
}
[/block]
The Client ID is a unique identifier for each client. It must contain uppercase letters or numbers and be of the form *PROVIDER.CLIENT*, where *PROVIDER* is the Provider ID of the parent Provider and *CLIENT* is replaced by a short meaningful string representing the Client. 

**Note:** The Client ID can't be modified.
[block:callout]
{
  "type": "info",
  "body": "TIB.PANGAEA \nProvider ID = TIB (German National Library of Science and Technology)\nClient = PANGAEA - Data Publisher for Earth & Environmental Science",
  "title": "Example of Client ID"
}
[/block]

[block:api-header]
{
  "title": "re3data Record"
}
[/block]
Link to the corresponding record in the re3data registry of research data repositories. This field is optional.
[block:callout]
{
  "type": "info",
  "body": "Linking the re3data identifier automatically displays a number of fields from re3data without needing to store that information a second time in Fabrica.",
  "title": "Link to your re3data record"
}
[/block]

[block:api-header]
{
  "title": "Client Name"
}
[/block]
Full name of the Client. This is typically the name of the organization, as the organization wants it displayed. For example, "Archaeology Data Service". 
[block:api-header]
{
  "title": "Contact Name"
}
[/block]
This is the name of the person responsible for the account. This person is considered to be the primary contact for any necessary DataCite or system communications. 
[block:api-header]
{
  "title": "Contact Email"
}
[/block]
The email address for the contact. This email address receives reset password requests. (This address should also subscribe to the [All Users mailing list](doc:how-to-contact-datacite)). 
[block:api-header]
{
  "title": "Domains"
}
[/block]
By default a DOI can point to any URL, indicated by an asterix *** in the domain settings. To limit the list of domains that can be used to register URLs for a DOI, enter one or more domains or subdomains, separated by a comma.
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]