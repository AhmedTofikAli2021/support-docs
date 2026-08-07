---
title: Fabrica Dashboard
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
## About the Fabrica dashboard

Each DataCite account type has access to different functions through the DataCite Fabrica dashboard, which is organized into tabs.

| Section                                               | Direct Member | Consortium Lead | Consortium Organization | Repository |
| :---------------------------------------------------- | :------------ | :-------------- | :---------------------- | :--------- |
| [Info](#info)                                         | ✅             | ✅               | ✅                       | ✅          |
| [Settings](#settings)                                 | ✅             | ✅               | ✅                       | ✅          |
| [Contacts](#contacts)                                 | ✅             | ✅               | ✅                       | :x:        |
| [Repositories](#repositories)                         | ✅             | ✅               | ✅                       | :x:        |
| [Prefixes](#prefixes)                                 | ✅             | ✅               | ✅                       | ✅          |
| [DOIs](#dois)                                         | ✅             | ✅               | ✅                       | ✅          |
| [Consortium Organizations](#consortium-organizations) | :x:           | ✅               | :x:                     | :x:        |

## Info

The _Info_ tab includes charts showing:

- The number of DOIs created this year and over time.
- _For Direct Members, Consortium Leads, and Consortium Organizations:_ The number of Repositories created this year and over time.
- _For Consortium Leads_: The number of Consortium Organizations created this year and over time.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/136e332-Screenshot_2023-01-25_at_13.46.24.png",
        "Screenshot 2023-01-25 at 13.46.24.png",
        2812
      ],
      "align": "center",
      "sizing": "650px",
      "border": true,
      "caption": "Info tab for a Direct Member account"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/317d57d-Screenshot_2023-01-25_at_13.52.12.png",
        "Screenshot 2023-01-25 at 13.52.12.png",
        2824
      ],
      "align": "center",
      "sizing": "650rt",
      "border": true,
      "caption": "Info tab for a Consortium Lead account"
    }
  ]
}
[/block]


For Repository accounts, the "Create DOI" button is also accessible from this tab.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/60e8592-Screenshot_2023-01-25_at_11.49.29.png",
        "Screenshot 2023-01-25 at 11.49.29.png",
        1536
      ],
      "align": "center",
      "sizing": "500px",
      "border": true,
      "caption": "Info tab for a Repository account"
    }
  ]
}
[/block]


## Settings

On the _Settings_ tab, you can [set the account password](doc:reset-fabrica-password#section-if-you-are-already-logged-in) and update account information. This information is used in various DataCite services, including the [member listing](https://www.datacite.org/members) on our website.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9494ee1-Screenshot_2023-01-25_at_12.48.13.png",
        "Screenshot 2023-01-25 at 12.48.13.png",
        1950
      ],
      "align": "center",
      "sizing": "500px",
      "border": true,
      "caption": "Settings tab for a Direct Member account"
    }
  ]
}
[/block]


For more information, see [Settings in DataCite Fabrica](doc:fabrica-settings).

## Contacts

The _Contacts_ tab lists all of your contacts. The contact Name, Email, Roles and Date Created are displayed here. Click the "Add Contact" button on the left to add new organizational contacts.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6627d3f-Screenshot_2023-01-25_at_12.49.09.png",
        "Screenshot 2023-01-25 at 12.49.09.png",
        "Contacts tab for a Direct Member account"
      ],
      "align": "center",
      "sizing": "500px",
      "caption": "Contacts tab for a Direct Member account"
    }
  ]
}
[/block]


For more information, see [Contacts in DataCite Fabrica](doc:fabrica-contacts).

## Repositories

The _Repositories_ tab lists Repositories under the account. The Repository information including the Repository ID and system email can be viewed here.

To search for an individual Repository, enter the Repository name or the Repository ID in the search box and click Search. The default sorting order for Repositories is by Name and can be changed to Date Joined or Relevance. Results can be filtered by Year joined, Type, Repository Type, and Software.

