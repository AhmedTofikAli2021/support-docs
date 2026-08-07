---
title: Getting a test account
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
All test versions of DataCite services require test account credentials (an Account ID and password). This is a separate set of credentials from DataCite production service credentials. 

Just like with our production services, there are two levels of credentials for the test system: a Repository account allows you to create and manage DOIs, and a Member account allows you to create and manage Repositories. 
[block:api-header]
{
  "title": "Request a test account"
}
[/block]
DataCite staff will create test accounts for Members during onboarding. The Member will then have the authority and responsibility for creating test accounts for their Repositories. 

If you are a Repository of a DataCite Member, please contact your Member to request a test account. 

DataCite staff can also create test accounts for potential members who have not yet joined. If you are considering membership and would like a test account, please contact DataCite support at support@datacite.org. 
[block:api-header]
{
  "title": "Set up your test account"
}
[/block]
After your test account has been created, either by your Member or by DataCite staff, you will receive an automated email from the test instance of DOI Fabrica containing a *Generate password* link.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9ca7a8f-afc05a2-Email.PNG",
        "afc05a2-Email.PNG",
        1150,
        163,
        "#f7faf9"
      ],
      "border": true,
      "caption": "Password generation email from Fabrica Test"
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
        "https://files.readme.io/a03af13-5768f9b-SetPassword.PNG",
        "5768f9b-SetPassword.PNG",
        1284,
        564,
        "#396c90"
      ],
      "border": true,
      "caption": "Password setting page in Fabrica Test"
    }
  ]
}
[/block]
Clicking on *Submit* will set the password and will take you to the *Sign in* page. Click on the *Sign in* button in the upper right corner of your screen and enter your Account ID and the password. You will find your Account ID in the same system e-mail as the password link. 
[block:api-header]
{
  "title": "Use your test account"
}
[/block]
The same test account credentials work for all DataCite services that have a test instance. These test services will have "test" in the URL. These test services are: 
* DOI Fabrica (https://doi.test.datacite.org)
* REST API (https://api.test.datacite.org)
* MDS API (https://mds.test.datacite.org)
* EZ API (https://ez.test.datacite.org)