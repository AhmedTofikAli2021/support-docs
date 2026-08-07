---
title: Client Dashboard
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
When Clients log in to Fabrica, they are presented with the Fabrica dashboard. The dashboard is the central hub for all activities related to DataCite's DOI Registration Service. From the dashboard, Clients can manage Settings and DOIs, and view a list of their available Prefixes. 
[block:api-header]
{
  "title": "Client Dashboard: Info"
}
[/block]
The *Info* page is the first page presented to Clients after login and gives an overview of account information and includes the name of the Client and the total number of DOIs. Clients can also view the total number of DOIs by year by hovering over the graph. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7e8d4ee-Bildschirmfoto_2018-01-31_um_13.07.00.png",
        "Bildschirmfoto 2018-01-31 um 13.07.00.png",
        2196,
        996,
        "#fcfdfd"
      ],
      "caption": "Client Dashboard: Info",
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Client Dashboard: Settings"
}
[/block]
The *Settings* tab contains the Client ID, re3data ID with related repository information, technical contact information and the allowed domains for DOI landing pages. Information on when the record was created and last updated is in the lower right-hand corner. 

From the *Settings* tab, you can [reset the Client password](doc:reset-fabrica-password#section-if-you-are-already-logged-in), [update Client settings](doc:fabrica-update-client), or [delete a Client](doc:fabrica-delete-client).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6a7b341-Bildschirmfoto_2018-01-31_um_13.11.32.png",
        "Bildschirmfoto 2018-01-31 um 13.11.32.png",
        2776,
        1290,
        "#f4f8f7"
      ],
      "caption": "Client Dashboard: Settings",
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Client Dashboard: Prefixes"
}
[/block]
The DOI prefix is used as a namespace so DOIs are globally unique without requiring global coordination for each new identifier. All DOI prefixes are numbers without any semantic meaning. 

The *Prefixes* tab contains a list of all prefixes assigned to your Client account including the date they have been added. By default, every Client is assigned the demo prefix 10.5072, and your Provider will typically assign each Client at least one additional prefix. If you require additional prefixes, please contact your Provider. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3638e9e-Bildschirmfoto_2018-01-31_um_13.09.25.png",
        "Bildschirmfoto 2018-01-31 um 13.09.25.png",
        2112,
        1136,
        "#fcfdfd"
      ],
      "border": true,
      "caption": "Client Dashboard: Prefixes"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Client Dashboard: DOIs"
}
[/block]
The *DOIs* tab lists all the DOIs registered by the Client. Clients can view DOI information including author, version, publication year, publisher and licensing data.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4f235fd-Bildschirmfoto_2018-01-31_um_13.10.01.png",
        "Bildschirmfoto 2018-01-31 um 13.10.01.png",
        2160,
        1212,
        "#f9fbfc"
      ],
      "border": true,
      "caption": "Client Dashboard: DOIs"
    }
  ]
}
[/block]
Clients can use the search form to find an individual DOI. It is currently only possible to search by exact DOI. To take advantage of additional search fields and filtering, please use [DataCite Search](https://search.datacite.org).

From the DOIs tab, Clients can [create a DOI via a form](doc:fabrica-create-doi-form), [create a DOI via file upload](doc:fabrica-create-doi-file-upload), [update a DOI](doc:fabrica-update-doi), or [delete a Draft DOI](doc:fabrica-delete-doi). 
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]