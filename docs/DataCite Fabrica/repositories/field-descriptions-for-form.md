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
    "0-0": "DOI  \nState Selection  \nURL  \nCreators  \nTitle  \nPublisher  \nPublication Year  \nResource Type General",
    "0-1": "Subjects  \nContributors  \nDates  \nRelated Identifiers  \nDescriptions  \nGeolocations",
    "0-2": "Language  \nAlternate Identifiers  \nRights  \nSizes  \nFormats  \nVersion  \nFunding References  \nRelated Items"
  },
  "cols": 3,
  "rows": 1,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


Detailed descriptions of metadata requirements and field examples are included in the documentation for the [DataCite Metadata Schema](https://schema.datacite.org). 

For many of the fields, Fabrica will validate the entered information, and that field will subsequently turn green if the information is valid or red if it is not. You will not be able to save until you properly resolve any red fields. In the case of Draft state, there is no validation, so you will not be prevented from saving. If you later update a Draft to a different state, you will need to resolve any resulting red validation errors first. 

## DOI Field

The DOI field is where you set the DOI you would like to create. This field corresponds to the Identifier field in the DataCite Metadata Schema. 

First, select one of the available prefixes from the dropdown box on the left. 

A DOI suffix (the part that comes after the prefix) is auto-filled by default. To generate a new DOI name automatically, click the refresh icon on the right side of the DOI name field. Use the x icon on the far right to clear the contents of the DOI name field. You may also type and/or cut and paste your own DOI name into the field manually.

![](https://files.readme.io/cf2c7b8-Screen_Shot_2019-04-23_at_18.02.26.png "Screen Shot 2019-04-23 at 18.02.26.png")

## State Selection Field

Use the state selection radio buttons to select a state for the DOI. 

Drafts are only visible within DOI Fabrica and can be deleted. Registered DOIs will be made public via registration in the Handle System. Findable DOIs will be registered via the Handle System and will also be included in [DataCite Commons](https://commons.datacite.org/). 

[Learn more about states](doc:doi-states) 

![](https://files.readme.io/980862c-Screen_Shot_2019-04-23_at_18.03.59.png "Screen Shot 2019-04-23 at 18.03.59.png")

## URL Field

Enter the URL of the landing page that the DOI points to. 

The URL must be fully formed, as in `https://www.datacite.org` instead of `datacite.org`. URLs containing `https://` are encouraged. 

DOI Fabrica will verify that the URL will resolve. If the URL does resolve, the field will turn green. If it does not resolve, the field will turn red and display an error message.  If you don't understand an error message, please [contact us](doc:how-to-contact-datacite). 

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
      "border": true
    }
  ]
}
[/block]


## Creators

The Creators field is where you add the information about the authors of the content. This field is required. You can include up to 25 creators when you create a DOI via the Form.

### Auto-populate the Creator

To do this, add a **Name Identifier** like an [ORCID](https://orcid.org/) or [ROR](http://www.ror.org/) in the Name Identifier field. The identifier must be entered as a **URL** e.g. <https://ror.org/04wxnsj81>. Note: Using this method means the name fields will not be editable to avoid any accidental incorrect attribution. 

![](https://files.readme.io/9d240f8-Screenshot_2023-01-25_at_12.09.04.png "Screenshot 2023-01-25 at 12.09.04.png")

### Manually add the Creator

The **type** of creator must be selected using the radio buttons. The default type is **"Unknown"**, use this if you don't know the type of Creator. Otherwise select  **"Person"** or  **"Organization"** 

![](https://files.readme.io/1a7c497-Screen_Shot_2020-05-11_at_12.05.58.png "Screen Shot 2020-05-11 at 12.05.58.png")

1. Person

To add the name of a person enter the Given Name and Family Name of the Creator in the corresponding fields.

![](https://files.readme.io/b422f80-Screen_Shot_2019-10-21_at_10.51.01.png "Screen Shot 2019-10-21 at 10.51.01.png")

The "Name" field will be constructed automatically from the information entered, but it is not editable. The names are entered like this (instead of using a single name string), so the name can be more appropriately parsed for display by both DataCite services and other services downstream.

The affiliation of the creator can also be included (optional). The organization name is populated by the [ROR](https://ror.org/) look-up. 

![](https://files.readme.io/31aa21a-Screen_Shot_2019-10-21_at_10.53.40.png "Screen Shot 2019-10-21 at 10.53.40.png")

> 📘 Affiliation
> 
> Remember affiliation information included in the DOI metadata will be retrieved via the affiliation facet in DataCite Commons.

Multiple creators can be included by clicking on the "Add another creator" button.

2. Organization

To add an organization as the creator select "Organization" using the radio button and type the name in the field below.

Organizations can also have affiliations, for example if the main organization is a project or working group, rather than a formal organization.

You can add multiple affiliations.

![](https://files.readme.io/358a77b-Screen_Shot_2019-10-21_at_10.31.02.png "Screen Shot 2019-10-21 at 10.31.02.png")

## Title

The Title field is a required field. You can add the information in one of two ways.

1. To include the main title of the content, add it into the Title field and save.

![](https://files.readme.io/8e9256b-Screen_Shot_2019-10-21_at_10.56.31.png "Screen Shot 2019-10-21 at 10.56.31.png")

2. If the title is not the main title of the content, use the Title Type field and select the appropriate option from the drop down menu.

![](https://files.readme.io/902d0f9-Screen_Shot_2019-10-21_at_10.58.02.png "Screen Shot 2019-10-21 at 10.58.02.png")

There is the option to select the language from the drop down menu and also to include another title by clicking "Add another title".

![](https://files.readme.io/38e14af-Screen_Shot_2019-10-21_at_10.59.02.png "Screen Shot 2019-10-21 at 10.59.02.png")

## Publisher

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
      "align": "center"
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
      "align": "center"
    }
  ]
}
[/block]


> 📘 Publishers not in ROR
> 
> If the organization you want to include in this field is not included in the ROR look-up, then just click ENTER when promoted to enter your own publisher name.

This field is used to form the citation for the dataset, so consider which entity would be most appropriate. The information in this field does not need to match that of the repository account holding the DOIs in DataCite Fabrica.

## Publication Year

Enter the year when the resource was or will be made publicly available. The field accepts a valid year between 1000 and 2028. 

![](https://files.readme.io/9c574ea-Screenshot_2023-01-26_at_10.36.48.png "Screenshot 2023-01-26 at 10.36.48.png")

## Resource Type General

The general type of the resource. This is a controlled list as specified in the [DataCite Metadata Schema](https://schema.datacite.org). 

![](https://files.readme.io/7a65ad4-Screen_Shot_2019-04-23_at_18.25.51.png "Screen Shot 2019-04-23 at 18.25.51.png")

In the Resource Type subfield include a short free-text description of the resource type. 

![](https://files.readme.io/4eea3a0-Screen_Shot_2020-05-12_at_12.25.51.png "Screen Shot 2020-05-12 at 12.25.51.png")

## Subjects

In the Subjects field add the subject, keyword, classification code, or key phrase describing the resource. Use the drop down menu to select from the [OECD Fields of Science](https://www.oecd.org/science/inno/38235147.pdf). 

![](https://files.readme.io/5d4a8f7-Screen_Shot_2020-05-11_at_18.39.52.png "Screen Shot 2020-05-11 at 18.39.52.png")

When you select from the OECD list, the Subject Scheme and Subject Scheme URI will be auto-populated.

![](https://files.readme.io/79c3c23-Screen_Shot_2020-05-11_at_18.41.19.png "Screen Shot 2020-05-11 at 18.41.19.png")

If the subject name does appear in the drop down OCED menu, type the name of the subject and press enter. Optionally add the Subject Scheme and Subject Scheme URI if available.

![](https://files.readme.io/4d0109d-Screen_Shot_2020-05-12_at_13.44.50.png "Screen Shot 2020-05-12 at 13.44.50.png")

## Contributors

A contributor is an institution or person responsible for collecting, managing, distributing, or otherwise contributing to the development of the resource. Select the Contributor Type from the drop down menu.

![](https://files.readme.io/9153cf2-Screen_Shot_2020-05-11_at_18.42.25.png "Screen Shot 2020-05-11 at 18.42.25.png")

As with the Creator field, the type of contributor should be indicated using the radio buttons, select "Person", "Organization" or "Unknown". If the contributor is a person then add the name, either by entering a Name Identifier, like an ORCID, as shown below, or by typing the Given Name and Family Name into the corresponding fields.

![](https://files.readme.io/b6c80ba-Screen_Shot_2020-05-12_at_18.26.04.png "Screen Shot 2020-05-12 at 18.26.04.png")

If the contributor is an organization, type the name into the Name field.

![](https://files.readme.io/4edce8a-Screen_Shot_2020-05-12_at_18.32.12.png "Screen Shot 2020-05-12 at 18.32.12.png")

Finally, the affiliation of the contributor can be optionally added.

![](https://files.readme.io/2c62bb4-Screen_Shot_2020-05-12_at_18.27.09.png "Screen Shot 2020-05-12 at 18.27.09.png")

## Dates

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

![](https://files.readme.io/1620173-Screen_Shot_2020-05-13_at_11.03.51.png "Screen Shot 2020-05-13 at 11.03.51.png")

Specific information about the date can be added if appropriate. This is a free text field and may be used to provide more information about the publication, release or collection date details. It may also be used to clarify dates in ancient history for example: 55 BC, 55BCE.

![](https://files.readme.io/f32785b-Screen_Shot_2020-05-13_at_11.06.28.png "Screen Shot 2020-05-13 at 11.06.28.png")

Another date can be added by clicking on the "add another date" button.

## Related Identifiers

Use the Related Identifiers field to add information about related resources. These must be globally unique identifiers. You can view the full list of supported unique identifiers [here](https://support.datacite.org/docs/schema-optional-properties-v43#section-12-a-related-identifier-type).  When the identifier is entered, the Related Identifier Type is auto-populated, in the example below, a DOI.

![](https://files.readme.io/b83c20f-Screen_Shot_2020-05-13_at_11.16.33.png "Screen Shot 2020-05-13 at 11.16.33.png")

Then select the Relation Type from the drop down menu. The full controlled vocabulary of relationTypes with descriptions can be found in the appendix of the DataCite metadata schema documentation [here](https://schema.datacite.org/meta/kernel-4.3/doc/DataCite-MetadataKernel_v4.3.pdf). More information about Relation Types can be found [here](doc:relationtype_for_citation).

![](https://files.readme.io/eabe9ff-Screen_Shot_2020-05-13_at_11.19.12.png "Screen Shot 2020-05-13 at 11.19.12.png")

Finally, the Resource Type General of the related identifier can be included. This is optional.

![](https://files.readme.io/32ce9c9-Screen_Shot_2020-05-13_at_11.23.22.png "Screen Shot 2020-05-13 at 11.23.22.png")

## Descriptions

The Description field is free text field and includes any additional information.

**Description Type**

The Description Type can optionally be added underneath the description text from the drop down menu e.g Abstract.

![](https://files.readme.io/84fe636-Screen_Shot_2019-10-21_at_11.04.30.png "Screen Shot 2019-10-21 at 11.04.30.png")

Description Type also includes the SeriesInformation option. To encourage consistent data entry between clients, the form validates series information according to the DataCite-preferred way of parsing the entered information. You will receive an orange warning message if the series information does not conform, but you will not be prevented from saving. 

The help text below the description field provides information about the correct format:

Enter series information in the recommended format of **series title, followed by comma and optional volume(issue), firstpage-lastpage**

![](https://files.readme.io/f87d2cc-Screen_Shot_2019-10-21_at_11.04.10.png "Screen Shot 2019-10-21 at 11.04.10.png")

There is an option to choose a language for the description and you can include multiple descriptions by clicking " Add another description".

![](https://files.readme.io/0dd5f30-Screen_Shot_2019-10-21_at_11.05.38.png "Screen Shot 2019-10-21 at 11.05.38.png")

## Geolocations

The Geolocations field describes a spatial region or named place where the data was gathered or about which the resource is focused. 

The example below includes a Geolocation Box. A box is defined by two geographic points. Left low corner and right upper corner. Each point is defined by its longitude and latitude. More information about Geolocation Box metadata field is available [here](https://support.datacite.org/docs/schema-optional-properties-v43#section-18-2-geo-location-box) 

![](https://files.readme.io/b558d98-Screen_Shot_2020-05-13_at_11.26.56.png "Screen Shot 2020-05-13 at 11.26.56.png")

## Language

Include the primary language of the resource being shared by selecting from the drop-down list of languages.

![](https://files.readme.io/90580ac-Screen_Shot_2020-05-13_at_11.30.34.png "Screen Shot 2020-05-13 at 11.30.34.png")

## Alternate Identifiers

An Alternate Identifier is an identifier, other than the primary identifier, in this case a DOI. It can be any alphanumeric string which is unique within its domain of issue. This field could be used for, for example, local identifiers. Alternate Identifier should be used as another identifier of the same instance (same location, same file). 

In the example below, the Alternate Identifier is a PMID. Select the Alternate Identifier Type from the drop down list as shown below.

![](https://files.readme.io/c883bfc-Screen_Shot_2020-05-13_at_11.34.15.png "Screen Shot 2020-05-13 at 11.34.15.png")

If the Alternate Identifier Type does not appear in the list, add it by typing it into the field and click enter.

![](https://files.readme.io/3eb8e7b-Screen_Shot_2020-05-13_at_11.38.55.png "Screen Shot 2020-05-13 at 11.38.55.png")

## Rights

This metadata field can be used to add any rights information for this resource. The property may be repeated to record complex rights characteristics. Start by selecting from the standard licenses. If the license does not appear in the list, type it into the field and click enter.

![](https://files.readme.io/98b2542-Screen_Shot_2020-05-13_at_11.41.02.png "Screen Shot 2020-05-13 at 11.41.02.png")

Once the Rights license is selected from the list, the Rights URI field will be auto-populated. Alternatively add this information manually if a new license type is being added.

![](https://files.readme.io/bb8c136-Screen_Shot_2020-05-13_at_11.42.17.png "Screen Shot 2020-05-13 at 11.42.17.png")

## Sizes

Add the Size of the resource in this field if applicable. Sizes can be included as, for example, bytes, pages, inches or duration (extent), for example, hours, minutes, days.

![](https://files.readme.io/3dd7a60-Screen_Shot_2020-05-13_at_11.47.19.png "Screen Shot 2020-05-13 at 11.47.19.png")

## Formats

This field describes the technical format of the resource. This is a free text field, in the example below the format is PDF.

![](https://files.readme.io/7ed041a-Screen_Shot_2020-05-13_at_11.49.02.png "Screen Shot 2020-05-13 at 11.49.02.png")

## Version

This field is for including the version number of the resource. The Version field is used for minor version changes only. Register a new identifier for a major version change. Individual stewards need to determine which are major vs. minor versions. Based on the work of the Earth Science Information Partners (ESIP). More guidance [here](http://wiki.esipfed.org/index.php/Interagency_Data_Stewardship/Citations/provider_guidelines#Note_on_Versioning_and_Locators).

![](https://files.readme.io/63fa07a-Screen_Shot_2020-05-13_at_11.52.35.png "Screen Shot 2020-05-13 at 11.52.35.png")

## Funding References

The Funding References field is for including information about financial support (funding) for the resource being registered. 

Start by selecting the Funder Name. If the name does not appear in the list, add it by typing it into the field and then click enter.

![](https://files.readme.io/bade0b7-Screen_Shot_2020-05-13_at_11.53.42.png "Screen Shot 2020-05-13 at 11.53.42.png")

The Funder Identifier and Funder Identifier Type are auto-populated when the Funder Name is selected from the look up. Alternatively, add this information into the corresponding fields.

![](https://files.readme.io/ece0d14-Screen_Shot_2020-05-13_at_11.55.09.png "Screen Shot 2020-05-13 at 11.55.09.png")

Add the code assigned by the funder to a sponsored award (grant) in the Award Number field. Then include the Award Title and the Award URI in the appropriate fields as shown below.

![](https://files.readme.io/510edf6-Screen_Shot_2020-05-13_at_11.57.23.png "Screen Shot 2020-05-13 at 11.57.23.png")

## Related Items

The Related Items field is for including information about a resource related to the one being registered, e.g. a journal or book of which the article or chapter is part.

It can be used to provide series information or a text citation where the related resource  
does not have an identifier. However, it is also possible to provide an identifier here.

**Related Item Title**

This is the Title of the related item. This field is required. Example: Journal of the American Chemical Society

![](https://files.readme.io/454eadb-Screenshot_2023-01-04_at_15.56.15.png "Screenshot 2023-01-04 at 15.56.15.png")

**Related Item Type **

Information about a resource related to the one being registered, e.g., a journal or book of which the article or chapter is part. This is a required field and cannot be repeated.

Example: Can be used to provide series information or a text citation where the related resource does not have an identifier. However, it is also optional to provide an identifier here.

![](https://files.readme.io/ed75e7c-Screenshot_2023-01-04_at_15.20.18.png "Screenshot 2023-01-04 at 15.20.18.png")

**Relation Type**

This is a description of the relationship between the resource being registered (A) and the related resource (B). Choose from the controlled list values in the drop down menu.

![](https://files.readme.io/ef6f399-Screenshot_2023-01-04_at_15.23.13.png "Screenshot 2023-01-04 at 15.23.13.png")

**Related Item Identifier and Related Identifier Type**

Related Item Identifier is the identifier for the related item e.g. 1520-5126, this field is optional. Related Identifier Type is the type of the Identifier for the related item, e.g., DOI, this is required if you include the related item identifier and will be auto-populated.

![](https://files.readme.io/68d1e14-Screenshot_2023-01-04_at_15.27.20.png "Screenshot 2023-01-04 at 15.27.20.png")

**Volume, Issue and Number**

These fields allow you to include the Volume of the related item, the Issue number or name of the related item and the Number of the related item, e.g., report number of article number. These fields are all optional.

![](https://files.readme.io/7d97e1c-Screenshot_2023-01-04_at_15.42.40.png "Screenshot 2023-01-04 at 15.42.40.png")

**Publication year**

The year when the item was or will be made publicly available, this is an optional field. The date format is YYYY.

![](https://files.readme.io/4264753-Screenshot_2023-01-04_at_15.44.36.png "Screenshot 2023-01-04 at 15.44.36.png")

**Creator Name**

The full name of the related item creator. This field is optional.

![](https://files.readme.io/323ecde-Screenshot_2023-01-04_at_15.46.20.png "Screenshot 2023-01-04 at 15.46.20.png")

**Contributor Name and Contributor Type**

An institution or person identified as contributing to the development of the resource. If multiple contributors are identified, this subproperty may be repeated for each contributor. This field is optional. The Contributor Type is the type of contributor of the resource and is required if the Contributor Name is entered.

![](https://files.readme.io/698cb5c-Screenshot_2023-01-04_at_15.47.37.png "Screenshot 2023-01-04 at 15.47.37.png")

> 📘 Properties of the DataCite Metadata Schema
> 
> The Fabrica form is intended to provide a user friendly way for DataCite users to create DOIs and metadata. However, to prevent the web interface from becoming too big, the following  elements of the DataCite metadata schema are not available in the form:
> 
> 6.c valueURI (Subject)  
> 12.c relatedMetadataScheme (RelatedIdentifier)  
> 12.d schemeURI (RelatedIdentifier)  
> 12.e schemeType (RelatedIdentifier)  
> 16.b rightsIdentifier  
> 16.c rightsIdentifierScheme  
> 16.d schemeURI (Rights)  
> 18.4 geoLocationPolygon  
> 18.4.1 polygonPoint  
> 18.4.1.1 pointLongitude  
> 18.4.1.2 pointLatitude  
> 18.4.2 inPolygonPoint  
> 18.4.2.1 pointLongitude  
> 18.4.2.2 pointLatitude  
> 19.2.b schemeURI (FundingReference - funderIdentifier)  
> 20.1.b relatedMetadataScheme (RelatedItem - relatedItemIdentifier)  
> 20.1.c schemeURI (RelatedItem - relatedItemIdentifier)  
> 20.1.d schemeType (RelatedItem - relatedItemIdentifier)  
> 20.2.1.a nameType (RelatedItem - creator)  
> 20.2.2 givenName (RelatedItem - creator)  
> 20.2.3 familyName (RelatedItem - creator)  
> 20.3.a titleType (RelatedItem - title)  
> 20.7.a numberType (RelatedItem - number)  
> 20.8 firstPage (RelatedItem)  
> 20.9 lastPage (RelatedItem)  
> 20.10 publisher (RelatedItem)  
> 20.11 edition (RelatedItem)  
> 20.12.1.a nameType (RelatedItem - contributor)  
> 20.12.2 givenName (RelatedItem - contributor)  
> 20.12.3 familyName (RelatedItem - contributor)
> 
> Use [file upload](doc:fabrica-create-doi-file-upload) option if you wish to include any of these elements. Learn more about the [DataCite metadata schema](http://schema.datacite.org/).

> 📘 Would you like to know more?
> 
> If you have any questions, requests or ideas please [contact us.](doc:how-to-contact-datacite)