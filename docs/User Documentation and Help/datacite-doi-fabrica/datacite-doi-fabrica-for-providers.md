---
title: DataCite DOI Fabrica for Providers
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
[block:callout]
{
  "type": "info",
  "body": "[What is the difference between Members, Providers, and Clients?](doc:members-providers-and-clients) \n[DOI Fabrica account creation](doc:datacite-doi-fabrica#section-how-to-create-a-doi-fabrica-account)\n[Demo accounts](doc:demo-account)",
  "title": "See Also"
}
[/block]

[block:api-header]
{
  "title": "Provider Dashboard: Info"
}
[/block]
When Providers log in to Fabrica, they are presented with the Provider dashboard. From the homepage, Providers can manage Settings, Clients, Prefixes, and DOIs.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/687500b-Bildschirmfoto_2018-01-31_um_13.05.33.png",
        "Bildschirmfoto 2018-01-31 um 13.05.33.png",
        2758,
        994,
        "#f8fafa"
      ],
      "caption": "Provider Dashboard: Info",
      "border": true
    }
  ]
}
[/block]
The *Info* tab is the first tab presented to Providers after login and gives an overview of the Provider's account information. The two charts display the total number of Client accounts and the total number of DOIs created in the current year across all of the Provider's Clients. Providers can also view the total number of Clients and DOIs by year by hovering over the charts. 
[block:api-header]
{
  "title": "Provider Dashboard: Settings"
}
[/block]
The *Settings* tab contains the unique Provider ID, Provider name, as well as additional information about the provider: contact information, website, country, and description. This provider information is used in various DataCite services, including the [member listing](https://www.datacite.org/members.html) on the homepage.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8a8d1d5-Bildschirmfoto_2018-03-31_um_10.05.26.png",
        "Bildschirmfoto 2018-03-31 um 10.05.26.png",
        1391,
        1019,
        "#f8f9f9"
      ],
      "caption": "Provider Dashboard: Settings",
      "border": true
    }
  ]
}
[/block]
### Set Password

To set a new password for the Provider account click on the *Set Password* button on the right. Passwords must be at least 8 characters long and can be suggested by DOI Fabrica to provide better security. Click submit after entering the same new password in both the **New Password** and **Confirm Password** input fields.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/006a527-Bildschirmfoto_2018-02-08_um_22.53.33.png",
        "Bildschirmfoto 2018-02-08 um 22.53.33.png",
        2190,
        1042,
        "#fcfdfd"
      ],
      "caption": "Provider Dashboard: Set Password"
    }
  ]
}
[/block]
### Edit Provider Settings

To modify the Provider settings:
1. Click on the *Edit Provider* button on the upper right of the Provider Settings page. 
2. Make changes to the Provider information.
3. Click *Save* at the bottom of the record. 

**Note:** The Provider ID cannot be changed. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5f06c01-Bildschirmfoto_2018-03-31_um_10.07.29.png",
        "Bildschirmfoto 2018-03-31 um 10.07.29.png",
        1372,
        1180,
        "#fbfcfb"
      ],
      "caption": "Provider Dashboard: Edit Provider Settings",
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Provider Dashboard: Clients"
}
[/block]
The *Clients* tab lists all of the Clients associated with a Provider account. Providers can view Client information including the Client ID, the re3data ID (if available), contact name, contact email, and the domains allowed for the DOI landing pages.

The default sorting order for  Clients is by *Name*. To change sorting order to sort by *Date joined*, click on the arrow in the dropdown box at the top of the Client list and select *Sort by Date Joined*. To search for an individual Client, enter the Client name or the Client ID in the search box and click *Search*. 

To filter the Client list by year joined, select the appropriate box on the right side of the screen. To deactivate the filter, re-click the selected box.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3a66773-Provider_Clients.PNG",
        "Provider_Clients.PNG",
        1367,
        780,
        "#d7dcd8"
      ],
      "caption": "Provider Dashboard: Clients",
      "border": true
    }
  ]
}
[/block]
 By clicking on the Client's name the total number of DOIs created in the current year are displayed.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/37a3086-Provider_Client_DOI_Statistics.PNG",
        "Provider_Client_DOI Statistics.PNG",
        807,
        442,
        "#23aeab"
      ],
      "caption": "Provider Dashboard: Clients, Specific Client Selected",
      "border": true
    }
  ]
}
[/block]
## Create New Client Accounts

