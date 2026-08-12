---
title: Field Descriptions for Form
excerpt: ''
deprecated: false
hidden: true
link:
  new_tab: false
  url: https://support.datacite.org/docs/fabrica-doi-form#required-properties
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Repositories can register DOIs and update metadata using the DOI Form in DataCite Fabrica. 

Detailed descriptions of metadata requirements and field examples are included in the [DataCite Metadata Schema](https://schema.datacite.org) documentation.

> 📘 About validation in the DOI Form
> 
> For many fields, Fabrica will validate the entered information. The field will turn green if the information is valid or red if it is not. You will not be able to save until you properly resolve any invalid fields. 
> 
> [block:image]{"images":[{"image":["https://files.readme.io/14b68bec1cf370956c0ec8eb20b05c6d2d49342a0804d5d4a4de2f88e899d5e0-Screenshot_2025-07-10_at_13.06.07.png","",""],"align":"center","sizing":"500px","border":true}]}[/block]
> 
> In the case of Draft state, there is no validation, so you will not be prevented from saving. If you later update a Draft to a different state, you will need to resolve any resulting validation errors first.

## Required Properties

### DOI

The DOI field is where you set the DOI you would like to create. This field corresponds to the [Identifier](https://datacite-metadata-schema.readthedocs.io/en/4/properties/identifier/) property in the DataCite Metadata Schema.

The [DOI prefix](doc:doi-basics#prefix) is automatically populated. If your Repository has more than one prefix, select one of the available prefixes from the dropdown box on the left. 

By default, a [DOI suffix](doc:doi-basics#suffix) is randomly generated. To randomly generate a new suffix, click the refresh icon to the right of the DOI field. Use the "X" icon on the right to clear the contents. You can also manually specify a suffix in this field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cf2c7b8-Screen_Shot_2019-04-23_at_18.02.26.png",
        "Screen Shot 2019-04-23 at 18.02.26.png",
        ""
      ],
      "align": "center",
      "sizing": "800px",
      "border": true
    }
  ]
}
[/block]


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
        "https://files.readme.io/980862c-Screen_Shot_2019-04-23_at_18.03.59.png",
        "Screen Shot 2019-04-23 at 18.03.59.png",
        ""
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
        "https://files.readme.io/fbcbc1a-Screenshot_2023-01-25_at_12.12.42.png",
        "Screenshot 2023-01-25 at 12.12.42.png",
        2246
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Creators

The Creators field is where you add the information about the authors of the content. For each Creator, the Name field is required.

 You can include up to 25 creators when you create a DOI via the form. Multiple creators can be included by clicking "Add another creator".

#### Name identifier

To auto-populate the Creator name, add an [ORCID iD](https://orcid.org/) or [ROR ID](http://www.ror.org/) in the Name identifier field. The identifier must be entered as a URL, for example <https://ror.org/04wxnsj81>. Using this method means the name fields will not be editable to avoid any accidental incorrect attribution. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9d240f8-Screenshot_2023-01-25_at_12.09.04.png",
        "Screenshot 2023-01-25 at 12.09.04.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


#### Name type

The type of Creator must be selected using the radio buttons. The default type is "Unknown". Otherwise, select  "Person" or  "Organization".

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1a7c497-Screen_Shot_2020-05-11_at_12.05.58.png",
        "Screen Shot 2020-05-11 at 12.05.58.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


#### Name

To add the name of a person, enter the Given Name and Family Name of the Creator in the corresponding fields. When Given Name and Family Name are provided, the  "Name (from Given Name and Family Name)" is constructed automatically and is not editable.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b422f80-Screen_Shot_2019-10-21_at_10.51.01.png",
        "Screen Shot 2019-10-21 at 10.51.01.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


To add an organization as the creator, select "Organization" using the radio button and type the name in the field below.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/358a77b-Screen_Shot_2019-10-21_at_10.31.02.png",
        "Screen Shot 2019-10-21 at 10.31.02.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


#### Affiliation

The affiliation of the creator can also be included. The organization name is populated by the [ROR](https://ror.org/) look-up. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/31aa21a-Screen_Shot_2019-10-21_at_10.53.40.png",
        "Screen Shot 2019-10-21 at 10.53.40.png",
        ""
      ],
      "align": "center",
      "sizing": "500px",
      "border": true
    }
  ]
}
[/block]


