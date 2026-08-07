---
title: DataCite DOI Fabrica for Clients
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
  "type": "info",
  "title": "See Also",
  "body": "[What is the difference between Members, Providers, and Clients?](doc:members-providers-and-clients) \n[DOI Fabrica account creation](doc:datacite-doi-fabrica#section-how-to-create-a-doi-fabrica-account)\n[Demo accounts](doc:demo-account)"
}
[/block]

[block:api-header]
{
  "title": "Client Dashboard: Info"
}
[/block]
When Clients log in to Fabrica, they are presented with the Fabrica dashboard. The dashboard is the central hub for all activities related to DataCite's DOI Registration Service. From the dashboard, Clients can manage Settings and DOIs, and see their Prefixes. 

The *Info* page is the first page presented to Clients after login and gives an overview of account information and includes the name of the Client and the total number of DOIs. Clients can also view the total number of DOIs by year by hovering over the graph. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7e8d4ee-Bildschirmfoto_2018-01-31_um_13.07.00.png",
        "Bildschirmfoto 2018-01-31 um 13.07.00.png",
        2196,
        996,
        "#fcfdfd"
      ],
      "caption": "Client Dashboard: Info",
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Client Dashboard: Settings"
}
[/block]
The *Settings* tab contains the Client ID, re3data ID with related repository information, technical contact information and the allowed domains for DOI landing pages. Information on when the record was created and last updated is in the lower right-hand corner. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6a7b341-Bildschirmfoto_2018-01-31_um_13.11.32.png",
        "Bildschirmfoto 2018-01-31 um 13.11.32.png",
        2776,
        1290,
        "#f4f8f7"
      ],
      "caption": "Client Dashboard: Settings",
      "border": true
    }
  ]
}
[/block]
### Set Password

To set a new password, click on the *Set Password* button on the right. Passwords must be at least 8 characters long and can be suggested by DOI Fabrica to provide better security. Click submit after entering the same new password in both the **New Password** and **Confirm Password** input fields.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1504858-FabricaDeleteStep3.png",
        "FabricaDeleteStep3.png",
        1269,
        362,
        "#f9fcfa"
      ],
      "border": true,
      "caption": "Client Dashboard: Settings, Set Password"
    }
  ]
}
[/block]
### Edit Client Settings

To modify the Client settings:
1. Click on the *Edit Client* button in the upper right of the Client Settings page. 
2. Make changes to the Client information.
3. Click *Save* at the bottom of the record. 

**Note:** The Client ID cannot be changed.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/56b5471-Client_Edit_Settings.PNG",
        "Client_Edit_Settings.PNG",
        1232,
        710,
        "#e6ebeb"
      ],
      "caption": "Client Dashboard: Settings, Edit Client",
      "border": true
    }
  ]
}
[/block]
Description of Client information:

1. Client ID: The Client ID is a unique identifier for each client. It must contain uppercase letters or numbers and use the following naming convention: Provider ID.Client, where Provider is the Provider ID, and Client is replaced by a meaningful name describing the Client. The Client ID can't be modified.
[block:callout]
{
  "type": "info",
  "body": "TIB.PANGAEA \nProvider ID = TIB (German National Library of Science and Technology)\nClient = PANGAEA - Data Publisher for Earth & Environmental Science",
  "title": "Example of Client ID"
}
[/block]
2. re3data Record: link to the corresponding record in the re3data registry of research data repositories (optional)
3. Client Name: name of the client
4. Contact Name: name of the technical person responsible for the account.
5. Contact Email: email address for the technical contact. This email address receives reset password requests. (This address should also subscribe to the [All Users mailing list](doc:how-to-contact-datacite)). 
6. Domains: by default a DOI can point to any URL, indicated by an asterix *** in the domain settings. To limit the list of domains that can be used to register URLs for a DOI, enter one or more domains or subdomains, separated by a comma.
[block:api-header]
{
  "title": "Client Dashboard: Prefixes"
}
[/block]
The DOI prefix is used as a namespace so DOIs are globally unique without requiring global coordination for each new identifier. All DOI prefixes are numbers without any semantic meaning. 

