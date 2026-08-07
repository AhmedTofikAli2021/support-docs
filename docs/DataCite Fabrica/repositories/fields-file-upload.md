---
title: Field Descriptions for File Upload
excerpt: ''
deprecated: false
hidden: true
link:
  new_tab: false
  url: https://support.datacite.org/docs/fabrica-doi-file-upload#field-descriptions
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Repositories can register DOIs and update metadata using the File Upload in DataCite Fabrica.

Detailed descriptions of metadata requirements and field examples are included in the [DataCite Metadata Schema](https://schema.datacite.org) documentation.

### DOI

The DOI field is where you set the DOI you would like to create. This field corresponds to the [Identifier](https://datacite-metadata-schema.readthedocs.io/en/4/properties/identifier/) property in the DataCite Metadata Schema.

The [DOI prefix](doc:doi-basics#prefix) is automatically populated. If your Repository has more than one prefix, select one of the available prefixes from the dropdown box on the left. 

By default, a [DOI suffix](doc:doi-basics#suffix) is randomly generated. To randomly generate a new suffix, click the refresh icon to the right of the DOI field. Use the "X" icon on the right to clear the contents. You can also manually specify a suffix in this field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/88c7b8d-Screen_Shot_2018-05-01_at_08.41.57.png",
        "Screen Shot 2018-05-01 at 08.41.57.png",
        975
      ],
      "align": "center",
      "sizing": "800px",
      "border": true
    }
  ]
}
[/block]


> ❗️ The DOI field takes precedence over the `<identifier>` property
> 
> In the case of a mismatch, the DOI in the metadata will be replaced by the DOI that appears in the DOI field at the top of the page.

### State

Use the state selection radio buttons to select a [DOI state](doc:doi-states).

- **Draft** records are not yet registered within the global Handle System, which means the identifier can be deleted. Draft records require only the identifier number in order to be created or saved. It is not necessary to enter a valid URL or valid metadata when creating a Draft.
- **Registered** DOIs are registered with the global Handle System. However, metadata for Registered DOIs is not openly available.
- **Findable** DOIs are registered within the global Handle System. Metadata for Findable DOIs is openly available and indexed in DataCite’s APIs and DataCite Commons.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bfbf711-Screen_Shot_2018-05-01_at_08.44.43.png",
        "Screen Shot 2018-05-01 at 08.44.43.png",
        979
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### URL

Enter the URL of the landing page that the DOI points to. 

The URL must be fully formed, as in `https://www.datacite.org` instead of `datacite.org`. URLs containing `https://` are encouraged. 

Fabrica will verify that the URL is within the [allowed domains for your repository](docs:update-repository-settings#domains). If the URL is allowed, the field will turn green. If the URL is not allowed, the field will turn red and display an error message.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/77bccb5-Screenshot_2023-01-26_at_10.06.38.png",
        "Screenshot 2023-01-26 at 10.06.38.png",
        2120
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Metadata

#### Upload a file or copy and paste

Upload metadata by clicking "Upload File" or adding a complete metadata record to the text box.

The following formats are accepted:

- XML 
- JSON (either citeproc, schema.org, or codemeta formats) 
- bibTeX 
- RIS

All metadata will be converted to DataCite XML after you save the DOI record. For more information, see [What formats can I use to submit metadata?]\(<https://support.datacite.org/docs/what-formats-can-i-use-to-submit-my-metadata-and-how-do-i-do-it>

If the metadata is valid, the field will turn green. The field will turn orange or red as a warning if the input cannot be validated.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9430d94-Screen_Shot_2018-05-01_at_08.50.49.png",
        "Screen Shot 2018-05-01 at 08.50.49.png",
        994
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


> 📘 About validation in the DOI File Upload
> 
> Metadata is validated for Findable and Registered DOIs in the DOI File Upload.
> 
> In the case of Draft state, there is no validation, so you will not be prevented from saving. If you later update a Draft to a different state, you will need to resolve any resulting validation errors first.
> 
> Watch this short tutorial to learn more about validating XML metadata:
> 
> [block:embed]{"html":"<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FxrBv9Q3l6GA%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DxrBv9Q3l6GA&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FxrBv9Q3l6GA%2Fhqdefault.jpg&type=text%2Fhtml&schema=youtube\" width=\"640\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>","url":"https://www.youtube.com/watch?v=xrBv9Q3l6GA","title":"How to validate your DataCite XML metadata","favicon":"https://www.youtube.com/favicon.ico","image":"https://i.ytimg.com/vi/xrBv9Q3l6GA/hqdefault.jpg","provider":"youtube.com","href":"https://www.youtube.com/watch?v=xrBv9Q3l6GA","typeOfEmbed":"youtube"}[/block]

#### Harvest metadata from a landing page

Another way to upload metadata is from a landing page that uses  [schema.org](http://schema.org) or from a software repository that uses [codemeta](https://codemeta.github.io/). In either case, you can enter the URL of the landing page or software repository by itself in the metadata field. When the DOI is saved, Fabrica will automatically retrieve the metadata from the landing page or software repository and use it to populate the DOI record.