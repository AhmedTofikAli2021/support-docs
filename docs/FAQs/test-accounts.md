---
title: Test Accounts
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
[block:callout]
{
  "type": "danger",
  "title": "Our test accounts have recently changed",
  "body": "Throughout November 2018, we will be in the process of transitioning existing users from \"demo accounts\" to \"test accounts\" where appropriate. Please bear with us as as this transition takes place."
}
[/block]
Test accounts allow users to try out DataCite services in a safe sandbox environment. A test account allows you to configure your systems to automatically register and manage DOIs via one of our APIs or to try out the latest functionality in DOI Fabrica without the risk of creating live DOIs. 
[block:callout]
{
  "type": "warning",
  "title": "Please note:",
  "body": "Test accounts are in a separate test system and are NOT in our live production system. While you can perform all the same tasks in the test system as in the production system, nothing you do in the test system will result in a live DOI."
}
[/block]

[block:api-header]
{
  "title": "Requesting a test account"
}
[/block]
If you are an existing Client of a DataCite Provider, please contact your Provider to request a test account. If you are a Provider, a test account will be created for you as part of your onboarding. 

If you are not yet a DataCite Provider or Client, please contact DataCite support at [support@datacite.org](mailto:support@datacite.org) to request a test account. 
[block:api-header]
{
  "title": "Set up your test account"
}
[/block]
After your request is handled by the relevant party, you will receive an automatically generated e-mail from the test instance of DOI Fabrica containing a *Generate a password* link. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/afc05a2-Email.PNG",
        "Email.PNG",
        1150,
        163,
        "#f7faf9"
      ]
    }
  ]
}
[/block]
Clicking on *Generate a password* takes you to the *Set Password* page. You can set your own password or have one automatically suggested for you.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5768f9b-SetPassword.PNG",
        "SetPassword.PNG",
        1284,
        564,
        "#396c90"
      ]
    }
  ]
}
[/block]
Clicking on *Submit* will set the password and will take you to the *Sign in* page. Click on the *Sign in* button in the upper right corner of your screen and enter your *Account ID* and the password. You will find your Account ID in the same system e-mail as the password link. 
[block:callout]
{
  "type": "info",
  "body": "* DOI Fabrica (https://doi.test.datacite.org)\n* REST API (https://api.test.datacite.org)\n* MDS API (https://mds.test.datacite.org)\n* EZ API (https://ez.test.datacite.org)",
  "title": "The same test account credentials work for the test instances of:"
}
[/block]

[block:api-header]
{
  "title": "Create and Manage DOIs"
}
[/block]
A test account allows all the same DOI registration functionality of the regular DataCite systems, but none of the DOIs created are "live" or "real" in any way. They are only visible to those with access to your account, as well as to DataCite staff. 

For detailed information on how to register and manage DOIs via the DOI Fabrica interface, please see [DataCite DOI Fabrica for Clients](doc:datacite-doi-fabrica-for-clients).

For detailed information on working with our APIs for Members, please see the [DataCite REST API Guide](doc:api), [DataCite MDS API Guide](doc:mds-2), or the [DataCite EZ API Guide](doc:datacite-ez-api-guide). Remember that your test account works with the test instances of these APIs, which will have URLs with the form `*.test.datacite.org`. 
[block:callout]
{
  "type": "danger",
  "title": "Make sure to login with the correct credentials!",
  "body": "The credentials for your test account are entirely separate from the credentials for your production account. If you're experiencing errors, please first ensure you're authenticating with the correct credentials."
}
[/block]