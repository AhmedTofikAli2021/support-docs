---
title: >-
  Field Descriptions for Repository Settings (Consortium Leads and Consortium
  Organizations)
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
## Repository ID

The Repository ID is a unique identifier for each Repository. It must contain uppercase letters or numbers and be of the form _MEMBER.REPOSITORY_, where _MEMBER_ is the MEMBER ID of the parent organization and _REPOSITORY_ is replaced by a short string representing the Repository. 

**Note:** The Repository ID can't be modified.

> 📘 Example of Repository ID
> 
> VFRU.ZZSX19  
> Member ID =  VFRU  
> Repository = ZZSX19

## Type

The Type field refers to the platform where the content will be shared and is automatically designated as "Repository". Select "Periodical" from the drop-down menu if the DOIs registered will be assigned to publications and journals. Select ["IGSN ID Catalog"](doc:registering-igsn-ids) from the drop-down menu if the the DOIs registered will be [IGSN IDs](doc:about-igsn-ids-for-material-samples) assigned to material samples and features-of-interest.

![](https://files.readme.io/cad2463-Screen_Shot_2023-03-10_at_12.50.12_PM.png "Screen Shot 2023-03-10 at 12.50.12 PM.png")

> 🚧 
> 
> Repositories with an IGSN ID Catalog Type cannot change Types after creation. Repositories with a Repository or Periodical Type cannot change to the IGSN ID Catalog Type after creation.

## re3data Record

Link to the corresponding record in the re3data registry of research data repositories. This field is optional.

> 📘 Link to your re3data record
> 
> Linking the [re3data](https://www.re3data.org/) identifier automatically displays a number of fields from re3data without needing to store that information a second time in Fabrica. In the case of disciplinary repositories, the **Repository Discipline field will be automatically populated.**

## Repository Name

Full name of the Repository. This is typically the name of the organization, as the organization wants it displayed. For example, "Archaeology Data Service". 

An Alternate Repository Name can be included if appropriate.

## System Email

This email address receives reset password requests. 

## Service Contact

This is the name of the person responsible for the account. This person is considered to be the primary contact for any necessary DataCite or system communications. 

## Description

Add an optional description of the repository here.

## URL

The homepage of the repository.

## Language

Select the language of the repository from the drop down list.

## Software

Select the software used by the Repository from the drop down list e.g CKAN.

![](https://files.readme.io/6b6de67-Screenshot_2023-01-25_at_16.12.31.png "Screenshot 2023-01-25 at 16.12.31.png")

## Domains

By default a DOI can point to any URL, indicated by an asterix \* in the domain settings. 

![](https://files.readme.io/a3b7bed-Screen_Shot_2020-11-03_at_10.22.35.png "Screen Shot 2020-11-03 at 10.22.35.png")

To limit the list of domains that can be used to register URLs for a DOI, enter one or more domains or subdomains, separated by a comma. You can use an asterix to allow any subdomain, e.g. "\*.example.org". Make sure you are entering only the hostname, not a full URL starting with "http" or "https". Also keep in mind the "www" is a subdomain.

![](https://files.readme.io/d7b2fdc-Screen_Shot_2020-10-28_at_09.51.08.png "Screen Shot 2020-10-28 at 09.51.08.png")

## Repository type

Add the type of Repository (e.g. Institutional, Disciplinary).

## Repository Discipline

This will only appear if the Repository Type "Disciplinary" has been selected. Add the discipline of the repository using the look-up from the OECD Fields of Science or enter a keyword.

> 👍 The Repository Discipline field
> 
> The Repository Discipline field is used to enrich DOI metadata. This does not modify DOI metadata but it used to enhance search queries, so if the Repository Discipline is Biology, DOIs registered by the repository will be captured by queries for the subject "Biology" in the Graph QL API and DataCite Commons. This feature is only for disciplinary repositories.

![](https://files.readme.io/eb78a0b-small-Screenshot_2023-05-03_at_12.55.49.png)



## Certificate

The certificate held by the Repository e.g CoreTrustSeal. More information about certificates can be found here [RDA/WDS Certification of Digital Repositories IG](https://www.rd-alliance.org/groups/rdawds-certification-digital-repositories-ig.html)

## Account is active checkbox

If the box is checked the account is active and can register DOIs. If the box is unchecked the account is "Inactive" and can no longer register DOIs.

> 📘 Would you like to know more?
> 
> If you have any questions, requests or ideas please your Consortium Lead.