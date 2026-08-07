---
title: Update a DOI
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
Repositories can update the metadata for any of their registered DOIs. This is especially helpful for DOIs that were originally saved in a Draft state. [Learn more about states](doc:doi-states) 

From the DOIs tab on the Repository Dashboard, select the DOI you want to update. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f716108-Screenshot_2019-04-26_at_13.15.12.png",
        "Screenshot 2019-04-26 at 13.15.12.png",
        1092,
        430,
        "#f7f7f7"
      ],
      "border": true,
      "caption": ""
    }
  ]
}
[/block]
Once the DOI is selected, in the upper left corner, click either the *Update DOI via Form* button or the *Update DOI via File Upload* button, depending on your preference. If the DOI is currently in the Draft state, you will also have the option to [delete the DOI](doc:fabrica-delete-doi) 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ff2171d-Screenshot_2019-04-26_at_13.14.52.png",
        "Screenshot 2019-04-26 at 13.14.52.png",
        1091,
        459,
        "#f6f7f7"
      ],
      "caption": "",
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Updating DOIs with older schema using the DOI Form",
  "body": "The DOI Form will update the metadata schema to the latest version when the DOI is in an older schema version."
}
[/block]
Whichever method you choose, you will be able to add or update the URL, the metadata, and the state of the DOI. The DOI name itself cannot be changed. 

For detailed explanations of each field, see either [Field Descriptions for the File Upload Screen](doc:fields-file-upload) or [Field Descriptions for the Form Screen](doc:field-descriptions-for-form).
[block:callout]
{
  "type": "info",
  "body": "There is no validation step for Draft DOIs. Metadata validation only happens when a DOI is saved in  Registered or Findable state. If there are problems then validation errors will be shown in the Form or File Upload.",
  "title": "A note about validation"
}
[/block]
Draft DOIs can be updated to be either Registered or Findable. Registered DOIs can be updated to be Findable, and Findable DOIs may be changed back to Registered. Neither Registered nor Findable DOIs may be returned to the Draft state. This means that updating a Draft DOI to another state is final. [Learn more about states](doc:doi-states) 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f973994-Screenshot_2019-04-26_at_13.18.36.png",
        "Screenshot 2019-04-26 at 13.18.36.png",
        914,
        537,
        "#f9fafa"
      ],
      "caption": "",
      "border": true
    }
  ]
}
[/block]
Once you've filled in the appropriate fields, click the *Update DOI* button at the bottom of the page. Your changes will be saved in DOI Fabrica, and the record page for the DOI will be displayed.
[block:callout]
{
  "type": "warning",
  "title": "When will the DOIs I updated show up in DataCite Search?",
  "body": "DOIs will be indexed into DataCite Search within 15 minutes after being updated in DOI Fabrica."
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Would you like to know more?",
  "body": "If you have any questions, requests or ideas please [contact us.](doc:how-to-contact-datacite)"
}
[/block]