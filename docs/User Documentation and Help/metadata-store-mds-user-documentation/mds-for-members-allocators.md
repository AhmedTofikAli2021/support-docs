---
title: Metadata Store (MDS) for Members (Allocators)
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
[block:api-header]
{
  "type": "basic",
  "title": "Datacentre Management: Create New Data Center"
}
[/block]
This functionality is only available for Members (Allocators) and allows them to create new Data Center (User) accounts. Every Data Center accessing the DataCite service through a Member should have its own account (username and password).

You can access this functionality through the left menu:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/68567b5-image13.png",
        "image13.png",
        228,
        109,
        "#eaeaea"
      ]
    }
  ]
}
[/block]
You will have to provide:

1. Symbol: (equivalent to username) The symbol of a user will always follow the naming convention MEMBER.USER, where MEMBER is the Member’s symbol, and USER is replaced by a meaningful name describing the user.
2. Contact Name: Name of the technical responsible for this account, usually personnel of the User.
3. Contact Email: Email address to contact the technical responsible. This address should also subscribe to the [All Users mailing list](doc:how-to-contact-datacite).
4. Enable DOI Quota: Depending on your business model, certain accounts may have a maximum limit of DOIs per period. You can configure the amount using this option.
5. Is Active: By default, all accounts are active.
6. Domains: A list of all domains allowed for DOI’s landing pages. It includes sub-domians by default (e.g. adding datacite.org to the list will also enable blog.datacite.org or profiles.datacite.org). If you try to mint a new DOI pointing to an address outside the allowed domains, the system will return an error.
7. Prefixes: You can assign different prefixes to the same user account. The suggested best practice is one prefix per service (and per account, by extension). Please, always add the test prefix 10.5072 to all the accounts.
You can choose multiple prefixes from the list on the right hand side and move them to the list on the left to add them to the new account.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/01d81b8-Screen_Shot_2017-01-03_at_11.07.56.png",
        "Screen Shot 2017-01-03 at 11.07.56.png",
        1168,
        326,
        "#e1e1e1"
      ]
    }
  ]
}
[/block]
8. Comments: Please, use this field to save any comments or remarks.
9. Experiments: Currently not in use.
10. Send Welcome Mail: This field is a checkbox. It is active by default. It will send an email to the Technical Contact email address with a link to create a new password and activate the account. If you want to pre-create accounts without contacting the user, uncheck this box.
[block:api-header]
{
  "type": "basic",
  "title": "Data Center Management: Modify a Data Center"
}
[/block]
This functionality is only available for Members (Allocators) and allows them to modify the information, contact address, quota and other characteristics of the Data Center (User) account.

In order to find the User (DataCentre) you can use the 'List all Datacentres', or find it by Symbol or Name, using the left menu:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ce397bb-image13.png",
        "image13.png",
        228,
        109,
        "#eaeaea"
      ]
    }
  ]
}
[/block]
Once you find the appropriate User (Datacentre) please use the icons to edit it:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/199a3b0-image01.png",
        "image01.png",
        483,
        46,
        "#a1a3a4"
      ]
    }
  ]
}
[/block]
* Binoculars: Preview the details of the user
* Green arrow: Switch accounts to the User (in this example, DATACITE.DATACITE)
* Yellow pen: Edit the User 

When you start editing the user, you will see the same form as [Create new datacentre](https://datacite.readme.io/docs/metadata-store-mds-user-documentation#section-datacentre-management-create-new-datacentre). Just edit it with the new details and save the form to update the User (Datacentre) account.
[block:api-header]
{
  "type": "basic",
  "title": "Datacentre Management: Switch Users"
}
[/block]
If you want to access the DataCite Metadata Store (MDS) under the credentials of one of your Users (Datacentres), for example to troubleshoot and issue, or to help them assign/modify a DOI, you can switch to their account without requesting their credentials.

On the top right of your DataCite Metadata Store (MDS) page, use the dropdown menu to select the User (Datacentre) account you want to access:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/132ee49-user.png",
        "user.png",
        1106,
        152,
        "#315d9c"
      ]
    }
  ]
}
[/block]
Once you have done it, the page will update and function exactly as if you had used that particular account. You will see the current account on the top right of the page:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6576f90-user2.png",
        "user2.png",
        875,
        62,
        "#444444"
      ]
    }
  ]
}
[/block]
Use the 'Logout' link to close the User (Datacentre) account and go back to your Member (Allocator) interface.
[block:api-header]
{
  "type": "basic",
  "title": "Datacentre Management: Assign New Prefixes"
}
[/block]
To assign new prefixes to a Datacentre, search, find and modify it (following [these steps](doc:mds-for-members-allocators#section-datacentre-management-modify-a-datacentre)).

Scroll through the form until the section 'Prefixes':
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b0242e4-Screen_Shot_2017-01-03_at_11.07.56.png",
        "Screen Shot 2017-01-03 at 11.07.56.png",
        1168,
        326,
        "#e1e1e1"
      ]
    }
  ]
}
[/block]
You can assign multiple prefixes to the same user account. Choose from the list on the right hand side and move them to the list on the left to assign them.

If you don't have enough new prefixes, contact us to [request more](doc:request-more-prefixes-for-your-mds).
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]