Organizations can also have affiliations, for example if the main organization is a project or working group rather than a formal organization. You can add multiple affiliations.

> 📘 Affiliations in DataCite Commons
> 
> Affiliation information included in the DOI metadata will be retrieved via the affiliation facet in DataCite Commons.

### Title

To include the main title of the content, add it into the Title field and save.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8e9256b-Screen_Shot_2019-10-21_at_10.56.31.png",
        "Screen Shot 2019-10-21 at 10.56.31.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


If the title is not the main title of the content, use the Title Type and select the appropriate option from the drop down menu.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/902d0f9-Screen_Shot_2019-10-21_at_10.58.02.png",
        "Screen Shot 2019-10-21 at 10.58.02.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


There is the option to select the language from the drop down menu and also to include another title by clicking "Add another title".

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/38e14af-Screen_Shot_2019-10-21_at_10.59.02.png",
        "Screen Shot 2019-10-21 at 10.59.02.png",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


### Publisher

Type the name of the entity that holds, publishes, archives, issues, or produces the resource. The Publisher names and identifiers are provided by the Research Organization Registry (ROR).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9309db9-Screenshot_2024-01-23_at_09.27.06.png",
        "Screen Shot 2019-04-23 at 18.23.22.png",
        1242
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


The ROR ID is automatically populated once the Publisher name has been selected.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0bb4cb5-Screenshot_2024-01-23_at_09.31.53.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


> 📘 Publishers not in ROR
> 
> If the organization you want to include in this field is not included in the ROR look-up, press Enter when prompted to enter your own publisher name.

This field is used to form the citation for the dataset, so consider which entity would be most appropriate. The information in this field does not need to match that of the repository account holding the DOIs in DataCite Fabrica.

### Publication Year

Enter the year when the resource was or will be made publicly available. The field accepts a valid year between 1000 and 2028. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9c574ea-Screenshot_2023-01-26_at_10.36.48.png",
        "Screenshot 2023-01-26 at 10.36.48.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Resource Type General

