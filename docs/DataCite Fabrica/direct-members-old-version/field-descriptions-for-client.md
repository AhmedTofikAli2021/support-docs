---
title: Field Descriptions for Repository Settings (old version)
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
[block:api-header]
{
  "title": "Repository ID"
}
[/block]
The Repository ID is a unique identifier for each Repository. It must contain uppercase letters or numbers and be of the form *MEMBER.REPOSITORY*, where *MEMBER* is the MEMBER ID of the parent organization and *REPOSITORY* is replaced by a short string representing the Repository. 

**Note:** The Repository ID can't be modified.
[block:callout]
{
  "type": "info",
  "body": "VFRU.ZZSX19\nMember ID =  VFRU \nRepository = ZZSX19",
  "title": "Example of Repository ID"
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
  "title": "Repository Name"
}
[/block]
Full name of the Repository. This is typically the name of the organization, as the organization wants it displayed. For example, "Archaeology Data Service". 

An Alternate Repository Name can be included if appropriate.
[block:api-header]
{
  "title": "System Email"
}
[/block]
This email address receives reset password requests. 
[block:api-header]
{
  "title": "Service Contact"
}
[/block]
This is the name of the person responsible for the account. This person is considered to be the primary contact for any necessary DataCite or system communications. 
[block:api-header]
{
  "title": "Description"
}
[/block]
Add an optional description of the repository here.
[block:api-header]
{
  "title": "URL"
}
[/block]
The homepage of the repository.
[block:api-header]
{
  "title": "Language"
}
[/block]
Select the language of the repository from the drop down list.
[block:api-header]
{
  "title": "Software"
}
[/block]
Select the software user by the Repository from the drop down list e.g CKAN.
[block:api-header]
{
  "title": "Domains"
}
[/block]
By default a DOI can point to any URL, indicated by an asterix * in the domain settings. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a3b7bed-Screen_Shot_2020-11-03_at_10.22.35.png",
        "Screen Shot 2020-11-03 at 10.22.35.png",
        2236,
        326,
        "#fcfcfc"
      ]
    }
  ]
}
[/block]
To limit the list of domains that can be used to register URLs for a DOI, enter one or more domains or subdomains, separated by a comma. You can use an asterix to allow any subdomain, e.g. "*.example.org". Make sure you are entering only the hostname, not a full URL starting with "http" or "https". Also keep in mind the "www" is a subdomain.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d7b2fdc-Screen_Shot_2020-10-28_at_09.51.08.png",
        "Screen Shot 2020-10-28 at 09.51.08.png",
        2348,
        340,
        "#fafbfc"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Repository type"
}
[/block]
Add the type of Repository e.g institutional
[block:api-header]
{
  "title": "Certificate"
}
[/block]
The certificate held by the Repository e.g CoreTrustSeal. More information about certificates can be found here [RDA/WDS Certification of Digital Repositories IG](https://www.rd-alliance.org/groups/rdawds-certification-digital-repositories-ig.html)

[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]