---
title: DataCite Profiles
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
Access the DataCite Profiles web interface here: [https://profiles.datacite.org](https://profiles.datacite.org) 
[block:api-header]
{
  "type": "basic",
  "title": "What is DataCite Profiles?"
}
[/block]
DataCite Profiles provides a single sign-on for all personalized DataCite services. 
[block:api-header]
{
  "type": "basic",
  "title": "Who can use DataCite profiles?"
}
[/block]
**Researchers** can connect their ORCID profiles and automatically update their ORCID record when their ORCID ID is included in the metadata of a newly registered DOI. 
[block:api-header]
{
  "type": "basic",
  "title": "Sign in"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cd773d0-Screen_Shot_2017-01-03_at_12.30.22.png",
        "Screen Shot 2017-01-03 at 12.30.22.png",
        2406,
        168,
        "#312516"
      ]
    }
  ]
}
[/block]
On top right of the page, you will find a 'Sign in' button. You can only interact with Profiles if you have signed in. 

Although different services for authentication are supported, the initial account setup requires linking your account with an [ORCID iD](https://orcid.org). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/984fe6f-Bildschirmfoto_2017-09-21_um_06.03.02.png",
        "Bildschirmfoto 2017-09-21 um 06.03.02.png",
        1374,
        1128,
        "#382c1e"
      ]
    }
  ]
}
[/block]
Click on your preferred sign in option. You will be redirected to log in or create an account, and to accept the DataCite Profiles connection. For example, if you are using ORCID, you will see the next screen: 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bda0571-Screen_Shot_2017-01-03_at_12.35.54.png",
        "Screen Shot 2017-01-03 at 12.35.54.png",
        1962,
        1170,
        "#405f73"
      ]
    }
  ]
}
[/block]
If you use our test services, you will be redirected to the [ORCID Sandbox](https://sandbox.orcid.org/signin). The login process is exactly the same, but you need to create an ORCID sandbox account even if you already have a regular ORCID account.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eacb3a8-Bildschirmfoto_2017-09-21_um_06.50.11.png",
        "Bildschirmfoto 2017-09-21 um 06.50.11.png",
        2698,
        1372,
        "#357c97"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Settings and Your Account"
}
[/block]
Once you have signed in, you can manage your profile from the top right of the page. There, you can access your Personal Settings, see all the DOIs linked to your ORCID ID in DataCite Search, jump to your ORCID record, or sign out.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/17bfe9c-Bildschirmfoto_2017-09-21_um_06.10.33.png",
        "Bildschirmfoto 2017-09-21 um 06.10.33.png",
        1312,
        656,
        "#3d2e1c"
      ]
    }
  ]
}
[/block]
Your Personal Settings page is divided into a maximum of four sections, depending on your type of profile. You can use the menu on the right to navigate them.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a804745-Bildschirmfoto_2017-09-21_um_06.18.53.png",
        "Bildschirmfoto 2017-09-21 um 06.18.53.png",
        2394,
        796,
        "#f3f3f3"
      ]
    }
  ]
}
[/block]
The first section (Your account) provides you an overview of your Profiles account. The information is automatically filled in from the external services (Google, ORCID, GitHub) connected to your account.
[block:api-header]
{
  "type": "basic",
  "title": "Social Login"
}
[/block]
Under Social Login you can connect and disconnect the different Sign in services supported. In this example, the account is:

- Not connected to Google: you can click the red button to connect
- Connected to ORCID: you can click the green button to expire the ORCID token
- Connected to Github: you can click the black button to unlink the Github account
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/94b56e4-Bildschirmfoto_2017-09-21_um_06.14.45.png",
        "Bildschirmfoto 2017-09-21 um 06.14.45.png",
        1870,
        596,
        "#f3f3f3"
      ]
    }
  ]
}
[/block]
The process is similar to the initial [Sign in](doc:datacite-profiles-user-documentation#section-sign-in). You will be redirected to log in or create an account, and to accept the DataCite Profiles connection.
[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "ORCID Claims"
}
[/block]
By connecting your ORCID iD to DataCite Profiles, you enable two different ways to synchronise information between the two services:

* ORCID Search & Link: where you can add works to your ORCID record manually from [DataCite Search](doc:datacite-search-user-documentation) 
* ORCID Auto-Update: every time a new DOI is registered with your ORCID iD in the metadata, your ORCID Record will be updated automatically.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/32531fb-Screen_Shot_2017-01-03_at_13.17.29.png",
        "Screen Shot 2017-01-03 at 13.17.29.png",
        2060,
        1072,
        "#eaf1ea"
      ]
    }
  ]
}
[/block]
Using the first box, you can access [DataCite Search](doc:datacite-search-user-documentation) directly to find your datasets and push them to your ORCID profile.

The second box provides you a button to enable or disable ORCID Auto-Update.

The last box displays basic stats on the number of records claimed by Search & Link and Auto-Update. By clicking 'More info' you can access the complete list of records claimed.
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]