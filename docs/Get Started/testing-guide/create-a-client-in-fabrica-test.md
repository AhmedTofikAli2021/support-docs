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
Members, Consortium leads and Consortium Organization accounts have permission to create and manage test accounts for their Repositories. These test accounts are entirely separate from the production system.

## Create a Repository

Creating a Repository in the test instance of Fabrica is identical to creating a Repository in the production instance of Fabrica. Please refer to the main [Fabrica guide](doc:doi-fabrica) for detailed information about Fabrica and the different types of accounts.

Navigate to the test instance of Fabrica at <https://doi.test.datacite.org> and log in with your Member/Consortium Lead or Consortium Organization test account credentials. 

> 📘 Make sure to login with the correct credentials!
> 
> Your Member credentials for your test account are entirely separate from the credentials for your production account. If you're experiencing errors, please first ensure you're authenticating with the correct set of credentials.

Go to the "Repositories" tab of the Member dashboard and click the _Add Repository_ button on the left. Fill in the requested details and click _Add Repository_ at the bottom of the record. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b43e02-Screenshot_2023-01-06_at_10.30.08.png",
        "Screenshot 2023-01-06 at 10.30.08.png",
        1618
      ],
      "align": "center",
      "border": true,
      "caption": "Repositories tab"
    }
  ]
}
[/block]


A prefix is automatically assigned to the new Repository account.

![](https://files.readme.io/29cc629-Screenshot_2023-01-06_at_10.17.56.png "Screenshot 2023-01-06 at 10.17.56.png")

An automated email with the Repository ID and a link to set up a password will be sent to the system email that you specified in the Repository settings.

> 📘 Log in with your Repository account to create test DOIs!
> 
> Now you have created your new Repository use the Repository ID + Password to log in to Fabrica and create some test DOIs.

For detailed explanations of each field, see [Field Descriptions for Repository Settings](doc:fields-client-settings).

> 🚧 Your prefixes in test are different from your prefixes in production
> 
> The production system and the test system are separate, as are your accounts in both systems. This means that your prefix in the test system will very likely be different from your prefix in the production system. You won't be able to create DOIs in the test system using your normal prefix of choice. Since the DOIs you create in the test system aren't real and don't resolve, having different prefixes doesn't matter.

## Next Steps

The Repository test account is now ready to use. The Repository can create and manage DOIs in the test instances of all DataCite services. These services are: 

- Fabrica (<https://doi.test.datacite.org>)
- REST API (<https://api.test.datacite.org>)
- MDS API (<https://mds.test.datacite.org>)

> 📘 Would you like to know more?
> 
> If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)