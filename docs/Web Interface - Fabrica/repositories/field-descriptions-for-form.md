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
The following metadata fields are available to create a DOI via the form in Fabrica. Below you will find detailed descriptions of each field and how to use them.
[block:parameters]
{
  "data": {
    "h-0": "Mandatory Properties",
    "h-1": "Recommended Properties",
    "h-2": "Optional Properties",
    "0-2": "Language\nAlternate Identifiers\nRights\nSizes\nFormats\nVersion\nFunding References\n",
    "0-1": "Subjects\nContributors\nDates\nRelated Identifiers\nDescriptions\nGeolocations",
    "0-0": "DOI \nState Selection\nURL \nCreators \nTitle \nPublisher\nPublication Year \nResource Type General"
  },
  "cols": 3,
  "rows": 1
}
[/block]
Detailed descriptions of metadata requirements and field examples are included in the documentation for the [DataCite Metadata Schema](https://schema.datacite.org). 

For many of the fields, Fabrica will validate the entered information, and that field will subsequently turn green if the information is valid or red if it is not. You will not be able to save until you properly resolve any red fields. In the case of Draft DOIs, which require only the DOI to be saved, you will receive orange warning messages about potential problems instead of red validation errors, so you will not be prevented from saving. If you later update a Draft DOI to a different state, you will need to resolve any resulting red validation errors first. 
[block:api-header]
{
  "title": "DOI Field"
}
[/block]
The DOI field is where you set the DOI you would like to create. This field corresponds to the Identifier field in the DataCite Metadata Schema. 

First, select one of the available prefixes from the dropdown box on the left. 

A DOI suffix (the part that comes after the prefix) is auto-filled by default. To generate a new DOI name automatically, click the refresh icon on the right side of the DOI name field. Use the x icon on the far right to clear the contents of the DOI name field. You may also type and/or cut and paste your own DOI name into the field manually.
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
      "caption": ""
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
The Creators field is where you add the information about the authors of the content. This field is required. You can include up to 25 creators when you create a DOI via the Form.

##Auto-populate the Creator

To do this, add a **Name Identifier** like an [ORCID](https://orcid.org/) or [ISNI](http://www.isni.org/) in the Name Identifier field. The identifier must be entered as a **URL** e.g. https://orcid.org/0000-0002-1825-0097. Note: Using this method means the name fields will not be editable to avoid any accidental incorrect attribution. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fc6342a-Screen_Shot_2020-05-11_at_10.35.36.png",
        "Screen Shot 2020-05-11 at 10.35.36.png",
        2308,
        1340,
        "#fbfbfb"
      ]
    }
  ]
}
[/block]
##Manually add the Creator

The **type** of creator must be selected using the radio buttons. The default type is **"Unknown"**, use this if you don't know the type of Creator. Otherwise select  **"Person"** or  **"Organization"** 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1a7c497-Screen_Shot_2020-05-11_at_12.05.58.png",
        "Screen Shot 2020-05-11 at 12.05.58.png",
        1372,
        428,
        "#f9f8f8"
      ]
    }
  ]
}
[/block]
1. Person

To add the name of a person enter the Given Name and Family Name of the Creator in the corresponding fields.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b422f80-Screen_Shot_2019-10-21_at_10.51.01.png",
        "Screen Shot 2019-10-21 at 10.51.01.png",
        1059,
        703,
        "#fafbfb"
      ]
    }
  ]
}
[/block]
The "Name" field will be constructed automatically from the information entered, but it is not editable. The names are entered like this (instead of using a single name string), so the name can be more appropriately parsed for display by both DataCite services and other services downstream.

The affiliation of the creator can also be included (optional). The organization name is populated by the [ROR](https://ror.org/) look-up. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/31aa21a-Screen_Shot_2019-10-21_at_10.53.40.png",
        "Screen Shot 2019-10-21 at 10.53.40.png",
        935,
        339,
        "#f7f8f9"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Remember affiliation information included in the DOI metadata will be retrieved via the affiliation facet in DataCite Search.",
  "title": "Affiliation"
}
[/block]
Multiple creators can be included by clicking on the "Add another creator" button.

2. Organization

To add an organization as the creator select "Organization" using the radio button and type the name in the field below.

Organizations can also have affiliations, for example if the main organization is a project or working group, rather than a formal organization.

