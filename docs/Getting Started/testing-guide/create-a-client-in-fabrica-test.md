---
title: Create a Repository in Fabrica Test
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
Members Consortium and Consortium Organization accounts have permission to create and manage test accounts for their Repositories. These test accounts are entirely separate from the production accounts the Repositories might otherwise have.


[block:callout]
{
  "type": "warning",
  "body": "DOIs you create in the test system aren't real and don't resolve.",
  "title": "Remember"
}
[/block]

[block:api-header]
{
  "title": "Create a Repository"
}
[/block]
Creating a Repository in the test instance of Fabrica is identical to creating a Repository in the production instance of Fabrica. 

First, navigate to the test instance of Fabrica at https://doi.test.datacite.org and login with your Member test account credentials. 
[block:callout]
{
  "type": "warning",
  "title": "Make sure to login with the correct credentials!",
  "body": "The credentials for your test account are entirely separate from the credentials for your production account. If you're experiencing errors, please first ensure you're authenticating with the correct set of credentials."
}
[/block]
Go to the Repository tab of the Member dashboard and click the *Create Repository* button on the left. Fill in the requested details and click *Save* at the bottom of the record. A system email with the Repository ID and a link to set up a password will automatically be sent to the system email that you specified in the Repository settings.

For detailed explanations of each field, see [Field Descriptions for Repository Settings](doc:fields-client-settings).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3ced5a5-Screen_Shot_2019-10-03_at_13.54.58.png",
        "Screen Shot 2019-10-03 at 13.54.58.png",
        1100,
        506,
        "#fbfcfd"
      ],
      "caption": "Provider Dashboard: Clients",
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Assign a prefix"
}
[/block]
After you create the Repository test account, you need to assign a prefix to it in order for it to be usable. Assigning a prefix in the test instance of Fabrica is nearly identical to assigning a prefix in the production instance of Fabrica. 

If you have just created a Repository, you will still have the Repository view of the dashboard on your screen, so remember to switch back to your Member dashboard by following the breadcrumbs at the top of the page. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2908a1f-Screen_Shot_2019-10-04_at_11.39.58.png",
        "Screen Shot 2019-10-04 at 11.39.58.png",
        477,
        162,
        "#f9fbfb"
      ],
      "border": true,
      "caption": "Click your Provider name to return to the Provider dashboard after creating a Client"
    }
  ]
}
[/block]
Go to the Prefixes tab of your Member dashboard. Click the *Assign Prefix* button on the left. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/acb1a56-Screen_Shot_2019-10-04_at_11.42.08.png",
        "Screen Shot 2019-10-04 at 11.42.08.png",
        994,
        434,
        "#fcfcfc"
      ],
      "border": true,
      "caption": "Provider dashboard: Prefixes"
    }
  ]
}
[/block]
In this step, you are claiming a prefix from DataCite's available pool to assign to your Member account. Select an available prefix from the drop down and click *Assign Prefix* to assign that prefix to your Member account. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1b3a9d0-Screen_Shot_2019-10-04_at_11.42.50.png",
        "Screen Shot 2019-10-04 at 11.42.50.png",
        1100,
        416,
        "#fbfcfc"
      ],
      "border": true,
      "caption": "Provider dashboard: Prefixes: Assign Prefix"
    }
  ]
}
[/block]
You'll see that now the prefix is added to your Member account. This means it is now part of your available pool to assign to Repositories, **but it has not yet been assigned to a Repository**. 

To assign the prefix to a Repository, first select the Repository you would like to give the prefix to by going to the Repositories tab on your Member dashboard and clicking on the name of the Repository. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7e4b62c-Screen_Shot_2019-10-04_at_11.45.24.png",
        "Screen Shot 2019-10-04 at 11.45.24.png",
        1094,
        399,
        "#fbfcfc"
      ],
      "border": true,
      "caption": "Provider dashboard: Clients"
    }
  ]
}
[/block]
Now you're in the Repository view of the dashboard. Go to the Prefixes tab. You'll see all the prefixes currently assigned to that Repository, if there are any. If you have an available unassigned prefix in your pool, the *Assign Prefix* button will appear on the left. Click the *Assign Prefix* button to go to the prefix assignment screen. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/41b26d6-Screen_Shot_2019-10-04_at_11.47.41.png",
        "Screen Shot 2019-10-04 at 11.47.41.png",
        1100,
        373,
        "#fcfdfd"
      ],
      "border": true,
      "caption": "Client dashboard: Prefixes"
    }
  ]
}
[/block]
Select the prefix from the dropdown that you want to assign, and click the *Assign Prefix* 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8beb51b-Screen_Shot_2019-10-04_at_11.48.15.png",
        "Screen Shot 2019-10-04 at 11.48.15.png",
        1106,
        368,
        "#fafcfc"
      ],
      "border": true,
      "caption": "Client dashboard: Prefixes: Assign Prefix"
    }
  ]
}
[/block]
The prefix will now show up in the list of prefixes assigned to that Repository. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c30e331-Screen_Shot_2019-10-04_at_11.48.55.png",
        "Screen Shot 2019-10-04 at 11.48.55.png",
        1090,
        542,
        "#fbfdfd"
      ],
      "border": true,
      "caption": "Client dashboard: Prefixes"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Don't forget to assign the prefix twice!",
  "body": "A prefix must first be assigned to the Member and then to the Repository. Make sure you have gone through both prefix assignment actions."
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Your prefixes in test are different from your prefixes in production",
  "body": "The production system and the test system are separate, as are your accounts in both systems. This means that your prefix list in the test system will very likely be different from your prefix list in the production system, so you won't necessarily be able to create DOIs in the test system using your normal prefix of choice. Since the DOIs you create in the test system aren't real and don't resolve, having different prefixes doesn't matter."
}
[/block]

[block:api-header]
{
  "title": "Next Steps"
}
[/block]
The Repository test account is now ready to use. The Repository can create and manage DOIs in the test instances of all DataCite services. These services are: 
* DOI Fabrica (https://doi.test.datacite.org)
* REST API (https://api.test.datacite.org)
* MDS API (https://mds.test.datacite.org)

To learn more about using the test system, see: 
* [Testing in DOI Fabrica](docs:testing-in-doi-fabrica)
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]