The *Prefixes* tab contains a list of all prefixes assigned to your Client account including the date they have been added. By default, every Client is assigned the demo prefix 10.5072, and your Provider will typically assign each Client at least one additional prefix. If you require additional prefixes, please contact your Provider. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3638e9e-Bildschirmfoto_2018-01-31_um_13.09.25.png",
        "Bildschirmfoto 2018-01-31 um 13.09.25.png",
        2112,
        1136,
        "#fcfdfd"
      ],
      "border": true,
      "caption": "Client Dashboard: Prefixes"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Client Dashboard: DOIs"
}
[/block]
The *DOIs* tab lists all the DOIs registered by the Client. Clients can view DOI information including author, version, publication year, publisher and licensing data.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4f235fd-Bildschirmfoto_2018-01-31_um_13.10.01.png",
        "Bildschirmfoto 2018-01-31 um 13.10.01.png",
        2160,
        1212,
        "#f9fbfc"
      ],
      "border": true,
      "caption": "Client Dashboard: DOIs"
    }
  ]
}
[/block]
Clients can use the search form to find an individual DOI. It is currently only possible to search by exact DOI. To take advantage of additional search fields and filtering, please use [DataCite Search](https://search.datacite.org).

### Creating DOIs

Clients can create DOIs from within the *DOIs* tab. 

First, click the orange *Create DOI (File Upload)* button on the right side of the page. **Note:** The *Create DOI (Form)* functionality is not yet released. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/da93618-Screen_Shot_2018-05-01_at_08.34.44.png",
        "Screen Shot 2018-05-01 at 08.34.44.png",
        1346,
        462,
        "#f8f9fa"
      ],
      "caption": "Client Dashboard: DOIs",
      "border": true
    }
  ]
}
[/block]
You will be taken to the DOI registration screen. An automatically-generated DOI is pre-filled for you. If you would like to change the prefix, you may select one of your available prefixes from the dropdown box on the left. 

**Note:** The prefix 10.5072 is a demo prefix. DOIs created with this prefix can only be saved in Draft form, which means they are only visible within DOI Fabrica and can be deleted. [Learn more about states](doc:about-states-in-datacite-doi-fabrica)
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/88c7b8d-Screen_Shot_2018-05-01_at_08.41.57.png",
        "Screen Shot 2018-05-01 at 08.41.57.png",
        975,
        594,
        "#f8f9f9"
      ],
      "caption": "Client Dashboard: DOIs, Add DOI",
      "border": true
    }
  ]
}
[/block]
You may also change the DOI name (the string of characters that follows the prefix). To generate a new DOI name automatically, click the refresh icon on the right side of the DOI name field. Use the x icon on the far right to clear the contents of the DOI name field. You may also type and/or cut and paste your own DOI name into the field manually. 

Select a state for the DOI you'd like to register. Draft DOIs are only visible within DOI Fabrica and can be deleted. Registered DOIs will be made public via registration in the Handle System. Findable DOIs will be registered via the Handle System and will also be included in DataCite search. 


[block:callout]
{
  "type": "warning",
  "body": "DOIs will be indexed into DataCite Search, 8 or 24 hrs after being created in DOI Fabrica.",
  "title": "When would I be able to see the DOIs I created in DataCite Search?"
}
[/block]
**Note:** DOIs with the test prefix 10.5072 can only be saved in Draft form.  
[Learn more about states](doc:about-states-in-datacite-doi-fabrica)
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bfbf711-Screen_Shot_2018-05-01_at_08.44.43.png",
        "Screen Shot 2018-05-01 at 08.44.43.png",
        979,
        607,
        "#f9fafa"
      ]
    }
  ]
}
[/block]
Enter the URL of the landing page that the DOI points to. DOI Fabrica will verify that the URL will resolve. If the URL does resolve, the field will turn green. If it does not resolve, the field will turn red and display an error message.  If you don't understand an error message, please [contact us](doc:how-to-contact-datacite). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/794b210-Screen_Shot_2018-05-01_at_08.46.01.png",
        "Screen Shot 2018-05-01 at 08.46.01.png",
        977,
        609,
        "#f7faf9"
      ],
      "caption": "Client Dashboard: DOIs, Add DOI",
      "border": true
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3d73ea2-Screen_Shot_2018-05-01_at_08.48.16.png",
        "Screen Shot 2018-05-01 at 08.48.16.png",
        993,
        602,
        "#f9f9f9"
      ],
      "caption": "Client Dashboard: DOIs, Add DOI",
      "border": true
    }
  ]
}
[/block]
Enter metadata about this DOI in the **Metadata** field. You may upload a metadata file by clicking the *Upload File* button above the **Metadata** field. You may upload a file in any of the following formats: 
* XML 
* JSON (either citeproc, schema.org, or codemeta formats) 
* bibTeX 
* RIS

