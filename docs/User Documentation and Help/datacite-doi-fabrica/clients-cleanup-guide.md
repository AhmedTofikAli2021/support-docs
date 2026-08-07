---
title: Client Cleanup and Deletion Guide
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
You can use DOI Fabrica to delete your Clients. There are two scenarios in which a Provider can delete Clients using DOI Fabrica. 

- **Scenario 1**: Delete Clients with no DOIs registrations
- **Scenario 2**: Delete Clients where DOIs registration occurred. DOIs are moved to another Client managed by the same provider.

This guide covers the steps for these scenarios. There are only two steps for Clients cleanup. First, transfer DOIs if they exist. Second, delete the client. These steps are described in detail below.

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
You can't delete a Client if there are associated DOIs. When you click on *Delete Client*, you will instead see the screen below, asking you to first transfer all DOIs to another client:

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


[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]