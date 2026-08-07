---
title: Field Descriptions for Form
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
The following metadata fields are available to create a DOI via the form in Fabrica:

  * DOI Field (required)
  * State Selection Field (required)
  * URL Field (required)
  * [Creators Field](doc:creators)  (required)
  * [Title Field](doc:title) (required)
  * Publisher (required)
  * Publication Year (required)
  * Resource Type General (required)
  * Resource Type (optional)
  * [Description](doc:description) (optional)

The form contains all metadata fields in the DataCite Metadata Schema that are designated as required, as well as the recommended Description field and free-text Resource Type field. Detailed descriptions of metadata requirements and field examples are included in the documentation for the [DataCite Metadata Schema](https://schema.datacite.org). 

For many of the fields, Fabrica will validate the entered information, and that field will subsequently turn green if the information is valid or red if it is not. You will be unable to save until you properly resolve any red fields. In the case of Draft DOIs, which require only the DOI to be saved, you will receive orange warning messages about potential problems instead of red validation errors, so you will not be prevented from saving. If you later update a Draft DOI to a different state, you will need to resolve any resulting red validation errors first. 
[block:api-header]
{
  "title": "DOI Field"
}
[/block]
The DOI field is where you set the DOI you would like to create. This field corresponds to the Identifier field in the DataCite Metadata Schema. 

First, select one of the available prefixes from the dropdown box on the left. 

A DOI name (the part that comes after the prefix) is auto-filled by default. To generate a new DOI name automatically, click the refresh icon on the right side of the DOI name field. Use the x icon on the far right to clear the contents of the DOI name field. You may also type and/or cut and paste your own DOI name into the field manually.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cf2c7b8-Screen_Shot_2019-04-23_at_18.02.26.png",
        "Screen Shot 2019-04-23 at 18.02.26.png",
        1175,
        528,
        "#fafafb"
      ]
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
        "https://files.readme.io/980862c-Screen_Shot_2019-04-23_at_18.03.59.png",
        "Screen Shot 2019-04-23 at 18.03.59.png",
        1201,
        614,
        "#fbfbfb"
      ],
      "caption": "Client Dashboard: DOIs, Create DOI (Form)"
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
        "https://files.readme.io/51a21dc-Screen_Shot_2019-04-23_at_18.05.16.png",
        "Screen Shot 2019-04-23 at 18.05.16.png",
        1163,
        645,
        "#f9fafa"
      ],
      "caption": "",
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Creators"
}
[/block]
See full details of the creators field [here](doc:creators).
[block:api-header]
{
  "title": "Title"
}
[/block]
See full details of the title field [here](doc:title).
[block:api-header]
{
  "title": "Publisher"
}
[/block]
Enter the name of the entity that holds, publishes, archives, issues, or produces the resource. This field is used to form the citation for the dataset, so consider which entity would be most appropriate. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ca668cd-Screen_Shot_2019-04-23_at_18.23.22.png",
        "Screen Shot 2019-04-23 at 18.23.22.png",
        1242,
        244,
        "#f9fcfb"
      ],
      "caption": "Client Dashboard: DOIs, Create DOI (Form)"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Publication Year"
}
[/block]
Enter the year when the resource was or will be made publicly available. The field accepts a valid year entry between 1450 and next year, with a rolling window for each subsequent year. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d650329-Screen_Shot_2019-04-23_at_18.25.11.png",
        "Screen Shot 2019-04-23 at 18.25.11.png",
        1217,
        250,
        "#f8fdfa"
      ],
      "caption": "Client Dashboard: DOIs, Create DOI (Form)"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Resource Type General"
}
[/block]
The general type of the resource. This is a controlled list as specified in the [DataCite Metadata Schema](https://schema.datacite.org). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a65ad4-Screen_Shot_2019-04-23_at_18.25.51.png",
        "Screen Shot 2019-04-23 at 18.25.51.png",
        1307,
        608,
        "#f9fcfb"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Resource Type"
}
[/block]
This is an optional field. You may include a short free-text description of the resource type. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e1366b6-Screen_Shot_2019-04-23_at_18.34.25.png",
        "Screen Shot 2019-04-23 at 18.34.25.png",
        1309,
        566,
        "#fafdfb"
      ],
      "caption": "Client Dashboard: DOIs, Create DOI (Form)"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Description"
}
[/block]
See full details of the description field [here](doc:description). 
[block:callout]
{
  "type": "info",
  "title": "Would you like to know more?",
  "body": "If you have any questions, requests or ideas please [contact us.](doc:how-to-contact-datacite)"
}
[/block]