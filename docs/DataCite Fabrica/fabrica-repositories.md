---
title: Repositories in DataCite Fabrica
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
Direct Members, Consortium Leads, and Consortium Organizations can create new Repository accounts and manage existing accounts.

> 📘 Access the Repositories tab in DataCite Fabrica
> 
> Direct Members, Consortium Leads, and Consortium Organizations can access the _Repositories_ tab in DataCite Fabrica. Repository accounts don't have this tab.

## Create a Repository

- **Direct Members and Consortium Organizations**: Create a Repository from the _Repositories_ tab by clicking “Add Repository”. 
- **Consortium Leads**: Before creating a Repository, navigate to a specific Consortium Organization via the _Consortium Organizations_ tab. Then, go to the _Repositories_ tab to create Repositories for that specific Consortium Organization.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a220eb4-Screen_Shot_2021-03-30_at_14.32.14.png",
        "Screen Shot 2021-03-30 at 14.32.14.png",
        ""
      ],
      "align": "center",
      "sizing": "800px",
      "border": true
    }
  ]
}
[/block]


Fill in the requested details and click "Add Repository" at the bottom of the record. For detailed descriptions of each field, see [Repository Settings](doc:fabrica-settings#repository-settings). 

> 📘 Required fields
> 
> To create a new Repository account you will need to enter the minimum required information:
> 
> - The Repository name
> - The system email contact
> - The type of software from the drop-down list (choose "Other" if your software is not listed)
> 
> We recommend including other information about the Repository like the description and URL, which will appear in DataCite Commons, for example: <https://commons.datacite.org/repositories/8orcn81>

An email with the Repository ID and a link to set up a password will be sent to the system email specified in the Repository settings.

### Automatic prefix assignment

Once the new Repository has been created, a prefix is automatically assigned. The same prefix is also linked with the associated Direct Member or Consortium Organization account.

[block:embed]
{
  "html": false,
  "url": "https://datacite.org/wp-content/uploads/2026/03/Create_repo_2026_1.gif",
  "title": null,
  "favicon": null,
  "image": "https://datacite.org/assets/prefix_2.gif",
  "provider": "datacite.org",
  "href": "https://datacite.org/wp-content/uploads/2026/03/Create-repo-2026.mov",
  "height": "400",
  "width": "600%",
  "iframe": true
}
[/block]


A message will appear in the _Settings_ tab showing the prefix that has been assigned to the new Repository.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/095c2ef-Screenshot_2022-07-13_at_13.00.25.png",
        "Screenshot 2022-07-13 at 13.00.25.png",
        ""
      ],
      "align": "center",
      "sizing": "800px",
      "border": true
    }
  ]
}
[/block]


> 📘 Additional prefixes
> 
> Fabrica will automatically assign just one prefix to a newly created Repository account. To request additional prefixes, send an email to [support@datacite.org](mailto:support@datacite.org). We recommend [one prefix per Repository account](doc:how-many-prefixes-should-i-have-per-repository-account-in-fabrica).

To see the prefix assigned to a Repository, click on the _Prefixes_ tab.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/035501f-Screenshot_2022-07-13_at_13.01.03.png",
        "Screenshot 2022-07-13 at 13.01.03.png",
        ""
      ],
      "align": "center",
      "sizing": "800px",
      "border": true
    }
  ]
}
[/block]


## Delete a Repository

Direct Members, Consortium Leads, and Consortium Organizations can delete empty Repositories. If the Repository contains registered DOIs, you must first [transfer the DOIs](doc:fabrica-transfer-dois) to another Repository.

Once remaining DOIs have been transferred, go to the _Repositories_ tab of the dashboard. Select the Repository to go to the Repository dashboard.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9ae4cf6-Screen_Shot_2021-03-30_at_14.33.29.png",
        "Screen Shot 2021-03-30 at 14.33.29.png",
        2634
      ],
      "align": "center",
      "sizing": "800px",
      "border": true
    }
  ]
}
[/block]


Go to the _Settings_ tab and click the "Delete" button on the left. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b6afe4b-Screen_Shot_2019-10-10_at_14.01.20.png",
        "Screen Shot 2019-10-10 at 14.01.20.png",
        1302
      ],
      "align": "center",
      "sizing": "500px",
      "border": true
    }
  ]
}
[/block]


Type the Repository ID in the box to confirm and click "Delete". This action cannot be undone.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9f54ed8-Screen_Shot_2019-10-10_at_14.02.36.png",
        "Screen Shot 2019-10-10 at 14.02.36.png",
        1235
      ],
      "align": "center",
      "sizing": "800px",
      "border": true
    }
  ]
}
[/block]


> 🚧 Repositories with DOIs can't be deleted
> 
> You will not be able to delete a Repository that contains DOIs. When you click "Delete", you will instead see a warning asking you to first transfer all DOIs to another Repository:
> 
> [block:image]{"images":[{"image":["https://files.readme.io/ec2e9e6-Screen_Shot_2019-10-10_at_14.04.12.png","Screen Shot 2019-10-10 at 14.04.12.png",1385],"align":"center","border":true}]}[/block]
> 
> Click "Transfer DOIs" to initiate the DOI transfer. See [Transfer DOIs Between Repositories](doc:fabrica-transfer-dois) for more information.