You can add multiple affiliations.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/358a77b-Screen_Shot_2019-10-21_at_10.31.02.png",
        "Screen Shot 2019-10-21 at 10.31.02.png",
        561,
        280,
        "#f7f9f9"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Title"
}
[/block]
The Title field is a required field. You can add the information in one of two ways.

1. To include the main title of the content, add it into the Title field and save.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8e9256b-Screen_Shot_2019-10-21_at_10.56.31.png",
        "Screen Shot 2019-10-21 at 10.56.31.png",
        1040,
        252,
        "#fbfdfc"
      ]
    }
  ]
}
[/block]
2. If the title is not the main title of the content, use the Title Type field and select the appropriate option from the drop down menu.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/902d0f9-Screen_Shot_2019-10-21_at_10.58.02.png",
        "Screen Shot 2019-10-21 at 10.58.02.png",
        1018,
        318,
        "#f8fbfa"
      ]
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
        1004,
        385,
        "#f8fbfb"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Publisher"
}
[/block]
Enter the name of the entity that holds, publishes, archives, issues, or produces the resource. This field is used to form the citation for the dataset, so consider which entity would be most appropriate. The information in this field does not need to match that of the repository account holding the DOIs in Fabrica.
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
      "caption": ""
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
      "caption": ""
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
In the Resource Type subfield include a short free-text description of the resource type. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4eea3a0-Screen_Shot_2020-05-12_at_12.25.51.png",
        "Screen Shot 2020-05-12 at 12.25.51.png",
        2334,
        600,
        "#fcfcfc"
      ],
      "caption": ""
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Subjects"
}
[/block]
In the Subjects field add the subject, keyword, classification code, or key phrase describing the resource. Use the drop down menu to select from the [OECD Fields of Science](https://www.oecd.org/science/inno/38235147.pdf). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5d4a8f7-Screen_Shot_2020-05-11_at_18.39.52.png",
        "Screen Shot 2020-05-11 at 18.39.52.png",
        2444,
        816,
        "#f9fafa"
      ]
    }
  ]
}
[/block]
When you select from the OECD list, the Subject Scheme and Subject Scheme URI will be auto-populated.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/79c3c23-Screen_Shot_2020-05-11_at_18.41.19.png",
        "Screen Shot 2020-05-11 at 18.41.19.png",
        2180,
        920,
        "#fafbfb"
      ]
    }
  ]
}
[/block]
If the subject name does appear in the drop down OCED menu, type the name of the subject and press enter. Optionally add the Subject Scheme and Subject Scheme URI if available.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4d0109d-Screen_Shot_2020-05-12_at_13.44.50.png",
        "Screen Shot 2020-05-12 at 13.44.50.png",
        2314,
        312,
        "#f4f6f8"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Contributors"
}
[/block]
A contributor is an institution or person responsible for collecting, managing, distributing, or otherwise contributing to the development of the resource. Select the Contributor Type from the drop down menu.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9153cf2-Screen_Shot_2020-05-11_at_18.42.25.png",
        "Screen Shot 2020-05-11 at 18.42.25.png",
        2166,
        916,
        "#fafafb"
      ]
    }
  ]
}
[/block]
As with the Creator field, the type of contributor should be indicated using the radio buttons, slect "Person", "Organization" or "Unknown". If the contributor is a person then add the name, either by entering a Name Identifier, like an ORCID, as shown below, or by typing the Given Name and Family Name into the corresponding fields.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b6c80ba-Screen_Shot_2020-05-12_at_18.26.04.png",
        "Screen Shot 2020-05-12 at 18.26.04.png",
        2348,
        1324,
        "#fbfbfb"
      ]
    }
  ]
}
[/block]
If the contributor is an organization, type the name into the Name field.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4edce8a-Screen_Shot_2020-05-12_at_18.32.12.png",
        "Screen Shot 2020-05-12 at 18.32.12.png",
        2102,
        634,
        "#fafafa"
      ]
    }
  ]
}
[/block]
Finally, the affiliation of the contributor can be optionally added.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c62bb4-Screen_Shot_2020-05-12_at_18.27.09.png",
        "Screen Shot 2020-05-12 at 18.27.09.png",
        2142,
        848,
        "#fafbfb"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Dates"
}
[/block]
The Dates field is where any dates relevant to the content can be added. The following formats are accepted:

Date:
YYYY
YYYY-MM-DD 
YYYYMM-DDThh:mm:ssTZD (or any other format or level of granularity described in
W3CDTF)

Date ranges:
 2004-03-02/2005-06-02 (RKMSISO8601 standard for depicting date ranges)