The general type of the resource. This is a controlled list as specified in the [DataCite Metadata Schema](https://schema.datacite.org). 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a65ad4-Screen_Shot_2019-04-23_at_18.25.51.png",
        "Screen Shot 2019-04-23 at 18.25.51.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


#### Resource Type

Includes a short free-text description of the resource type.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4eea3a0-Screen_Shot_2020-05-12_at_12.25.51.png",
        "Screen Shot 2020-05-12 at 12.25.51.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


## Recommended Properties

### Subjects

In the Subjects field, add the subject, keyword, classification code, or key phrase describing the resource. Use the dropdown menu to select from the [OECD Fields of Science](https://www.oecd.org/science/inno/38235147.pdf). 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5d4a8f7-Screen_Shot_2020-05-11_at_18.39.52.png",
        "Screen Shot 2020-05-11 at 18.39.52.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


When you select from the OECD list, the Subject Scheme and Subject Scheme URI will be automatically filled in.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/79c3c23-Screen_Shot_2020-05-11_at_18.41.19.png",
        "Screen Shot 2020-05-11 at 18.41.19.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


If the subject name does appear in the dropdown menu, type the name of the subject and press Enter. Optionally, add the Subject Scheme and Subject Scheme URI if applicable.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4d0109d-Screen_Shot_2020-05-12_at_13.44.50.png",
        "Screen Shot 2020-05-12 at 13.44.50.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Contributors

A contributor is an institution or person responsible for collecting, managing, distributing, or otherwise contributing to the development of the resource. 

#### Contributor Type

Select the Contributor Type from the drop down menu.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9153cf2-Screen_Shot_2020-05-11_at_18.42.25.png",
        "Screen Shot 2020-05-11 at 18.42.25.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


#### Name type

As with the Creator field, indicate the type of contributor name using the radio buttons ("Person", "Organization" or "Unknown"). 

#### Name

If the contributor is a person, add the name by entering a name identifier or specifying the Given Name and Family Name.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b6c80ba-Screen_Shot_2020-05-12_at_18.26.04.png",
        "Screen Shot 2020-05-12 at 18.26.04.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


If the contributor is an organization, enter the organization name into the Name field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4edce8a-Screen_Shot_2020-05-12_at_18.32.12.png",
        "Screen Shot 2020-05-12 at 18.32.12.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


#### Affiliation

Finally, the affiliation of the contributor can be optionally added.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c62bb4-Screen_Shot_2020-05-12_at_18.27.09.png",
        "Screen Shot 2020-05-12 at 18.27.09.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Dates

The Dates field is where any dates relevant to the content can be added.  Another date can be added by clicking "Add another date".

The following formats are accepted:

- Single date:
  - YYYY
  - YYYY-MM-DD
  - YYYYMM-DDThh:mm:ssTZD (or any other format or level of granularity described in  
    W3CDTF)
- Date range:
  - 2004-03-02/2005-06-02 (RKMSISO8601 standard for depicting date ranges)

Years before 0000 must be prefixed with a - sign. For example, `-0054`  indicates 55 BC.

#### Date Type

Select the Date Type from the dropdown list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1620173-Screen_Shot_2020-05-13_at_11.03.51.png",
        "Screen Shot 2020-05-13 at 11.03.51.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


#### Date information

Specific information about the date can be added if appropriate. This is a free text field and may be used to provide more information about the publication, release or collection date details. It may also be used to clarify dates in ancient history for example: 55 BC, 55BCE.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f32785b-Screen_Shot_2020-05-13_at_11.06.28.png",
        "Screen Shot 2020-05-13 at 11.06.28.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Related Identifiers

#### Related Identifier

Enter the identifier of the related resource. This must be a globally unique identifiers.

#### Related Identifier Type

For some identifier types (including DOIs), when the identifier is entered, the  [Related Identifier Type](https://datacite-metadata-schema.readthedocs.io/en/4/appendices/appendix-1/relatedIdentifierType/) is auto-populated. Otherwise, select the Related Identifier Type from the dropdown list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b83c20f-Screen_Shot_2020-05-13_at_11.16.33.png",
        "Screen Shot 2020-05-13 at 11.16.33.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


#### Relation Type

Select the [Relation Type](https://datacite-metadata-schema.readthedocs.io/en/4/appendices/appendix-1/relationType/) from the dropdown list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eabe9ff-Screen_Shot_2020-05-13_at_11.19.12.png",
        "Screen Shot 2020-05-13 at 11.19.12.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


#### Resource Type General

Optionally, include the Resource Type General of the resource identified by the Related Identifier

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/32ce9c9-Screen_Shot_2020-05-13_at_11.23.22.png",
        "Screen Shot 2020-05-13 at 11.23.22.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Descriptions

The Description field is a free text field for any additional information. Include multiple descriptions by clicking " Add another description".

#### Description Type

Select the [Description Type](https://datacite-metadata-schema.readthedocs.io/en/4/appendices/appendix-1/descriptionType/) from the dropdown list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/84fe636-Screen_Shot_2019-10-21_at_11.04.30.png",
        "Screen Shot 2019-10-21 at 11.04.30.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


> 📘 Formatting SeriesInformation
> 
> Description Type also includes the SeriesInformation option. To encourage consistent data entry between clients, the form validates series information according to the DataCite-preferred way of parsing the entered information. You will receive an orange warning message if the series information does not conform, but you will not be prevented from saving. The help text below the description field provides information about the correct format:
> 
> `series title, volume(issue), firstpage-lastpage`
> 
> ![](https://files.readme.io/f87d2cc-Screen_Shot_2019-10-21_at_11.04.10.png "Screen Shot 2019-10-21 at 11.04.10.png")

#### Language

There is an option to choose a language for the description.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0dd5f30-Screen_Shot_2019-10-21_at_11.05.38.png",
        "Screen Shot 2019-10-21 at 11.05.38.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Geolocations

The Geolocations field describes a spatial region or named place where the data was gathered or about which the resource is focused. The example below includes a Geolocation Box.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b558d98-Screen_Shot_2020-05-13_at_11.26.56.png",
        "Screen Shot 2020-05-13 at 11.26.56.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


## Optional Properties

### Language

Include the primary language of the resource being shared by selecting from the dropdown list of languages.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/90580ac-Screen_Shot_2020-05-13_at_11.30.34.png",
        "Screen Shot 2020-05-13 at 11.30.34.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Alternate Identifiers

An Alternate Identifier is an identifier other than the primary identifier. It can be any alphanumeric string which is unique within its domain of issue. This field can be used for local identifiers and globally unique identifiers. Alternate Identifier should be used as another identifier of the same instance (same location, same file). 

In the example below, the Alternate Identifier is a PMID. Select the Alternate Identifier Type from the drop down list as shown below.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c883bfc-Screen_Shot_2020-05-13_at_11.34.15.png",
        "Screen Shot 2020-05-13 at 11.34.15.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


If the Alternate Identifier Type does not appear in the list, add it by typing it into the field and click Enter.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3eb8e7b-Screen_Shot_2020-05-13_at_11.38.55.png",
        "Screen Shot 2020-05-13 at 11.38.55.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Rights

Select from the standard licenses in the dropdown list. If the license does not appear in the list, type it into the field and press Enter.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/98b2542-Screen_Shot_2020-05-13_at_11.41.02.png",
        "Screen Shot 2020-05-13 at 11.41.02.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


When a license is selected from the list, the Rights URI field is auto-populated. Alternatively, add this information manually if a new license type is being added.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bb8c136-Screen_Shot_2020-05-13_at_11.42.17.png",
        "Screen Shot 2020-05-13 at 11.42.17.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Sizes

Add the Size of the resource in this field, if applicable.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3dd7a60-Screen_Shot_2020-05-13_at_11.47.19.png",
        "Screen Shot 2020-05-13 at 11.47.19.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Formats

This field describes the technical format of the resource. This is a free text field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7ed041a-Screen_Shot_2020-05-13_at_11.49.02.png",
        "Screen Shot 2020-05-13 at 11.49.02.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Version

This field is for including the version number of the resource.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/63fa07a-Screen_Shot_2020-05-13_at_11.52.35.png",
        "Screen Shot 2020-05-13 at 11.52.35.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Funding References

The Funding References field is for including information about financial support (funding) for the resource being registered. 

Select the Funder Name from the dropdown list. If the name does not appear in the list, add it by typing it into the field and press Enter.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bade0b7-Screen_Shot_2020-05-13_at_11.53.42.png",
        "Screen Shot 2020-05-13 at 11.53.42.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


When a funder is selected from the list, the Funder Identifier and Funder Identifier Type are auto-populated. Alternatively, add this information manually.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ece0d14-Screen_Shot_2020-05-13_at_11.55.09.png",
        "Screen Shot 2020-05-13 at 11.55.09.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


Add the code assigned by the funder to a sponsored award (grant) in the Award Number field. Include the Award Title and the Award URI in the appropriate fields, as shown below.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/510edf6-Screen_Shot_2020-05-13_at_11.57.23.png",
        "Screen Shot 2020-05-13 at 11.57.23.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


### Related Items

The Related Items field is for including information about a resource related to the one being registered, e.g., a journal or book of which the article or chapter is part.

It can be used to provide series information or a text citation where the related resource does not have an identifier. However, it is also possible to provide an identifier here.

#### Title

This is the Title of the related item. This field is required. Example: Journal of the American Chemical Society

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/454eadb-Screenshot_2023-01-04_at_15.56.15.png",
        "Screenshot 2023-01-04 at 15.56.15.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


#### Related Item Type

Information about a resource related to the one being registered, e.g., a journal or book of which the article or chapter is part. This is a required field and cannot be repeated.

Example: Can be used to provide series information or a text citation where the related resource does not have an identifier. However, it is also optional to provide an identifier here.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ed75e7c-Screenshot_2023-01-04_at_15.20.18.png",
        "Screenshot 2023-01-04 at 15.20.18.png",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


#### Relation Type

This is a description of the relationship between the resource being registered (A) and the related resource (B). Choose from the controlled list values in the drop down menu.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ef6f399-Screenshot_2023-01-04_at_15.23.13.png",
        "Screenshot 2023-01-04 at 15.23.13.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


#### Related Item Identifier and Related Identifier Type

Related Item Identifier is the identifier for the related item. This field is optional. 

Related Identifier Type is the type of the Identifier for the related item, e.g., DOI. This is required if you include an Related Item Identifier and will be auto-populated.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/68d1e14-Screenshot_2023-01-04_at_15.27.20.png",
        "Screenshot 2023-01-04 at 15.27.20.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


#### Volume, Issue and Number

These optional fields allow you to include the Volume, Issue (number or name), and Number (e.g., report number or article number) of the Related Item.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7d97e1c-Screenshot_2023-01-04_at_15.42.40.png",
        "Screenshot 2023-01-04 at 15.42.40.png",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


#### Publication Year

The year when the item was or will be made publicly available. This is an optional field. The date format is YYYY.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4264753-Screenshot_2023-01-04_at_15.44.36.png",
        "Screenshot 2023-01-04 at 15.44.36.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


#### Creator Name

The full name of the Related Item's Creator. This field is optional.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/323ecde-Screenshot_2023-01-04_at_15.46.20.png",
        "Screenshot 2023-01-04 at 15.46.20.png",
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


#### Contributor Name and Contributor Type

An institution or person identified as contributing to the development of the resource. If multiple Contributors are identified, this sub-property may be repeated for each Contributor. This field is optional. 

The Contributor Type is the type of contributor of the resource and is required if the Contributor Name is provided.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/698cb5c-Screenshot_2023-01-04_at_15.47.37.png",
        "Screenshot 2023-01-04 at 15.47.37.png",
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


> 📘 Sub-properties not in the DOI Form
> 
> The Fabrica DOI Form is intended to provide a user-friendly way for DataCite users to create DOIs and metadata. To prevent the web interface from becoming too big, the following sub-properties from the DataCite Metadata Schema are **not** available in the form:
> 
> - Subject: valueURI (6.c)
> - RelatedIdentifier: relatedMetadataScheme (12.c), schemeURI (12.d), and schemeType (12.e)
> - Rights: rightsIdentifier (16.b), rightsIdentifierScheme (16.c), and schemeURI (16.d)
> - GeoLocation: geoLocationPolygon (18.4) and its sub-properties (18.4.\*)
> - FundingReference: schemeURI for funderIdentifier (19.2.b)
> - RelatedItem:  relatedMetadataScheme (20.1.b), schemeURI (20.1.c), and schemeType (20.1.d) for RelatedItemIdentifier; nameType (20.2.1.a), givenName (20.2.2), and familyName (20.2.3) for Creator; titleType (20.3), numberType (20.7.a), firstPage (20.8), lastPage (20.9), publisher (20.10), edition (20.11); nameType (20.12.1.a), givenName (20.12.2), and familyName (20.12.3) for Contributor
> 
> Use [file upload](doc:fabrica-create-doi-file-upload) option to include any of these elements. Learn more about the [DataCite Metadata Schema](http://schema.datacite.org/).