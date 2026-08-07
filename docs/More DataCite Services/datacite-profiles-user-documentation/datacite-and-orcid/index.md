---
title: How to Connect Your ORCID to DataCite
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
DataCite provides persistent identifiers (DOIs) for all research outputs. [ORCID](https://orcid.org/) provides persistent identifiers (ORCID iDs) for all researchers. The two organisations work closely together to identify research and connect it to the researchers that created it.

DataCite's integration with ORCID makes it quick and easy for researchers to link any works which have a DataCite DOI to their ORCID record. 

Here we describe the two ways in which your works with a DataCite DOI can be linked to your ORCID profile.

# 1\. ORCID Import works from other services

The [ORCID Import works from other services](https://info.orcid.org/documentation/workflows/search-and-link-workflow/) allows you to manually add your works to your ORCID record from [DataCite Commons](https://support.datacite.org/docs/datacite-commons).

Start by logging in to your ORCID account on <https://orcid.org> and then scroll down to the "Works" section. Click the “Add” button and a drop down list of options will appear. Select "Import works from other services" and then scroll down to select “DataCite”.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4d71e60fd642c86c8c70fa115423eca321d28525126a37861c362c129e34b89d-Screenshot_2026-06-18_at_10.00.44.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4246c5f42a28e2bf81004e13cad76e9d8887d61f28c2fea96a04067685e18c3c-Screenshot_2026-06-18_at_10.01.39.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


When you click on "DataCite", you will be redirected to [DataCite Commons](https://commons.datacite.org/). You will see options to search for works with your ORCID iD or works with your name.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3e9397c1de3894dc7e76eb6a4654269fdf132b0ca343ce2fa9820319f0585e09-Screenshot_2025-09-08_at_13.09.33.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


## Adding a Work to Your ORCID Record

Click on a work record in DataCite Commons and then click the **"Add to ORCID Record"** button to add the work to the "Works" list in your ORCID record:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fa5bd6a-Screenshot_2023-08-31_at_14.48.08.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


> 👍 ORCID
> 
> You can find detailed instructions in the DataCite Commons documentation [Add a DOI to Your ORCID](doc:orcid-claiming).

# 2\. ORCID Auto-Update

Enabling [ORCID](https://orcid.org/) auto-update allows DataCite to automatically update your ORCID record every time a new DOI is registered with your ORCID iD in the metadata.

> 📘 Requirements for ORCID auto-update
> 
> For auto-update to work, you will need:
> 
> - An ORCID record.
> - A [DataCite Profiles](doc:datacite-profiles-user-documentation) account with ORCID auto-update permissions enabled.
> - DataCite DOIs with your ORCID iD as a creator.

To automatically add your works to your ORCID record, you first need to enable ORCID auto-update in your [DataCite Profiles](https://profiles.datacite.org/) settings. Sign in and select "Click to Enable" next to "ORCID Auto-Update". You will then be prompted to allow DataCite to automatically add works to your ORCID record. You can revoke permissions for auto-update at any time in the settings of your ORCID record or in your DataCite Profiles settings. See a detailed description on our [DataCite Profile pages](doc:datacite-profiles-user-documentation).

> 👍 
> 
> Auto-update will trigger for findable DOIs registered or updated after the user enables auto-update. To trigger ORCID auto-update for existing DOIs, you will need to make an update to one of the following fields:
> 
> - Creator
> - RelatedIdentifier
> - FundingReference
> 
> Making a change to any of these metadata properties will also update the work metadata in your ORCID record if the work has been added with auto-update.

### Troubleshooting

If you have any issues with auto-update functionality please check out the [ORCID auto-update troubleshooting guide](doc:orcid-auto-update-not-working) or get in contact by sending an email to [support@datacite.org](mailto:support@datacite.org).