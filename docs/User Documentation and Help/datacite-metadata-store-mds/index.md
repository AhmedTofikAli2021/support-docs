---
title: DataCite Metadata Store (MDS)
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
[block:callout]
{
  "type": "danger",
  "title": "Make the switch to DOI Fabrica",
  "body": "The MDS web interface is being retired in favor of DataCite DOI Fabrica. If you're a DataCite Provider or Client, you already have an account in DOI Fabrica using your MDS credentials. [Learn more about DOI Fabrica](doc:about-fabrica)"
}
[/block]
Access the DataCite Metadata Store (MDS) here: [https://mds.datacite.org](https://mds.datacite.org) 
[block:api-header]
{
  "type": "basic",
  "title": "What is the DataCite Metadata Store?"
}
[/block]
The DataCite Metadata Store, often called the MDS, is a service to manage activities related to Digital Object Identifier (DOI) registration at DataCite. The MDS is used to create, register, store and manage DOIs and associated metadata created by DataCite's users and members. Users with an MDS account can create, register, and manage DOIs and associated metadata for their records.
[block:api-header]
{
  "type": "basic",
  "title": "Who can use the DataCite Metadata Store?"
}
[/block]
There are two main users for the DataCite Metadata Store (MDS): 1) DataCite Providers and, 2) DataCite customers that have an account with a DataCite Member (DataCite Clients). 

1. If you are a DataCite Provider, you can create accounts, manage prefixes, set quotas and handle your Clients' activity. 

2. If you are a DataCite Client, you can register new DOIs, upload and update metadata and edit your account.
[block:api-header]
{
  "type": "basic",
  "title": "Architecture of the DataCite Metadata Store"
}
[/block]
The next model describes the underlying DataCite Metadata Store (MDS) structure:

```
Provider --> Client --> DOI --> Metadata
 |            ^
 |            |
`--> Prefix <--´
```

* A Provider has many Clients, while a Client belongs to only one Provider
* A Client has many DOIs, while a DOI belongs to only one Client
* A DOI has many Metadata versions, while a Metadata version belongs to only one DOI
* A Provider has many Prefixes, while a Prefix can belong to only one Provider and one or more of their Clients (with the exception of the test prefix, which is assigned to every Client regardless of Provider)
* A Client has many Prefixes, and those Prefixes must belong to the list of prefixes assigned to that Client's parent Provider
* A Prefix can belong to many Clients (but within only one Provider)

As a best practice, DataCite encourages its Providers to avoid shared Prefixes between Data Centers.
[block:api-header]
{
  "type": "basic",
  "title": "Login"
}
[/block]
Please log in using the link on the upper right link corner of the page:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a796885-image09.png",
        "image09.png",
        166,
        29,
        "#c5cccf"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
If you do not have an account, you will need to become a DataCite Provider or become a customer of an existing DataCite Member (DataCite Client).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ecea2ca-image12.png",
        "image12.png",
        349,
        214,
        "#dad9c9"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
If you don’t remember your password, you can obtain a new one using the ‘Forgotten password?’ link. You will have to provide us your symbol (account name).
[block:api-header]
{
  "type": "basic",
  "title": "Functionalities for Members and Users"
}
[/block]
If you are a Provider you can find the DataCite Metadata Store (MDS) documentation here: [MDS for Members](doc:mds-for-members-allocators)

If you are a Client you can find the DataCite Metadata Store (MDS) documentation here: [MDS for Users](doc:mds-for-users-datacentres)

[What is the difference between Members, Providers, and Clients?](doc:members-providers-and-clients)
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]