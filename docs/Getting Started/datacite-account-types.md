---
title: Accounts in DataCite
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: fabrica-contacts
      title: Fabrica Contacts and Mailing Lists
---
When you join DataCite, your organization will be given access to [DataCite Fabrica](doc:doi-fabrica) and the [API](doc:api). To create, update and manage your organization's information and your DOIs you will need to know the ID and password of the account you want to use. 

You can [reset the password](doc:reset-fabrica-password) at any time (you will need to know the ID of the account you want to reset the password for). A set password email will then be sent to the system email contact. 

- Reset password in the production environment: <https://doi.datacite.org/reset>.
- Reset password in the test environment: <https://doi.test.datacite.org/reset>.

### What about the API?

> 👍 Good news! You can use the same account credentials to access DataCite Fabrica and the API.

There are different types of account depending on what type of membership you have and what you want to do.  Below is a description of each type of account. 

> 📘 Test and production
> 
> Remember the credentials and prefix you will use to access are different for the **test environment**: <https://doi.test.datacite.org> /  <https://api.test.datacite.org> and the **production environment**: <https://doi.datacite.org> / <https://api.datacite.org>.

## Direct Member Account

A Direct Member is an organization that joins DataCite to register DOIs and participate in the governance of the organization. 

A Direct Member account ID is a string of characters and looks something like this **RFDS.**

When you access with a Direct Member account you will have permission to:

- Retrieve stats about the DOIs, prefixes and Repositories belonging to the Direct Member.
- Update your organizational profile.
- Create and update contacts.
- Create and update Repository accounts.
- Retrieve all DOIs and metadata registered by the Repository accounts under the Direct Member.

## Consortium Lead Account

A Consortium Lead account is the organization that heads up a DataCite Consortium. This organization is responsible for administering the accounts of the organizations that form part of the consortium.

A Consortium Lead account ID is a string of characters and looks something like this **BCLSCO**.

When you access with a Consortium Lead account you will have permission to:

- Retrieve stats about the number of DOIs, prefixes, Repositories and Consortium Organizations managed by the Consortium.
- Update the organizational profile.
- Create and update contacts.
- Create and update Consortium Organizations.
- Create and update Repository accounts.
- Retrieve all DOIs and metadata registered by the Repository accounts under the Consortium membership.

## Consortium Organization Account

A Consortium Organization is an organization that has joined a DataCite Consortium. A Consortium Organization account ID is a string of characters and looks something like this **GFHD**.

When you access with a Consortium Organization you will have permission to:

- Retrieve information about the number of DOIs, prefixes and Repositories managed by the Consortium Organization.
- Update the organizational profile.
- Create and update contacts.
- Create and update Repository accounts.
- Retrieve all DOIs and metadata registered by the Repository accounts under the Consortium Organization. 

## Repository Account

A Repository account is the account you use to register DOIs. Repositories represent a store where all the DOIs for a group of resources are registered and will stay together. A Repository has its own set of credentials and one prefix for DOI registration. Each Direct Member and Consortium Organization will have at least one associated Repository account.

The Repository account ID includes the ID of the associated Direct Member or Consortium Organization and looks something like this: **GFHD.JHSHSPA.**

When you access with a Repository account you will have permission to:

- Create and update DOIs and metadata.
- Update the Repository information.
- Retrieve the prefix assigned to the Repository.
- Retrieve DOIs and metadata registered by the Repository.

> 📘 
> 
> Repository accounts appear in DataCite Commons in the Repositories tab: <https://commons.datacite.org/repositories/or2c2n>

> 📘 Getting Started
> 
> All DataCite accounts are created through DataCite membership. If your organization is interested in joining DataCite, please reach out to us by sending an email to [info@datacite.org](mailto:info@datacite.org) and expressing your interest. You can find more information about membership on our [website](https://datacite.org/become.html). 
> 
> If you have any questions about your existing DataCite accounts, please contact [support@datacite.org](support@datacite.org)