Direct Members and Consortium Organizations can [create a Repository](doc:fabrica-repositories#create-a-repository) from this page by clicking “Add Repository”. Consortium Leads should first navigate to a specific Consortium Organization via the _Consortium Organizations_ tab.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0f80fbd-Screenshot_2023-01-25_at_12.53.24.png",
        "Screenshot 2023-01-25 at 12.53.24.png",
        1954
      ],
      "align": "center",
      "sizing": "500px",
      "border": true,
      "caption": "Repositories tab for a Direct Member account"
    }
  ]
}
[/block]


For more information, see [Repositories in DataCite Fabrica](doc:fabrica-repositories).

## Prefixes

The [DOI prefix](doc:doi-basics#prefix) is used as a namespace so DOIs are globally unique without requiring global coordination for each new identifier. All DOI prefixes are numbers without any semantic meaning. 

The _Prefixes_ tab contains a list of all prefixes assigned to the account. A new prefix is assigned automatically when you [create a Repository](doc:fabrica-repositories#create-a-repository).

> 📘 
> 
> We recommend one prefix per Repository. Create a new Repository account if a new prefix is required.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/12eb82f-Screenshot_2023-01-25_at_12.55.44.png",
        "Screenshot 2023-01-25 at 12.55.44.png",
        1924
      ],
      "align": "center",
      "sizing": "500px",
      "border": true,
      "caption": "Prefixes tab for a Direct Member account"
    }
  ]
}
[/block]


For more information, see [Prefixes in DataCite Fabrica](doc:fabrica-prefixes).

## DOIs

The _DOIs_ tab lists the DOIs registered under the account. This list can be sorted by Date Updated (default), Date Created, DOI, Alphabetically, or Relevance.

You can filter DOIs using the facets on the left, including State, Resource Type, Year created, Repository, Prefix, Schema Version, and Link Check Status. The search bar can be used to find an individual DOI.

From the _DOIs_ tab, Repository accounts can [create a DOI via a form](doc:fabrica-doi-form#create-a-doi), [create a DOI via file upload](doc:fabrica-doi-file-upload#create-a-doi), [update a DOI](doc:fabrica-doi-form#update-a-doi), or [delete Draft records](doc:fabrica-delete-doi). **Only Repository accounts can create and update DOIs through Fabrica.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3b7f766-Screenshot_2023-01-25_at_13.08.07.png",
        "Screenshot 2023-01-25 at 13.08.07.png",
        2800
      ],
      "align": "center",
      "sizing": "800px",
      "border": true,
      "caption": "DOIs tab for a Direct Member account"
    }
  ]
}
[/block]


For more information, see [DOIs in DataCite Fabrica](doc:fabrica-dois).

### Export DOI Metadata

You can [export DOI metadata](doc:export-doi-metadata) from the _DOIs_ tab. Click “Export DOI Metadata” to export a CSV file containing the basic metadata of the DOIs in the list.

Only the 25 records on the page view will be exported. To export more records, scroll through to the next page.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e5c291c-Screenshot_2023-01-25_at_13.02.25.png",
        "Screenshot 2023-01-25 at 13.02.25.png",
        ""
      ],
      "align": "center",
      "sizing": "500px",
      "border": true
    }
  ]
}
[/block]


## Consortium Organizations

For Consortium Lead accounts, the _Consortium Organizations_ tab lists all of the organizations under your Consortium. To search for an individual Consortium Organization, enter the name or the ID of the Consortium Organization in the search box and click Search. The default sorting order is by Name and can be changed to Date Joined or Relevance. Results can be filtered by Year joined.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/53933a6-Screenshot_2023-01-25_at_13.53.21.png",
        "Screenshot 2023-01-25 at 13.53.21.png",
        "Consortium Organizations tab for a Consortium Lead account"
      ],
      "align": "center",
      "sizing": "500px",
      "border": true,
      "caption": "Consortium Organizations tab for a Consortium Lead account"
    }
  ]
}
[/block]


For more information, see [Consortium Organizations in DataCite Fabrica](doc:fabrica-consortium-organizations).