---
title: Field Descriptions for File Upload
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
The following are descriptions of each field on the DOI registration screen in file upload mode. 

For all the fields, Fabrica will validate the entered information, and that field will subsequently turn green if the information is valid or red if it is not. You will be unable to save until you properly resolve any red fields. In the case of Draft DOIs, which require only the DOI to be saved, you will receive orange warning messages about potential problems instead of red validation errors, so you will not be prevented from saving. If you later update a Draft DOI to a different state, you will need to resolve any resulting red validation errors first. 
[block:api-header]
{
  "title": "DOI Field"
}
[/block]
The DOI field is where you set the DOI you would like to create. 

First, select one of your available prefixes from the dropdown box on the left. 

A DOI name (the part that comes after the prefix) is auto-filled for you by default. To generate a new DOI name automatically, click the refresh icon on the right side of the DOI name field. Use the x icon on the far right to clear the contents of the DOI name field. You may also type and/or cut and paste your own DOI name into the field manually.
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

[block:api-header]
{
  "title": "State Selection Field"
}
[/block]
Use the state selection radio buttons to select a state for the DOI. 

Draft DOIs are only visible within DOI Fabrica and can be deleted. Registered DOIs will be made public via registration in the Handle System. Findable DOIs will be registered via the Handle System and will also be included in DataCite search. 

[Learn more about states](doc:doi-states) 
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

[block:api-header]
{
  "title": "URL Field"
}
[/block]
Enter the URL of the landing page that the DOI points to. 

The URL must be fully formed, as in `https://www.datacite.org` instead of `datacite.org`. URLs containing `https://` are encouraged. 

DOI Fabrica will verify that the URL will resolve. If the URL does resolve, the field will turn green. If it does not resolve, the field will turn red and display an error message.  If you don't understand an error message, please [contact us](doc:how-to-contact-datacite). 
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

[block:api-header]
{
  "title": "Metadata Field"
}
[/block]
Enter metadata about this DOI in the **Metadata** field. 

You may upload a metadata file by clicking the *Upload File* button above the **Metadata** field. You may upload a file in any of the following formats: 
* XML 
* JSON (either citeproc, schema.org, or codemeta formats) 
* bibTeX 
* RIS

These are the same formats as in DOI content negotiation. All metadata will be converted to DataCite XML after you save the DOI record. [Learn more about supported content types](doc:doi-content-negotiation#section-supported-content-types) 

Alternatively, you may type or cut and paste metadata directly into the metadata field if you would like more fine-grained control. 

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
  "body": "In the case of a mismatch, the DOI in the metadata will be replaced by the DOI that appears in the DOI field at the top of the page."
}
[/block]
##Automatic metadata harvesting
It is also possible to harvest metadata automatically from either a landing page that uses  [schema.org](http://schema.org) or from a software repository that uses [codemeta](https://codemeta.github.io/). In either case, you may enter the URL of the landing page or software repository by itself in the metadata field. When the DOI is saved, Fabica will automatically retrieve the metadata from the landing page or software repository and use it to populate the DOI record.
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us.](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]