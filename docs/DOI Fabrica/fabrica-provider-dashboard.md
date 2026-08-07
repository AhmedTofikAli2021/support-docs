---
title: Provider Dashboard
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
When Providers log in to Fabrica, they are presented with the Provider dashboard. From the homepage, Providers can manage Settings, Clients, Prefixes, and DOIs.
[block:api-header]
{
  "title": "Provider Dashboard: Info"
}
[/block]
The *Info* tab gives an overview of the Provider's account information. The two charts display the total number of Client accounts and the total number of DOIs created in the current year across all of the Provider's Clients. Providers can also view the total number of Clients and DOIs by year by hovering over the charts. 
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

[block:api-header]
{
  "title": "Provider Dashboard: Prefixes"
}
[/block]
The DOI prefix is used as a namespace so DOIs are globally unique without requiring global coordination for each new identifier. All DOI prefixes are numbers without any semantic meaning. 

The *Prefixes* tab contains a list of all prefixes assigned to a Provider. From this tab, you can [assign additional prefixes](doc:fabrica-assign-prefixes).
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
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]