These are the same formats as in DOI content negotiation. All metadata will be converted to DataCite XML after you save the DOI record. [Learn more about supported content types](doc:doi-content-negotiation#section-supported-content-types) 

If the metadata is valid, the field will turn green. The field will turn orange as a warning if the input cannot be validated.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9430d94-Screen_Shot_2018-05-01_at_08.50.49.png",
        "Screen Shot 2018-05-01 at 08.50.49.png",
        994,
        768,
        "#f4f9f7"
      ],
      "caption": "Client Dashboard: DOIs, Add DOI",
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "danger",
  "body": "In the case of a mismatch, the DOI in the metadata will be replaced by the DOI that appears in the DOI field at the top of the Create DOI page."
}
[/block]
Finally, click the *Create DOI* button at the bottom of the page. Your DOI will be saved in DOI Fabrica, and the record page for the DOI will be displayed.


### Updating DOIs

Clients can update the metadata for any of their registered DOIs. This is especially helpful for DOIs that were originally saved in a Draft state. [Learn more about states](doc:about-states-in-datacite-doi-fabrica)

From the DOIs tab on the Client Dashboard, select the DOI you want to update. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3eaf9e5-Screen_Shot_2018-05-01_at_08.58.26.png",
        "Screen Shot 2018-05-01 at 08.58.26.png",
        1310,
        590,
        "#f6f6f7"
      ],
      "border": true,
      "caption": "Client Dashboard: DOIs"
    }
  ]
}
[/block]
In the upper right corner, click the *Update DOI (File Upload)* button. If the DOI is currently in the Draft state, you will also have the option to delete the DOI. [Learn more about states](doc:about-states-in-datacite-doi-fabrica)

**Note:** The *Update DOI (Form)* functionality is not yet released.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2bd1ac6-Screen_Shot_2018-05-01_at_09.02.47.png",
        "Screen Shot 2018-05-01 at 09.02.47.png",
        1317,
        714,
        "#f7f9f9"
      ],
      "caption": "Client Dashboard: DOIs, selected DOI",
      "border": true
    }
  ]
}
[/block]
On the Update DOI screen, you can see all of the currently entered metadata for the DOI. You may add or update a URL, or you may add or update metadata. Metadata can be edited directly in the **Metadata** field, or you can upload a file of one of the supported types. The DOI itself cannot be changed.

You may also update the state of the DOI. Draft DOIs can be updated to be either Registered or Findable. Registered DOIs can be updated to be Findable, and Findable DOIs may be updated to be Registered. Neither Registered nor Findable DOIs may be returned to the Draft state. This means that updating a Draft DOI to another state is final. [Learn more about states](doc:about-states-in-datacite-doi-fabrica)
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bed5ec4-Screen_Shot_2018-05-01_at_09.04.41.png",
        "Screen Shot 2018-05-01 at 09.04.41.png",
        1329,
        789,
        "#f8fafa"
      ],
      "caption": "Client Dashboard: DOIs, Edit DOI",
      "border": true
    }
  ]
}
[/block]
### Deleting DOIs

It is possible to delete a Draft DOI. First, select the Draft DOI you would like to delete from the list of DOIs on the *DOIs* tab in the client dashboard. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a0c5a09-Screen_Shot_2018-05-01_at_08.34.44.png",
        "Screen Shot 2018-05-01 at 08.34.44.png",
        1346,
        462,
        "#f8f7f7"
      ],
      "border": true,
      "caption": "Client dashboard: DOIs"
    }
  ]
}
[/block]
On the DOI record screen, click the *Delete DOI* button. **Note:** The *Delete DOI* button is only available for Draft DOIs. Registered and Findable DOIs cannot be deleted. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/09c4e66-Screen_Shot_2018-05-01_at_09.11.50.png",
        "Screen Shot 2018-05-01 at 09.11.50.png",
        1323,
        572,
        "#f7f8f8"
      ],
      "caption": "Client dashboard: DOIs, selected DOI"
    }
  ]
}
[/block]
You will be asked to confirm DOI deletion by re-entering the DOI to be deleted. You may cut and paste the DOI into the provided field. Click the *Delete* button to finalize deletion. DOI deletion cannot be undone. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4448247-Screen_Shot_2018-05-01_at_09.13.19.png",
        "Screen Shot 2018-05-01 at 09.13.19.png",
        1240,
        384,
        "#f9fcfa"
      ],
      "caption": "Client dashboard: DOIs, Delete DOI"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]