Years before 0000 must be prefixed with a - sign, e.g. -0054 to indicate 55 BC.

Then select the Date Type from the drop down list.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1620173-Screen_Shot_2020-05-13_at_11.03.51.png",
        "Screen Shot 2020-05-13 at 11.03.51.png",
        2054,
        948,
        "#fbfbfc"
      ]
    }
  ]
}
[/block]
Specific information about the date can be added if appropriate. This is a free text field and may be used to provide more information about the publication, release or collection date details. It may also be used to clarify dates in ancient history for example: 55 BC, 55BCE.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f32785b-Screen_Shot_2020-05-13_at_11.06.28.png",
        "Screen Shot 2020-05-13 at 11.06.28.png",
        2062,
        840,
        "#fcfcfc"
      ]
    }
  ]
}
[/block]
Another date can be added by clicking on the "add another date" button.
[block:api-header]
{
  "title": "Related Identifiers"
}
[/block]
Use the Related Identifiers field to add information about related resources. These must be globally unique identifiers. You can view the full list of supported unique identifiers [here](https://support.datacite.org/docs/schema-optional-properties-v43#section-12-a-related-identifier-type).  When the identifier is entered, the Related Identifier Type is auto-populated, in the example below, a DOI.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b83c20f-Screen_Shot_2020-05-13_at_11.16.33.png",
        "Screen Shot 2020-05-13 at 11.16.33.png",
        2236,
        536,
        "#f9fafa"
      ]
    }
  ]
}
[/block]
Then select the Relation Type from the drop down menu. The full controlled vocabulary of relationTypes with descriptions can be found in the appendix of the DataCite metadata schema documentation [here](https://schema.datacite.org/meta/kernel-4.3/doc/DataCite-MetadataKernel_v4.3.pdf). More information about Relation Types can be found [here](doc:relationtype_for_citation).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eabe9ff-Screen_Shot_2020-05-13_at_11.19.12.png",
        "Screen Shot 2020-05-13 at 11.19.12.png",
        2256,
        1316,
        "#fafbfb"
      ]
    }
  ]
}
[/block]
Finally, the Resource Type General of the related identifier can be included. This is optional.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/32ce9c9-Screen_Shot_2020-05-13_at_11.23.22.png",
        "Screen Shot 2020-05-13 at 11.23.22.png",
        1904,
        728,
        "#fbfcfd"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Descriptions"
}
[/block]
The Description field is free text field and includes any additional information.

**Description Type**

The Description Type can optionally be added underneath the description text from the drop down menu e.g Abstract.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/84fe636-Screen_Shot_2019-10-21_at_11.04.30.png",
        "Screen Shot 2019-10-21 at 11.04.30.png",
        1624,
        735,
        "#fbfcfc"
      ]
    }
  ]
}
[/block]
Description Type also includes the SeriesInformation option. To encourage consistent data entry between clients, the form validates series information according to the DataCite-preferred way of parsing the entered information. You will receive an orange warning message if the series information does not conform, but you will not be prevented from saving. 

The help text below the description field provides information about the correct format:

Enter series information in the recommended format of **series title, followed by comma and optional volume(issue), firstpage-lastpage**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f87d2cc-Screen_Shot_2019-10-21_at_11.04.10.png",
        "Screen Shot 2019-10-21 at 11.04.10.png",
        1610,
        514,
        "#fcfbfb"
      ]
    }
  ]
}
[/block]
There is an option to choose a language for the description and you can include multiple descriptions by clicking " Add another description".
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0dd5f30-Screen_Shot_2019-10-21_at_11.05.38.png",
        "Screen Shot 2019-10-21 at 11.05.38.png",
        1616,
        704,
        "#fbfcfc"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Geolocations"
}
[/block]
The Geolocations field describes a spatial region or named place where the data was gathered or about which the resource is focused. 

The example below includes a Geolocation Box. A box is defined by two geographic points. Left low corner and right upper corner. Each point is defined by its longitude and latitude. More information about Geolocation Box metadata field is available [here](https://support.datacite.org/docs/schema-optional-properties-v43#section-18-2-geo-location-box) 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b558d98-Screen_Shot_2020-05-13_at_11.26.56.png",
        "Screen Shot 2020-05-13 at 11.26.56.png",
        2170,
        1228,
        "#fbfcfc"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Language"
}
[/block]
Include the primary language of the resource being shared by selecting from the drop-down list of languages.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/90580ac-Screen_Shot_2020-05-13_at_11.30.34.png",
        "Screen Shot 2020-05-13 at 11.30.34.png",
        2112,
        602,
        "#f9fafb"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Alternate Identifiers"
}
[/block]
An Alternate Identifier is an identifier, other than the primary identifier, in this case a DOI. It can be any alphanumeric string which is unique within its domain of issue. This field could be used for, for example, local identifiers. Alternate Identifier should be used as another identifier of the same instance (same location, same file). 

