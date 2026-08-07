---
title: Repository Settings
excerpt: ''
deprecated: false
hidden: true
link:
  new_tab: false
  url: https://support.datacite.org/docs/fabrica-settings#repository-settings
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Repositories can update their settings. Direct Members, Consortium Leads, and Consortium Organizations can also update the settings of their respective Repositories.

To modify the Repository settings, go to the _Settings_ tab on the Repository dashboard. Direct Members, Consortium Leads, and Consortium Organizations will first need to select the Repository from their list of Repositories in order to view the appropriate Repository dashboard. 

Click the "Update Repository" button on the top left. Enter any changes in the appropriate fields and click "Update Account" at the bottom of the page.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1631568-Screenshot_2023-01-25_at_12.04.45.png",
        "Screenshot 2023-01-25 at 12.04.45.png",
        ""
      ],
      "align": "center",
      "sizing": "500px",
      "border": true
    }
  ]
}
[/block]


## Repository Information

### Repository ID

The Repository ID is a unique identifier for each Repository. It must contain uppercase letters or numbers. The first part of the ID corresponds to the Member ID or Consortium Organization ID._ Note: The Repository ID can't be modified._

> 📘 Example Repository ID
> 
> VFRU.ZZSX19  
> Member ID =  VFRU  
> Repository = ZZSX19

### Type

The Type field refers to the platform where the content will be shared. The default value is "Repository".

- Select "Periodical" from the drop-down menu if the DOIs registered will be assigned to publications and journals.
- Select "[IGSN ID Catalog](doc:registering-igsn-ids)" from the drop-down menu if the the DOIs registered will be [IGSN IDs](doc:about-igsn-ids-for-material-samples) assigned to material samples and features-of-interest.
- Select "RAiD Registry" only if you are a RAiD Registration Agency (RA) and will be registering DOIs with the RAiD Service. [Read more about RAiD](doc:raids).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1076d71-Screenshot_2024-05-09_at_11.59.35.png",
        "Screen Shot 2023-03-10 at 12.50.12 PM.png",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


> 🚧 
> 
> Repositories with an IGSN ID Catalog Type cannot change Types after creation. Repositories with a Repository or Periodical Type cannot change to the IGSN ID Catalog Type after creation.

### re3data Record (optional)

Link to the corresponding record in the re3data registry of research data repositories.