Providers are able to create new Client accounts and manage existing accounts. Every Client accessing Fabrica through an associated Provider must have their own account. To add a new Client click the *Add Client* button on the right, fill in the requested details described below and click *Save* at the bottom of the record. A system email with the Client ID and a link to set up a password will automatically be sent to the contact email in the Client settings.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dc0262a-CreatClient.PNG",
        "CreatClient.PNG",
        1243,
        395,
        "#f7f8f9"
      ],
      "caption": "Provider Dashboard: Clients"
    }
  ]
}
[/block]
Description of Client information:

1. Client ID: The Client ID is a unique identifier for each client. It must contain uppercase letters or numbers and use the following naming convention: ProviderID.Client, where Provider is the Provider ID, and Client is replaced by a meaningful name describing the Client. The Client ID can't be modified.
[block:callout]
{
  "type": "info",
  "title": "Example of Client ID",
  "body": "TIB.PANGAEA \nProvider ID = TIB (German National Library of Science and Technology)\nClient = PANGAEA - Data Publisher for Earth & Environmental Science"
}
[/block]
2. re3data Record: link to the corresponding record in the re3data registry of research data repositories (optional)
3. Client Name: name of the Client (i.e. the organization)
4. Contact Name: name of the technical person responsible for the account
5. Contact Email: email address for the technical contact. This email address receives reset password requests. (This address should also subscribe to the [All Users mailing list](doc:how-to-contact-datacite)).
6. Domains: by default a DOI can point to any URL, indicated by an asterix *** in the domain settings. To limit the list of domains that can be used to register URLs for a DOI, enter one or more domains or subdomains, separated by a comma.

## Edit Client Account

Providers are able to manage existing Client accounts. To edit a Client account:
1. Click on the name of the Client
2. Click on Client *Settings*
3. Click the *Edit Client* button
4. Update the Client information and click *Save* at the bottom of the record.
 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/45359a2-Provider_EditClient_Account.PNG",
        "Provider_EditClient_Account.PNG",
        821,
        637,
        "#e2e3dc"
      ],
      "border": true,
      "caption": "Provider Dashboard: Settings, Edit Client"
    }
  ]
}
[/block]
## Delete Client Account

