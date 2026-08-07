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
The following are descriptions of each field in the DOI registration form. 

The form contains all metadata fields in the DataCite Metadata Schema that are designated as required, as well as the recommended Description field and free-text Resource Type field. Detailed descriptions of metadata requirements and field examples are included in the [DataCite Metadata Schema](https://schema.datacite.org) itself. 

For many of the fields, Fabrica will validate the entered information, and that field will subsequently turn green if the information is valid or red if it is not. You will be unable to save until you properly resolve any red fields. In the case of Draft DOIs, which require only the DOI to be saved, you will receive orange warning messages about potential problems instead of red validation errors, so you will not be prevented from saving. If you later update a Draft DOI to a different state, you will need to resolve any resulting red validation errors first. 
[block:api-header]
{
  "title": "DOI Field"
}
[/block]
The DOI field is where you set the DOI you would like to create. This field corresponds to the Identifier field in the DataCite Metadata Schema. 

First, select one of your available prefixes from the dropdown box on the left. **Note:** The prefix 10.5072 is a demo prefix. DOIs created with this prefix can only be saved in Draft form, which means they are only visible within DOI Fabrica and can be deleted. [Learn more about states](doc:doi-states) 

A DOI name (the part that comes after the prefix) is auto-filled for you by default. To generate a new DOI name automatically, click the refresh icon on the right side of the DOI name field. Use the x icon on the far right to clear the contents of the DOI name field. You may also type and/or cut and paste your own DOI name into the field manually.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ecc2621-Screen_Shot_2018-05-29_at_18.46.17.png",
        "Screen Shot 2018-05-29 at 18.46.17.png",
        942,
        621,
        "#f8f9f9"
      ],
      "caption": "Client Dashboard: DOIs, Create DOI (Form)",
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

**Note:** DOIs with the test prefix 10.5072 can only be saved in Draft form.  
[Learn more about states](doc:doi-states) 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d62e182-Screen_Shot_2018-05-29_at_18.47.35.png",
        "Screen Shot 2018-05-29 at 18.47.35.png",
        949,
        626,
        "#f8f9f9"
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
        "https://files.readme.io/a4b8066-Screen_Shot_2018-05-29_at_18.48.18.png",
        "Screen Shot 2018-05-29 at 18.48.18.png",
        942,
        711,
        "#f8faf9"
      ],
      "caption": "Client Dashboard: DOIs, Create DOI (Form)",
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
In the Creators field, enter the names of the people who have created the data the DOI points to. These are typically the main researchers involved in producing the data or the authors (in the case of a publication). 

Please enter one name per line. Personal names should be entered in "Family Name, Given Name" format, as in "Smith, John". Corporate names are also acceptable. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9e883de-Screen_Shot_2018-05-29_at_18.49.30.png",
        "Screen Shot 2018-05-29 at 18.49.30.png",
        968,
        578,
        "#f8faf9"
      ],
      "caption": "Client Dashboard: DOIs, Create DOI (Form)"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Title"
}
[/block]
Enter the title of the item the DOI describes, such as the title of a dataset or publication. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e374f7b-Screen_Shot_2018-05-29_at_18.54.12.png",
        "Screen Shot 2018-05-29 at 18.54.12.png",
        1023,
        614,
        "#f7fbf9"
      ],
      "caption": "Client Dashboard: DOIs, Create DOI (Form)"
    }
  ]
}
[/block]

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
        "https://files.readme.io/f48fec9-Screen_Shot_2018-05-29_at_19.09.59.png",
        "Screen Shot 2018-05-29 at 19.09.59.png",
        1018,
        613,
        "#f8fbfa"
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
        "https://files.readme.io/5052785-Screen_Shot_2018-05-29_at_19.12.07.png",
        "Screen Shot 2018-05-29 at 19.12.07.png",
        1028,
        570,
        "#f8fcfa"
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
        "https://files.readme.io/28da84c-Screen_Shot_2018-05-29_at_19.18.12.png",
        "Screen Shot 2018-05-29 at 19.18.12.png",
        1023,
        741,
        "#f8fafa"
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
        "https://files.readme.io/cb02038-Screen_Shot_2018-05-29_at_19.18.54.png",
        "Screen Shot 2018-05-29 at 19.18.54.png",
        1009,
        687,
        "#fafcfb"
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
This is an optional field. You may provide a free-text description of the resource that includes whatever additional information does not belong in the previous fields. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/03c10f0-Screen_Shot_2018-05-29_at_19.22.41.png",
        "Screen Shot 2018-05-29 at 19.22.41.png",
        993,
        665,
        "#f9fbfa"
      ],
      "caption": "Client Dashboard: DOIs, Create DOI (Form)"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Would you like to know more?",
  "body": "If you have any questions, requests or ideas please [contact us.](doc:how-to-contact-datacite)"
}
[/block]