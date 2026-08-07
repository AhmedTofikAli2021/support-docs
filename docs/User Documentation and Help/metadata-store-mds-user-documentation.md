---
title: DataCite Metadata Store (MDS)
excerpt: User Documentation
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
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
There are two main users for the DataCite Metadata Store (MDS): 1) DataCite Members (or Allocators) and, 2) DataCite customers that have an account with a DataCite Member (DataCite Users). 

1. If you are a DataCite Member (Allocator), you can create accounts, manage prefixes, set quotas and handle your Users' activity. 

2. If you are a customer of a DataCite Customer, you can register new DOIs, upload and update metadata and edit your account.
[block:api-header]
{
  "type": "basic",
  "title": "Architecture of the DataCite Metadata Store"
}
[/block]
The next model describes the underlying DataCite Metadata Store (MDS) structure:

```
Allocating Member --> Data Center --> DOI --> Metadata
   |                        ^
   |                        |
   `-------> Prefix <-------´
```

* An Allocating Member has many Data Centers, a Data Center belongs to only one Allocator Member
* A Data Center has many DOIs, a DOI belongs to only one Data Center
* A DOI has many Metadata versions, a Metadata version belongs to only one DOI
* An Allocating Member has many Prefixes, a Prefix can belong to only one Allocating Member and one or more of their Data Centers (with the exception of the test prefix)
* A Data Center has many Prefixes and they must belong to the list of prefixes assigned to Data Center's Allocating Member
* A Prefix can belong to many Data Centers (but within only one Allocating Member)

As a best practice, DataCite encourages its Allocating Members to avoid shared Prefixes between Data Centers.
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
If you do not have an account, you will need to become a DataCite Member or become a customer of an existing DataCite Member (DataCite User).
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
If you are a Member (Allocator) you can find the DataCite Metadata Store (MDS) documentation here: [MDS for Members](doc:mds-for-members-allocators)

If you are a User (Data Centre) you can find the DataCite Metadata Store (MDS) documentation here: [MDS for Users](doc:mds-for-users-datacentres)

[What is the difference between a Member and a User?](doc:what-is-the-difference-between-members-and-users)
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]