In the example below, the Alternate Identifier is a PMID. Select the Alternate Identifier Type from the drop down list as shown below.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c883bfc-Screen_Shot_2020-05-13_at_11.34.15.png",
        "Screen Shot 2020-05-13 at 11.34.15.png",
        2288,
        966,
        "#fbfbfc"
      ]
    }
  ]
}
[/block]
If the Alternate Identifier Type does not appear in the list, add it by typing it into the field and click enter.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3eb8e7b-Screen_Shot_2020-05-13_at_11.38.55.png",
        "Screen Shot 2020-05-13 at 11.38.55.png",
        1936,
        318,
        "#f6f8f9"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Rights"
}
[/block]
This metadata field can be used to add any rights information for this resource. The property may be repeated to record complex rights characteristics. Start by selecting from the standard licenses. If the license does not appear in the list, type it into the field and click enter.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/98b2542-Screen_Shot_2020-05-13_at_11.41.02.png",
        "Screen Shot 2020-05-13 at 11.41.02.png",
        2060,
        790,
        "#f8f9fa"
      ]
    }
  ]
}
[/block]
Once the Rights license is selected from the list, the Rights URI field will be auto-populated. Alternatively add this information manually if a new license type is being added.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bb8c136-Screen_Shot_2020-05-13_at_11.42.17.png",
        "Screen Shot 2020-05-13 at 11.42.17.png",
        2068,
        608,
        "#fcfcfd"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Sizes"
}
[/block]
Add the Size of the resource in this field if applicable. Sizes can be included as, for example, bytes, pages, inches or duration (extent), for example, hours, minutes, days.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3dd7a60-Screen_Shot_2020-05-13_at_11.47.19.png",
        "Screen Shot 2020-05-13 at 11.47.19.png",
        2034,
        234,
        "#fbfbfb"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Formats"
}
[/block]
This field describes the technical format of the resource. This is a free text field, in the example below the format is PDF.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7ed041a-Screen_Shot_2020-05-13_at_11.49.02.png",
        "Screen Shot 2020-05-13 at 11.49.02.png",
        2104,
        212,
        "#fcfcfd"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Version"
}
[/block]
This field is for including the version number of the resource. The Version field is used for minor version changes only. Register a new identifier for a major version change. Individual stewards need to determine which are major vs. minor versions. Based on the work of the Earth Science Information Partners (ESIP). More guidance [here](http://wiki.esipfed.org/index.php/Interagency_Data_Stewardship/Citations/provider_guidelines#Note_on_Versioning_and_Locators).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/63fa07a-Screen_Shot_2020-05-13_at_11.52.35.png",
        "Screen Shot 2020-05-13 at 11.52.35.png",
        2096,
        234,
        "#fdfdfd"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Funding References"
}
[/block]
The Funding References field is for including information about financial support (funding) for the resource being registered. 

Start by selecting the Funder Name. If the name does not appear in the list, add it by typing it into the field and then click enter.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bade0b7-Screen_Shot_2020-05-13_at_11.53.42.png",
        "Screen Shot 2020-05-13 at 11.53.42.png",
        2262,
        854,
        "#f8f8f9"
      ]
    }
  ]
}
[/block]
The Funder Identifier and Funder Identifier Type are auto-populated when the Funder Name is selected from the look up. Alternatively, add this information into the corresponding fields.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ece0d14-Screen_Shot_2020-05-13_at_11.55.09.png",
        "Screen Shot 2020-05-13 at 11.55.09.png",
        2266,
        744,
        "#f9f9fa"
      ]
    }
  ]
}
[/block]
Add the code assigned by the funder to a sponsored award (grant) in the Award Number field. Then include the Award Title and the Award URI in the appropriate fields as shown below.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/510edf6-Screen_Shot_2020-05-13_at_11.57.23.png",
        "Screen Shot 2020-05-13 at 11.57.23.png",
        1914,
        792,
        "#fafafa"
      ]
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