> 📘 Link to your re3data record
> 
> Linking the [re3data](https://www.re3data.org/) identifier automatically displays a number of fields from re3data without needing to store that information a second time in Fabrica. In the case of disciplinary repositories, the **Repository Discipline field will be automatically populated.** 
> 
> Only re3data repositories with an "open" or "restricted" data upload type are available to select.

> ❗️ Linking re3data records currently unavailable
> 
> New links to re3data records cannot be established in Fabrica as of March 2025. Please contact [support@datacite.org](mailto:support@datacite.org) for assistance.

### Repository Name

Full name of the Repository. This is typically the name of the organization, as the organization wants it displayed. For example, "Archaeology Data Service". 

### Repository Alternate Name (optional).

An Alternate Repository Name can be included if appropriate.

### System Email

This email address receives reset password requests. 

### Service Contact (optional)

This is the name of the person responsible for the account. This person is considered to be the primary contact for any necessary DataCite or system communications. 

### Description (optional)

Add a description of the repository here.

### URL (optional)

The homepage of the repository.

### Language (optional)

Select the language of the repository from the dropdown list.

### Software (optional)

Select the software used by the Repository from the dropdown list.

![](https://files.readme.io/9588bde-repository_software.png)

### Domains

Define which domains or subdomains can be used for DOI URLs in the repository. The default setting for this field is that a DOI can point to any URL. This is indicated by single asterisk  `*` in the domain settings. 

![](https://files.readme.io/c875847-Screen_Shot_2020-11-03_at_10.22.35.png "Screen Shot 2020-11-03 at 10.22.35.png")

To limit the list of domains that can be used to register URLs for a DOI, enter one or more domains or subdomains, separated by a comma. You can use an asterisk to allow any subdomain, e.g. `\*.example.org`. Make sure you are entering only the hostname, not a full URL starting with `http` or `https`. Also keep in mind that `www` is a subdomain. 

![](https://files.readme.io/c9ed222-Screen_Shot_2020-10-28_at_09.51.08.png "Screen Shot 2020-10-28 at 09.51.08.png")

Refer to the table below to see how a repository's domain settings determine which domains are allowed in the repository's DOI URLs:

[block:parameters]
{
  "data": {
    "h-0": "Domains Setting in Fabrica",
    "h-1": "Description",
    "h-2": "Allowed Domains",
    "h-3": "Prohibited Domains",
    "0-0": "`*`",
    "0-1": "Allow all domains",
    "0-2": "All domains",
    "0-3": "N/A",
    "1-0": "`*.datacite.org`",
    "1-1": "Only allow URLs with subdomains of `datacite.org`",
    "1-2": "`www.datacite.org`  \n`doi.datacite.org`",
    "1-3": "`datacite.org`  \n`orcid.org`",
    "2-0": "`www.datacite.org`",
    "2-1": "Only allow URLs with  domain `datacite.org` and subdomain `www`",
    "2-2": "`www.datacite.org`",
    "2-3": "`doi.datacite.org`  \n`datacite.org`  \n`orcid.org`",
    "3-0": "`datacite.org`",
    "3-1": "Only allow URLs with  domain `datacite.org` and do not allow subdomains of `datacite.org`",
    "3-2": "`datacite.org`",
    "3-3": "`www.datacite.org`  \n`doi.datacite.org`  \n`orcid.org`",
    "4-0": "`*.datacite.org,datacite.org`",
    "4-1": "Allow URLs with domain `datacite.org` and any subdomain of `datacite.org`",
    "4-2": "`www.datacite.org`  \n`doi.datacite.org`  \n`datacite.org`",
    "4-3": "`orcid.org`"
  },
  "cols": 4,
  "rows": 5,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


When registering or updating a DOI, the URL field in the Fabrica (both in the Form and File Upload view) will turn green when a valid URL is entered:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d854cb3ce38b6e3a32ff0f7ef28150b58050ad3a47eda10328d10201bb9e7af1-Screenshot_2025-03-03_at_14.58.42.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


> 📘 Troubleshooting
> 
> If you find the URL field is not accepting the URL, try adjusting the domain filter to allow both the domain and any subdomain:
> 
> ![](https://files.readme.io/be4fb7067921db2a438dd11f9e140467cff35bf8255fd43586b53dc7f339b4f6-Screen_Shot_2025-03-04_at_11.49.48_AM.png)

### Repository Type (optional)

Add the type of Repository (e.g. Institutional, Disciplinary).

### Repository Discipline (optional)

This will only appear if the Repository Type "Disciplinary" has been selected. Add the discipline of the repository using the look-up from the OECD Fields of Science.

> 👍 The Repository Discipline field
> 
> The Repository Discipline field is used to enrich DOI metadata. This does not modify DOI metadata but is used to enhance search queries, so if the Repository Discipline is Biology, DOIs registered by the repository will be captured by queries for the subject "Biology" in the Graph QL API and DataCite Commons. This feature is only for disciplinary repositories

![](https://files.readme.io/a3afe99-small-Screenshot_2023-05-03_at_12.55.49.png)

### Certificate (optional)

The certificate held by the Repository, e.g., CoreTrustSeal. More information about certificates can be found here: [RDA/WDS Certification of Digital Repositories IG](https://www.rd-alliance.org/groups/rdawds-certification-digital-repositories-ig.html)

### Account is active

_This setting is only available to Direct Members, Consortium Leads, and Consortium Organizations when updating a Repository account. Repositories cannot change their own account status._

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6f94b3eb09346aafcceff6a18dc5aa88c50826d7c6c07a5f5f8216b4c4a28072-Screenshot_2025-07-08_at_11.36.13.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "300px",
      "border": true
    }
  ]
}
[/block]


If the box is checked, the account is active and can register DOIs. If the box is unchecked, the account is "Inactive" and can no longer register DOIs.