To delete a Client account, click on the name of the Client and click on the *Delete Client* button. Enter the Client ID and click on the *Delete* button under the Client ID.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f5cffb2-Provider_DeleteClient_Account.PNG",
        "Provider_DeleteClient_Account.PNG",
        1116,
        351,
        "#d0d4d8"
      ],
      "border": true,
      "caption": "Provider Dashboard: Settings, Delete Client"
    }
  ]
}
[/block]
You can't delete a Client if there are associated DOIs. If you attempt to delete a Client that has associated DOIs, you will instead see the screen below, asking you to first transfer all DOIs to another client:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/21643e8-Bildschirmfoto_2017-11-07_um_09.54.31.png",
        "Bildschirmfoto 2017-11-07 um 09.54.31.png",
        2586,
        744,
        "#b9c2c7"
      ],
      "border": true,
      "caption": "Provider Dashboard: Settings, Delete Client"
    }
  ]
}
[/block]
Click on *Transfer DOIs* to initiate the DOI transfer, described [below](https://support.datacite.org/docs/datacite-doi-fabrica-for-providers#section-transfer-dois-to-another-client).
[block:api-header]
{
  "title": "Provider Dashboard: Prefixes"
}
[/block]
The DOI prefix is used as a namespace so DOIs are globally unique without requiring global coordination for each new identifier. All DOI prefixes are numbers without any semantic meaning. 

The *Prefixes* tab contains a list of all prefixes assigned to a Provider. To add a prefix, click the *Assign Prefix* button on the upper right. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bfbc58b-Prefixes_provider.PNG",
        "Prefixes_provider.PNG",
        956,
        593,
        "#cad3d0"
      ],
      "caption": "Provider Dashboard: Prefixes",
      "border": true
    }
  ]
}
[/block]
On the next screen, select an available prefix from the dropdown box and click the *Assign* button. If you don't see prefixes in the list, contact DataCite to [request additional prefixes](doc:request-more-prefixes-for-your-mds).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7f30405-Screen_Shot_2018-04-25_at_17.15.32.png",
        "Screen Shot 2018-04-25 at 17.15.32.png",
        982,
        331,
        "#f9fbfb"
      ],
      "border": true,
      "caption": "Provider Dashboard: Prefixes: Assign Prefix"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Provider Dashboard: DOIs"
}
[/block]
The *DOI* tab lists all the DOIs registered by all Clients associated with a Provider. Providers can view DOI information including author, version, publication year and publisher.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bbbd3e6-Provider_DOIstatistics.PNG",
        "Provider_DOIstatistics.PNG",
        1034,
        759,
        "#d9e1dc"
      ],
      "caption": "Provider Dashboard: DOIs registered by Clients",
      "border": true
    }
  ]
}
[/block]
Providers can use the search form to find an individual DOI. It is currently only possible to search by exact DOI. To take advantage of additional search fields and filtering, please use [DataCite Search](https://search.datacite.org).


## Transfer a single DOI to another Client

Providers can transfer DOIs between their Clients. When viewing the record for a single DOI, click the *Transfer DOI* button in the upper right to begin the process. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0b6f3e7-Screen_Shot_2018-04-25_at_17.30.35.png",
        "Screen Shot 2018-04-25 at 17.30.35.png",
        1190,
        683,
        "#f7fafa"
      ],
      "caption": "Provider Dashboard: DOIs: DOI record"
    }
  ]
}
[/block]
On the *Transfer DOI* screen, select the Client to which this DOI should be transferred and click the *Transfer* button to complete the transfer. You can only transfer DOIs to a Client you manage. Please [contact DataCite staff](mailto:support@datacite.org) if you want to transfer the DOI to a Client not managed by you. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/24830b0-Screen_Shot_2018-04-25_at_17.34.32.png",
        "Screen Shot 2018-04-25 at 17.34.32.png",
        1120,
        353,
        "#f8fbfb"
      ],
      "border": true,
      "caption": "Provider Dashboard: DOIs: Transfer DOI"
    }
  ]
}
[/block]
## Transfer all Client DOIs to another Client

Start the DOI transfer by clicking on the *Transfer DOIs* button in the *DOIs* screen of the Client.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c13de2d-Bildschirmfoto_2017-11-07_um_10.19.48.png",
        "Bildschirmfoto 2017-11-07 um 10.19.48.png",
        2746,
        944,
        "#28a8aa"
      ],
      "caption": "DOI tab: transfer DOI",
      "border": true
    }
  ]
}
[/block]
In the next screen, select the Client to which you want to transfer all Client DOIs. You can only transfer DOIs to a Client you manage, please contact DataCite staff if you want to transfer DOIs to a Client not managed by you. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0082dbe-Bildschirmfoto_2017-11-22_um_12.15.59.png",
        "Bildschirmfoto 2017-11-22 um 12.15.59.png",
        2078,
        894,
        "#2d7b84"
      ],
      "caption": "DOI tab: transfer DOIs to Client",
      "border": true
    }
  ]
}
[/block]
Click on *Transfer* to initiate the DOI transfer. The final screen will remind you that the DOI transfer is visible outside of DOI Fabrica (e.g. in DataCite Search) only complete after successful re-indexing, which can take up to 8 hours. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ea5951d-Bildschirmfoto_2017-11-22_um_12.17.58.png",
        "Bildschirmfoto 2017-11-22 um 12.17.58.png",
        2644,
        1074,
        "#49bb89"
      ],
      "caption": "DOI tab: initiate transfer",
      "border": true
    }
  ]
}
[/block]
## Transfer Client DOIs to multiple Clients

If you want to transfer DOIs to multiple Clients, you can either transfer each DOI [individually](#section-transfer-one-dois-to-another-client), or [ask DataCite staff](mailto:support@datacite.org) to manually do the DOI transfer for you.
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]