---
title: Metadata Store (MDS) for Users (Data centers)
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
  "title": "MDS UI deprecated",
  "body": "The MDS user interface (the human-readable portal at https://mds.datacite.org) has been retired as of December 1, 2018 in favor of DataCite DOI Fabrica. The MDS UI no longer exists. These help pages are now historical. \n\nIf you're a DataCite Provider or Client, you already have an account in DOI Fabrica using your MDS credentials. [Learn more about DOI Fabrica](doc:about-fabrica)\n\nThis change does not affect the [MDS API](doc:mds-api-guide), which is still available through the https://mds.datacite.org endpoint."
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Dataset Management: Register New Dataset"
}
[/block]
You can create a new DOI for your dataset from your left menu: 'Register new Dataset'.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ccf59d5-image00.png",
        "image00.png",
        707,
        105,
        "#e6e6e6"
      ]
    }
  ]
}
[/block]
 In the form, fill in the next fields:

1. DOI: Fill the new DOI name you want to mint. 
2. URL: Provide the URL of the landing page of the object.
3. XML upload: Choose an XML containing the metadata description of the object. Only files following the DataCite Metadata Schema will be allowed. Please check the [DataCite Metadata Schema Documentation](doc:schema-40) for the current version of the DataCite Metadata Schema.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2d3b71c-Screen_Shot_2016-12-28_at_11.29.20.png",
        "Screen Shot 2016-12-28 at 11.29.20.png",
        1164,
        735,
        "#dddede"
      ]
    }
  ]
}
[/block]
When you hit ‘Save’ the request will be sent and the form will be evaluated. If all the information provided is correct, a new DOI will be minted. Be aware that it can take up to 24 hours until a DOI update is globally known. New DOIs should be resolvable after about 5 minutes.

[block:api-header]
{
  "type": "basic",
  "title": "Dataset Management: Modify a Dataset"
}
[/block]
If you want to update the DOI pointing to one of your datasets you can do it using the DataCite Metadata Store (MDS). First, you will have to locate the dataset by Listing all your datasets using the Find by DOI functionality on your left menu:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/18c695d-image07.png",
        "image07.png",
        229,
        130,
        "#ebebeb"
      ]
    }
  ]
}
[/block]
The list of results will look like this:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2a3063b-image00.png",
        "image00.png",
        707,
        105,
        "#e6e6e6"
      ]
    }
  ]
}
[/block]
Use the binoculars icon to preview the DOI information, and access the edit and update functions.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/245e8c7-Screen_Shot_2016-12-28_at_11.25.04.png",
        "Screen Shot 2016-12-28 at 11.25.04.png",
        1980,
        854,
        "#d8d8d8"
      ]
    }
  ]
}
[/block]
Once you preview a DOI entry, you can use the Yellow pencil button on the bottom right of the first box to edit the dataset's DOI. You will see the same submission form you had when you [registered the dataset](doc:mds-for-users-datacentres#section-dataset-management-register-new-dataset). You can now update the URL and/or metadata.
[block:callout]
{
  "type": "info",
  "body": "If you have any questions, requests or ideas please [contact us!](doc:how-to-contact-datacite)",
  "title": "Would you like to know more?"
}
[/block]