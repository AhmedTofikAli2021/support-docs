---
title: Create a Client in Fabrica Test
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
Providers have the authority and discretion to create and manage test accounts for their Clients. These test accounts are entirely separate from the production accounts the Clients might otherwise have. The number of Client test accounts you have will not affect your total number of accounts for billing purposes. 
[block:api-header]
{
  "title": "Create a Client account"
}
[/block]
Creating a Client in the test instance of Fabrica is nearly identical to creating a Client in the production instance of Fabrica. 

First, navigate to the test instance of Fabrica at https://doi.test.datacite.org and login with your Provider test account credentials. 
[block:callout]
{
  "type": "warning",
  "title": "Make sure to login with the correct credentials!",
  "body": "The credentials for your test account are entirely separate from the credentials for your production account. If you're experiencing errors, please first ensure you're authenticating with the correct set of credentials."
}
[/block]
Go to the Clients tab of the Provider dashboard and click the *Create Client* button on the left. Fill in the requested details and click *Save* at the bottom of the record. A system email with the Client ID and a link to set up a password will automatically be sent to the contact email that you specified in the Client settings.

For detailed explanations of each field, see [Field Descriptions for Client Settings](doc:fields-client-settings).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e6c3ab4-Screenshot_2018-11-16_at_14.38.56.png",
        "Screenshot 2018-11-16 at 14.38.56.png",
        997,
        520,
        "#fafcfc"
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
After you create the Client test account, you need to assign a prefix to it in order for it to be usable. Assigning a prefix in the test instance of Fabrica is nearly identical to assigning a prefix in the production instance of Fabrica. 

If you have just created a Client, you will still have the Client view of the dashboard on your screen, so remember to switch back to your Provider dashboard by following the breadcrumbs at the top of the page. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4eadd85-Screenshot_2018-11-16_at_14.47.41.png",
        "Screenshot 2018-11-16 at 14.47.41.png",
        613,
        228,
        "#f3f6f6"
      ],
      "border": true,
      "caption": "Click your Provider name to return to the Provider dashboard after creating a Client"
    }
  ]
}
[/block]
Go to the Prefixes tab of your Provider dashboard. Click the *Assign Prefix* button on the left. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a3f3d2e-Screenshot_2018-11-16_at_14.51.17.png",
        "Screenshot 2018-11-16 at 14.51.17.png",
        587,
        341,
        "#fafcfb"
      ],
      "border": true,
      "caption": "Provider dashboard: Prefixes"
    }
  ]
}
[/block]
In this step, you are claiming a prefix from DataCite's available pool to assign to your Provider account. Select an available prefix from the dopdown and click *Assign Prefix* to assign that prefix to your Provider account. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0c7e4dd-Screenshot_2018-11-16_at_14.53.51.png",
        "Screenshot 2018-11-16 at 14.53.51.png",
        712,
        394,
        "#f9fbfb"
      ],
      "border": true,
      "caption": "Provider dashboard: Prefixes: Assign Prefix"
    }
  ]
}
[/block]
You'll see that now the prefix is added to your Provider account. This means it is now part of your available pool to assign to Clients, **but it has not yet been assigned to a Client**. 

To assign the prefix to a Client, first select the Client you would like to give the prefix to by going to the Clients tab on your Provider dashboard and clicking on the Client's name. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6ad12f7-Screenshot_2018-11-16_at_15.16.26.png",
        "Screenshot 2018-11-16 at 15.16.26.png",
        694,
        536,
        "#fafbfb"
      ],
      "border": true,
      "caption": "Provider dashboard: Clients"
    }
  ]
}
[/block]
Now you're in the Client's view of the dashboard. Go to the Prefixes tab. You'll see all the prefixes currently assigned to that Client, if there are any. If you have an available unassigned prefix in your pool, the *Assign Prefix* button will appear on the left. Click the *Assign Prefix* button to go to the prefix assignment screen. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d2aa479-Screenshot_2018-11-16_at_15.15.34.png",
        "Screenshot 2018-11-16 at 15.15.34.png",
        687,
        560,
        "#fafcfc"
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
        "https://files.readme.io/65fb2d1-Screenshot_2018-11-16_at_15.19.24.png",
        "Screenshot 2018-11-16 at 15.19.24.png",
        645,
        455,
        "#f8fbfc"
      ],
      "border": true,
      "caption": "Client dashboard: Prefixes: Assign Prefix"
    }
  ]
}
[/block]
The prefix will now show up in the list of prefixes assigned to that Client. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/826b7ff-Screenshot_2018-11-16_at_15.21.20.png",
        "Screenshot 2018-11-16 at 15.21.20.png",
        669,
        533,
        "#fafcfc"
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
  "body": "A prefix must first be assigned to the Provider and then to the Client. Make sure you have gone through both prefix assignment actions."
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Your prefixes in test are different from your prefixes in production",
  "body": "The production system and the test system are separate, as are your accounts in both systems. This means that your prefix list in the test system will be different from your prefix list in the production system, so you won't be able to create DOIs in the test system using your normal prefix of choice. Since the DOIs you create in the test system aren't real and don't resolve, having different prefixes doesn't matter."
}
[/block]

[block:api-header]
{
  "title": "Next Steps"
}
[/block]
The Client test account is now ready to use. The Client can create and manage DOIs in the test instances of all DataCite services. These services are: 
* DOI Fabrica (https://doi.test.datacite.org)
* REST API (https://api.test.datacite.org)
* MDS API (https://mds.test.datacite.org)
* EZ API (https://ez.test.datacite.org)

To learn more about using the test system, see: 
* [Testing in DOI Fabrica](docs:testing-in-doi-fabrica)
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]